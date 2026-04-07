<script>
    import Features from "$lib/sections/Features.svelte";
    import AppSuite from "$lib/sections/AppSuite.svelte";
    let email = $state("");
</script>

<section class="relative min-h-[90vh] flex flex-col items-center justify-center px-6 pt-20">
  <div class="absolute top-1/4 left-1/2 -translate-x-1/2 w-150 h-75 bg-blue-500/10 blur-[120px] z-10"></div>

  <div class="max-w-4xl text-center space-y-10">
    <!-- <div class="inline-flex items-center gap-2 px-4 py-1.5 rounded-full border border-white/10 bg-white/5 text-[11px] font-semibold uppercase tracking-wider text-blue-400">
      <span class="w-2 h-2 rounded-full bg-blue-500 animate-pulse"></span>
      Serving Dubai Coffee, Zamboanga
    </div> -->

    <h1 class="text-4xl md:text-6xl font-bold tracking-tight text-white">
      Modern Mobile-Friendly POS.<br />
      <span class="opacity-40">Resilient by design.</span>
    </h1>

    <p class="text-lg md:text-xl text-zinc-400 max-w-2xl mx-auto leading-relaxed">
      A beautiful, offline-first experience built for the rhythm of busy cafes. 
      Syncs locally, functions anywhere.
    </p>

    <div class="flex flex-col sm:flex-row items-center justify-center gap-3 pt-6">
      <a href="#contact" class="cursor-pointer z-10 w-full sm:w-auto bg-white text-black font-bold px-8 py-4 rounded-2xl hover:bg-zinc-200 transition-all active:scale-95">
        Request Early Access and Shop Integration
      </a>
    </div>

    <div class="mt-24 relative group">
      <div class="absolute -inset-1 bg-linear-to-r from-blue-500 to-emerald-500 rounded-3xl blur opacity-10 group-hover:opacity-20 transition duration-1000"></div>
      
      <div class="relative bg-[#0a0a0a] border border-white/10 rounded-3xl p-4 shadow-2xl overflow-hidden aspect-video w-full flex items-center justify-center">
        <span class="text-zinc-700 font-mono text-xs tracking-[0.2em] uppercase italic">
          Preview of Coffee_POS App UI
        </span>
      </div>
    </div>
  </div>
</section>

<Features />
<AppSuite />