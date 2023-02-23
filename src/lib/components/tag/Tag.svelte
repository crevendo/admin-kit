<script lang="ts">
  export let color: string;
</script>

<button on:click>
  {#if color === "yellow"}
    <p class="inline-flex rounded-full bg-yellow-100 px-2 text-xs font-semibold leading-5 text-yellow-800 ml-3">
      <slot />
    </p>
  {:else if color === "red"}
    <p class="inline-flex rounded-full bg-red-100 px-2 text-xs font-semibold leading-5 text-red-800 ml-3">
      <slot />
    </p>
  {:else}
    <p class="inline-flex rounded-full bg-green-100 px-2 text-xs font-semibold leading-5 text-green-800 ml-3">
      <slot />
    </p>
  {/if}
</button>
