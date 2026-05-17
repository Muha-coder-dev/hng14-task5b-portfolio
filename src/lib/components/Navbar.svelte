<script lang="ts">
  import { Menu, X } from 'lucide-svelte';
  import { Motion } from 'svelte-motion';
  import { slide } from 'svelte/transition';

  let isOpen = $state(false);

  const links = [
    { name: 'WORK', href: '#work' },
    { name: 'CAPABILITIES', href: '#capabilities' },
    { name: 'ABOUT', href: '#about' },
    { name: 'CONTACT', href: '#contact' }
  ];
</script>

<nav class="fixed top-0 w-full z-50 mix-blend-difference text-white py-6 px-6 md:px-12 flex justify-between items-center">
  <a href="/" class="text-2xl font-bold tracking-tighter hover:text-gray-300 transition-colors">
    Muhammad.
  </a>

  <button class="md:hidden z-50 text-white focus:outline-none" onclick={() => isOpen = !isOpen}>
    {#if isOpen}
      <X size={32} />
    {:else}
      <Menu size={32} />
    {/if}
  </button>

  <div class="hidden md:flex gap-8">
    {#each links as link}
      <a href={link.href} class="text-sm font-medium tracking-widest hover:text-gray-400 transition-colors">
        {link.name}
      </a>
    {/each}
  </div>
</nav>

{#if isOpen}
  <div transition:slide={{ duration: 400 }} class="fixed inset-0 z-40 bg-black flex flex-col items-center justify-center space-y-8 md:hidden">
    {#each links as link}
      <a href={link.href} onclick={() => isOpen = false} class="text-4xl font-bold tracking-tighter hover:text-[#FF4D29] transition-colors">
        {link.name}
      </a>
    {/each}
  </div>
{/if}
