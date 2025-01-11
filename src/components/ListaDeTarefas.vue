<script setup>
const props = defineProps(['tarefas'])
</script>

<template>
    <ul class="list-group mt-4" v-if="tarefas.length > 0" > 
        <li class="list-group-item" v-for="tarefa in props.tarefas">
            <input @change="evento => tarefa.finalizada = evento.target.checked" :checked="tarefa.finalizada"
                :id="tarefa.titulo" type="checkbox">
            <label :class="{ done: tarefa.finalizada }" class="ms-3" for="tarefa.titulo">
                {{ tarefa.titulo }}
            </label>
        </li>
    </ul>
    <p v-else>Nenhuma tarefa pendente!</p>
</template>

<style scoped>
.done {
    text-decoration: line-through;
}

p {
    color: red;
    font-size: 16px;
    font-style: italic;
    font-weight: bold;
    padding: 8px;
}
</style>

