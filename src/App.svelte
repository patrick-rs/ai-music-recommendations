<script>
  let value = "";

  let artists = "";

  async function doSearch() {
    let response = await fetch(
      "http://localhost:8080/Like/Artist?" +
        new URLSearchParams({
          search: value,
        })
    );
    artists = await response.text();
  }
</script>

<div class="flex">
  <div class="mx-auto grid bg-gray-100">
    <h3 class="mx-auto p-10 text-2xl font-bold">Similar Artists</h3>
    <div class="m-5 grid grid-cols-2 gap-10">
      <input
        class="content-center"
        bind:value
        placeholder="Enter an artist..."
      />
      <button
        class="rounded bg-blue-500 px-4 py-2 font-bold text-white hover:bg-blue-700"
        on:click={doSearch}>Search</button
      >
      <ul class="col-span-2">{artists}</ul>
    </div>
  </div>
</div>
