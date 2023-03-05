<template>
    <section id="area">
        <CPanel
            @add-block-text="addBlockText()"
            @elem-delete="e => elemsText = elemsText.filter(elem => elem !== e)"
        />
        <CTheField
            :elemsText="elemsText"
        />
    </section>
</template>

<script>
import CTheField from './CTheField.vue';
import CPanel from './panel/CPanel.vue';

export default {
    name: "CTheArea",
    data() {
        return {
            elemsText: [

            ],
        }
    },
    components: { CPanel, CTheField },
    methods: {

        remove() {

            Array.from(document.querySelectorAll('.fieldElemFocus')).forEach(e => {

                e.remove();

            });
        },
        addBlockText() {
            const key = this.elemsText?.at(-1)?.key;

            const elem = {
                key: key || key === 0 ? key + 1 : 0,
                title: '',
                content: '',
            };

            this.elemsText.push(elem);
        },

    },
}
</script>

<style scope>
#area {
    display: grid;
    grid-area: area;
    grid-template-areas:
        "field panel";
    grid-template-columns: auto 4%;
}
</style>