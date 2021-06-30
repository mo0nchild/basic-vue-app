<template>
    <div>
        <ul>
        <li v-for = "(item, index) in todos" 
        v-on:click = "deleteTodos(index)"
        v-bind:key = "index">Action: {{item}}<hr></li>
    </ul>
    </div>
</template>

<script>
export default{
    props: ['todos'],
    methods: {
        deleteTodos(index){
            this.$emit('delete-todo', index);
        }
    }
};
</script>

<style scoped>
    div{
        border: 2px solid white;
        border-radius: 20px;
    }
    
</style>
