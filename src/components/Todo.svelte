<script>
    let title = ''
    let todos = [{"name": "First", "id":1}]

    const addTodo = () => {
        todos = [...todos, {
            "name": title,
            "id": Math.random()
        }]
    }
</script>

<div class="container">
    <div class="box">
        <input bind:value={title} type="text" placeholder="Enter todo" />
        <button on:click={addTodo}>Add</button>
    </div>
    <h2 style="text-align:center">Todos</h2>
    <hr />
   <div class="todos">
    {#each todos as todo}
            <p class="todo-item">{todo.name}</p>
        {:else}
            <p>No Todos</p>
        {/each}
   </div>
</div>

<style>
    .container {
        width: 80%;
        margin: 0 auto;
    }
    .box {
        padding: 10px;
        display: flex;
        justify-content: space-around;
        margin: 10px auto;
    }

    input {
        padding: 10px;
        width: 60%;
        font-family: 'Segoe UI';
        font-weight: bold;
    }

    button {
        padding: 3px 20px;
        border: none;
        background-color: tomato;
        font-family: 'Segoe UI';
        font-weight: bold;
        color: white;
        box-shadow: 2px 2px 5px #ccc;
        border-radius: 4px;
    }

    .todo-item {
        background-color: blue;
        padding: 10px;
        border-radius: 4px;
        box-shadow: 2px 2px 5px #ccc;
        margin: 10px;
        color: white;
        text-align: center;
        width: 50%;
        margin: 20px auto;
    }

    .todos {
        margin: 20px;
    }
</style>