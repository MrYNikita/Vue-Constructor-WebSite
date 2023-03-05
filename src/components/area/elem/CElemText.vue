<template>
    <CElem
        @elem-move="(e, d) => $emit('elem-move', e, d)"
        @elem-delete="$emit('elem-delete', $el)"
    >
        <div class="div_elem-content">
            <input/>
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
</style>