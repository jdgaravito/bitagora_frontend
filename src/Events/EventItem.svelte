<script>
  // import Image from "svelte-image";
  export let name;
  export let startDate;
  export let category;
  export let location;
  export let streetAddress;
  export let price;
  export let isAccessibleForFree;
  export let priceCurrency;
  export let description;
  export let image;
  import FaRegHeart from "svelte-icons/fa/FaRegHeart.svelte";
  import FaHeart from "svelte-icons/fa/FaHeart.svelte";
</script>

<style>
  article {
    display: block;
    box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
    background-position: center center;
    background-repeat: no-repeat;
    object-fit: cover;
  }

  article:hover {
    box-shadow: 0px 6px 6px rgba(0, 0, 0, 0.25);
    filter: brightness(100%);
  }

  header {
    display: flex;
    justify-content: space-between;
    padding: 13px;
  }

  .fav {
    width: 32px;
    height: 32px;
    color: var(--main_light);
  }

  .fav:hover {
    opacity: 80%;
  }

  .box-date {
    color: var(--main_light);
  }
  .text-container {
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
    align-self: flex-end;
  }
  .price-tag {
    background: var(--main_light);
    color: var(--main_black);
    max-width: 60px;
    text-align: center;
    line-height: 15px;
    padding: 13px;
    margin-left: 10px;
    font-weight: 700;
    text-transform: uppercase;
    font-family: var(--header_font);
  }

  .event-category {
    color: var(--main_light);
    font-family: var(--header_font);
    opacity: 90%;
    font-size: 0.8rem;
    padding-left: 13px;
    padding-bottom: 2px;
    margin:0;
    margin-top: 50px;
  }

  .event-title {
    color: var(--main_light);
    text-transform: uppercase;
    font-family: var(--header_font);
    font-size: 1.25rem;
    padding-left: 0.8125rem;
    margin: 0;
  }

  .event-location {
    color: var(--main_light);
    padding-left: 0.8125rem;
    margin: 0;
  }
</style>

<article style="background-image: url({image});">
  <header>
    <time class="box-date" datetime={startDate} content={startDate}>
      {startDate}
    </time>
    <div class="fav">
      <FaRegHeart />
    </div>
  </header>
  <div class="price-tag">
    {#if price === '0' || isAccessibleForFree === 'true'}
      Gratis
    {:else}${price}{/if}
  </div>
  <main class="text-container">
    <h4 class="event-category">{category}</h4>
    <h3 class="event-title">{name}</h3>
    <p class="event-location">{location}</p>
  </main>
</article>
