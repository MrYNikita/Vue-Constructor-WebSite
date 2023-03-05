<template>
    <CElem
        @elem-move="(e, d) => $emit('elem-move', e, d)"
        @elem-delete="$emit('elem-delete', $el)"
    >
        <div class="div_elem-content">
            <input @click="$emit('move-off')"/>
            <textarea></textarea>
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

}
.div_elem-content>input {
    background-color: red;
}
</style>