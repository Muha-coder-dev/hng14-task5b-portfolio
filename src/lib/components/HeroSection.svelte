<script lang="ts">
  import { Motion } from 'svelte-motion';
  import { onMount } from 'svelte';

  let canvas: HTMLCanvasElement;

  onMount(() => {
    const ctx = canvas.getContext('2d');
    if (!ctx) return;

    let particlesArray: any[] = [];
    let numParticles = window.innerWidth < 768 ? 50 : 120;

    const mouse = { x: null as number | null, y: null as number | null };

    window.addEventListener('mousemove', (e) => {
      mouse.x = e.x;
      mouse.y = e.y;
    });

    class Particle {
      x: number;
      y: number;
      size: number;
      speedX: number;
      speedY: number;

      constructor() {
        this.x = Math.random() * canvas.width;
        this.y = Math.random() * canvas.height;
        this.size = Math.random() * 2 + 0.5;
        this.speedX = Math.random() * 0.5 - 0.25;
        this.speedY = Math.random() * 0.5 - 0.25;
      }

      update() {
        this.x += this.speedX;
        this.y += this.speedY;

        if (this.x < 0 || this.x > canvas.width) this.speedX *= -1;
        if (this.y < 0 || this.y > canvas.height) this.speedY *= -1;

        if (mouse.x && mouse.y) {
          let dx = mouse.x - this.x;
          let dy = mouse.y - this.y;
          let distance = Math.sqrt(dx * dx + dy * dy);
          if (distance < 100) {
            this.x -= dx / 10;
            this.y -= dy / 10;
          }
        }
      }

      draw() {
        if (!ctx) return;
        ctx.fillStyle = '#FF4D29';
        ctx.beginPath();
        ctx.arc(this.x, this.y, this.size, 0, Math.PI * 2);
        ctx.closePath();
        ctx.fill();
      }
    }

    function init() {
      particlesArray = [];
      for (let i = 0; i < numParticles; i++) {
        particlesArray.push(new Particle());
      }
    }

    function animate() {
      if (!ctx) return;
      ctx.clearRect(0, 0, canvas.width, canvas.height);
      for (let i = 0; i < particlesArray.length; i++) {
        particlesArray[i].update();
        particlesArray[i].draw();
      }
      requestAnimationFrame(animate);
    }

    const resize = () => {
      canvas.width = window.innerWidth;
      canvas.height = window.innerHeight;
      numParticles = window.innerWidth < 768 ? 50 : 120;
      init();
    };

    window.addEventListener('resize', resize);
    resize();
    animate();

    return () => {
      window.removeEventListener('resize', resize);
    };
  });
</script>

<div class="relative min-h-screen bg-black text-white overflow-hidden flex flex-col">
  <!-- Particle Canvas -->
  <canvas bind:this={canvas} class="absolute inset-0 z-0 opacity-60"></canvas>

  <!-- Grid Overlay -->
  <div class="absolute inset-0 z-10 pointer-events-none opacity-[0.03]" style="background-image: linear-gradient(#fff 1px, transparent 1px); background-size: 70px 70px;"></div>

  <div class="scanline"></div>

  <section class="relative z-30 flex-1 flex flex-col items-center justify-center px-6 pt-16 pb-20">
    <Motion let:motion initial={{ opacity: 0, y: 30 }} animate={{ opacity: 1, y: 0 }} transition={{ duration: 0.9 }}>
      <div use:motion class="text-center max-w-4xl">
        <h1 class="text-5xl sm:text-6xl md:text-8xl font-bold tracking-tighter mb-6 font-sans">
          Hi, I'm Muhammad
        </h1>
        <p class="text-base sm:text-lg md:text-2xl text-zinc-300 max-w-2xl mx-auto leading-tight mb-12">
          I build high-performance frontend architectures <br class="hidden md:block" />
          and interactive user interfaces.
        </p>

        <Motion let:motion initial={{ opacity: 0, y: 20 }} animate={{ opacity: 1, y: 0 }} transition={{ delay: 0.6, duration: 0.8 }}>
          <div use:motion>
            <a href="/hireme" class="group relative inline-flex items-center justify-center px-10 py-5 border-2 border-white bg-black hover:bg-white hover:text-black transition-all duration-300 text-lg font-medium tracking-wider overflow-hidden rounded-full">
              <span class="relative z-10">WHY YOU SHOULD HIRE ME</span>
              <div class="absolute inset-0 bg-gradient-to-r from-transparent via-white/20 to-transparent -translate-x-full group-hover:translate-x-full transition-transform duration-700"></div>
            </a>
          </div>
        </Motion>
      </div>
    </Motion>

    <div class="absolute bottom-10 left-1/2 -translate-x-1/2 z-40 animate-bounce">
      <a href="#projects" class="block text-white/70 hover:text-white transition-colors">
        <div class="w-11 h-11 rounded-full border border-white/40 flex items-center justify-center">
          <div class="w-3 h-5 border-r-2 border-b-2 border-white/70 rotate-45"></div>
        </div>
      </a>
    </div>
  </section>
</div>
