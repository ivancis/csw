<script>
  import {
    TextInput,
    FormGroup,
  } from "carbon-components-svelte";

  import Search from "./components/Search.svelte";
  import Agenda from "./components/Agenda.svelte";
  import PatientList from "./components/PatientList.svelte";

  // Only executes in "development" mode
  // Completely removed when building for production
  if (process.env.NODE_ENV === "development") {
    console.group("carbon-svelte-webpack");
    console.info("This message only appears in development.");
    console.groupEnd();
  }

  let size = "default";
  let toggle = false;
  let selectedOption = "two";
</script>

<style>
  .dashboard {
		display: grid;
		grid-gap: 3rem;
    place-content: center stretch;
		margin: 0;
		padding: 1rem;
    width: 100%;
    min-height: 100vh;
	}

	.dashboard-section {
		display: grid;
		margin: auto;
		width: 100%;
		max-width: 1200px;
	}
</style>

<div class="dashboard">
	<section class="dashboard-section">
    <FormGroup
      labelText="Why not this one aswell"
      textInput-Aclaration="$"
      textInput-AclarationAlignment="left"
    >
      <TextInput
        labelText="aclarationLeft"
        placeholder="Placeholder"
        invalid
        invalidText="fuck"
        size="xl"
      />
    </FormGroup>
  </section>
	<section class="dashboard-section">
		<Search />
	</section>
	<section class="dashboard-section">
		<Agenda />
	</section>
	<section class="dashboard-section">
		<PatientList />
	</section>
</div>