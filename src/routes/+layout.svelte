<script>
    import { onMount } from 'svelte';
    import Navbar from '../components/Navbar.svelte';
  
    onMount(async () => {
      // Import Bootstrap only when the component is mounted (i.e., in the browser)
      import('bootstrap/dist/js/bootstrap.bundle.min');
    });
  </script>
  
  <slot />
  