<template>
<div class="todoList">
    <div class="addTask"> 
      <label for="todo"></label>
      <input v-model="newTask" @click="showAdd" type="text" name="todo" placeholder="Input task">
      <button @click="addTask" v-if="show">Add</button>
    </div>  

 <div class="selectedItems" v-if="show">

   <ul>
     <li v-for="task in allTasks" 
     v-bind:todo="task"
     v-bind:key="task"
     ><a href="">{{task}}</a> <button @click="removeTask(task)">X</button></li>
   </ul> 
 </div>


</div>
</template>

<script>
export default {
  name: 'todo',
  props:['todo'],
 data: function () {
    return {
      show:false,
     newTask:"",
     allTasks:[]
    }
  },
  methods:{
    addTask(){
      this.allTasks.push(this.newTask);
      this.newTask="";
      console.log(this.allTasks)
   
    },
    removeTask(task){
      var index = this.allTasks.indexOf(task);
      this.allTasks.splice(index,1);
    },
     showAdd(){
      this.show=true
    }

  },

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped  lang='scss'>

.todoList{
  // border:1px solid black;
  width:50%;
  margin:0 auto;
  background-color: #D0CCD0;
  padding-top:10px;
  border-radius: 20px;
.addTask{
  
    input{
    padding:15px;
    border-radius: 15px;
    border:none;
    width:50%;
  }
  ::placeholder{
    background-color: #FBFCFF;
    color:#274156;
    font-weight: bolder;
    font-size: 14px;
  }
  button{
    background-color: #274156;
    color:#FBFCFF;
    padding:15px 24px;
    margin:10px;
    font-weight: bolder;
    border-radius: 15px;
    font-size: 14px;
    line-height: 14px;
    cursor: pointer;
  }
}
.selectedItems{
  ul{
    background-color: #274156;
    margin:0;
    padding:10px 0px 0px 0px;
    border-radius: 20px;
    
    // &:last-of-type{
    //       border-bottom-left-radius: 20px;
    //     border-bottom-right-radius: 20px;
    // }

      li{
      list-style-type: none;
      border-bottom: 1px solid #FBFCFF;
       padding:7px;
       &:last-of-type{
               border-radius: 40px;
       }
      
      a{
        font-weight: 600;
        color:#FBFCFF;
        text-decoration: none;
      }
      button{
            background-color: #FBFCFF;
            color:#274156;
            padding:5px 5px;
            // margin:10px;
            font-weight: bolder;
            border-radius: 5px;
            font-size: 14px;
            line-height: 14px;
            border:none;
            cursor: pointer;
            float:right;
            margin-right:20px;
      }
    }
  }
}



}
</style>
