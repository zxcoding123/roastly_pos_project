<script>
  import "../app.css";
  import { fly, fade } from 'svelte/transition';
  import CursorBlob from "$lib/components/CursorBlob.svelte";
  import coffeeLogo from '$lib/assets/coffee_pos_icon_v2.png';

  let { children } = $props();
  let isMenuOpen = $state(false);

  const navLinks = [
    { name: "Features", href: "#features" },
    { name: "Founders", href: "#founders" },
    { name: "Ecosystem", href: "#ecosystem" },
    { name: "Contact", href: "#contact" }
  ];

  const toggleMenu = () => {
    isMenuOpen = !isMenuOpen;
    // Logic to prevent background scrolling when menu is open
    if (typeof document !== 'undefined') {
      document.body.style.overflow = isMenuOpen ? 'hidden' : 'auto';
    }
  };

  const trackNav = (name) => {
    if (window.umami) {
      umami.track('Navigation Link Clicked', { name: name });
    }
  };
</script>

<CursorBlob />

<div class="min-h-screen flex flex-col overflow-x-hidden bg-black text-white">
  <nav class="fixed top-0 w-full z-[100] border-b border-white/5 bg-black/50 backdrop-blur-md">
   <div class="max-w-6xl mx-auto px-6 h-20 flex justify-between items-center">
  <a href="/#home"  data-umami-event="nav-click"
    data-umami-event-name="Navigation Link Clicked: Home" class="flex items-center gap-2 outline-none group">
    <div class="w-8 h-8 rounded-lg shadow-lg overflow-hidden border border-white/10 group-hover:border-white/20 transition-colors">
      <img src="{coffeeLogo}" alt="Roastly Logo" class="w-full h-full object-cover" />
    </div>
    <span class="text-xl font-bold tracking-tight text-white">Roastly.</span>
  </a>
  
  <div class="hidden md:flex gap-10 text-sm font-medium text-zinc-400">
    {#each navLinks as link (link.name)}
  <a 
    href={link.href} 
    onclick={() => trackNav(link.name)}
    class="hover:text-white transition-colors"
  >
    {link.name}
  </a>
{/each}
  </div>

  <div class="flex items-center">
    <button 
      onclick={toggleMenu}
      class="md:hidden relative z-[110] w-10 h-10 flex flex-col items-center justify-center gap-1.5 focus:outline-none"
      aria-label="Toggle Menu"
    >
      <span class="w-6 h-0.5 bg-white transition-all duration-300 {isMenuOpen ? 'rotate-45 translate-y-2' : ''}"></span>
      <span class="w-6 h-0.5 bg-white transition-all duration-300 {isMenuOpen ? 'opacity-0' : ''}"></span>
      <span class="w-6 h-0.5 bg-white transition-all duration-300 {isMenuOpen ? '-rotate-45 -translate-y-2' : ''}"></span>
    </button>

    <a href="#contact" class="hidden md:block">
      <button class="btn-primary text-sm px-5 py-2 cursor-pointer transition-transform active:scale-95">
        Get Started
      </button>
    </a>
  </div>
</div>
  </nav>

 {#if isMenuOpen}
  <div 
    transition:fade={{ duration: 200 }}
    class="fixed inset-0 z-[80] bg-black/60 backdrop-blur-xl"
  ></div>

  <div 
    transition:fly={{ x: 500, duration: 400, opacity: 1 }}
    class="fixed inset-0 z-[90] flex flex-col p-10 justify-center items-end bg-black"
  >
    <div class="mt-20 space-y-6 text-right"> {#each navLinks as link, i (link.name)}
        <div transition:fly={{ y: 30, delay: 150 + (i * 60), duration: 600 }}>
          <a 
            href={link.href} 
            onclick={toggleMenu}
            class="text-6xl font-black tracking-tighter text-white hover:text-blue-500 transition-all duration-300 block active:scale-95"
          >
            {link.name}
          </a>
        </div>
      {/each}
    </div>

    <div class="mt-8 pt-10 border-t border-white/10 w-full text-right" transition:fade={{ delay: 500 }}>
      <p class="text-zinc-500 font-mono text-[10px] uppercase tracking-[0.3em] mb-6">Connect</p>
      <div class="flex flex-col gap-2">
        <a href="tel:+639536640119" class="text-white font-bold text-lg">+63 953 664 0119</a>
        <a href="mailto:ahmadaquino.2002@gmail.com" class="text-blue-400 font-medium">ahmadaquino.2002@gmail.com</a>
        <div class="h-4"></div> <a href="tel:+639300275680" class="text-white font-bold text-lg">+63 930 027 5680</a>
        <a href="mailto:alilfahad403@gmail.com" class="text-blue-400 font-medium text-xs">alilfahad403@gmail.com</a>
      </div>
    </div>
  </div>
{/if}

  <main class="flex-grow pt-20">
    {@render children()}
  </main>

    <footer class="py-20 border-t border-white/5 px-6">
    <div class="max-w-6xl mx-auto grid grid-cols-1 md:grid-cols-4 gap-12 text-sm text-zinc-500">
      <div class="col-span-2">
        <div class="flex items-center gap-2 mb-4 text-white">
          <div class="w-6 h-6 bg-white/10 rounded-md"><img src="{coffeeLogo}" alt="Roastly Logo" class="w-full h-full object-cover" /></div>
          <span class="font-bold">Roastly</span>
        </div>
        <p class="max-w-xs leading-relaxed">
          The next generation of coffee offline-first point-of-sale mobile application. 
          Crafted with care in Zamboanga City.
        </p>
      </div>
   <div class="space-y-4">
  <p class="text-white font-medium uppercase tracking-widest text-[10px] mb-4">Technologies</p>
  
  <div class="grid grid-cols-1 gap-3">
  
    <div class="flex items-center gap-2 group cursor-pointer">
      <span class="w-1 h-1 bg-blue-500 rounded-full group-hover:scale-150 transition-transform"></span>
      <p class="hover:text-white transition-colors">Flutter & Dart</p>
    </div>

    <div class="flex items-center gap-2 group cursor-pointer">
      <span class="w-1 h-1 bg-emerald-500 rounded-full group-hover:scale-150 transition-transform"></span>
      <p class="hover:text-white transition-colors">Isar & Hive Database</p>
    </div>

    <div class="flex items-center gap-2 group cursor-pointer">
      <span class="w-1 h-1 bg-purple-500 rounded-full group-hover:scale-150 transition-transform"></span>
      <p class="hover:text-white transition-colors">Bonsoir (mDNS/NSD)</p>
    </div>

    <div class="flex items-center gap-2 group cursor-pointer">
      <span class="w-1 h-1 bg-yellow-500 rounded-full group-hover:scale-150 transition-transform"></span>
      <p class="hover:text-white transition-colors">Local WebSockets</p>
    </div>
  </div>
</div>
      <div class="space-y-3">
        <p class="text-white font-medium uppercase tracking-widest text-[10px]">Connect</p>
        <a href="#contact" data-umami-event="nav-click"
    data-umami-event-name="Navigation Link Clicked: Contact Us" class="hover:text-white cursor-pointer">Contact Us</a>
      </div>
    </div>
  </footer>
</div>

<style>
  :global(html) {
    scroll-behavior: smooth;
  }
</style>