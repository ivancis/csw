<!-- patient list -->
<script>
  import {
    DataTable,
    Modal,
    OverflowMenu,
    OverflowMenuItem,
    Toolbar,
    ToolbarContent,
    ToolbarSearch,
    ToolbarMenu,
    ToolbarMenuItem,
    Button,
  } from "carbon-components-svelte";

  let open = false;

  const headers = [
    { key: "name", value: "Name" },
    { key: "port", value: "Port" },
    { key: "rule", value: "Rule" },
  ];

  const rows = [
    { id: "a", name: "Load Balancer 3", port: 3000, rule: "Round robin" },
    { id: "b", name: "Load Balancer 1", port: 443, rule: "Round robin" },
    { id: "c", name: "Load Balancer 2", port: 80, rule: "DNS delegation" },
    { id: "d", name: "Load Balancer 6", port: 3000, rule: "Round robin" },
    { id: "e", name: "Load Balancer 4", port: 443, rule: "Round robin" },
    { id: "f", name: "Load Balancer 5", port: 80, rule: "DNS delegation" },
  ];
</script>

<DataTable
  sortable
  title="Patient list"
  {headers}
  {rows}
>
</DataTable>

<Modal
  bind:open
  modalHeading="Modal"
  primaryButtonText="Yes"
  secondaryButtonText="No"
  on:click:button--secondary={() => (open = false)}
  on:open
  on:close
  on:submit
>
  <p>Modal body</p>
</Modal>


<style lang="scss"></style>