<script lang="ts">
  export let title: string = "";
</script>

<div class="p-10">
  <h2>{title}</h2>
  <slot />
</div>
