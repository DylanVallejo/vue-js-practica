<template>
    <p>Balance Component</p>
    <h4>Your balance <br><span>${{ total }}</span></h4>
    
</template>
<script setup>
    import { defineProps } from 'vue';
        
    const props = defineProps({
        total: {
            type: Number,
            required: true
        }
    });

</script>
<style>

</style>