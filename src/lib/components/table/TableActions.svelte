<script lang="ts">
  import Pencil from "../../icons/Pencil.svelte";
  import Eye from "../../icons/Eye.svelte";
  import Trash from "../../icons/Trash.svelte";
  import Button from "../form/Button.svelte";
  import { createEventDispatcher } from "svelte";

  const dispatch = createEventDispatcher();

  export let disableEdit: boolean = false;
  export let disableView: boolean = false;
  export let disableDelete: boolean = false;

  export let endpoint: string;
  export let id: number;

  const deleteAction = async () => {
    if (endpoint) await fetch(endpoint + "/" + "delete/" + id, { method: "DELETE" });
    dispatch("delete", id);
  };

  const viewAction = async () => {
    if (endpoint) window.location.assign(endpoint + "/" + id);
    dispatch("view", id);
  };

  const editAction = async () => {
    if (endpoint) window.location.assign(endpoint + "/edit/" + id);
    dispatch("edit", id);
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
