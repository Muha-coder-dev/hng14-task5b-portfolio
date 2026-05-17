<svelte:head>
  <title>Hire Muhammad Salisu | Frontend Developer</title>
  <meta name="description" content="Skilled frontend developer with SvelteKit, React & TypeScript. Good looking, funny, and ships 10x faster. Ready to join your team or build your next project." />
</svelte:head>

<main class="bg-black text-white min-h-screen font-sans selection:bg-[#FF4D29]/30">

  <!-- Navbar -->
  <nav class="fixed top-0 w-full z-50 bg-black/80 backdrop-blur border-b border-zinc-900 py-4 px-6 md:px-12 flex justify-between items-center">
    <a href="/" class="text-xl font-bold tracking-tighter text-white hover:text-[#FF4D29] transition-colors">
      ← Salisu.
    </a>
    <div class="flex gap-6 text-sm font-medium tracking-widest">
      <a href="/#projects" class="text-zinc-400 hover:text-white transition-colors">WORK</a>
      <a href="/#about" class="text-zinc-400 hover:text-white transition-colors">ABOUT</a>
      <a href="/#contact" class="text-zinc-400 hover:text-white transition-colors">CONTACT</a>
    </div>
  </nav>

  <!-- Hero -->
  <section class="min-h-screen flex flex-col items-center justify-center px-6 text-center relative overflow-hidden">
    <div class="absolute inset-0 opacity-[0.03]" style="background-image: linear-gradient(#fff 1px, transparent 1px), linear-gradient(90deg, #fff 1px, transparent 1px); background-size: 60px 60px;"></div>

    <p class="text-[#FF4D29] font-mono tracking-widest uppercase text-sm mb-6 animate-pulse">Available for hire</p>

    <h1 class="text-7xl md:text-[10rem] font-black tracking-tighter leading-none mb-4">
      MUHAMMAD
    </h1>
    <h2 class="text-2xl md:text-4xl font-bold text-zinc-400 mb-10 tracking-tight">
      Frontend Developer
    </h2>
    <p class="text-lg text-zinc-400 max-w-xl mb-12 leading-relaxed">
      You've probably seen my portfolio... and you're still not fully convinced. Cool. Let's get personal.
    </p>
    <a href="#reasons" class="px-10 py-5 bg-[#FF4D29] hover:bg-[#e64525] text-white font-bold text-lg rounded-full transition-all duration-300 hover:scale-105 shadow-lg shadow-orange-900/30">
      Why Hire Me →
    </a>
  </section>

  <!-- Reasons -->
  <section id="reasons" class="py-32 px-6 md:px-12 max-w-5xl mx-auto">
    <h2 class="text-4xl md:text-6xl font-black tracking-tighter mb-20 text-white">
      Here are <span class="text-[#FF4D29]">7 solid reasons</span><br/>why you should hire me:
    </h2>

    <div class="space-y-0">
      {#each reasons as reason, i}
        <div class="group flex items-start gap-8 py-10 border-b border-zinc-900 hover:border-[#FF4D29] transition-colors duration-300">
          <span class="text-[#FF4D29] font-mono text-lg font-bold pt-1 min-w-[2rem]">0{i + 1}</span>
          <div>
            <h3 class="text-2xl md:text-3xl font-bold text-white group-hover:text-[#FF4D29] transition-colors duration-300">{reason.title}</h3>
            {#if reason.desc}
              <p class="text-zinc-500 mt-2 text-lg">{reason.desc}</p>
            {/if}
          </div>
        </div>
      {/each}
    </div>
  </section>

  <!-- CTA -->
  <section class="py-32 px-6 text-center border-t border-zinc-900">
    <h2 class="text-5xl md:text-8xl font-black tracking-tighter mb-6">So... what are<br/>you waiting for?</h2>
    <p class="text-zinc-400 text-xl mb-16 max-w-xl mx-auto">
      Send me that job offer or let's build something unreal together.
    </p>
    <div class="flex flex-col sm:flex-row gap-6 justify-center">
      <a href="mailto:muhammadsalisi123@gmail.com" class="px-10 py-5 bg-[#FF4D29] hover:bg-[#e64525] text-white font-bold text-lg rounded-full transition-all duration-300 hover:scale-105">
        Email Me
      </a>
      <a href="https://github.com/Muha-coder-dev" target="_blank" class="px-10 py-5 border-2 border-white hover:border-[#FF4D29] hover:text-[#FF4D29] text-white font-bold text-lg rounded-full transition-all duration-300">
        Be Amazed by My GitHub
      </a>
    </div>
  </section>

  <!-- Footer -->
  <footer class="py-10 px-6 border-t border-zinc-900 text-center text-zinc-600 text-sm font-mono">
    © {new Date().getFullYear()} Muhammad Salisu. Built with SvelteKit.
  </footer>

</main>

<script lang="ts">
  const reasons = [
    { title: "I'm a very skilled Frontend Developer", desc: "SvelteKit, React, Next.js, TypeScript — I know my tools." },
    { title: "I love building cool stuff", desc: "Every project is a chance to push the boundaries of what's possible." },
    { title: "I have great communication & collaboration skills", desc: "I work well with teams and communicate clearly under pressure." },
    { title: "I'm good looking", desc: "Okay, this one speaks for itself." },
    { title: "I have a very good sense of humour", desc: "Great vibes make great teams." },
    { title: "I believe in simplicity & smart work", desc: "Clean code, efficient solutions, no unnecessary complexity." },
    { title: "Stop being behind", desc: "While you're hesitating, someone else is already shipping." },
  ];
</script>
