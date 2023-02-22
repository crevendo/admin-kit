<script lang="ts">
    export let contentCentered: boolean = false
</script>
<li class:text-center="{contentCentered}"
    class="overflow-hidden rounded-md bg-white p-10 shadow list-none relative h-full">
    <slot/>
</li>
