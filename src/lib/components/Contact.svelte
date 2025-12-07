<script lang="ts">
    import mailIcon from '$lib/assets/icons/mail.svg';
    import sendIcon from '$lib/assets/icons/send.svg';
  let nom = '';
  let prenom = '';
  let email = '';
  let telIndicatif = '+33';
  let tel = '';
  let commentaire = '';

  function handleSubmit() {
    // Ici tu peux ajouter la logique d'envoi du formulaire
    console.log({ nom, prenom, email, telIndicatif, tel, commentaire });
  }
</script>

<section class="w-full py-16 bg-white" id="contact">
  <h2 class="text-3xl md:text-4xl text-center mb-12 font-['Tenor Sans']">Contact</h2>

  <form on:submit|preventDefault={handleSubmit} class="max-w-3xl mx-auto flex flex-col gap-6 px-4 md:px-0">
    <!-- Nom et Prénom -->
<div class="flex flex-col md:flex-row">
  <input 
    type="text" 
    placeholder="Nom" 
    bind:value={nom} 
    class="flex-1 border border-black border-r-0 p-3 placeholder-gray-400 rounded-none"
  />
  <input 
    type="text" 
    placeholder="Prénom" 
    bind:value={prenom} 
    class="flex-1 border-t border-b border-r border-black p-3 placeholder-gray-400 rounded-none"
  />
</div>


    <!-- Email -->
<div class="flex items-center border border-black p-1">
    <img src={mailIcon} alt="Email" class="h-6 w-6 mr-1 ml-3" />
  <input 
    type="email" 
    placeholder="Adresse email" 
    bind:value={email} 
    class="flex-1 border-none margin-none placeholder-gray-400 focus:outline-none"
  />
</div>


    <!-- Téléphone -->
<div class="flex">
  <input 
    type="text" 
    bind:value={telIndicatif} 
    class="w-15 border border-black border-r-0 p-3 placeholder-gray-400 rounded-none" 
  />
  <input 
    type="tel" 
    placeholder="Numéro de téléphone" 
    bind:value={tel} 
    class="flex-1 border-t border-b border-r border-black p-3 placeholder-gray-400 rounded-none"
  />
</div>

    <!-- Commentaire -->
    <textarea 
      placeholder="Votre message..." 
      bind:value={commentaire} 
      class="w-full border border-black p-3 placeholder-gray-400 resize-none h-32"
    ></textarea>

    <!-- Bouton Envoyer -->
    <button 
      type="submit" 
      class="flex items-center justify-center gap-2 border hover:bg-gray-100 p-3 text-black transition duration-200"
    >
        <img src={sendIcon} alt="Envoyer" class="h-5 w-5" />
        <span>Envoyer</span>
    </button>

  </form>
</section>
