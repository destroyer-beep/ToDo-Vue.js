<template>
    <div class="tasks">
        <h2 class="tasks__header">Список задач</h2>
        <task-item
                v-for="task in tasks"
                :task="task"
        />
    </div>
</template>

<script>
    import TaskItem from '@/components/taskItem'
    export default {
        components: {
            TaskItem
        },
        props: {
            tasks: {
                type: Array,
                required: true
            }
        }
    }
</script>

<style scoped>
.tasks__header {
    width: 10%;
    margin: 20px auto;
    font-size: 30px;
}
</style>