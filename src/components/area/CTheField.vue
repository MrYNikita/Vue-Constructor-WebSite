<template>
    <section id="field">
        <CElemText
            v-for="text in elemsText"
            :key="'text' + text.key"
            @move-off="console.log('WW')"
            @elem-move="(e, d) => move(e, d)"
            @elem-delete="elem => del(elem)"
        />
        <CElemFilm
            v-for="film in elemsFilm"
            :key="'film' + film.key"
            @elem-move="(e, d) => move(e, d)"
            @elem-delete="elem => del(elem)"
        />
    </section>
</template>

<script>
import CElemFilm from './elem/CElemFilm.vue';
import CElemText from './elem/CElemText.vue';

export default {
    name: "CTheField",
    props: {
        elemsText: Array,
        elemsFilm: Array,
    },
    data() {
        return {
            console,
        }
    },
    methods: {
        del(elem) {
            elem.remove();
            this.$emit('elem-delete', elem.key);
        },
        /**
         * @arg {CElem} elem
         * @arg {MouseEvent} even
        */
        move(even, elem) {

            if ([HTMLInputElement, HTMLTextAreaElement, HTMLParagraphElement].find(c => even.target instanceof c)) {

                elem.isMove = false;
                return;

            }

            elem.style.top = parseInt(elem.style.top) + even.offsetY - 20 + 'px';
            elem.style.left = parseInt(elem.style.left) + even.offsetX - 15 + 'px';
        },
    },
    components: { CElemText, CElemFilm }
}
</script>

<style scope>
#field {
    position: relative;
    width: 95%;
    height: 100%;
    grid-area: field;
}
</style>