<template>
  <div>
    <input class="form-control" placeholder="New Item" v-model="inputValue"/>
        <button class="btn btn-primary" @click="handleSubmit">Submit</button>
        <ul class="list-group">
          <TodoItem
            class="list-group-item list-group-item-secondary" 
            v-for="(item,index) of array" 
            :key="index"
            :content="item"
            :index="index"
            @delete-item="handleDelete"/>
        </ul>
  </div>
</template>

<script>
import TodoItem from './components/TodoItem.vue'

export default {
  name: 'TodoList',
  components: {
    TodoItem
  },
  data: function(){
    return {
      inputValue:'',
      array: []
    }
  },
  methods: {
    handleSubmit: function(){
        this.array.push(this.inputValue);
        this.inputValue='';
    },
    handleDelete: function(index){
        this.array.splice(index,1);
    }
  }
}
</script>

<style>
  ul{
    list-style: none;
  }
</style>
