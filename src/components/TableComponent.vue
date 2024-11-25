<template>
        <h3>{{ title }}</h3>
        <p>{{ noti }}</p>
        
    
</template>

<script setup>
    
    defineProps(['students', 'title']);
    const emit = defineEmits('delete');
    const ChamVaoNut = (id)=>{
        emit('delete',id)
    }
    
</script>

<style lang="scss" scoped>

</style>