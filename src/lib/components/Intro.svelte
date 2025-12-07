<script lang="ts">
  import introImage from '$lib/assets/image 1.png';
  // No script logic needed for this component
</script>

<!-- Intro.svelte -->
<section class="relative h-screen w-full overflow-hidden" id="intro">
  <!-- Background image -->
  <img
    src={introImage}
    alt="intro"
    class="absolute inset-0 w-full h-full object-cover"
  />

  <!-- Content -->
  <div class="relative z-10 h-full flex flex-col justify-between text-white text-shadow-lg px-8 pt-32 pb-16">
    <!-- Title -->
    <h1 style="font-family: 'Tenor Sans';" class="text-4xl md:text-6xl max-w-3xl leading-tight drop-shadow-md">
      Secrétaire Comptable Digital à Bordeaux
    </h1>

    <!-- Subtitle -->
    <p class="font-['Biryani'] text-lg md:text-2xl max-w-4xl leading-relaxed drop-shadow-md">
      Vous cherchez à gagner du temps et à optimiser votre gestion administrative et comptable ?
    </p>
  </div>
</section>