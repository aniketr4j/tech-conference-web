<script>
    import { onMount } from "svelte";

    let navbarToggler, navbarCollapse;

    onMount(() => {
        navbarToggler = document.querySelector(".navbar-toggler");
        navbarCollapse = document.getElementById("navbarNav");

        navbarToggler.addEventListener("click", () => {
            if (navbarCollapse.classList.contains("show")) {
                bootstrap.Collapse.getInstance(navbarCollapse).hide();
            } else {
                bootstrap.Collapse.getInstance(navbarCollapse).show();
            }
        });

        // Close navbar when a nav-link is clicked (for any screen size)
        document.querySelectorAll(".nav-link").forEach((link) => {
            link.addEventListener("click", () => {
                if (navbarCollapse.classList.contains("show")) {
                    bootstrap.Collapse.getInstance(navbarCollapse).hide();
                }
            });
        });
    });
</script>

<nav class="navbar navbar-expand-lg navbar-dark sticky-top custom-navbar">
	<div class="container">
		<a class="navbar-brand" href="/">
			<img
				src="tech.jpeg"
				alt="TechConf Logo"
				width="40"
				height="40"
				class="d-inline-block align-top"
			/>
		</a>
		<button
			class="navbar-toggler"
			type="button"
			data-bs-toggle="collapse"
			data-bs-target="#navbarNav"
			aria-controls="navbarNav"
			aria-expanded="false"
			aria-label="Toggle navigation"
		>
			<span class="navbar-toggler-icon"></span>
		</button>
		<div class="collapse navbar-collapse" id="navbarNav">
			<ul class="navbar-nav ms-auto">
				<li class="nav-item"><a class="nav-link" href="/">Home</a></li>
				<li class="nav-item"><a class="nav-link" href="/speakers">Speakers</a></li>
				<li class="nav-item"><a class="nav-link" href="/schedule">Schedule</a></li>
				<li class="nav-item"><a class="nav-link" href="/sponsors">Sponsors</a></li>
				<li class="nav-item"><a class="nav-link" href="/about">About</a></li>
				<li class="nav-item"><a class="nav-link" href="/contact">Contact</a></li>
			</ul>
		</div>
	</div>
</nav>

<style>
	.custom-navbar {
		background: linear-gradient(to right, #1a1a2e, #0f0f1b);
		padding: 10px 0;
		box-shadow: 0 4px 8px rgba(0, 0, 0, 0.6);
		backdrop-filter: blur(10px);
		border-bottom: 1px solid rgba(255, 255, 255, 0.1);
		transition: all 0.3s ease-in-out;
	}

	.custom-navbar .nav-link {
		color: rgba(255, 255, 255, 0.8);
		font-weight: 500;
		transition: color 0.3s ease-in-out;
	}

	.custom-navbar .nav-link:hover {
		color: #ffffff;
	}

	.navbar-toggler {
		border-color: rgba(255, 255, 255, 0.5);
	}

	.navbar-toggler-icon {
		background-color: white;
		border-radius: 3px;
		width: 24px;
		height: 24px;
		display: flex;
		align-items: center;
		justify-content: center;
	}
</style>
