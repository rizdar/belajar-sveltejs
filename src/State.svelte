<script>
  let count = $state(0)

let a = $state(10);
let b = $state(5);
let sum = $derived(a + b);

let todos = $state([
  {
    done : false,
    text : "add more todo"
  }
])

function addTodo(status, description) {
  todos.push({done : status, text : description})
}

let numbers = $state([1, 2, 3])

let total = $derived.by(() => {
  let total = 0;
  for (const n of numbers) {
    total += n
  }

  return total
})


</script>



<button onclick={() => count++}>
  click : {count}
</button>

<ul>

  {#each todos as todo }
    <li>status : {todo.done ? "selesai" : "belum selesai"}</li>
    <li>description : {todo.text}</li>
  {/each}
</ul>

<p>Nilai a : {a}</p>
<p>Nilai B : {b}</p>
<p>Jumlah: {sum}</p>
<button onclick={() => a += 1}>Tambah A</button>
<button onclick={() => b += 1}>Tambah B</button>


<button onclick={() => numbers.push(numbers.length + 1)}>
{numbers.join(' + ')} = {total}
</button>

