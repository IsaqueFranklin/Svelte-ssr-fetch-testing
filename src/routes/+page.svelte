<script>
    import {pokemon} from "../stores/pokestore";
    console.log($pokemon)
</script>

<svelte:head>
    <title>Pokedex</title>
</svelte:head>

<div class="my-8">
    <h1 class="text-3xl font-semibold">Pokedex project</h1>
</div>

{#each $pokemon as poke}
    <div class="border border-black rounded-lg py-4 px-4 my-2">
        <p>{poke.name}</p>
    </div>
{/each}
