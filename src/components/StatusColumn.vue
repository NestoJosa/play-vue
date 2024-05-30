<template> 
    <div class="status-column">
        <h2>{{ title }}</h2>
        <!-- Loop through cards and render -->
        <ul>
            <li v-for="card in cardsList" v-bind:key="card.id">
                <TaskCard 
                    v-bind:title="card.title"
                    v-bind:description="card.description"
                />
            </li>
        </ul>
    </div>
</template>

<script>
import TaskCard from './TaskCard.vue';

export default {
    name: 'StatusColumn',
    components: {
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
