<template>
    <div id="CBackdrop">
        <CThePanel/>
        <CTheArea/>
        <CTheHeader/>
    </div>
</template>

<script>
import CThePanel from './CThePanel.vue';
import CTheArea from './CTheArea.vue';
import CTheHeader from './CTheHeader.vue';

export default {
    name: 'CBackdrop',
    props: {

    },
    components: {
    CThePanel,
    CTheHeader,
    CTheArea
},
}
</script>

<style scoped>
#CBackdrop {
    width: 100%;
    height: 100%;
    display: grid;
    grid-template-areas:
        "header header"
        "area panel";
    grid-template-rows: 10% auto;
    grid-template-columns: 80% auto;
}
</style>