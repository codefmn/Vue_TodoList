<template>
  <div>
    <li @click="handleClick"> {{index+1}}: {{content}} </li>
  </div>
</template>

<script>
export default {
  name: 'TodoItem',
  props: ['content','index'],
  methods: {
    handleClick: function(){
        this.$emit('delete-item',this.index);
    }
  }
}
</script>

<style scoped>

</style>
