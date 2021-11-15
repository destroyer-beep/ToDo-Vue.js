<template>
    <form @submit.prevent class="form">
        <label class="form__label" for="header">Название</label>
        <input
                v-model="task.header"
                class="form__header"
                id="header"
                name="header"
                type="text"
                placeholder="Введите название задачи"
        >
        <label class="form__label" for="description">Описание</label>
        <input
                v-model="task.description"
                class="form__description"
                id="description"
                name="description"
                type="text"
                placeholder="Введите описание задачи"
        >
        <button class="task__button" @click="createTask">
            Добавить задачу
        </button>
    </form>
</template>

<script>
    export default {
        data() {
            return {
                task: {
                    header: '',
                    description: ''
                }
            }
        },
        methods: {
            createTask() {
                if(this.task.header !== '' && this.task.description !== '') {
                    this.task.id = Math.floor(Math.random() * 10**4);
                    this.task.date = new Date();
                    this.$emit('create', this.task);
                    this.task = {
                        header: '',
                        description: ''
                    }
                }
            }
        }
    }
</script>

<style scoped>
.form {
    padding: 20px;
    border-top: 5px solid darkgoldenrod;
    border-bottom: 5px solid darkgoldenrod;
    display: flex;
    flex-direction: column;
}
.form__label {
    margin: 25px 0 10px 0;
    font-size: 30px;
}
input {
    width: 500px;
    height: 50px;
    padding: 5px;
    border: 1px solid darkgoldenrod;
    font-size: 20px;
}
.task__button {
    padding: 10px;
    width: 10%;
    margin-top: 40px;
    background-color: white;
    font-size: 20px;
    border: 1px solid darkgoldenrod;
}
</style>