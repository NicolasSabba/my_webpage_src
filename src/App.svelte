<script>
	import Baner from "./components/Baner.svelte";
</script>

<style>
  :global(body) {
		margin: 0px;
		padding: 0px;
    height: max-content;
    max-width: none;
    background-color: var(--background-color-light);
    font-family: Quicksand;
  }

  #background {
    position: absolute;
    overflow: hidden;
    height: 100%;
    width: 100%;
    top: 0;
    left: 0;
    bottom: 0;
    right: 0;
    z-index: -1;
    padding: 0px;
    margin: 0px;
    opacity: 0.08;
    background-blend-mode: color-burn;
    background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='40' height='40' viewBox='0 0 40 40'%3E%3Cg fill-rule='evenodd'%3E%3Cg fill='%23000000' fill-opacity='1'%3E%3Cpath d='M0 38.59l2.83-2.83 1.41 1.41L1.41 40H0v-1.41zM0 1.4l2.83 2.83 1.41-1.41L1.41 0H0v1.41zM38.59 40l-2.83-2.83 1.41-1.41L40 38.59V40h-1.41zM40 1.41l-2.83 2.83-1.41-1.41L38.59 0H40v1.41zM20 18.6l2.83-2.83 1.41 1.41L21.41 20l2.83 2.83-1.41 1.41L20 21.41l-2.83 2.83-1.41-1.41L18.59 20l-2.83-2.83 1.41-1.41L20 18.59z'/%3E%3C/g%3E%3C/g%3E%3C/svg%3E");
  }

  :global(:root) {
    --background-color-dark: #525057;
    --background-color-light: #eff3ef;
    --accent-dark: #c35638;
    --accent-light: #8d9096;
    --main-color: #f4c35b;
  }
</style>

<svelte:head>
  <title>Nicolas C. Sabbatini V.</title>
  <link
    rel="stylesheet"
    type="text/css"
    href="//fonts.googleapis.com/css?family=Quicksand" />
</svelte:head>

<main>
  <div id="background" />
	<Baner></Baner>
	<p>asdasd</p>
	<p>asdasd</p>
	<p>asdasd</p>
	<p>asdasd</p>
	<p>asdasd</p>
	<p>asdasd</p>
</main>
