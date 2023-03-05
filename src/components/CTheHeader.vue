<template>
    <header id="header">
    </header>
</template>

<script>
export default {
    name: 'CTheHeader',
}
</script>

<style scope>
#header {
    display: flex;
    grid-area: header;
    align-items: center;
    background-color: var(--color-main);
    border-bottom: 3px solid var(--color-border);
}
</style>