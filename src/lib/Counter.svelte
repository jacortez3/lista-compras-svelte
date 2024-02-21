<script>

import Button, { Label } from '@smui/button';

  let count = 0
  const increment = () => {
    count += 1
  }
</script>

<Button color="secondary" on:click={increment} variant="raised">
  <Label>count is {count}</Label>
</Button>

