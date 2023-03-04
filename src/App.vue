<template>
    <div id="app">
        <CTheBackdrop/>
    </div>
</template>

<script>
import CTheBackdrop from './components/CTheBackdrop.vue';


export default {
    name: 'App',
    components: {
    CTheBackdrop,
}
}
</script>

<style>
:root {
    --color-main: #1a9258;
    --color-border: #46ffb2;
}
* {
    margin: 0;
    padding: 0;
    resize: none;
    border: none;
    outline: none;
    box-sizing: border-box;
    text-align: center;
    user-select: none;
    overflow: hidden;
    font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
}
html {
    background-color: #2c2c2c;
}
html, body, #app {
    width: 100%;
    height: 100%;
}
svg {
    fill: #4cab7c;
}
</style>
