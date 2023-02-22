<script lang="ts">
  import Icon from "../../icons/Icon.svelte";

  export let icon: any = "";
  export let style: string = "";
</script>

<div>
  {#if style === "danger"}
    <button
      on:click
      type="submit"
      class="w-full flex justify-center py-2 px-4 border border-transparent rounded-md shadow-sm text-sm font-medium text-white bg-red-500 hover:bg-red-600 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-red-500"
    >
      <slot />
    </button>
  {:else if icon}
    <button
      on:click
      type="button"
      class="inline-flex items-center rounded-md border border-gray-300 bg-white px-4 py-2 text-sm font-medium text-gray-700 shadow-sm hover:bg-gray-50 focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2"
    >
      <Icon {icon} class="w-5 h-5 mr-2" />
      <slot />
    </button>
  {:else}
    <button
      on:click
      type="submit"
      class="w-full flex justify-center py-2 px-4 border border-transparent rounded-md shadow-sm text-sm font-medium text-white bg-indigo-600 hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500"
    >
      <slot />
    </button>
  {/if}
</div>
