<script>
  import { spring } from 'svelte/motion';

  // Using a spring makes the movement feel "organic" and premium
  let coords = spring({ x: 0, y: 0 }, {
    stiffness: 0.05,
    damping: 0.25
  });

  let opacity = $state(0);

  function handleMove(e) {
    coords.set({ x: e.clientX, y: e.clientY });
    if (opacity === 0) opacity = 1;
  }
</script>

<svelte:window 
  onpointermove={handleMove} 
  onpointerdown={() => opacity = 1}
/>

<div
  class="pointer-events-none fixed left-0 top-0 z-[9999] sm:hidden md:block hidden"
  style="
    transform: translate({$coords.x}px, {$coords.y}px) translate(-50%, -50%);
    opacity: {opacity};
  "
>
  <div class="h-16 w-16 rounded-full bg-blue-500/10 blur-xl"></div>
  <div class="absolute inset-0 h-16 w-16 rounded-full border border-white/20 scale-95 shadow-[inset_0_0_20px_rgba(255,255,255,0.1)]"></div>
</div>