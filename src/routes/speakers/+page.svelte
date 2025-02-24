<script>
	import Navbar from '../../components/Navbar.svelte';
  import Footer from '../../components/Footer.svelte';
	import { speakers } from '../../lib/data.js';
</script>

<Navbar />

<!-- Background with filter effect -->
<div class="speakers-container">
	<div class="overlay"></div>
	<!-- Overlay for better readability -->
	<div class="container my-5">
		<h2 class="text-center mb-4 text-white">Our Speakers</h2>
		<div class="row g-4">
			<!-- Bootstrap gutter class for spacing -->
			{#each speakers as speaker}
				<div class="col-md-4 d-flex justify-content-center">
					<div class="card speaker-card d-flex flex-column align-items-center">
						<div class="image-container">
							<img
								src={speaker.image}
								class="card-img-top rounded-circle speaker-img"
								alt={speaker.name}
							/>
						</div>
						<div class="card-body text-center d-flex flex-column justify-content-between">
							<h5 class="card-title">{speaker.name}</h5>
							<p class="card-text">{speaker.title}</p>
							<p class="card-bio">{speaker.bio}</p>
						</div>
					</div>
				</div>
			{/each}
		</div>
	</div>
</div>
<Footer/>

<style>
  	/* Background Styling */
	.speakers-container {
		position: relative;
		background:
			linear-gradient(135deg, rgba(0, 0, 50, 0.8), rgba(0, 50, 100, 0.8)),
			url('https://source.unsplash.com/1600x900/?technology,conference') center/cover no-repeat;
		padding: 80px 0; /* Ensuring consistent spacing */
		min-height: 100vh;
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.overlay {
		position: absolute;
		top: 0;
		left: 0;
		width: 100%;
		height: 100%;
		backdrop-filter: blur(8px);
		background: rgba(0, 0, 0, 0.4);
		z-index: 1;
	}

	.container {
		position: relative;
		z-index: 2;
		max-width: 90%; /* Ensuring consistent spacing from all sides */
	}

	/* Speaker Card */
	.speaker-card {
		width: 100%;
		max-width: 300px; /* Slightly increased width */
		min-height: 450px; /* Ensuring equal height */
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: space-between;
		transition:
			transform 0.3s ease,
			box-shadow 0.3s ease;
		border-radius: 12px;
		overflow: hidden;
		padding: 20px;
		background: rgba(255, 255, 255, 0.12);
		backdrop-filter: blur(14px);
		border: 1px solid rgba(255, 255, 255, 0.2);
		box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
	}

	.speaker-card:hover {
		transform: scale(1.05);
		box-shadow: 0 6px 20px rgba(0, 0, 0, 0.3);
	}

	/* Image Styling */
	.image-container {
		width: 160px;
		height: 160px;
		display: flex;
		justify-content: center;
		align-items: center;
		overflow: hidden;
		border-radius: 50%;
		margin-bottom: 10px;
	}

	.image-container img {
		width: 100%;
		height: 100%;
		object-fit: cover;
		border-radius: 50%;
	}

	/* Text Styling */
	.card-body {
		flex-grow: 1;
		display: flex;
		flex-direction: column;
		justify-content: space-between; /* Proper alignment */
		text-align: center;
		padding: 10px;
		width: 100%;
	}

	.card-title {
		font-size: 1.2rem;
		font-weight: bold;
		color: #ffffff;
		margin-bottom: 6px;
		min-height: 40px; /* Prevents uneven height */
	}

	.card-text {
		font-size: 1rem;
		font-style: italic;
		color: #d9d9d9;
		margin-bottom: 6px;
		min-height: 40px; /* Ensures alignment */
	}

	.card-bio {
		font-size: 0.9rem;
		color: #eeeeee;
		margin-top: 8px;
		text-align: center;
		line-height: 1.4;
		min-height: 60px; /* Ensures uniform card height */
		overflow: hidden;
		text-overflow: ellipsis;
		display: -webkit-box;
		/* -webkit-line-clamp: 3; Limits text to 3 lines */
		-webkit-box-orient: vertical;
	}

	/* Proper grid spacing */
	.row {
		display: flex;
		justify-content: center; /* Centering cards */
		flex-wrap: wrap;
		gap: 30px; /* Proper spacing between cards */
		margin: 0 auto;
	}

	.col-md-4 {
		flex: 0 1 calc(33.33% - 20px);
		display: flex;
		justify-content: center;
		align-items: stretch; /* Makes all cards equal height */
		padding: 10px;
	}

</style>