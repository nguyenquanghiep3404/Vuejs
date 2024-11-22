<template>
    <div>
        <h3>parentSlotComponent</h3>
    </div>
    <ChildrenSlotComponent v-slot="slotProps">
        <!-- <template v-slot:header>
            <h1 class="text-primary">Header</h1>
        </template>
        <div>
            <h3>Content</h3>
        </div>
        <template v-slot:footer>
            <h1 class="text-primary">footer</h1>
        </template> -->
        <!-- scoped clot -->
        <p>{{ slotProps.mes }}</p>
    </ChildrenSlotComponent>
    
</template>

<script setup>
import ChildrenSlotComponent from './ChildrenSlotComponent.vue';
</script>
<style lang="scss" scoped>

</style>