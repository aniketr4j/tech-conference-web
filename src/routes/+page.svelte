<script>
	import { onMount } from 'svelte';
	import Navbar from '../components/Navbar.svelte';
	import Footer from '../components/Footer.svelte';

	let countdown = '';

	onMount(() => {
		const eventDate = new Date('2025-06-15T09:00:00').getTime();
		setInterval(() => {
			const now = new Date().getTime();
			const distance = eventDate - now;
			const days = Math.floor(distance / (1000 * 60 * 60 * 24));
			const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
			const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
			countdown = `${days}d ${hours}h ${minutes}m`;
		}, 1000);
	});
</script>

<Navbar />

<!-- Parent Container with Background -->
<div class="parent-container">
	<!-- Hero Section -->
	<section class="hero-section text-white text-center d-flex align-items-center justify-content-center">
		<div>
			<h1 class="display-3 fw-bold">TechConf 2025</h1>
			<p class="lead">Where Technology Meets Innovation</p>
			<a href="/register" class="btn btn-primary">Register Now</a>
		</div>
	</section>

	<!-- Countdown Timer -->
	<section class="countdown text-center py-4 text-white">
		<h2>Event Starts In:</h2>
		<p class="display-5">{countdown}</p>
	</section>

	<!-- Featured Speakers Section -->
	<section class="featured-speakers py-5">
		<div class="container">
			<h2 class="text-center mb-4">Keynote Speakers</h2>
			<div class="row">
				{#each [
					{ name: 'Adarsh B U', title: 'Manufacturing & Energy Domain Solution Consultant at Happiest Minds Technologies', img: 'adarsh.jpeg' },
					{ name: 'Raja Manickam', title: 'Founder, IVP Semiconductor India PVT. LTD.', img: 'manickam.jpeg' },
					{ name: 'Dr. Satya Gupta', title: 'President, VLSI Society Of India & CII National Committee Member', img: 'satya.jpeg' },
					{ name: 'Kaushal Kukkar', title: 'Founder and CEO, AmIMotion', img: 'kaushal.jpeg' },
					{ name: 'Narang N Kishor', title: 'Mentor & Principal Design Architect, Narnix Technolabs Pvt. Ltd.', img: 'narang.jpeg' },
					{ name: 'Dr. Vishnu Srivastava', title: 'Ex Emeritus Scientist (CSIR) & Ex Emeritus Professor (AcSIR), CSIR-CEERI', img: 'vishnu.jpeg' }
				] as speaker}
					<div class="col-md-4 d-flex align-items-stretch">
						<div class="card text-center">
							<img src={speaker.img} class="card-img-top rounded-circle speaker-img" alt={speaker.name} />
							<div class="card-body">
								<h5 class="card-title">{speaker.name}</h5>
								<p class="card-text">{speaker.title}</p>
							</div>
						</div>
					</div>
				{/each}
			</div>
		</div>
	</section>
</div>

<Footer />

<!-- CSS Styling -->
<style>
	/* Parent Container Background */
	.parent-container {
		background:
			linear-gradient(135deg, rgba(0, 0, 50, 0.8), rgba(0, 50, 100, 0.8)),
			url('https://source.unsplash.com/1600x900/?technology,conference') center/cover no-repeat;
		background-blend-mode: overlay;
	}

	/* Hero Section */
	.hero-section {
		height: 80vh;
		display: flex;
		align-items: center;
		justify-content: center;
		text-align: center;
	}

	/* Countdown Timer */
	.countdown {
		padding: 40px 0;
		font-weight: bold;
	}

	/* Featured Speakers Section */
	.featured-speakers {
		padding: 80px 0;
	}

	.featured-speakers h2 {
		color: white;
		font-weight: bold;
		text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
	}

	/* Speaker Cards */
	.featured-speakers .card {
		width: 100%;
		max-width: 350px;
		margin: 20px auto;
		padding: 20px;
		transition: transform 0.3s ease-in-out, box-shadow 0.3s ease-in-out;
		background: rgba(255, 255, 255, 0.1);
		backdrop-filter: blur(10px);
		border: 1px solid rgba(255, 255, 255, 0.3);
		color: white;
		text-align: center;
		display: flex;
		flex-direction: column;
		justify-content: center;
	}

	.featured-speakers .container {
		padding-bottom: 80px;
		display: flex;
		flex-wrap: wrap;
		justify-content: center;
	}

	/* Speaker Cards Hover Effect */
	.featured-speakers .card:hover {
		transform: scale(1.05);
		box-shadow: 0 8px 20px rgba(255, 255, 255, 0.3);
	}

	/* Speaker Images */
	.speaker-img {
		width: 120px;
		height: 120px;
		object-fit: cover;
		margin: 30px auto;
		border-radius: 50%;
		border: 4px solid #007bff;
	}

	/* Responsive Layout */
	@media (max-width: 992px) {
		.hero-section {
			height: auto;
			padding: 50px 0;
		}
		.featured-speakers {
			padding: 60px 20px;
		}
		.featured-speakers .card {
			margin-bottom: 30px;
		}
	}

	@media (max-width: 768px) {
		.hero-section {
			padding: 40px 0;
		}
		.row {
			flex-direction: column;
		}
		.speaker-img {
			width: 100px;
			height: 100px;
			margin: 20px auto;
		}
	}
  .btn-primary{
    background:
			linear-gradient(135deg, rgba(0, 0, 50, 0.8), rgba(0, 50, 100, 0.8)),
			url('https://source.unsplash.com/1600x900/?technology,conference') center/cover no-repeat;
    color: white;
    font-weight: bold;
    font-size: 1.3rem;
    padding: 14px 28px;
    border-radius: 6px;
    text-transform: uppercase;
    transition: all 0.3s ease-in-out;
    display: inline-block;
    box-shadow: 0px 3px 10px rgba(255, 204, 0, 0.4);
  }
  .btn-primary:hover{
    background-color: #e6b800;
    transform: scale(1.05);
    box-shadow: 0px 5px 15px rgba(255, 204, 0, 0.6);
  }
</style>
