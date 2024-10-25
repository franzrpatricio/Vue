<!-- Options API = Traditional way -->
<!-- script -->
<script>
  export default{
    data(){
      return{
        name:'John Doe',
        work:'NA',
        status: 'active',
        tasks:['One','Two','Three'],
        link:'https://www.google.com/'
      };
    },
    methods:{
      toggleStatus(){
        if (this.status === 'active') {
          this.status = 'pending';
        } else if (this.status === 'pending') {
          this.status = 'inactive';
        } else {
          this.status = 'active'
        }
      }
    }
  };
</script>

<!-- template -->
<template>
  <h1>Name: {{name}}</h1>
  <h2>Work: {{ work }}</h2>
  <p v-if="status === 'active'">User is active.</p>
  <p v-else-if="status === 'pending'">Pending User.</p>
  <p v-else-if="status === 'rejected'">User is rejected.</p>
  <p v-else>User is inactive.</p>

  <h3>Tasks:</h3>
  <ul>
    <li v-for="task in tasks" :key="task">{{ task }}</li>
  </ul>

  <a :href="link">Google</a> <br/>
  <button @click="toggleStatus">Change Status</button>
</template>

<!-- style -->
