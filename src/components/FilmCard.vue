<template>
    <div>
        <div class="card p-2 text-center">
            <div class="card-body">
                <h5 class="card-title">{{titolo}}</h5>
                <p class="card-text">{{titoloOriginale}}</p>
                <p class="card-text">{{lingua}}</p>
                <p class="card-text">{{votoMedio}}</p>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'FilmCard',

    props: ['lingua', 'titolo', 'titoloOriginale', 'votoMedio'],
}

</script>

<style>

</style>