<template>
  <div class="new-class">
      <input v-model="name" @keydown.enter="add" type="text"
      class='form-element' placeholder="Do It">
      <button @click="add" class='form-element'>+</button>
  </div>
</template>

<script>
export default {
    data(){
        return{
            name:''
        }
    },
    methods:{
        add(){
            this.$emit('taskAdded',{name: this.name})
            this.name = ''
        }
    }
}
</script>

<style>
.new-task{
    margin:35px;
}
.form-element{
    outline:none;
    font-size: 2rem;
    border: 1px solid #ffffff;
    padding: 5px 10px 8px;
    color:#ffffff
}
input.form-element{
    width: 500px;
    background-color: rgba(255, 255, 255, 0.055);
    border-top-left-radius: 8px;
    border-bottom-left-radius: 8px;
}
button.form-element{
    border-left:none;
    background-color: #2196f3;
    border-top-right-radius: 8px;
    border-bottom-right-radius: 8px;
}
</style>