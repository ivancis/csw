<script>
  import { Search, ButtonSet, Button } from "carbon-components-svelte";

  let value = "";
</script>


<div class="search">
  <Search bind:value />
  <ButtonSet>
    <Button
      size="small"
      disabled={value === 'Cloud functions'}
      on:click={() => (value = 'Cloud functions')}
    >
      Set value
    </Button>
    <Button
      kind="ghost"
      size="small"
      disabled={value.length === 0}
      on:click={() => (value = '')}
    >
      Clear value
    </Button>
  </ButtonSet>
  <div>Value: {value}</div>
</div>


<style>

  .form-grid {
    display: grid;
    grid-gap: 1rem;
  }
  
  .form-grid__section {
    display: flex;
    flex-wrap: wrap;
    margin: -0.5rem;
  }
  
  .form-grid__item {
    flex: 1;
    display: grid;
    margin: 0.5rem;
  }
  
  </style>