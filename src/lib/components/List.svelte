<script lang="ts">
  import { onMount } from "svelte";

  import Input from "./Input.svelte";

  export let label: string = "";
  export let placeholder: string = "";
  export let name: string = "";
  export let value: string = "";

  let items: string[] = [];
  let itemsFlat: string = "";
  let actualName = "";

  onMount(() => {
    if (value != "") {
      items = value.split(",");
    }
    updateItemsFlat();
  });

  const addItem = () => {
    items = [...items, actualName];
    actualName = "";
    updateItemsFlat();
  };

  const remove = (item: string) => {
    items = items.filter((i) => i !== item);
    updateItemsFlat();
  };

  const updateItemsFlat = () => {
    itemsFlat = items.join(",");
  };
</script>

<div>
  <input {name} type="hidden" bind:value={itemsFlat} />
  <form on:submit|preventDefault={addItem}>
    <Input bind:value={actualName} {label} {placeholder} />
  </form>
  <ul>
    {#each items as item}
      <li class="py-1">
        <span>{item}</span>
        <button class="text-indigo-500" on:click={() => remove(item)}
          >&times;</button
        >
      </li>
    {/each}
  </ul>
</div>
