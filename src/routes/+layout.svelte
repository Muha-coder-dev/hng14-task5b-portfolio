<script lang="ts">
  import './layout.css';
  import { onMount } from 'svelte';
  import Navbar from '$lib/components/Navbar.svelte';
  
  let { children } = $props();

  onMount(() => {
    document.documentElement.classList.add('dark');
  });
</script>

<div class="min-h-screen bg-black text-white font-sans selection:bg-orange-500 selection:text-white">
  <Navbar />
  <main>
    {@render children()}
  </main>
</div>
