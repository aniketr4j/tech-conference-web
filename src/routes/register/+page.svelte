<script>
	import Navbar from '../../components/Navbar.svelte';
  import Footer from '../../components/Footer.svelte';

	let name = '';
	let email = '';
	let password = '';
	let errors = { name: '', email: '', password: '' };

	function validateForm() {
		errors = { name: '', email: '', password: '' };

		if (!name.trim()) {
			errors.name = 'Please enter your name.';
		}
		if (!email.trim()) {
			errors.email = 'Please enter your email.';
		} else if (!/^\S+@\S+\.\S+$/.test(email)) {
			errors.email = 'Enter a valid email address.';
		}
		if (!password.trim()) {
			errors.password = 'Please enter your password.';
		} else if (password.length < 6) {
			errors.password = 'Password must be at least 6 characters.';
		}

		return Object.values(errors).every((error) => error === '');
	}

	function handleSubmit(event) {
		event.preventDefault();
		if (validateForm()) {
			alert('Registration successful!');

			// Reset fields after successful registration
			name = '';
			email = '';
			password = '';
		}
	}
</script>

<Navbar />

<div class="container my-5">
	<h2>Register for Tech Conference</h2>
	<form on:submit={handleSubmit}>
		<div class="mb-3">
			<label class="form-label" for="name">Name</label>
			<input
				type="text"
				id="name"
				class="form-control"
				bind:value={name}
				placeholder="Enter your name"
			/>
			{#if errors.name}
				<div class="text-danger">{errors.name}</div>
			{/if}
		</div>

		<div class="mb-3">
			<label class="form-label" for="email">Email</label>
			<input
				type="email"
				id="email"
				class="form-control"
				bind:value={email}
				placeholder="Enter your email"
			/>
			{#if errors.email}
				<div class="text-danger">{errors.email}</div>
			{/if}
		</div>

		<div class="mb-3">
			<label class="form-label" for="password">Password</label>
			<input
				type="password"
				id="password"
				class="form-control"
				bind:value={password}
				placeholder="Enter your password"
			/>
			{#if errors.password}
				<div class="text-danger">{errors.password}</div>
			{/if}
		</div>

		<button type="submit" class="btn btn-primary">Register</button>
	</form>
</div>




<style>
	.text-danger {
		color: red;
		font-size: 14px;
		margin-top: 5px;
	}

	.form-control {
		border-radius: 8px;
		padding: 10px;
	}
  .btn-primary{
    padding: 12px;
    font-size: 18px;
    font-weight: bold;
    background: #ff5722;
    border: none;
    color: #fff;
    border-radius: 8px;
    text-transform: uppercase;
    transition: all 0.3s ease-in-out;
    box-shadow: 0px 3px 10px rgba(255, 87, 34, 0.4);
  }
</style>
