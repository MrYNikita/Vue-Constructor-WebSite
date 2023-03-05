<template>
    <CElem
        @elem-move="(e, d) => $emit('elem-move', e, d)"
        @elem-delete="$emit('elem-delete', $el)"
    >
        <div>
            <p v-for="(film, index) in films" v-bind:key="index">
                {{ 1 }}
            </p>
        </div>
    </CElem>
</template>

<script>
import CElem from './CElem.vue';
import axios from 'axios';

export default {
    name: "CElemFilm",
    data() {
        return {
            films: this.getFilms(),
        }
    },
    components: { CElem },
    methods: {
        async getFilms() {
            const films = await axios('https://6404e70deed195a99f7865db.mockapi.io/film/films');

            this.films = films.data.splice(0, 5);
        },
    }
}
</script>

<style scope>
.elem_film-list {
    display: flex;
    flex-direction: column;
}
</style>