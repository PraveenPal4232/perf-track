<script>
  import { Link } from "svelte-routing";

  export let hideDescription = false;
  const getProps = () => ({ "style": 'display: flex; align-items: center; text-decoration: none;' });
</script>

<style>
	div {
    padding: 2rem 0;
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: space-between;
    box-sizing: border-box;
  }

  img {
    max-height: 16px;
    margin-right: 0.8rem;
  }

  a, span {
    color: #333333;
    font-weight: 600;
    transition: all .1s ease-in-out;
    text-decoration: none;
  }

  p a:hover, a:hover, span:hover, .about-link span:hover {
    text-decoration: none;
    color: #ff6168;
    font-weight: 600;
  }
  
  p a {
    font-weight: 600;
  }

  .about-link {
    display: flex;
    align-items: center;
    padding: 0;
  }

  .about-link span {
    font-weight: 600;
  }

  @media (max-width: 1240px) {
    div {
      display: none;
    }
  }
</style>

<div>
  <Link getProps="{getProps}" to="about">
    <div class="about-link">
      <img src="/images/perf-track-logo.png" alt="Flame logo" />
      <span>About</span>
    </div>
  </Link>
  <p>
    {#if !hideDescription}
    Data from <a href="https://httparchive.org/">HTTP Archive</a> and <a href="https://developers.google.com/web/tools/chrome-user-experience-report">Chrome User Experience Report</a>
    {/if}
  </p>
  <a href="https://github.com/GoogleChromeLabs/perf-track">
    GitHub
  </a>
 </div>