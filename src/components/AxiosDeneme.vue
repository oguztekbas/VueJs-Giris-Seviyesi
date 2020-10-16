<template>
  <div class="hello">
    <h1>Selam</h1>
    <p>
    BEN AXİOS DENEMEYİMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMM
      <a href="https://cli.vuejs.org" target="_blank" rel="noopener"
        >BEN AXİOS DENEMEYİMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMM</a
      >.
    </p>
    <h3>BEN AXİOS DENEMEYİMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMM</h3>
    <ul>
      <li v-for="product in list" :key="product.id">
        {{product.productName}}
      </li>
     
    </ul>
  </div>
</template>

<script>

import axios from 'axios';

export default {
  name: "HelloWorld",
  props: {
    msg: String
  },
  data(){
    return {
      list:[]
    }
  },
  created(){
    this.getProducts();
  },
  methods: {
    getProducts(){
      
      axios.get('https://localhost:44373/api/product/getproducts',{
        headers: {
           Authorization: 'Bearer ' + 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VyaWQiOiI3ZTNhYWY1Ny0wMjYzLTQ0MTAtYmI4My02MjhiYTliMjJmY2EiLCJ1c2VybmFtZSI6ImRlbmVtZXVzZXJuYW0iLCJuYmYiOjE2MDI3NjAwNDIsImV4cCI6MTYwMjg0NjQ0MiwiaWF0IjoxNjAyNzYwMDQyfQ.7iz8y_p64CBaH08822W4ISWjIl4OwfbOTwreqlUXAXw',
         }
      })
      .then((res) => {
        
        console.log(res.data);
        this.list = res.data;
      })
      .catch((err) => {
        console.log(err);
      });
    }
  }
};
</script>




