<template>
    <header id="header">
        <div id="switch">
            <input type="radio" />
            <p>Просмотр</p>
        </div>
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
#switch {
    width: 40%;
    display: flex;
}
#switch>* {
    margin-left: 2%;
}
</style>