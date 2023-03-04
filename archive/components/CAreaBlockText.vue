<template>
    <div id="CAreaBlockText">
        <CAreaBlockPanel/>
        <input class="inputTitle" placeholder="Заголовок"/>
        <textarea class="inputContent" placeholder="Текст"></textarea>
    </div>
</template>

<script>
import CAreaBlockPanel from './CAreaBlockPanel.vue';


export default {
    name: 'CAreaBlockText',
    components: {
    CAreaBlockPanel
}
}
</script>

<style scoped>
#CAreaBlockText {
    width: 16em;
    height: 8em;
    display: grid;
    align-items: center;
    grid-template-areas:
        "title panel"
        "text panel";
    border-radius: 10px;
    grid-template-rows: 20% auto;
    grid-template-columns: 90% auto;
    background-color: #ffffff;


    /* DEV */
    position: absolute;
    top: 100px;
    left: 100px;
}
#CAreaBlockText>.inputContent,.inputTitle{
    margin-top: 1em;
    margin-inline: 5%;
}
.inputTitle {
    grid-area: title;
}
.inputContent {
    width: auto;
    height: 70%;
    resize: none;
    grid-area: text;
}
</style>