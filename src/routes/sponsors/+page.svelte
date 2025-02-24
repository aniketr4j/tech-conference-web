<script>
	import Navbar from '../../components/Navbar.svelte';
    import Footer from '../../components/Footer.svelte';
	import { sponsors } from '../../lib/data.js';
</script>

<Navbar />

<div class="container my-5">
    <h2 class="text-center mb-4">Our Sponsors</h2>
    <div class="row g-4">
        {#each sponsors as sponsor}
            <div class="col-12 col-sm-6 col-md-4 col-lg-3 d-flex justify-content-center">
                <div class="sponsor-card text-center">
                    <div class="image-container">
                        <a href={sponsor.link} target="_blank" rel="noopener noreferrer">
                            <img src={sponsor.logo} alt={sponsor.name} class="sponsor-img" />
                        </a>
                    </div>
                    <p class="mt-2">{sponsor.name} <br> {sponsor.area}</p>
                </div>
            </div>
        {/each}
    </div>
</div>
<Footer/>

<style>
/* Responsive Glassmorphic Container */
.container.my-5 {
	background: linear-gradient(135deg, rgba(0, 0, 255, 0.2), rgba(0, 255, 255, 0.2));
	padding: 40px 20px;
	border-radius: 15px;
	backdrop-filter: blur(10px);
	box-shadow: 0px 6px 18px rgba(0, 0, 0, 0.2);
	border: 1px solid rgba(255, 255, 255, 0.15);
	animation: gradientShift 6s infinite alternate ease-in-out;
}

/* Background Animation */
@keyframes gradientShift {
	0% {
		background: linear-gradient(135deg, rgba(0, 0, 255, 0.2), rgba(0, 255, 255, 0.2));
	}
	100% {
		background: linear-gradient(135deg, rgba(0, 100, 255, 0.3), rgba(0, 255, 150, 0.3));
	}
}

/* Responsive Sponsor Cards */
.sponsor-card {
	background: rgba(255, 255, 255, 0.12);
	padding: 20px;
	border-radius: 12px;
	width: 100%;
	max-width: 250px;
	display: flex;
	flex-direction: column;
	align-items: center;
	height: auto;
	justify-content: center;
	backdrop-filter: blur(6px);
	border: 1px solid rgba(255, 255, 255, 0.15);
	box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
	transition: transform 0.3s ease, box-shadow 0.3s ease, background 0.3s ease;
}

/* Hover Effect */
.sponsor-card:hover {
	transform: scale(1.06);
	box-shadow: 0 6px 12px rgba(0, 0, 0, 0.2);
	background: rgba(255, 255, 255, 0.18);
}

/* Responsive Image Container */
.image-container {
	width: 100%;
	max-width: 180px;
	height: auto;
	display: flex;
	justify-content: center;
	align-items: center;
	overflow: hidden;
}

/* Responsive Sponsor Logo */
.sponsor-img {
	max-width: 100%;
	height: auto;
	object-fit: contain;
}

/* Uniform Text Style */
.sponsor-card p {
	margin-top: 10px;
	font-size: 16px;
	text-align: center;
	color: white;
	font-weight: 500;
}

/* Bootstrap Responsive Grid Adjustments */
.row.g-4 {
	row-gap: 20px;
}

/* Mobile Adjustments */
@media (max-width: 576px) {
    .sponsor-card {
        padding: 15px;
        max-width: 90%;
    }

    .sponsor-img {
        max-width: 150px;
    }

    .sponsor-card p {
        font-size: 14px;
    }
}

/* Tablet Adjustments */
@media (max-width: 768px) {
    .sponsor-card {
        max-width: 100%;
    }

    .sponsor-img {
        max-width: 160px;
    }
}
</style>
