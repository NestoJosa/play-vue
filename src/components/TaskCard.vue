<template>
    <div class="task-card">
        <h3>{{ title }}</h3>
        <p>{{ description }}</p>
    </div>
</template>

<script>

export default {
    name: 'TaskCard',
    props: {
        title: {
            type: String,
            required: true,
        },
        description: {
            type: String,
            required: true,
        }
    },
}

</script>

<style scoped>
.task-card {
    padding: 10px;
    margin: 5px;
    background-color: #f4f4f4;
    border: 1px solid #ddd;
    border-radius: 5px;
}
</style>