<script setup>
    const props = defineProps(['resposta', 'recebeNumeroA', 'recebeNumeroB', 'selecionaOperacao', 'calcular']);
</script>

<template>
    <form>
        <div class="row">
            <div class="col-md-4">
                <label class="form-control text-center" for="numero-a">Número A</label>
                <input class="form-control" type="number" id="numero-1" @change="props.recebeNumeroA">
            </div>
            <div class="col-md-4">
                <label class="form-control text-center" for="numero-b">Número B</label>
                <input class="form-control" type="number" id="numero-b" @change="props.recebeNumeroB">
            </div>
            <div class="col-md-4">
                <label class="form-control text-center" for="numero-b">Reposta</label>
                <p class="form-control text-center">
                    {{ props.resposta }}
                </p>
            </div>
        </div>
        <div class="row mt-5">
            <div class="col mx-auto d-flex">
                <label class="form-control text-center" for="numero-b">Operação:</label>
                <select class="form-control" @change="props.selecionaOperacao">
                    <option class="text-center" value="adicao">Adição</option>
                    <option class="text-center" value="subtracao">Subtração</option>
                    <option class="text-center" value="multiplicacao">Multiplicação</option>
                    <option class="text-center" value="divisao">Divisão</option>
                </select>
            </div>
        </div>
    </form>
</template>