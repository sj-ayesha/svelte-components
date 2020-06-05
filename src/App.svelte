<script>
  import Product from "./Product.svelte";

  let products = [
    {
      id: "p1",
      title: "A Book",
      price: 9.99
    }
  ];

  //Extract event data
  function addToCart(event) {
    console.log(event);
  }

  function deleteProduct(event) {
    console.log(event);
  }
</script>

<style>

</style>

<main>
  {#each products as product}
    <!--Emmit Custom Events-->
    <Product
      {...product}
      on:add-to-cart={addToCart}
      on:delete={deleteProduct} />
  {/each}

</main>
