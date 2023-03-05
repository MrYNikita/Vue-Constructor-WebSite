<template>
    <div
        class="elem"
        v-bind:class="{ active: isActive }"
        v-bind:style="style"
        @click="isMove = isMove ? false : true"
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
            key: NaN,
            isMove: false,
            isActive: false,
            style: {
                top: "0px",
                left: "0px",
            },
        };
    },
    methods: {
        /** @arg {MouseEvent} e */
        move(e) {
            this.style.top = e.clientY + -300 / 2 + "px";
            this.style.left = e.clientX + -200 / 2 + "px";
        },
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

.active {
    background-color: red;
}
</style>