<script>
import StateComponent from './State.svelte';
import EffectComponent from './Effect.svelte';
import PropsComponent from './PropsComponent.svelte';
import Bindable from './Bindable.svelte';

// let color = "orange"
// let count = $state(0);
let message = $state("hello");
// $inspect(message)
</script>

<main>
<!-- <StateComponent/> -->
<!-- <EffectComponent/> -->
<!-- <PropsComponent adjective="cool" name="Rizki" {color} {count}/>
<button onclick={() => count++}>Counting +</button> -->

<Bindable bind:value={message}/>
<p>{message}</p>

</main>

<style>
  
</style>
