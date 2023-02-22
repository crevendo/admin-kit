<script lang="ts">
  export let itemsCenter: boolean = false;
</script>

<div class="flex gap-4 my-4" class:items-center={itemsCenter}>
  <slot />
</div>
