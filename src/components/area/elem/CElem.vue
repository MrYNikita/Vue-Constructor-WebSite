<template>
    <div
        class="elem"
        v-bind:class="{ active: isActive }"
        v-bind:style="style"
        @click="isMove = isMove ? false : true"
        @mousedown="isMove = isActive ? true : false"
        @mouseup="isMove = false"
        @mousemove="e => isMove && move(e)"
        @mouseout="() => sActive = false">
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
                left: '0px',
                top: '0px',
            },
        }
    },
    methods: {
        /** @arg {MouseEvent} e */
        move(e) {
            this.style.top = e.offsetY + 'px';
            this.style.left = e.offsetX + 'px';
        },
        active() {
            this.isActive = true;
        },
        unactive() {
            this.isActive = false;
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
    background-color: #fff;
}

.active {
    background-color: red;
}
</style>