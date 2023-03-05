<template>
    <CElem
        @elem-move="(e, d) => $emit('elem-move', e, d)"
        @elem-delete="$emit('elem-delete', $el)"
    >
        <div class="div_elem-content">
            <input class="div_elem-content__title" @click="$emit('move-off')"/>
            <textarea class="div_elem-content__text"></textarea>
        </div>
    </CElem>
</template>

<script>
import CElem from './CElem.vue';

export default {
    name: "CElemText",
    mixins: [CElem],
    components: { CElem }
}
</script>

<style scope>
.div_elem-content {
    display: flex;
    flex-direction: column;
    align-items: center;
}
.div_elem-content>* {
    margin-top: 5%;
    border-radius: 2px;
    background-color: #dbdbdb;
}
.div_elem-content__text {
    height: 80%;
}
</style>