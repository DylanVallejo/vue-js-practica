<template>
    <h3>
        History
    </h3>
    <ul id="list" class="list">
        <li v-for="transaction in transactions" :key="transaction.id">
            {{ transaction.text }} Cash 
            <span>
                {{ transaction.amount }}
            </span>
            <button class="delete-btn">
                x    
            </button>
        </li>
    </ul>
</template>
<script setup>
    import { defineProps } from 'vue';
    
    
    // utilizamos definePorps para acceder a los props enviados desde un padre
    const props = defineProps({
        transactions: {
            type: Array,
            required: true
        }
        
    });
    console.log(props.transactions[0].text)
</script>