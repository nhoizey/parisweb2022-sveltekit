<script>
  import Form from "./Form.svelte";
  import Imc from "./Imc.svelte";

  const name = "Nicolas";
  let historique = [];

  function sauvegarderIMC(event) {
    historique = [...historique, event.detail];
  }
</script>

<h1>Calculateur IMC</h1>
<p>Bonjour {name} ! Calculez votre IMC (Indice de Masse Corporelle)</p>
<Form on:sauvegarder={sauvegarderIMC} />
<Imc />

<h3>Evolution de l'IMC</h3>
<ul>
  {#each historique as item, index}
    <li>{index + 1}: {item.toFixed(2)}</li>
  {:else}
    <li>Pas encore d'historique</li>
  {/each}
</ul>
