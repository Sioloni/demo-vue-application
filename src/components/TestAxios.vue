<template>
  <div>
   <div v-for="(i, index) in users" :key="index">
     <p>{{i.id + " " + i.username + " " + i.age}}</p>

   </div>
  </div>
</template>


<script>
import axios from "axios";

export default {
  name: "TestAxios",
  data() {
    return {
      users: []
    };
  },
  mounted() {
    this.getOnUsers();
  },
  methods: {
    getOnUsers() {
      axios.get('http://localhost:2222/api/v1/user')
          .then(response => {
            console.log('Продукт успешно получен:', response.data);
            this.users = response.data;
            console.log(this.users)
          })
          .catch(error => {
            console.error('Ошибка при создании продукта:', error);
          });
    }
  }
};
</script>


<style>

</style>