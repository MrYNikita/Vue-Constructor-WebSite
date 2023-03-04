<template>
    <div id="CThePanel">
        <CThePanelElementText />
        <CThePanelElementCard />
        <CThePanelElementFilm />
    </div>
</template>

<script>

import CThePanelElementText from './CThePanelElementText.vue';
import CThePanelElementCard from './CThePanelElementCard.vue';
import CThePanelElementFilm from './CThePanelElementFilm.vue';

export default {
    name: 'CThePanel',
    props: {},
    components: {
        CThePanelElementText,
        CThePanelElementCard,
        CThePanelElementFilm,
    },
}
</script>

<style scoped>
#CThePanel {
    display: flex;
    grid-area: panel;
    border-width: 0;
    border-color: #46ffb2;
    border-style: solid;
    flex-direction: column;
    background-color: #e9e9e9;
    border-left-width: 3px;
}

#CThePanel>.CThePanelElement {
    height: 10em;
    cursor: pointer;
    display: flex;
    align-items: center;
    user-select: none;
    border-width: 0;
    border-bottom: 1px solid #565656;
    flex-direction: column;
    justify-content: center;
}
#CThePanel>.CThePanelElement:hover {
    background-color: #57937a59;
}
</style>