<template>
    <section id="CTheArea">
        <CAreaBlockText v-for="(element, index) in elements" v-bind:key="index"/>
    </section>
</template>

<script>
import CAreaBlockText from './CAreaBlockText.vue';

export default {
    name: 'CTheArea',
    data: function() { return {

        elements: [

            {},

        ],

    }},
    props: {},
    components: {
    CAreaBlockText
},
}
</script>

<style scoped>
#CTheArea {
    overflow: hidden;
}

.backdrop {
    width: 100%;
    height: 100%;
}
</style>