<template>
    <div>
        筛选：
        <select v-model="count" @change="filterTodos(count)">
            <option value="200">200</option>
            <option value="100">100</option>
            <option value="50">50</option>
            <option value="30">30</option>
            <option value="10">10</option>
            <option value="5">5</option>
        </select>
    </div>
</template>
<script>
import { mapActions } from "vuex";
export default {
    name: 'FilterTodos',
    data(){
        return{
            count: 200
        }
    },
    methods: mapActions(["filterTodos"])
    
}
</script>
<style scoped>

</style>