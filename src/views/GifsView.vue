<template>
    <div>
        <div class="row-auto">
            <div class="grid grid-cols-4 gap-4 sm:grid-cols-3 my-8">
                <Search @buscar="getGifs" />
            </div>
            <br />
            <div class="grid  grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4  gap-8">
                <div v-for="gif in gifs" :key="gif.id" class="max-w-sm rounded overflow-hidden shadow-lg">
                    <Card :gif="gif" />
                </div>
            </div>

        </div>
    </div>
</template>

<script>
import Search from '../components/Search.vue';
import Card from '../components/Card.vue';
export default {
    data() {
        return {
            gifs: [],
        };
    },
    created() {
        this.getGifs();
    },
    methods: {
        async getGifs(busqueda = "pokemon") {
            const res = await fetch(
                `https://api.giphy.com/v1/gifs/search?api_key=5WSi6kQTuM14SMuQ1Zvw2jlBMXbiDM7R&q=${busqueda}&limit=16`
            );
            const { data } = await res.json();

            this.gifs = data;
        },

    },
    components: { Card, Search },
};
</script>

<style lang="scss" scoped>

</style>
