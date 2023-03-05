<template>
    <div class="elemPanel">
        <button class="elemPanelButtonClose"
            @click="$emit('elem-delete')"
        >
        X</button>
    </div>
</template>

<script>
export default {
    name: 'CPanel',
}
</script>

<style scope>
.elemPanel {
    grid-area: panel;
}
.elemPanel>button {
    width: 30%;
    height: 90%;
    transition: background-color 0.25s;
    border-radius: 3px;
    background-color: #d5d5d5;
}
.elemPanelButtonClose:hover {
    background-color: #ff8080;
}
</style>