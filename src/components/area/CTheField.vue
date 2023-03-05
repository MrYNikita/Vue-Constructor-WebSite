<template>
    <section id="field">
        <CElem
            v-for="elem in elemText"
            :key="elem.key"
            @elem-move="(e, d) => move(e, d)"
            @elem-delete="elem => del(elem)"
        />
    </section>
</template>

<script>
import CElem from './elem/CElem.vue';

export default {
    name: "CTheField",
    props: {

        elemText: Array,

    },
    data() {
        return {
            console,
        }
    },
    methods: {
        del(elem) {
            elem.remove();
        },
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
    position: relative;
    width: 100%;
    height: 100%;
    grid-area: field;
}
</style>