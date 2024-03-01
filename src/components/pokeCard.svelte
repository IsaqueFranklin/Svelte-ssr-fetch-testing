<script>
    export let pokeman;
</script>

<div class="border border-gray-700 bg-gray-100 shadow-sm hover:shadow-md rounded-xl my-4 py-4 px-4">
    <a class="p-6 text-center flex flex-col items-center" href={`/pokemon/${pokeman.id}`}>
        <img class="h-40 w-40" src={pokeman.image} alt={pokeman.name} />
        <h2 class="text-xl">{pokeman.id}. {pokeman.name}</h2>
    </a>
</div>