<script>
  let {value = $bindable(), ...props } = $props();
</script>


<input bind:value={value} {...props}>


<style>
	input {
		font-family: 'Comic Sans MS';
		color: deeppink;
	}
</style>