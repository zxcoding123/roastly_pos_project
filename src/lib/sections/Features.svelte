<script>
  const features = [
    {
      title: "Role-Based Access",
      desc: "Granular permissions for Order Takers and Baristas.",
      size: "col-span-1",
      icon: "🔐"
    },
    {
      title: "Real-time Sync",
      desc: "Instant synchronization between the counter and the kitchen, even offline.",
      size: "col-span-1 md:col-span-2",
      icon: "⚡"
    },
    {
      title: "Revenue Insights",
      desc: "Deep dive into your daily sales, top-performing beans, and peak hours.",
      size: "col-span-1 md:col-span-2",
      icon: "📈"
    },
    {
      title: "Live Notifications",
      desc: "Never miss an order. Instant pings across all connected devices.",
      size: "col-span-1",
      icon: "🔔"
    },
    {
      title: "Barista Dashboard",
      desc: "A focused interface designed for speed and high-volume orders.",
      size: "col-span-1",
      icon: "☕"
    },
    {
      title: "Custom Inventory",
      desc: "Manage teas, coffees, and pastries with automatic restock alerts.",
      size: "col-span-1",
      icon: "📦"
    },
    {
      title: "Order History",
      desc: "Full audit logs of every transaction, modification, and refund.",
      size: "col-span-1",
      icon: "🕒"
    }
  ];
</script>

<section id="features" class="py-32 px-6 max-w-7xl mx-auto bg-blue-500/10 rounded-3xl border border-blue-500/20 shadow-lg m-20">
 <span class="text-blue-500 font-mono text-[10px] uppercase tracking-[0.4em] mb-4 block text-center" id="features">The Features</span>
  <div class="text-center mb-20">
    <h2 class="text-4xl md:text-5xl font-bold tracking-tight mb-6">Built for the grind.</h2>
    <p class="text-zinc-500 text-lg max-w-xl mx-auto leading-relaxed">
      Everything you need to run your café, from the first espresso of the morning to the final end-of-day report.
    </p>
  </div>

<div class="grid grid-cols-1 md:grid-cols-3 gap-px bg-white/10 rounded-3xl overflow-hidden border border-white/10 shadow-2xl">
  {#each features as feature (feature.title)}
    <div class="{feature.size} bg-[#050505] p-8 group relative overflow-hidden transition-colors hover:bg-white/2">
      
      <div class="absolute -inset-px bg-linear-to-br from-blue-500/5 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-700"></div>
      
      <div class="relative z-10">
        <div class="text-xl mb-6 opacity-80 group-hover:opacity-100 group-hover:scale-100 transition-all duration-500">
          {feature.icon}
        </div>
        
        <h3 class="text-lg font-semibold text-white/90 mb-2 tracking-tight">
          {feature.title}
        </h3>
        
        <p class="text-zinc-500 text-sm leading-relaxed font-medium">
          {feature.desc}
        </p>
      </div>
    </div>
  {/each}
</div>
</section>