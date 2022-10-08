<script>
  export let data;
  const recettes = data.recettes;
</script>

<section class="recettes">
  {#each recettes as item, index (item.name)}
    <article>
      <div>
        <h2>
          <a data-sveltekit-prefetch href="/recettes/{index}">{item.name}</a>
        </h2>
        <p>
          ⏱ {item.totalTime} min 👨‍🍳 {[
            "",
            "Très Facile",
            "Facile",
            "Moyenne",
            "Difficile",
          ][item.difficulty || 0]} € {["", "Bon marché", "Moyen", "Assez cher"][
            item.budget || 0
          ]} 😋 {item.people} Personnes
        </p>
      </div>
      <img src={item.image} alt={item.name} />
    </article>
  {/each}
</section>
