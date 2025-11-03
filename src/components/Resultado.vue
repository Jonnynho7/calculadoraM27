<script setup>
    const props = defineProps(['calculo'])
</script>

<template>
    <section class="mt-4 text-center">
        <div class="container">
            <h3>Resultado</h3>
            <p class="fs-4">{{ props.calculo }}</p>
        </div>
    </section>
</template>