<template>
  <HeaderComponent/>
  <div class="container">
    <BalanceComponent :total="total"/>
    <IncomeExpense/>
    <!-- pasando props al componente  en este caso transactions-->
    <TransactionList :transactions="transactions"/>
    <AddTransaction/>
  </div>
</template>

<script setup>
import HeaderComponent from  './components/HeaderComponent.vue';
import BalanceComponent from './components/BalanceComponent.vue';
import IncomeExpense from './components/IncomeExpense.vue';
import TransactionList from './components/TransactionList.vue';
import AddTransaction from './components/AddTransaction.vue';
import { ref,computed } from 'vue';

  const transactions  = ref([
    {id: 1, text: 'Flower', amount: -19.99},
    {id:2, text: 'Salary', amount: 299.99},
    {id:3, text: 'Book', amount: -9.99},
    {id:4, text: 'Camera', amount: 150.00}
  ])
  
  
  //  computed depende de otros valores y ejecuta su funcion 
  // al detectar cambios en sus valores en esta caso dependera de transactions para ejecutarse
  
  
  const total = computed(()=>{
    return transactions.value.reduce((acc, transaction)=>{
      return acc + transaction.amount
    },0)
  })
  console.log(total.value)
  
    
    
</script>


<!-- 
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style> -->
