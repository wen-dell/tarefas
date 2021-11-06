<template>
    <div id="task">
        
        <form @submit.prevent="addItem">
            <input 
            type="text" 
            placeholder="Tarefa de hoje?"
            v-model="tarefa">
            <button type="submit">Adicionar</button>
        </form>

        <Item :lista="tarefas" :delete="deleteTask"/>

    </div>
</template>

<script>
import Item from './Item.vue';

export default {
    name: 'Task',
    components: {
        Item
    },
    data() {
        return {
            tarefa: '',
            tarefas: [],
        }
    },
    methods: {
        addItem() {
            if (this.tarefa !== '') {
                this.tarefas.push({
                    text: this.tarefa,
                    key: Date.now(),
                });
            } else {
                alert('Digite uma tarefa');
                return;
            }

            this.tarefa = '';
            console.log(this.tarefas);
        },
        deleteTask(key) {
            let filtro = this.tarefas.filter((item) => {
                return (item.key !== key);
            });
            this.tarefas = filtro;
        }
    }
}
</script>

<style scoped>
    #task {
        max-width: 700px;
        background: #FFF;
        border-radius: 4px;
        padding: 20px;
        margin: 20px auto;
        box-shadow: 0 0 20px rgba(0, 0, 0, 0.3);
    }

    form {
        margin-top: 30px;
        display: flex;
        flex-direction: row;
    }

    form button {
        cursor: pointer;
        background: #0f5959;
        border: 0;
        border-radius: 4px;
        margin-left: 10px;
        padding: 0 15px;
        display: flex;
        justify-content: center;
        align-items: center;
        color: #fff;
    }

    input {
        flex: 1;
        border: 1px solid #eee;
        padding: 6px 10px;
        border-radius: 4px;
        font-size: 14px;
        outline: none;
    }
</style>