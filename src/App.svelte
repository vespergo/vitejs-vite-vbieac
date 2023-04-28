<script>
import {onMount} from "svelte";
  let products = [];

onMount(async function () {
  
    const response = await fetch('https://dummyjson.com/products');
    const data = await response.json();
    products = data.products;
});

  
    
</script>

<table>
  <thead>
    <tr>
      <th>Name</th>
      <th>Price</th>
      <th>Description</th>
      <th>Image</th>
    </tr>
  </thead>
  <tbody>
    {#each products as product}
      <tr>
        <td>{product.title}</td>
        <td>{product.price}</td>
        <td>{product.description}</td>
        <td><img src={product.images[0]} alt={product.title} width="100" height="100" /></td>
      </tr>
    {/each}
  </tbody>
</table>
