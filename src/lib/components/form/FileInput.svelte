<script lang="ts">
    export let name: string
    let avatar: string | ArrayBuffer;
    let finalUrl: string

    const onFileSelected = async (e) => {
        let image = e.target.files[0];
        let reader = new FileReader();
        reader.readAsDataURL(image);
        reader.onload = async e => {
            avatar = e.target.result
            let response = await fetch("/files/images", {method: "POST", body: JSON.stringify({file: e.target.result})})
            finalUrl = await response.text()
        };
    }

</script>
<div class="flex justify-center items-center w-full mt-5">
    <label for="dropzone-file"
           class="flex flex-col justify-center items-center w-full h-64 bg-gray-50 rounded-lg border-2 border-gray-300 border-dashed cursor-pointer hover:bg-gray-100">
        <div class="flex flex-col justify-center items-center pt-5 pb-6">
            {#if avatar}
                <img class="avatar" src="{avatar}" alt="d"/>
            {:else}
                <svg aria-hidden="true" class="mb-3 w-10 h-10 text-gray-400" fill="none"
                     stroke="currentColor" viewBox="0 0 24 24"
                     xmlns="http://www.w3.org/2000/svg">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                          d="M7 16a4 4 0 01-.88-7.903A5 5 0 1115.9 6L16 6a5 5 0 011 9.9M15 13l-3-3m0 0l-3 3m3-3v12"></path>
                </svg>
                <p class="mb-2 text-sm text-gray-500 dark:text-gray-400"><span
                        class="font-semibold">Click para subir</span></p>
                <p class="text-xs text-gray-500 dark:text-gray-400">SVG, PNG, JPG or GIF
                    (MAX.
                    800x400px)</p>
            {/if}
        </div>
        <input id="dropzone-file" type="file" class="hidden" on:change={(e)=>onFileSelected(e)}/>
        <input {name} bind:value={finalUrl}/>
    </label>
</div>