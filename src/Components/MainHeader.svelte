<script>
  import FaFacebookF from "svelte-icons/fa/FaFacebookF.svelte";
  import FaInstagram from "svelte-icons/fa/FaInstagram.svelte";
  import FaTwitter from "svelte-icons/fa/FaTwitter.svelte";
</script>

<style>
  .logo-img {
    max-width: 300px;
    padding: 50px 0 50px 0;
  }
  .top-wrapper {
    background: var(--main_black);
  }
  .top-container {
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
  .top-header {
    color: var(--main_light);
    text-transform: uppercase;
    font-family: var(--header_font);
  }
  .top-header a {
    color: var(--main_light);
    text-decoration: none;
    line-height: 2.5rem;
    font-size: 0.75rem;
    letter-spacing: 1px;
    font-weight: 700;
    padding: 10px 10px 10px 0px;
  }
  .top-header a:hover {
    opacity: 80%;
  }
  .social_icons {
    display: flex;
    align-content: flex-end;
  }
  .icon {
    color: var(--main_light);
    width: 1.25rem;
    height: 1.25rem;
    padding: 0.625rem;
  }

  .icon a {
    color: var(--main_light);
  }
  .icon a:hover {
    opacity: 80%;
  }
  .header-inner {
    background: var(--main_bg);
  }

  .main-nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
    color: var(--main_black);
    text-transform: uppercase;
    font-weight: 700;
    font-family: var(--header_font);
    font-size: 1rem;
    line-height: 10px;
    letter-spacing: 0.075rem;
    border-bottom: 0.1875rem solid var(--main_black);
  }

  .page_menu a {
    text-decoration: none;
    color: var(--main_black);
    padding: 0.625rem;
  }
  .page_menu a:hover {
    background: var(--main_focus);
    color: var(--main_light);
  }

  .featured-nav-item {
    padding: 1rem;
  }
  .featured-nav-item:hover {
    background: var(--main_focus);
    color: var(--main_light);
  }
</style>

<header class="main-header">
  <div class="wrapper top-wrapper">
    <div class="inner top-container">
      <nav class="top-header ">
        <a href="/">Acerca de</a>
        <a href="/">Contáctanos</a>
      </nav>
      <div class="social_icons">
        <div class="icon">
          <a
            target="_blank"
            rel="noopener noreferrer"
            href="https://www.facebook.com/labitagora">
            <FaFacebookF />
          </a>
        </div>
        <div class="icon">
          <a
            target="_blank"
            rel="noopener noreferrer"
            href="https://www.instagram.com/labitagora">
            <FaInstagram />
          </a>
        </div>
        <div class="icon">
          <a
            target="_blank"
            rel="noopener noreferrer"
            href="https://www.twitter.com/labitagora">
            <FaTwitter />
          </a>
        </div>
      </div>

    </div>

  </div>
  <div class="header">
    <div class="inner header-inner">
      <div class="logo-section">
        <img class="logo-img" src="bitagora-logo.svg" alt="logo-bitagora" />
      </div>
      <div class="main-nav">
        <nav class="page_menu">
          <a href="/" class="active">Inicio</a>
          <a href="/">Bogotá Gratis</a>
          <a href="/">Bici</a>
          <a href="/">Blog</a>
        </nav>
        <div class="featured-nav" />
        <p class="featured-nav-item">Destacado</p>
      </div>
    </div>
  </div>
</header>
