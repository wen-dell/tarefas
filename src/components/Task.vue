<template>
    <div id="task">
        
        <form>
            <input type="text" placeholder="Tarefa de hoje?">
            <button type="submit">Adicionar</button>
        </form>

    </div>
</template>

<script>
export default {
    name: 'Task'
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