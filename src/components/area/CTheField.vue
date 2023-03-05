<template>
    <section id="field">
        <CElem v-for="elem in elemText" v-bind:key="elem.id" @elem-move="(e, d) => move(e, d)"/>
    </section>
</template>

<script>
import CElem from './elem/CElem.vue';

export default {
    name: "CTheField",
    props: {

        elemText: Array,

    },
    methods: {
        /**
         * @arg {CElem} elem
         * @arg {MouseEvent} even
        */
        move(even, elem) {
            elem.style.top = parseInt(elem.style.top) + even.offsetY - 300 / 2 + 'px';
            elem.style.left = parseInt(elem.style.left) + even.offsetX - 200 / 2 + 'px';
        },
    },
    components: { CElem }
}
</script>

<style scope>
#field {
    grid-area: field;
}
</style>