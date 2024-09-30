<template>
    <div class="grid">
        <slot name="one"/>
        <slot name="two"/>
    </div>
</template>

<script>
export default {
    
}
</script>

<style>
.grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
}
</style>