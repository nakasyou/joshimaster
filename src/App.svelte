<script lang="ts">
  import Quiz from "./components/Quiz.svelte";
import Start from "./components/Start.svelte"

  let isPlaying = false
</script>

<main>
  <div class="text-center">
    <div class="text-2xl">JosiMaster</div>
    <p>マルコフ連鎖のソース: ChatGPT</p>
  </div>
  {#if !isPlaying}
    <Start start={() => {
      isPlaying = true
    }}/>
  {/if}
  <Quiz />
</main>
