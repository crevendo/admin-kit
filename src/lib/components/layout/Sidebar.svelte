<script lang="ts">
  export let storeName: string;
</script>

<!-- Mobile -->
<div class="relative z-40 md:hidden" role="dialog" aria-modal="true">
  <div class="fixed inset-0 bg-gray-600 bg-opacity-75" />
  <div class="fixed inset-0 flex z-40">
    <div class="relative flex-1 flex flex-col max-w-xs w-full pt-5 pb-4 bg-indigo-700">
      <div class="absolute top-0 right-0 -mr-12 pt-2">
        <button
          type="button"
          class="ml-1 flex items-center justify-center h-10 w-10 rounded-full focus:outline-none focus:ring-2 focus:ring-inset focus:ring-white"
        >
          <span class="sr-only">Close sidebar</span>
          <svg
            class="h-6 w-6 text-white"
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke-width="2"
            stroke="currentColor"
            aria-hidden="true"
          >
            <path stroke-linecap="round" stroke-linejoin="round" d="M6 18L18 6M6 6l12 12" />
          </svg>
        </button>
      </div>

      <div class="flex-shrink-0 flex items-center px-4 text-white">
        Administrador de {storeName}
      </div>
      <div class="mt-5 flex-1 h-0 overflow-y-auto">
        <slot />
      </div>
    </div>
    <div class="flex-shrink-0 w-14" aria-hidden="true" />
  </div>
</div>

<!-- Desktop -->
<div class="md:flex md:w-64 md:flex-col md:inset-y-0 h-screen">
  <div class="flex flex-col flex-grow pt-5 bg-indigo-700 overflow-y-auto">
    <div class="flex items-center flex-shrink-0 px-4 text-white">
      Administrador de {storeName}
    </div>
    <div class="mt-5 flex-1 flex flex-col">
      <slot />
    </div>
  </div>
</div>
