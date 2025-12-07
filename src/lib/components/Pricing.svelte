<script lang="ts">
  interface Plan {
    title: string;
    details: string[];
    price: string;
    description: string;
  }

  const plans: Plan[] = [
    {
      title: "Formule Mini",
      details: ["10h/mois", "Sans engagement", "À distance", "Sur site", "Reportable"],
      price: "Forfait : 350€/mois",
      description: "Pour les besoins ponctuels ou les petites structures"
    },
    {
      title: "Formule Essentiel",
      details: ["20h/mois", "Sans engagement", "À distance", "Sur site", "Reportable"],
      price: "Forfait : 680€/mois",
      description: "Idéal pour une assistance régulière"
    },
    {
      title: "Formule Confort",
      details: ["30h/mois", "Sans engagement", "À distance", "Sur site", "Reportable"],
      price: "Forfait : 990€/mois",
      description: "Pour un accompagnement complet et continu"
    }
  ];
</script>

<section class="w-full py-16 bg-[#F5EBE0]" id="pricing">
  <h2 class="text-3xl md:text-4xl text-center mb-12 font-['Tenor Sans']">Tarifs</h2>
  
  <div class="flex flex-col md:flex-row justify-center items-stretch gap-8 px-4 md:px-10">
    {#each plans as plan}
      <div class="bg-white rounded-xl p-6 flex-1 max-w-sm flex flex-col items-center text-center">
        <h3 class="font-['Tenor Sans'] text-xl md:text-2xl mb-4">{plan.title}</h3>
        <ul class="list-none space-y-1 mb-4">
          {#each plan.details as detail}
            <li>{detail}</li>
          {/each}
        </ul>
        <p class="font-bold mb-2">{plan.price}</p>
        <p class="text-sm text-gray-700">{plan.description}</p>
      </div>
    {/each}
  </div>
</section>
