<template>
    <section id="area">
        <CPanel @add-block-text="addBlockText()" />
        <CTheField>
            <CElemText v-for="elem in elemText" v-bind:key="elem.id"/>
        </CTheField>
    </section>
</template>

<script>
import CTheField from './CTheField.vue';
import CElemText from './elem/CElemText.vue';
import CPanel from './panel/CPanel.vue';

export default {
    name: "CTheArea",
    data() {
        return {
            elemImg: [

            ],
            elemText: [
                {
                    key: 0,
                }
            ],
            elemFilm: [

            ],
        }
    },
    components: { CPanel, CTheField, CElemText },
    methods: {

        remove() {

            Array.from(document.querySelectorAll('.fieldElemFocus')).forEach(e => {

                e.remove();

            });
        },
        addBlockText() {
            const key = this.elemText?.at(-1)?.key;
            const elem = {

                key: key || key === 0 ? key + 1 : 0,
                title: '',
                content: '',

            };
            this.elemText.push(elem);
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
    grid-template-columns: 96% auto;
}
</style>