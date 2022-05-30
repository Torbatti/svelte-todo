<script>

    //https://svelte.dev/repl/7eb8c1dd6cac414792b0edb53521ab49?version=3.20.1
    //https://svelte.dev/repl/354bfb3b58be4e1994901059ee787c2b?version=3.48.0
    //https://svelte.dev/examples/each-block-bindings

    

    let todos=[];
    let todo_input="";

	

    function newTodo(){
        if (todo_input == ""){
        }else{
            todos=[...todos,{done:false,text:todo_input}]

            todo_input="";
        }
    }

    $: console.log(todos)

</script>


<nav class="h-4 bg-slate-700"></nav>

<div class="w-screen flex justify-center overflow-x-hidden">
    <main class="w-96">

        <div class="flex justify-between mt-12 p-4">
            <input type="text" name="" id="" placeholder="Enter Your Task" bind:value={todo_input} class="pl-2 rounded-sm w-72">

            <button on:click={newTodo}>
                <span class="iconify-inline text-slate-300" data-icon="fluent:add-20-filled" data-width="32" data-height="32"></span>
            </button>
        </div>

        <div class="">
            <div>
                {#each todos as todo}
                    <div class= "w-96 bg-slate-700 flex flex-row justify-between content-center rounded-sm px-4 mt-4">
                        <p class="text-slate-300 h-10 mt-4">{todo.text}</p>
                        <input bind:checked={todo.done} type="checkbox" class="h-6 w-6 mt-4">
                    </div>
                {/each}
            </div>
        </div>
        
    </main>
</div>


<style>

</style>