<template>
    <div class="tasks">
        <h2 class="tasks__header">Список задач</h2>
        <task-item
                v-if="tasks.length > 0"
                v-for="task in tasks"
                :task="task"
                :key="task.id"
                @delete="$emit('delete', task)"
        />
        <div v-else class="tasks__empty">Добавьте новые задачи!</div>
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
.tasks__empty {
    margin: 20px;
    font-size: 30px;
    color: red;
}
</style>