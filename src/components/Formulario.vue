<script setup>
    const props = defineProps(['cadastraTarefa', 'tarefaTemp', 'trocarFiltro','editaTarefaTemp'])
</script>

<template>
    <form @submit.prevent="props.cadastraTarefa">    <!--o .prevent junto no submit evita o comportamento padrão do form que é de atualizar a página quando clicado tal como no js -->
    <div class="row">
        <div class="col-md-8">
            <input :value="props.tarefaTemp" @change="props.editaTarefaTemp" required type="text" placeholder="Digite aqui a descrição da tarefa">
        </div>
        <div class="col-md-2">
            <button type="submit" class="btn btn-primary">Cadastrar</button>
        </div>
        <div class="col-md-2">
            <select @change="props.trocarFiltro" class="form-control">
                <option value="todas">Todas Tarefas</option>
                <option value="pendentes">Pendentes</option>
                <option value="finalizadas">Finalizadas</option>
            </select>
        </div>
    </div>
</form>
</template>