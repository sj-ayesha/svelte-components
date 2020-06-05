<script>
  import { createEventDispatcher } from "svelte";

  export let title;
  export let price;
  export let bestseller = false;
  //Emit Custom Events
  const dispatch = createEventDispatcher();

  function addTocart() {
    dispatch("add-to-cart", { id: "p1" });
  }
  //////////////////////////////////////////////////
</script>

<article>
  <h1>{title}</h1>
  <h2>Rs {price}</h2>
  {#if bestseller}
    <h3>bestseller</h3>
  {/if}
  <!--Event Forwarding - add function on App-->
  <button on:click={addTocart}>Add to cart</button>
  <button
    on:click={() => {
      dispatch('delete', 'p1');
    }}>
    Delete
  </button>
</article>
