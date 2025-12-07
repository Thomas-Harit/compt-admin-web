<!-- About.svelte -->
<script lang="ts">
  import personImage from '$lib/assets/image 2.png';
  import logo1 from '$lib/assets/icons/ggl-drive.svg';
  import logo2 from '$lib/assets/icons/notion.svg';
  import logo3 from '$lib/assets/icons/excel.svg';
  import logo4 from '$lib/assets/icons/unknown.svg';
</script>

<section class="w-full">
  <!-- Subsection 1 -->
  <div class="flex flex-col md:flex-row w-full bg-white">
    <!-- Left: Text -->
    <div class="w-full md:w-7/10 p-8 flex flex-col justify-center items-center">
      <h2 style="font-family: 'Tenor Sans';" class="text-4xl md:text-5xl mb-10">Pourquoi me choisir ?</h2>
      <ul style="font-family: 'Forum';" class="list-disc pl-5 space-y-3 text-lg md:text-xl max-w-3xl">
        <li>Expérience professionnelle solide</li>
        <li>Gestion efficace et rapide</li>
        <li>Solutions personnalisées</li>
        <li>Support et accompagnement humain</li>
      </ul>
    </div>
    <!-- Right: Image -->
    <div class="w-full md:w-3/10 h-64 md:h-auto">
      <img src={personImage} alt="Person" class="w-full h-full object-cover" />
    </div>
  </div>

  <!-- Subsection 2 -->
  <div class="w-full bg-[#F5EBE0] py-16 flex flex-col items-center">
    <h2 style="font-family: 'Tenor Sans';" class="text-3xl mb-8 text-center">Des outils simples et efficaces</h2>
    <div class="flex flex-wrap justify-center gap-8">
      <img src={logo1} alt="Logo 1" class="h-16" />
      <img src={logo2} alt="Logo 2" class="h-16" />
      <img src={logo3} alt="Logo 3" class="h-16" />
      <img src={logo4} alt="Logo 4" class="h-16" />
    </div>
  </div>
</section>