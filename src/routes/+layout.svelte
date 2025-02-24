<script lang="ts">
	//import '../app.css';
	let { children } = $props();
  import Banner from '$lib/banner.svelte';
	//import '@blaze/atoms'
</script>
<head>
    <link
  rel="stylesheet"
  href="https://cdn.jsdelivr.net/npm/@picocss/pico@2/css/pico.min.css"
>
</head>
<div class="banner">
<Banner></Banner>
</div>


<div class="container-fluid">
  <nav>
    <ul>
      <li><a class="contrast" href="/"><strong>Max Mata's Math Tutoring</strong></a></li>
    </ul>
    <ul>
      <li>
        <details class="dropdown">
          <summary>Sections</summary>
          <ul><li><a href="/Algebra">Algebra</a></li>
            <li><a href="/Geometry">Geometry</a></li>
            <li><a href="/Calculus">Calculus</a></li>
            <li><a href="/Statistics">Statistics</a></li>
            <li><a href="/Students">Students</a></li></ul>
        </details>
      </li>
      
    </ul>
  </nav>
</div>

  {@render children()}


<style>

  .banner{
        text-align: center;
        height: 8vh;
        background-color: #31343a;
        color: whitesmoke;
        align-items: center;
        align-content: center;
        max-height: 10vh;
        width: 100%;
    }
</style>
