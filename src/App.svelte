<script>
  import "carbon-components-svelte/css/g10.css";
  import { TextArea } from "carbon-components-svelte";
  import { Button } from "carbon-components-svelte";

  let value = "";

  function doSearch() {
    let response = fetch(
      "http://localhost:3000/search?" +
        new URLSearchParams({
          query: value,
        })
    );
    console.log(response);
  }
</script>

<h1>Hello</h1>

<TextArea
  labelText="App description"
  placeholder="Enter a description..."
  bind:value
/>

<Button on:click={doSearch}>Search</Button>
