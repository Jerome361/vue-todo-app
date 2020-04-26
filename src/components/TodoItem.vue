<template>
    <div class="todo-item" v-bind:class="{'is-complete': todo.completed}">
        <!-- :class="[todo.name === 'Jerome' ? '!is-complete':'is-complete']" -->
        <p>
            <input type="checkbox" v-on:change="markComplete">
            {{todo.title}}
            <button @click="$emit('del-todo', todo.id)">X</button>
        </p>
    </div>
</template>

<script>
export default {
    name: "TodoItem",
    props: ['todo'],
    methods: {
        markComplete() {
           return this.todo.completed = !this.todo.completed
        }
    }
    
}
</script>

<style scoped>
.todo-item {
  background: #f4f4f4;
  padding: 10px;
  border-bottom: 1px #ccc dotted
}
.is-complete {
    color: #ff0000;
  text-decoration: line-through;
}
.del {
  background: #ff0000;
}

</style> 