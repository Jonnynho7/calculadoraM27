<template>
    <form class="pt-2">
        <div class="row">
            <div class="col m4">
                <input v-model.number="estadoLocal.numA" type="number" class="form-control" placeholder="Número A" />
            </div>

            <div class="col m4">
                <input v-model.number="estadoLocal.numB" type="number" class="form-control" placeholder="Número B" />
            </div>

            <div class="col m4">
                <select v-model="estadoLocal.operacao" class="form-select">
                    <option value="" disabled>Selecione a operação</option>
                    <option value="+">Adição</option>
                    <option value="-">Subtração</option>
                    <option value="*">Multiplicação</option>
                    <option value="/">Divisão</option>
                </select>
            </div>
        </div>
    </form>
</template>

<script setup>
import { reactive, watch } from 'vue'

const emit = defineEmits(['atualizar'])

const estadoLocal = reactive({
    numA: 0,
    numB: 0,
    operacao: ''
})


watch(estadoLocal, () => {
    emit('atualizar', { ...estadoLocal })
})
</script>
