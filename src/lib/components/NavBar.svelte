<!-- NavBar.svelte -->
<script lang="ts">
  const links = [
    { label: "A propos", href: "#about" },
    { label: "Tarifs", href: "#pricing" },
    { label: "Contact", href: "#contact" }
  ];
</script>

<nav class="fixed top-0 left-0 w-full backdrop-blur-md bg-gray-500/20 border-b border-white z-50">
  <div class="max-w-7xl mx-auto px-6 h-16 flex items-center justify-between">
    <div style="font-family: 'Tenor Sans';" class="text-white text-xl tracking-wide flex items-center drop-shadow-md">
      <span style="font-family: 'The Nautigal';" class="font-['The Nautigal'] text-3xl mr-2 drop-shadow-md">MG</span>
      Compt' Admin
    </div>

    <div class="flex gap-8">
      {#each links as link}
        <a
          href={link.href}
          style="font-family: 'Tenor Sans';"
          class="text-white text-lg relative after:block after:h-[2px] after:w-0 after:bg-white after:transition-all after:duration-300 hover:after:w-full"
        >
          {link.label}
        </a>
      {/each}
    </div>
  </div>
</nav>
