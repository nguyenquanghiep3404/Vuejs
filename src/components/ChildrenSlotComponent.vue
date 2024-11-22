<template>
        <h3>ChildrenComponents</h3>
        <div class="header">
            <slot name="header"></slot>
        </div>
       
        <div class="footer">
            <slot name="footer"></slot>
        </div>
        <div>
            <!-- scoped slot -->
            <slot :mes="message"></slot>
        </div>
</template>

<script setup>
    const message = "Đây là message đc gửi từ children";
</script>

<style lang="scss" scoped>

</style>