<template>
    <div id="CAreaBlockPanel">
        <button class="buttonClose"></button>
        <div class="divMove" v-on:mousedown="e => {

            const f = () => {

                console.log('WW');

            };

            e.target.addEventListener('mousemove', f);

        }"></div>
        <div class="setColor">
            <input type="color"/>
        </div>
    </div>
</template>

<script>

export default {
    name: 'CAreaBlockPanel',
    data() {

        return {

            top: 0,
            left: 0,
            console: console,

        };

    },

}
</script>

<style scoped>
#CAreaBlockPanel {
    width: 100%;
    height: 100%;
    display: flex;
    grid-area: panel;
    flex-direction: column;
    background-color: #b6b6b6;
    border-top-right-radius: inherit;
    border-bottom-right-radius: inherit;
}
#CAreaBlockPanel>*{
    width: 100%;
    height: 100%;
    border: none;
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: inherit;
}
#CAreaBlockPanel>*:hover{
    background-color: #57937a;
}
.buttonClose {
    border-top-right-radius: inherit;
}
.setColor {
    border-bottom-right-radius: inherit;
}
.setColor > * {
    border: none;
    width: 80%;
    outline: none;
    overflow: hidden;
}
</style>