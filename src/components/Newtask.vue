<template>
  <div >
      
      <form @submit.prevent="onSubmit">
        Name:
        <input type="text" v-model="title1">
        Email:
        <input type="text" v-model="title2">
          <b-form-select v-model="selected" :options="options" size="sm" class="mt-3"></b-form-select>
          <button type="submit">Add</button>
          
    </form>
    
  </div>
</template>

<script>  
  export default {
      data(){
          return{
            
              title1: '',
              title2:'',
              selected: null,
              options: [
                    {value:null,text:'Select'},
                    {text:'Chairman'},
                    {text:'Vice Chairman'},
                    {text:'President'},
                    {text:'Vice-President'},
                    {text:'Senior Advisor'},
                    {text:'General Manager'},
                ]
              
          }
      },
      methods: {
        onSubmit() {
           if (this.title1.trim()) {
               const newTodo = {
                   id: Date.now(),
                   title1: this.title1,
                   completed: false
               }
               this.$emit('add-todo', newTodo)
               this.title1=""
           }
        },    
    }
  }
</script>

<style lang="scss" scoped>
form {
	margin-top:3rem;
	display:flex;
	flex-wrap:wrap;
}
form input {
	flex-grow:1;
	border:none;
	background:#f7f1f1;
	padding:0 1.5em;
	font-size:initial;
    padding: 5px 0px 20px 0px;
    line-height: 10px;
}
form button {
	padding:0 1.3rem;
	border:none;
	background:#007EFC;
    border-radius: 5px;
	color:white;
	text-transform:uppercase;
	font-weight:bold;
	border:1px solid rgba(255,255,255,.3);
	margin-left:5px;
	cursor:pointer;
	transition:background .2s ease-out;
}
</style>