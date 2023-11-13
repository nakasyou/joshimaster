<script lang="ts">
  import Quiz from "./components/Quiz.svelte"
</script>

<main>
  <div class="text-center my-2">
    <div class="text-2xl">JosiMaster</div>
    <p>マルコフ連鎖のソース: ChatGPT</p>
    <a href="https://github.com/nakasyou/joshimaster" class="underline hover:no-underline">ソースコードをGitHubで見る</a>
  </div>
  <div class="mx-2">
    <Quiz />
  </div>
  <div class="text-center">
    <button on:click={() => {

    }}>
    </button>
  </div>
</main>
