<template>
    <section id="field">
        <CElemText
            v-for="elem in elemsText"
            :key="elem.key"
            @move-off="console.log('WW')"
            @elem-move="(e, d) => move(e, d)"
            @elem-delete="elem => del(elem)"
        />
    </section>
</template>

<script>
import CElemText from './elem/CElemText.vue';

export default {
    name: "CTheField",
    props: {
        elemsText: Array,
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

            if ([HTMLInputElement, HTMLTextAreaElement].find(c => even.target instanceof c)) {

                elem.isMove = false;
                return;

            }

            elem.style.top = parseInt(elem.style.top) + even.offsetY - 300 / 2 + 'px';
            elem.style.left = parseInt(elem.style.left) + even.offsetX - 200 / 2 + 'px';
        },
    },
    components: { CElemText }
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