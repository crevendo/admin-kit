<script>
  import Button from "../lib/components/Button.svelte";
  import Coloumn from "../lib/components/Coloumn.svelte";
  import Input from "../lib/components/Input.svelte";
  import List from "../lib/components/List.svelte";
  import Row from "../lib/components/Row.svelte";
  import Section from "../lib/components/Section.svelte";
</script>

<div class="p-5">
  <h1 class="text-6xl mb-10">Administrador</h1>
  <Row>
    <Coloumn>
      <Section title="Exclusiones por Categoria">
        <List placeholder="Categoria" label="Agregar Categoria" />
      </Section>
    </Coloumn>
    <Coloumn>
      <Section title="Exclusiones por Asin">
        <List placeholder="Asin" label="Agregar Asin" />
      </Section>
    </Coloumn>
  </Row>

  <Row>
    <Coloumn>
      <Section title="Exclusiones por Palabra Clave">
        <List placeholder="Palabra Clave" label="Agregar Palabra Clave" />
      </Section>
    </Coloumn>
    <Coloumn>
      <Section title="Exclusiones por Precio">
        <Input
          placeholder="Precio"
          label="Excluir productos que sean mayor a"
        />
      </Section>
    </Coloumn>
  </Row>
  <Row>
    <Section>
      <Button>GUARDAR CAMBIOS</Button>
    </Section>
  </Row>
</div>
