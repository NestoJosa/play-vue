<template> 
    <div class="status-column">
        <h2>{{ title }}</h2>
        <!-- Loop through cards and render -->
        <draggable
            v-bind:list="cardsList"
            group="cards"
            itemKey="id"
            @update:modelValue="emitCardChange"
            >
            <template #item="{ element }">
                <TaskCard 
                    v-bind:title="element.title"
                    v-bind:description="element.description"
                />
            </template>
        </draggable>
    </div>
</template>

<script>
import draggable from 'vuedraggable';
import TaskCard from './TaskCard.vue';

export default {
    name: 'StatusColumn',
    components: {
        draggable,
        TaskCard,
    },
    props: {
        title: {
            type: String,
            required: true
        },
        cardsList: {
            type: Array,
            required: true
        }
    },
    methods: {
        emitCardChange() {
            this.$emit('update:cardsList', this.cardsList);
        },

    }
};
</script>

<style scoped>
.status-column {
    padding: 10px;
    margin: 10px;
    border: 1px solid #ddd;
    border-radius: 5px;
    width: 300px;
    background-color: #f9f9f9;
}

ul {
    padding-left: 0;
}

li {
    list-style-type: none;
}
</style>
