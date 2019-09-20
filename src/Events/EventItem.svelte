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
  export let image;
  export let favStatus;
  import FaRegHeart from "svelte-icons/fa/FaRegHeart.svelte";
  import FaHeart from "svelte-icons/fa/FaHeart.svelte";

  let eventDate = new Date(startDate);

  let monthNum = eventDate.getMonth() + 1;
  let dayName = eventDate.getDay();
  let dayNum = eventDate.getDate();

  export let monthText = "";
  switch (monthNum) {
    case 1:
      monthText = "Ene";
      break;
    case 2:
      monthText = "Feb";
      break;
    case 3:
      monthText = "Mar";
      break;
    case 4:
      monthText = "Abr";
      break;
    case 5:
      monthText = "May";
      break;
    case 6:
      monthText = "Jun";
      break;
    case 7:
      monthText = "Jul";
      break;
    case 8:
      monthText = "Ago";
      break;
    case 9:
      monthText = "Sep";
      break;
    case 10:
      monthText = "Oct";
      break;
    case 11:
      monthText = "Nov";
      break;
    case 12:
      monthText = "Dic";
      break;
  }
</script>

<style>
  article {
    box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
    background-position: center center;
    background-repeat: no-repeat;
    border-radius: 2px;
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
    padding-top: 3px;
    width: 32px;
    height: 32px;
    color: var(--main_light);
  }

  .fav:hover {
    opacity: 80%;
    cursor: pointer;
  }

  .box-date {
    color: var(--main_light);
  }

  .date-text {
    text-transform: uppercase;
    line-height: 0;
  }

  .date-text > span {
    font-size: 40px;
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
    margin: 0;
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

<!-- <a class="article-link" href="/"> -->
<article style="background-image: url({image});">
  <header>
    <time class="box-date" datetime={startDate} content={startDate}>
      <h4 class="date-text">
        <span>{dayNum}</span>
        {monthText}
      </h4>
    </time>
    <div class="fav">
      {#if favStatus === false}
        <FaRegHeart />
      {:else}
        <FaHeart />
      {/if}
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
<!-- </a> -->
