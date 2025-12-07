<!-- Carousel.svelte -->
<script lang="ts">
  import { onMount } from 'svelte';

  interface CarouselItem {
    title: string;
    points: string[];
  }

  const items: CarouselItem[] = [
    {
      title: 'Gestion Administrative',
      points: [
        'Saisie et mise en page de documents.',
        'Gestion des e-mails et courriers.',
        'Organisation des dossiers numériques (classement, archivage).',
        'Prise de rendez-vous et gestion d’agenda.'
      ]
    },
    {
      title: 'Assistance Comptable',
      points: [
        'Saisie et suivi des factures clients/fournisseurs.',
        'Rapprochements bancaires.',
        'Suivi des notes de frais.',
        'Préparation des documents pour l’expert-comptable.'
      ]
    },
    {
      title: 'Facturation et Suivi Clients',
      points: [
        'Émission et suivi des factures.',
        'Relance des impayés.',
        'Gestion des devis et contrats.'
      ]
    },
    {
      title: 'Digitalisation & Organisation',
      points: [
        'Mise en place d’outils collaboratifs.',
        'Optimisation des flux de travail (automatisations).',
        'Formation aux outils numériques de gestion.'
      ]
    },
    {
      title: 'Éco-Comptabilité',
      points: [
        'Solutions de comptabilité zéro papier.',
        'Sélection de logiciels éco-responsables.',
        'Audit et conseils pour réduire l’empreinte numérique.'
      ]
    }
  ];

  let currentIndex = 0;
  let container: HTMLDivElement;

  function scrollToIndex(index: number) {
    currentIndex = index;
    // wrap around for infinite effect
    const newIndex = (index + items.length) % items.length;
    const child = container.children[newIndex] as HTMLElement;
    const offset = child.offsetLeft - (container.clientWidth - child.clientWidth) / 2;
    container.scrollTo({ left: offset, behavior: 'smooth' });
  }

  function next() {
    scrollToIndex(currentIndex + 1);
  }

  function prev() {
    scrollToIndex(currentIndex - 1);
  }
</script>

<section class="w-full py-16 bg-white relative">
  <h2 style="font-family: 'Tenor Sans';" class="text-3xl md:text-4xl text-center mb-10">Un accompagnement sur mesure, sans engagement</h2>
  <!-- Carousel Container -->
  <div bind:this={container} class="overflow-x-hidden flex gap-8 px-8">
    {#each items as item}
      <div class="min-w-[300px] md:min-w-[350px] flex-shrink-0 bg-[#F5EBE0] rounded-xl p-6 flex flex-col items-center text-center">
        <h3 class="font-['Tenor Sans'] text-xl md:text-2xl mb-4">{item.title}</h3>
        <ul class="list-none space-y-2 text-base md:text-lg">
          {#each item.points as point}
            <li>{point}</li>
          {/each}
        </ul>
      </div>
    {/each}
  </div>

  <!-- Navigation Arrows using SVGs -->
  <button on:click={prev} class="absolute left-2 top-1/2 transform -translate-y-1/2 bg-gradient-to-r from-white/70 to-transparent rounded-full p-2 hover:from-white/90">
    <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 19l-7-7 7-7" />
    </svg>
  </button>
  <button on:click={next} class="absolute right-2 top-1/2 transform -translate-y-1/2 bg-gradient-to-l from-white/70 to-transparent rounded-full p-2 hover:from-white/90">
    <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7" />
    </svg>
  </button>

  <!-- Dots Indicator -->
  <div class="flex justify-center gap-3 mt-6">
    {#each items as _, i}
      <span class={`w-3 h-3 rounded-full ${i === ((currentIndex + items.length) % items.length) ? 'bg-black' : 'bg-gray-400'}`}></span>
    {/each}
  </div>
  <p style="font-family: 'Biryani';" class="text-lg md:text-xl text-center mt-12">Chaque entreprise est différente. Je m’adapte à votre rythme, à vos outils, et à vos besoins.</p>
</section>

<style>
  .scrollbar-hide::-webkit-scrollbar {
    display: none;
  }
  .scrollbar-hide {
    -ms-overflow-style: none;
    scrollbar-width: none;
  }
</style>
