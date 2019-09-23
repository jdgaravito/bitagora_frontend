<script>
  import MainHeader from "./Components/MainHeader.svelte";
  import Fetch from "./Components/Fetch.svelte";
  import EventsGrid from "./Events/EventsGrid.svelte";
  import AddEvent from "./Events/AddEvent.svelte";
  import FormInput from "./Components/Elements/FormInput.svelte";

  let name = "";
  let startDate = "";
  let startTime = "";
  let endDate = "";
  let endTime = "";
  let category = "";
  let location = "";
  let description = "";
  let streetAddress = "";
  let price = "";
  let image = "";
  let favStatus = false;

  let events = [
    {
      id: "e1",
      name: "Ciclo de Conferencias: El Derecho de Autor en Bibliotecas",
      startDate: "2019-09-12T21:30",
      endDate: "2019-09-14T22:30",
      category: "Conferencia",
      location: "A seis Manos",
      streetAddress: "Calle falsa 123",
      price: "2500",
      priceCurrency: "COP",
      description:
        "Quam lutpat quam dolortis. Nullandiat lortie nit feugiat minis, euguerostie. Delesto eugiatet magnim facipsustio etue. Velenibh velessim dolorpercing suscipi at esed. Ero conulputat dionsenim laore quip tumsandionse con aciliquisim tisiscipis.",
      image: "images/fuji.jpg",
      favStatus: false
    },

    {
      id: "e2",
      name: "Presentación del Libro: Miénteme Si Puedes",
      startDate: "2019-09-14T21:30",
      endDate: "2019-09-14T22:30",
      category: "Literatura",
      location: "A seis Manos",
      streetAddress: "Calle falsa 123",
      price: "0",
      priceCurrency: "COP",
      description:
        "Quam lutpat quam dolortis. Nullandiat lortie nit feugiat minis, euguerostie. Delesto eugiatet magnim facipsustio etue. Velenibh velessim dolorpercing suscipi at esed. Ero conulputat dionsenim laore quip tumsandionse con aciliquisim tisiscipis.",
      image:
        "https://upload.wikimedia.org/wikipedia/commons/thumb/6/69/Olympic_swimming_pool_%28Tbilisi%29.jpg/800px-Olympic_swimming_pool_%28Tbilisi%29.jpg",
      favStatus: false
    },

    {
      id: "e3",
      name: "Inauguración Exposición “Con un Pie en La Tierra",
      startDate: "2019-09-15T21:30",
      endDate: "2019-09-14T22:30",
      category: "Exposición",
      location: "A seis Manos",
      streetAddress: "Calle falsa 123",
      price: "2500",
      priceCurrency: "COP",
      description:
        "Quam lutpat quam dolortis. Nullandiat lortie nit feugiat minis, euguerostie. Delesto eugiatet magnim facipsustio etue. Velenibh velessim dolorpercing suscipi at esed. Ero conulputat dionsenim laore quip tumsandionse con aciliquisim tisiscipis.",
      image:
        "https://upload.wikimedia.org/wikipedia/commons/thumb/4/44/Cucurbita_2018_G1.jpg/1280px-Cucurbita_2018_G1.jpg",
      favStatus: false
    }
  ];

  function addEvent() {
    const newEvent = {
      id: Math.random().toString(),
      name: name,
      description: description,
      category: category,
      startDate: startDate,
      price: price,
      location: location,
      image: image
    };
    events = [newEvent, ...events];
  }
</script>

<style>
  :global(:root) {
    --main_focus: #800000;
    --main_black: #161616;
    --main_innactive: #505050;
    --main_bg: #fcfcfc;
    --main_light: #fafafa;
    --main_font: "OpenSans", sans-serif;
    --header_font: "Montserrat", sans-serif;
  }

  form{width: 30rem;
  max-width: 90%;
  margin: auto;}
</style>

<MainHeader />
<EventsGrid {events} />
<main class="inner">

  <!-- export let controlType;
  export let id;
  export let label;
  export let rows;
  export let type;
  export let value;
  export let placeholder; -->
  <form on:submit|preventDefault={addEvent}>
    <FormInput
      id="name"
      label="Nombre del Evento"
      type="text"
      value={name}
      on:input={event => (name = event.target.value)} />
    <FormInput
      id="category"
      label="Categoria del evento"
      type="text"
      value={category}
      on:input={event => (category = event.target.value)} />
    <FormInput
      id="streetAddress"
      label="Dirección del evento"
      type="text"
      value={streetAddress}
      on:input={event => (streetAddress = event.target.value)} />
    <FormInput
      id="image"
      label="Url de la imagen del evento"
      type="text"
      value={image}
      on:input={event => (image = event.target.value)} />
    <FormInput
      id="price"
      label="Precio"
      controlType="number"
      value={price}
      on:input={event => (price = event.target.value)} />
    <FormInput
      id="startDate"
      label="Fecha de inicio"
      controlType="date"
      value={startDate}
      on:input={event => (startDate = event.target.value)} />
    <FormInput
      id="description"
      label="Description"
      controlType="textarea"
      rows="3"
      value={description}
      on:input={event => (description = event.target.value)} />
    <button type="submit">Guardar evento</button>
  </form>
</main>
