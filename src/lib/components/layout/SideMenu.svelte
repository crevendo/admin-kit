<script lang="ts">
  import { Icon, Home, Bag, Box, Users, Code, Squares, Cog } from "@crevendo/admin-kit/icons";

  let items = [
    { label: "Inicio", icon: Home, href: "/" },
    { label: "Ordenes", icon: Bag, href: "/orders" },
    { label: "Productos", icon: Box, href: "/products" },
    { label: "Categorias", icon: Squares, href: "/categories" },
    { label: "Usuarios", icon: Users, href: "/users" },
    { label: "Integraciones", icon: Code, href: "/integrations" },
    { label: "Configuracion", icon: Cog, href: "/configuration" },
  ];

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
