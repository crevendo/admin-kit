<script>
  import Panel from "$lib/components/layout/Panel.svelte";
  import Row from "$lib/components/layout/Row.svelte";
  import Container from "$lib/components/layout/Container.svelte";
  import Coloumn from "$lib/components/layout/Coloumn.svelte";
</script>

<Container title="test">
  <Panel>
    <Row itemsCenter>
      <Coloumn>
        <img class="inline w-24 h-24 border mr-3" alt="product" src="https://m.media-amazon.com/images/I/21SPDoiRuGL.jpg" />
      </Coloumn>
      <Coloumn>
        <p>x x</p>
      </Coloumn>
      <Coloumn>
        <p>$ 100</p>
      </Coloumn>
    </Row>
    <Row>
      <p>Total: $ 100.00</p>
    </Row>
  </Panel>
</Container>
