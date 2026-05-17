<script lang="ts">
  import HeroSection from '$lib/components/HeroSection.svelte';
  import ProjectsSection from '$lib/components/ProjectsSection.svelte';
  import ContactSection from '$lib/components/ContactSection.svelte';
  import { Motion } from 'svelte-motion';
</script>

<svelte:head>
  <title>Muhammad | Frontend Engineer & UI Architect</title>
  <meta name="description" content="Portfolio of Muhammad, a Frontend Engineer building high-performance architectures and interactive user interfaces." />
</svelte:head>

<main class="bg-black selection:bg-[#FF4D29] selection:text-white">
  <HeroSection />
  
  <section id="about" class="py-32 px-6 md:px-12 bg-zinc-950 relative border-t border-zinc-900">
    <div class="max-w-7xl mx-auto flex flex-col items-center">
      <Motion let:motion initial={{ opacity: 0, y: 30 }} whileInView={{ opacity: 1, y: 0 }} viewport={{ once: true }} transition={{ duration: 0.8 }}>
        <div use:motion class="max-w-3xl text-center">
          <h2 class="text-[#FF4D29] font-mono tracking-widest uppercase mb-8">The Story.</h2>
          <p class="text-3xl md:text-5xl font-bold leading-tight text-white mb-12 tracking-tight">
            I craft digital experiences that combine robust engineering with cinematic visual design.
          </p>
        </div>
      </Motion>
    </div>
  </section>

  <ProjectsSection />
  <ContactSection />
</main>
