<script lang="ts">
  import Input from "./Input.svelte";

  export let label: string;
  export let placeholder: string;

  let items = [];

  let name = "";

  const addItem = () => {
    items = [
      ...items,
      {
        id: Math.random(),
        name,
        done: false,
      },
    ];
    name = "";
  };

  const remove = (item) => {
    items = items.filter((i) => i !== item);
  };

  const toggle = (item) => {
    item.done = !item.done;
    items = items;
  };
</script>

<div>
  <form on:submit|preventDefault={addItem}>
    <Input bind:value={name} {label} {placeholder} />
  </form>

  <ul>
    {#each items as item}
      <li class="py-1">
        <span>{item.name}</span>
        <button class="text-indigo-500" on:click={() => remove(item)}
          >&times;</button
        >
      </li>
    {/each}
  </ul>
</div>
