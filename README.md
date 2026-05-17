This is a SvelteKit project bootstrapped for a personal developer portfolio.

Getting Started
First, install the dependencies:

npm install
# or
yarn install
# or
pnpm install

Then, run the development server:

npm run dev
# or
yarn dev
# or
pnpm dev

Open http://localhost:5173 with your browser to see the result.

You can start editing the application by modifying src/routes/+page.svelte or the components in src/lib/components. The page auto-updates as you edit the files.

Architecture Explanation
The application follows a modular, component-based architecture:
- Framework: SvelteKit for static generation and server-side rendering.
- Styling: TailwindCSS (v4) with CSS custom properties to maintain theme consistency.
- Routing: Single-page scroll layout orchestrated through +page.svelte.

Animation Decisions
- Svelte Motion: Leveraged svelte-motion to handle complex scroll-based staggering for the Projects and Contact sections.
- Canvas Particles: The hero section uses a lightweight, custom HTML5 Canvas particle system for optimal performance without heavy 3D libraries.

Performance Optimization Techniques
- Zero-Runtime Overhead: Svelte's compilation eliminates virtual DOM diffing, resulting in surgical DOM updates.
- Lightweight Assets: The particle system is written in vanilla JS inside the Svelte component.

Accessibility Considerations
- Keyboard Navigation: Ensured the mobile navigation toggle and all project links are fully tab-navigable.
- Semantic HTML: Used semantic elements (nav, section, main, footer) to improve screen reader interpretation.

Trade-offs Made
- Canvas vs WebGL/Three.js: Traded a complex 3D particle field for a faster 2D canvas approach. This sacrifices depth perception but guarantees perfect Lighthouse performance scores and smoother scrolling.

Learn More
To learn more about the technologies used in this project, take a look at the following resources:
- SvelteKit Documentation - learn about SvelteKit features and routing.
- TailwindCSS Documentation - learn about utility-first CSS styling.

Deploy on Vercel
The easiest way to deploy your SvelteKit app is to use the Vercel Platform.
Check out the SvelteKit deployment documentation for more details.
