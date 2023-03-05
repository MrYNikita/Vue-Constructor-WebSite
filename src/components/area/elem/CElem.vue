<template>
    <div
        class="elem"
        v-bind:class="{ active: isActive }"
        v-bind:style="style"
        @click="isMove = isMove ? false : true"
        @mousemove="e => isMove && $emit('elem-move', e, this)"
    >
        <slot></slot>
    </div>
</template>

<script>
export default {
    name: 'CElem',
    data() {
        return {
            isMove: false,
            isActive: false,
            style: {
                top: '0px',
                left: '0px',
            },
        }
    },
    methods: {
        /** @arg {MouseEvent} e */
        move(e) {
            this.style.top = e.clientY + -300 / 2 + 'px';
            this.style.left = e.clientX + -200 / 2 + 'px';
        },
    },
}
</script>

<style scope>
.elem {
    transition: left 1s, top 1s;
    width: 200px;
    height: 300px;
    border-radius: 12px;
    position: relative;
    transition: background-color 0.25s;
    background-color: #fff;
}
.elem:hover {
    background-color: #21ffad;
}

.active {
    background-color: red;
}
</style>