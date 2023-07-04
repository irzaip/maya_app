<script>
  import { onMount } from 'svelte'
  import { banner, art } from "../assets/asciiArt.js"
  import TerminalInput from './TerminalInput.svelte';

  let container

  onMount(
  () => {

    function addLine(text, style) {
    let line = document.createElement("p")
    line.innerHTML = text
    line.classList.add("text-white")
    container.appendChild(line)
  }

  function renderBanner() {
    for (let i = 0; i < banner.length; i++) {
      if (i == banner.length - 1) {
        addLine(banner[i], ["line", "mb-4"])
      } else {
        addLine(banner[i], ["line"])
      }
    }
  }

  renderBanner()
  }
   )

</script>

<section class="container mx-auto">
  <div>
    <div bind:this={container} />
    <TerminalInput />
  </div>

</section>

<style>
  :global(html) {
    background-color: black;
    @apply font-mono;
  }
</style>