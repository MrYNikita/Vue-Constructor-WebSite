<template>
    <section id="field">
        <CElem
            v-for="elem in elems"
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
        elems: Array,
    },
    data() {
        return {

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
    width: 95%;
    height: 100%;
    grid-area: field;
}
</style>