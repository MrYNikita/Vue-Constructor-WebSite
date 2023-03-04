<template>
    <div id="backdrop">
        <CTheArea/>
        <CTheHeader/>
    </div>
</template>

<script>
import CTheArea from './area/CTheArea.vue';
import CTheHeader from './CTheHeader.vue';

export default {
    name: "CTheBackdrop",
    components: { CTheArea, CTheHeader, }
};
</script>

<style scoped>
#backdrop {
    width: 100%;
    height: 100%;
    display: grid;
    grid-template-areas:
        "header"
        "area";
    grid-template-rows: 10% auto;
}
</style>