<script>
  import EventItem from "./EventItem.svelte";
  export let events;
</script>

<style>
  .events-wrapper {
    margin-top: 5px;
    display: grid;
    grid-gap: 5px;
    grid-template-columns: repeat(auto-fit, minmax(370px, 1fr));
    grid-auto-rows: 300px;
    grid-auto-flow: dense;
  }
</style>

<section class="inner events-wrapper">
  {#each events as event}
    <EventItem
      name={event.name}
      startDate={event.startDate}
      category={event.category}
      price={event.price}
      priceCurrency={event.priceCurrency}
      isAccessibleForFree={event.isAccessibleForFree}
      location={event.location}
      streetAddress={event.streetAddress}
      image={event.image}
      favStatus={event.favStatus} />
  {/each}
</section>
