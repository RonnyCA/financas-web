<template>
  <div>
    <h1>{{titulo}}</h1>
    <input 
    type="text" 
    placeholder="nome do mercado" 
    v-model="name" 
    v-on:keyup.enter="AddMarket()"
    >
    <div>
    <table border="1px">
      <thead>
        <th>Id</th>
        <th>Nome</th>
        <th>Opções</th>
      </thead>
      <tbody>
        <tr v-for="(market, index) in markets" :key="index">
          <td>{{index}}</td>
          <!-- <td>{{market.id}}</td> -->
          <td>{{market.name}}</td>
          <td><button class="btn" @click="Remover()">Remover</button></td>
        </tr>
      </tbody>
    </table>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      titulo:"Mercados",
      name:"",
      markets:[        
      ]
    }
  },
  methods: {
    AddMarket() {
      let _market = {
        name: this.name
      }
      this.markets.push(_market);
    }
  },
}
</script>

<style>
</style>
