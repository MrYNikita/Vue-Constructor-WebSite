<template>
    <div
        class="elem"
        v-bind:style="style"
        @click="isMove = isMove ? false : true"
        @move-off="console.log('WW')"
        @mousemove="e => isMove && $emit('elem-move', e, this)"
    >
        <slot></slot>
        <CPanel @elem-delete="$emit('elem-delete', $el)"/>
    </div>
</template>

<script>
import CPanel from './panel/CPanel.vue';

export default {
    name: "CElem",
    data() {
        return {
            console,
            key: NaN,
            isMove: this.pIsMove,
            isActive: false,
            style: {
                top: "0px",
                left: "0px",
            },
        };
    },
    methods: {
    },
    components: { CPanel }
}
</script>

<style scope>
.elem {
    width: 200px;
    height: 300px;
    display: grid;
    grid-template-areas:
        "content"
        "panel";
    grid-template-rows: 90% auto;
    position: absolute;
    transition: left 1s, top 1s;
    transition: background-color 0.25s;
    border-radius: 12px;
    border: 3px solid #2c2c2c;
    background-color: #fff;
}
.elem:hover {
    background-color: #21ffad;
}
</style>