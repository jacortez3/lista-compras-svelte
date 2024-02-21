<link
  rel="stylesheet"
  href="node_modules/svelte-material-ui/themes/svelte.css"
  media="(prefers-color-scheme: light)"
/>
<link
  rel="stylesheet"
  href="node_modules/svelte-material-ui/themes/svelte-dark.css"
  media="screen and (prefers-color-scheme: dark)"
/>

<script lang="ts">

  
  import Button, { Label } from '@smui/button';
  import Textfield from '@smui/textfield';
  import Icon from '@smui/textfield/icon';
  import HelperText from '@smui/textfield/helper-text';
  import DataTable, { Head, Body, Row, Cell } from '@smui/data-table';


  let items = ['Manzanas', 'Bananas', 'Naranjas'];
  let newItem = '';

  function addItem() {
    if (newItem.trim() !== '') {
      items = [...items, newItem];
      newItem = '';
    }
  }

  function removeItem(index) {
    items = items.filter((_, i) => i !== index);
  }
</script>

<h1>Shopping List</h1>
<div class="columns margins">
  <div>
    <Textfield bind:value={newItem} label="Agregar ITEM">
      <HelperText slot="helper">Ingrese Producto</HelperText>
    </Textfield>
 
  </div>

</div>

<Button color="secondary" on:click={addItem} variant="raised">
  Add
</Button>


<ul>
  {#each items as item, index}
  <Row>
    <Cell>{item}</Cell>
    <Cell>
      <Button on:click={() => removeItem(index)} variant="raised">
        <Label>Remove</Label>
      </Button>
      </Cell>
  </Row>
   
  {/each}
</ul>

