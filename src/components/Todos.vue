<template>
  <div>
    <h2>待办事项</h2> 
    <div class="todos">
        <div v-bind:key="index" v-for="(todo,index) in allTodos" v-bind:class="{'is-complete':todo.completed}" class="todo">
            {{ todo.title }}
            <br>
            {{ todo.completed }}
            <div class="deleteicon">
            <!-- <svg t="1571739434439" class="icon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="7296" width="40" height="40"><path d="M656 288h144a16 16 0 0 1 16 16v16a16 16 0 0 1-16 16h-48v496a16 16 0 0 1-16 16H288a16 16 0 0 1-16-16V336h-48a16 16 0 0 1-16-16v-16a16 16 0 0 1 16-16h144v-80a16 16 0 0 1 16-16h256a16 16 0 0 1 16 16v80z m-48 0v-48H416v48h192z m32 48H320v464h384V336h-64z m-208 112h16a16 16 0 0 1 16 16v192a16 16 0 0 1-16 16h-16a16 16 0 0 1-16-16V464a16 16 0 0 1 16-16z m144 0h16a16 16 0 0 1 16 16v192a16 16 0 0 1-16 16h-16a16 16 0 0 1-16-16V464a16 16 0 0 1 16-16z" p-id="7297" fill="#2c2c2c"></path></svg> -->
            
            <i @click="changeCompleted(todo)" class="fas fa-check" id="check"></i>
            <i @click="deleteTodo(todo.id)" class="fas fa-trash-alt" id="delete"></i>
            </div>
        </div>
    </div>
  </div>
</template>

<script>
import { mapGetters,mapMutations,mapActions } from "vuex";
export default {
    name: "Todos",
    computed: mapGetters(["allTodos"]),
    methods: {
        ...mapActions(["fetchTodos","deleteTodo"]),
        changeCompleted(todo){
            console.log(todo.completed);
            console.log(todo.title);
            // TODO: 完成点击对勾改变头都的状态
            this.$store.commit("");
            this.todo.completed = !this.todo.completed;
        }
    },
    created(){
        this.fetchTodos();
    }
};
</script>

<style scoped>
h2 {
    color: rgb(160, 136, 136);
    text-align: center;
    font-size: 30px;
}
.deleteicon {
    display: inline-block;
    margin-right: 5px;
}
.todos {
    display: grid;
    grid-template-columns: repeat(3,1fr);
    grid-gap: 1rem;
}
.todo {
    font-family: 'Muli', sans-serif;
    font-size: 20px;
    border: 1px solid #ccc;
    background-color: #41b883;
    padding: 1rem;
    margin: 10px 30px;
    border-radius: 9px;
    text-align: center;
    position: relative;
    cursor: pointer;
    color: white;
}
.is-complete {
    background-color: rgb(59, 66, 112);
}
#check {
    position: absolute;
    top: 10px;
    right: 10px;
    color: #fff;
    padding: 10px;
    cursor: pointer;
}
#check:hover {
    background-color: lightslategray;
}
#delete:hover {
    background-color: lightslategray;
}
#delete {
    position: absolute;
    bottom: 10px;
    padding: 10px;
    right: 10px;
    color: #fff;
    cursor: pointer;
}
</style>>