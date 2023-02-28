<script lang="ts">
  import { Icon } from "@crevendo/admin-kit/icons";

  export let items: any;

  export let current: string = "/";
</script>

<nav class="px-2 space-y-1">
  {#each items as item}
    <a
      href={item.href}
      class:bg-indigo-800={current === item.href}
      class="text-white group flex items-center px-2 py-2 text-base font-medium rounded-md transition-all hover:bg-indigo-800"
    >
      <Icon icon={item.icon} class="w-5 h-5 mr-4" />
      {item.label}
    </a>
  {/each}
</nav>
