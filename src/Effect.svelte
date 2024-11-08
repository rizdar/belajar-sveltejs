<script>
  
  let size = $state(50);
	let color = $state('#ff3e00');
	
	let canvas;

	$effect(() => {
		const context = canvas.getContext('2d');
		context.clearRect(0, 0, canvas.width, canvas.height);

		// this will re-run whenever `color` or `size` change
		context.fillStyle = color;
		context.fillRect(0, 0, size, size);
	});

  let count = $state(0);
  let milliseconds = $state(1000);


    $effect(() => {
      // This will be recreated whenever `milliseconds` changes
      const interval = setInterval(() => {
          count += 1;
        }, milliseconds);
        console.log(count)

        return () => {
          // if a callback is provided, it will run
          // a) immediately before the effect re-runs
          // b) when the component is destroyed
          clearInterval(interval);
        };
    })

</script>


<canvas bind:this={canvas} width="100" height="100"></canvas>

<div class="controls">
	<label>
		<input type="range" bind:value={size} /> size
	</label>
	
	<label>
		<input type="color" bind:value={color} /> color
	</label>

</div>


<h1>{count}</h1>

<button onclick={() => (milliseconds *= 2)}>slower</button>
<button onclick={() => (milliseconds /= 2)}>faster</button>