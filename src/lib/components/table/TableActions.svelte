<script lang="ts">
  import Pencil from "../../icons/Pencil.svelte";
  import Eye from "../../icons/Eye.svelte";
  import Trash from "../../icons/Trash.svelte";
  import Button from "../form/Button.svelte";

  export let disableEdit: boolean = false;
  export let disableView: boolean = false;
  export let disableDelete: boolean = false;

  export let endpoint: string;
  export let id: number;

  const deleteAction = async () => {
    let response = await fetch(endpoint + "/" + "delete/" + id, { method: "DELETE" });
  };

  const viewAction = async () => {
    window.location.assign(endpoint + "/" + id);
  };

  const editAction = async () => {
    window.location.assign(endpoint + "/edit/" + id);
  };
</script>

<div class="flex gap-2">
  {#if !disableEdit}
    <Button on:click={editAction} icon={Pencil} />
  {/if}
  {#if !disableView}
    <Button on:click={viewAction} icon={Eye} />
  {/if}
  {#if !disableDelete}
    <Button on:click={deleteAction} icon={Trash} />
  {/if}
</div>
