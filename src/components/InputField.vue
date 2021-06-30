<template>
    <div>
        <input type="text" v-model = "todoText" maxlength="20">
        <button v-on:click = "addTodos">ADD</button>
    </div>
</template>

<script>
export default {
    data(){
        return {
            todoText: '',
        };
    },
    methods: {
        addTodos: function(){
            if(this.todoText == '')return ;

            this.$emit('add-todos', this.todoText);
            this.todoText = '';
        }
    }
}

</script>

<style scoped>
    input{
        background-color: #222222;
        border: 2px solid white;
        border-radius: 20px;
        font-size: 30px;
        color: white;
    }
    button{
        position: relative;
        right: -10px;

        background-color: #222222;
        border: 2px solid white;
        border-radius: 20px;
        font-size: 30px;
        color: white;
    }
</style>