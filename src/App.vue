<template>

<title-page/>

<task-form @create="createTask"/>

<task-list
        :tasks="tasks"
        @delete="deleteTask"
/>

</template>

<script>
    import TitlePage from '@/components/titlePage';
    import TaskForm from '@/components/taskForm';
    import TaskList from '@/components/taskList';

    export default {
        components: {
          TitlePage, TaskForm, TaskList
        },
        data() {
            return {
                tasks: []
            }
        },
        methods: {
            createTask(task) {
                this.tasks.push(task);
            },
            deleteTask(task) {
                this.tasks = this.tasks.filter(item => item.id !== task.id);
            }
        }
    }
</script>

<style>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
</style>