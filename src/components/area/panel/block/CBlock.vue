<template>
    <div class="panelBlock">
        <slot></slot>
    </div>
</template>

<script>
export default {
    name: 'CBlock',
}
</script>

<style scope>
.panelBlock {
    color: black;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: 10em;
    transition: background-color 0.5s;
    border-bottom: 3px solid #565656;
    background-color: #00000000;
}
.panelBlock:hover {
    background-color: #21ffad;
}
</style>