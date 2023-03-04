<template>
    <section id="field">
        <slot></slot>
    </section>
</template>

<script>
export default {
    name: 'CTheField',
}
</script>

<style scope>
#field {
    grid-area: field;
}
</style>