<script lang="ts">
  export let title: string = "";
</script>

<main>
  <div class="py-6">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 md:px-8 mb-8">
      {#if title}
        <h1 class="text-2xl font-semibold text-gray-900">{title}</h1>
      {/if}
    </div>
    <div class="max-w-7xl mx-auto px-4 sm:px-6 md:px-8">
      <slot />
    </div>
  </div>
</main>
