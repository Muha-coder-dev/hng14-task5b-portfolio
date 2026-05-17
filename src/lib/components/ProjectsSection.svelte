<script lang="ts">
  import { Motion } from 'svelte-motion';

  // Fallback data
  const projects = [
    {
      id: "zenoai",
      name: "ZenoAI",
      status: "In Development",
      description: "ZenoAI is an AI-powered productivity and automation platform...",
      tags: [
        { name: "SvelteKit", color: "text-orange-500" },
        { name: "TailwindCSS", color: "text-white" }
      ],
      source_code_link: "https://zenoai-ten.vercel.app/"
    },
    {
      id: "helious",
      name: "Helious",
      status: "Live",
      description: "Helious is an AI-powered smart contract analyzer...",
      tags: [
        { name: "TypeScript", color: "text-orange-500" },
        { name: "AI", color: "text-white" }
      ],
      source_code_link: "https://heliouss.vercel.app"
    }
  ];
</script>

<section id="projects" class="py-32 px-6 md:px-12 bg-black min-h-screen relative z-10">
  <div class="max-w-7xl mx-auto">
    <Motion let:motion {...({ initial: { opacity: 0, y: 20 }, whileInView: { opacity: 1, y: 0 }, viewport: { once: true }, transition: { duration: 0.6 } } as any)}>
      <h2 use:motion class="text-6xl md:text-8xl font-bold tracking-tighter mb-20 text-white">
        Selected Work
      </h2>
    </Motion>

    <div class="space-y-32">
      {#each projects as project, index}
        <Motion let:motion {...({ initial: { opacity: 0, y: 50 }, whileInView: { opacity: 1, y: 0 }, viewport: { once: true, margin: "-100px" }, transition: { duration: 0.8, delay: index * 0.1 } } as any)}>
          <div use:motion class="group relative flex flex-col md:flex-row gap-8 items-center border border-zinc-800 hover:border-[#FF4D29] p-8 md:p-12 rounded-2xl transition-colors duration-500">
            <div class="flex-1 space-y-6 z-10 relative">
              <div class="flex items-center gap-4">
                <span class="px-4 py-1 rounded-full text-xs font-mono uppercase tracking-wider bg-zinc-900 border border-zinc-700 text-zinc-300">
                  {project.status}
                </span>
              </div>
              <h3 class="text-4xl md:text-6xl font-bold tracking-tight text-white group-hover:text-[#FF4D29] transition-colors duration-500">
                {project.name}
              </h3>
              <p class="text-xl text-zinc-400 max-w-xl leading-relaxed">
                {project.description}
              </p>
              <div class="flex flex-wrap gap-4 pt-4">
                {#each project.tags as tag}
                  <span class="text-sm font-medium {tag.color} tracking-wider uppercase">
                    {tag.name}
                  </span>
                {/each}
              </div>
              <div class="pt-8">
                <a href={project.source_code_link} target="_blank" class="inline-flex items-center gap-2 text-white hover:text-[#FF4D29] transition-colors font-bold text-lg tracking-wide">
                  Visit Project <span class="group-hover:translate-x-2 transition-transform duration-300">→</span>
                </a>
              </div>
            </div>
          </div>
        </Motion>
      {/each}
    </div>
  </div>
</section>
