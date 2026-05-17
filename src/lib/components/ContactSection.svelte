<script lang="ts">
  import { Motion } from 'svelte-motion';
  import { ArrowUpRight } from 'lucide-svelte';
</script>

<section id="contact" class="py-32 px-6 md:px-12 bg-black min-h-screen flex flex-col justify-between">
  <div class="max-w-7xl mx-auto w-full pt-20">
    <Motion let:motion {...({ initial: { opacity: 0, y: 20 }, whileInView: { opacity: 1, y: 0 }, viewport: { once: true }, transition: { duration: 0.8 } } as any)}>
      <div use:motion class="text-center md:text-left">
        <h2 class="text-5xl md:text-9xl font-bold tracking-tighter mb-8 text-white">
          Let's talk <br/> about your <br/> next project.
        </h2>
        <a href="mailto:muhammadsalisi123@gmail.com" class="inline-flex items-center gap-4 text-2xl md:text-5xl font-bold tracking-tight text-[#FF4D29] hover:text-white transition-colors duration-300">
          Get in touch <ArrowUpRight size={48} />
        </a>
      </div>
    </Motion>
  </div>

  <footer class="max-w-7xl mx-auto w-full mt-32 pt-8 border-t border-zinc-900 flex flex-col md:flex-row justify-between items-center gap-8">
    <div class="text-zinc-500 font-mono text-sm">
      © {new Date().getFullYear()} Muhammad Salisu. Built with SvelteKit.
    </div>
    <div class="flex gap-8">
      <a href="https://github.com/Muha-coder-dev" target="_blank" class="text-white hover:text-[#FF4D29] uppercase tracking-widest text-sm font-bold transition-colors">GitHub</a>
      <a href="https://www.linkedin.com/in/muhammad-salisu-b0a4422b4" target="_blank" class="text-white hover:text-[#FF4D29] uppercase tracking-widest text-sm font-bold transition-colors">LinkedIn</a>
      <a href="https://x.com/desgnbymuhammad?t=1BYCeOCrtVzVdp-avAaOCg&s=09" target="_blank" class="text-white hover:text-[#FF4D29] uppercase tracking-widest text-sm font-bold transition-colors">Twitter</a>
    </div>
  </footer>
</section>
