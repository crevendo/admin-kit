<script lang="ts">
  export let align: "left" | "center" | "right" = "left";
</script>

<p class:text-center={align === "center"} class:text-right={align === "right"}><slot /></p>
