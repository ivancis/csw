<script>
  import { Button, ComboBox, TextInput, } from 'carbon-components-svelte';
  import { createForm } from 'svelte-forms-lib';
  import * as yup from 'yup';
  import { createEventDispatcher } from 'svelte';
  import Odontogram from './Odontogram.svelte'

  const patientOldId = 123;
  const patientNewdId = patientOldId + 1;

  const {
    form,
    errors,
    handleChange,
    isValid,
  } = createForm({
    initialValues: {
      patientLastName: '',
      patientName: '',
    },
    validationSchema: yup.object().shape({
      patientLastName: yup.string().required('Last name is required'),
      patientName: yup.string().required('Name is required'),
    }),
  });

  const dispatch = createEventDispatcher();

  $: ($isValid, dispatch('validate'));
</script>

<div class="form-grid">
  <div class="form-grid__section">
    <div class="form-grid__item">
      <TextInput
        id="patientid"
        name="patientid"
        labelText="Unique ID:"
        placeholder="Unique ID"
        size="xl"
        disabled
        light
        value={patientNewdId}
      />
    </div>
  </div>
  <div class="form-grid__section">
    <div class="form-grid__item">
      <TextInput
        id="patientName"
        name="patientName"
        labelText="Name:"
        placeholder="Patient name"
        size="xl"
        bind:value={$form.patientName}
        bind:invalid={$errors.patientName}
        invalidText={$errors.patientName}
        on:keyup={handleChange}
        on:blur={handleChange}
      />
    </div>
    <div class="form-grid__item">
      <TextInput
        id="patientLastName"
        name="patientLastName"
        labelText="Last name:"
        placeholder="Patient last name"
        size="xl"
        bind:value={$form.patientLastName}
        bind:invalid={$errors.patientLastName}
        invalidText={$errors.patientLastName}
        on:keyup={handleChange}
        on:blur={handleChange}
      />
    </div>
    <div class="form-grid__item">
      <TextInput labelText="DNI:" size="xl"/>
    </div>
  </div>
  <div class="form-grid__section">
    <div class="form-grid__item">
        <ComboBox
          titleText="Obra social:"
          placeholder="Obra social"
          size="xl"
          items={[{ id: '0', text: 'Slack' }, { id: '1', text: 'Email' }, { id: '2', text: 'Fax' }]}
        />
    </div>
    <div class="form-grid__item">
        <TextInput labelText="Nº afiliado:"/>
    </div>
  </div>
  <div class="form-grid__section">
      <div class="form-grid__item">
          <TextInput labelText="Domicilio:"/>
      </div>
      <div class="form-grid__item">
          <TextInput labelText="Localidad:"/>
      </div>
      <div class="form-grid__item">
          <TextInput labelText="C. Postal:"/>
      </div>
      <div class="form-grid__item">
          <TextInput labelText="Teléfono:"/>
      </div>
  </div>
  <div class="form-grid__section">
    <div class="form-grid__item">
      <Button>Submit</Button>
    </div>
  </div>
</div>

<Odontogram />

<style>

.form-grid {
  display: grid;
  grid-gap: 1rem;
}

.form-grid__section {
  display: flex;
  flex-wrap: wrap;
  margin: -0.5rem;
}

.form-grid__item {
  flex: 1;
  display: grid;
  margin: 0.5rem;
}

</style>