<script>
  export let icon;
  export let type = "";
  export let size = "";
</script>

<div class="inline-block">
  <div
    class={`items-center flex transition-all hover:text-indigo-500 ${$$props.class}`}
    style={`width: ${size}; height: ${size};`}
    class:hover:text-indigo-500={type === "action"}
    class:cursor-pointer={type === "action"}
  >
    <svelte:component this={icon} />
  </div>
</div>
