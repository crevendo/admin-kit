<script lang="ts">
  export let definition: string = "";
</script>

<p><span>{definition}:</span> <slot /></p>

<style lang="postcss">
  p {
    @apply text-gray-400 mb-2;
  }
  span {
    @apply text-gray-600 font-bold;
  }
</style>
