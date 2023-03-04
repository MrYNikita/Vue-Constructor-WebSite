<template>
    <section id="panel">
        <CBlockText @click.native="$emit('add-block-text')"/>
        <CBlockImage @click.native="$emit('add-block-img')"/>
        <CBlockFilm @click.native="$emit('add-block-film')"/>
    </section>
</template>

<script>
import CBlockFilm from './block/CBlockFilm.vue';
import CBlockImage from './block/CBlockImage.vue';
import CBlockText from './block/CBlockText.vue';

export default {
    name: "CTheAreaPanel",
    components: { CBlockText, CBlockImage, CBlockFilm },
}
</script>

<style scope>
#panel {
    display: flex;
    flex-direction: column;
    opacity: 0;
    position: relative;
    right: 0;
    width: 100%;
    grid-area: panel;
    border-left: 3px solid var(--color-border);
    transition: width 1s, right 1s, opacity 0.5s;
    background-color: #e9e9e9;
}

#panel:hover {
    right: 400%;
    width: 500%;
    opacity: 1;
}
</style>