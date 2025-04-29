<script>
  export default{
    data(){
      return{
        name: "John Doe",
        status: "pending",
        tasks: ['Task One','Task Two','Task Three','Task Four'],
        links:'https://google.com'
      };
    },
    method:{ //can access any data
      toggleStatus(){
        if(this.status === 'active'){
          this.status ='pendinig';
        }else if(this.status === 'pending'){
          this.status = 'inactive';
        }else{
          this.status ='active';
        }
      },
    },
  };
</script>
<template>
  <h1>{{ name }}</h1>
  <p v-if="status==='active'">User is active</p>
  <p v-else-if="status==='pending'">User is pending</p>
  <p v-else>User is inactive</p>

  <h3>Task:</h3>
  <ul>
    <li v-for="task in tasks":key="task">{{ task }}</li>
  </ul>
  <!--<a v-bind:href="links">Click for Google</a>-->
  <a :href="links">click for Google</a>
<br />
  <button @click="toggleStatus">Change Status</button>
</template>

