<script lang="ts">
  export let name: string = "";
  export let label: string = "";
  export let placeholder: string = "";
  export let value: string = "";
</script>

<label class="block text-gray-700 text-sm font-bold mb-2" for="username">
  {label}
</label>
<input
  {name}
  bind:value
  class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline my-4"
  id="username"
  type="text"
  {placeholder}
/>
