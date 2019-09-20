<script>
  import MainHeader from "./Components/MainHeader.svelte";
  import Fetch from "./Components/Fetch.svelte";
  import EventsGrid from "./Events/EventsGrid.svelte";
  import AddEvent from "./Events/AddEvent.svelte";
  
  

  const events = [
    {
      id: "e1",
      name: "Ciclo de Conferencias: El Derecho de Autor en Bibliotecas",
      startDate: "2019-09-12T21:30",
      endDate: "2019-09-14T22:30",
      category: "Conferencia",
      location: "A seis Manos",
      streetAddress: "Calle falsa 123",
      price: "2500",
      isAccessibleForFree: "false",
      priceCurrency: "COP",
      description:
        "Quam lutpat quam dolortis. Nullandiat lortie nit feugiat minis, euguerostie. Delesto eugiatet magnim facipsustio etue. Velenibh velessim dolorpercing suscipi at esed. Ero conulputat dionsenim laore quip tumsandionse con aciliquisim tisiscipis.",
      image: "images/fuji.jpg",
      favStatus: false,
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
      isAccessibleForFree: "true",
      priceCurrency: "COP",
      description:
        "Quam lutpat quam dolortis. Nullandiat lortie nit feugiat minis, euguerostie. Delesto eugiatet magnim facipsustio etue. Velenibh velessim dolorpercing suscipi at esed. Ero conulputat dionsenim laore quip tumsandionse con aciliquisim tisiscipis.",
      image:
        "https://upload.wikimedia.org/wikipedia/commons/thumb/6/69/Olympic_swimming_pool_%28Tbilisi%29.jpg/800px-Olympic_swimming_pool_%28Tbilisi%29.jpg",
      favStatus: false,
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
      isAccessibleForFree: "false",
      priceCurrency: "COP",
      description:
        "Quam lutpat quam dolortis. Nullandiat lortie nit feugiat minis, euguerostie. Delesto eugiatet magnim facipsustio etue. Velenibh velessim dolorpercing suscipi at esed. Ero conulputat dionsenim laore quip tumsandionse con aciliquisim tisiscipis.",
      image:
        "https://upload.wikimedia.org/wikipedia/commons/thumb/4/44/Cucurbita_2018_G1.jpg/1280px-Cucurbita_2018_G1.jpg",
      favStatus: false,
    }
  ];
</script>

<style>
  :global(:root) {
    --main_focus: #800000;
    --main_black: #161616;
    --main_innactive:  #505050 ;
    --main_bg: #fcfcfc;
    --main_light: #fafafa;
    --main_font: "OpenSans", sans-serif;
    --header_font: "Montserrat", sans-serif;
  }

</style>

<MainHeader />
<AddEvent/>
<!-- <EventsGrid {events}/> -->

