<script lang='ts'>
    import {pokemon} from "../stores/pokestore";
    import PokemanCard from '../components/pokeCard.svelte';

    let searchTerm = "";
    let filteredPokemon: any[];

    //Isso aqui é a reatividade que pode faz com que a qualquer mudança de algo no código dispare esse trambolho aí embaixo
    //Acredito que também possa ser utilizado como: $variávelEspecífica : {}
    //Tipo um useEffect do react.
    $: {
        //console.log(searchTerm)
        if(searchTerm){
            filteredPokemon = $pokemon.filter(pokeman => pokeman.name.toLowerCase().includes(searchTerm.toLowerCase()));
        } else {
            filteredPokemon = [...$pokemon]
        }
    }
</script>

<svelte:head>
    <title>Pokedex</title>
</svelte:head>

<div class="my-8">
    <h1 class="text-3xl font-semibold">Pokedex project</h1>
</div>

<input class="w-full rounded-xl text-lg p-4 border-2 border-gray-200" type="text" bind:value={searchTerm} placeholder="Saerch Pokemon" />

<div class="grid md:grid-cols-3 grid-cols-1 gap-4">
    {#each filteredPokemon as poke}
        <PokemanCard pokeman={poke} />
    {/each}
</div>
