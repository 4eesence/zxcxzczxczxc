<template> 
  <div class="cards">
    <Card v-for="tovar in tovars" :key ="tovar.id" :tovar="tovar" @onFav="addFavorite" @onSold="addSolled" @about="func" @remove="removeItem" @sale="changeItem"></Card>
  </div>
     
  </template> 
   
  <script> 
  import User from './components/User.vue'; 
  import Card from './components/Card.vue'; 
   
  export default { 
    name: 'App', 
    components: { 
      User, 
      Card, 
    }, 
     
   
  data() { 
    return { 
      name: "Ivan", 
      tovars:[ 
        {id: 1, name: "Пылесос", price: "100$",desc: "Пылесосит качественно", isFavorite: false}, 
        {id: 2, name: "Пылесос2", price: "200$", desc: "Пылесосит качественно", isFavorite: false}, 
        {id: 3, name: "Пылесос3", price: "300$", desc: "Пылесосит качественно", isFavorite: false}, 
        {id: 4, name: "Пылесос4", price: "400$", desc: "Пылесосит качественно", isFavorite: false}, 
        {id: 5, name: "Пылесос5", price: "500$", desc: "Пылесосит качественно", isFavorite: false}, 
        {id: 6, name: "Пылесос6", price: "600$", desc: "Пылесосит качественно", isFavorite: false}, 
        {id: 7, name: "Пылесос7", price: "700$", desc: "Пылесосит качественно", isFavorite: false}, 
        {id: 8, name: "Пылесос8", price: "800$", desc: "Пылесосит качественно", isFavorite: false}, 
        {id: 9, name: "Пылесос9", price: "900$", desc: "Пылесосит качественно", isFavorite: false}, 
        {id: 10, name: "Пылесос10", price: "1000$", desc: "Пылесосит качественно", isFavorite: false}, 
      ] 
   
    } 
  },
  methods:{
    addFavorite(id){
      alert('я избранный'+ id)
    },
  
    addSolled(id){
      alert('меня купили'+ id)
    },
  
    func(name, salary){
      console.log(name, salary);
    },
    removeItem(id){
      this.tovars = this.tovars.filter((tovar) => {
        if (tovar.id != id) {
          return tovar;
        }
      })
    },
    changeItem(id){
      this.tovars = this.tovars.map((tovar) => {
        if (tovar.id == id) {
          tovar.price = '-100$'
        }
        return tovar;
      })
    },
  } 
   
  } 
  </script> 
     
  <style> 
  #app { 
    font-family: Avenir, Helvetica, Arial, sans-serif; 
    -webkit-font-smoothing: antialiased; 
    -moz-osx-font-smoothing: grayscale; 
    text-align: center; 
    color: #2c3e50; 
    margin-top: 60px; 
  } 
   
  .cards{ 
    display: flex; 
    flex-wrap: wrap; 
    justify-content: center; 
  } 
  </style>
  