<script lang="ts">
  import Icon from "$lib/icons/Icon.svelte";
  export let title: string = "";
  export let icon: any;
  export let info: string = "";
</script>

<div class="text-center">
  {#if icon}
    <Icon {icon} size="40px" class="text-indigo-500" />
  {/if}
  {#if title}
    <span class="block my-5">{title}</span>
  {/if}
  {#if info}
    <span class="block text-2xl text-indigo-500">{info}</span>
  {/if}
</div>
