<template>
    <div class="task__item">
        <h2 class="task__header"><span class="task__header_text">Название задачи:</span> {{task.header}}</h2>
        <p class="task__description"><span class="task__description_text">Описание задачи:</span> {{task.description}}</p>
        <div class="task__info"><div>id: {{task.id}}</div><div>{{task.date}}</div></div>
        <div class="task__delete" @click="$emit('delete', task)">Удалить</div>
    </div>
</template>

<script>
    export default {
        props: {
            task: {
                type: Object,
                required: true
            }
        }
    }
</script>

<style scoped>
.task__item {
    padding: 30px;
    margin: 10px 10px 0 10px;
    border: 2px solid khaki;
}
.task__header {
    font-size: 40px;
}
.task__header_text {
    font-weight: 400;
}
.task__description {
    font-size: 30px;
}
.task__info {
    margin-top: 20px;
    display: flex;
    justify-content: space-between;
    font-size: 20px;
}
.task__delete {
    margin-top: 10px;
    padding: 10px 10px 10px 20px;
    text-decoration: underline;
    color: red;
    cursor: pointer;
    border: 1px solid red;
    width: 100px;
}
</style>