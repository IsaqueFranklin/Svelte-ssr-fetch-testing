<script>
    import "../app.css";
    import Nav from '../components/nav.svelte'
</script>

<div class="mx-auto px-8">
    <Nav />
    <div class="max-w-5xl justify-center mx-auto">
        <slot />
    </div>
</div>