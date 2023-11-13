<script lang="ts">
  import malko_ from '../assets/data.json'
  const malko: Record<string, {
    body: string
    hinshi?: string
  }[] | undefined> = malko_

  const malkoEntries = Object.entries(malko)
  let words: {
    word: string
    joshi: string
  }[] = []
  const re = () => {
  words = []
  words.push(...malkoEntries[Math.floor(malkoEntries.length * Math.random())][0].split(' ').map(entry => {
    return {
      word: entry,
      joshi: ''
    }
  }))
  for (let i = 0; i !== 100; i++) {
    const key = words.slice(-2).map(e => e.word).join(' ')
    
    const nextEntries = malko[key]
    if (!nextEntries) {
      break
    }
    const nextEntry = nextEntries[Math.floor(Math.random() * nextEntries.length)]
    words.push({
      word: nextEntry.body,
      joshi: nextEntry.joshi || ''
    })
  }
  }
  re()
</script>
<div class="leading-loose text-lg">
  {#each words as word}
    {#if [''].includes(word.joshi)}
      {word.word}
    {:else}
      <button class="px-1 bg-green-100 rounded-lg" on:click={() => {
        alert(`これは${word.joshi}です！`)
      }}>{word.word}</button>
    {/if}
  {/each}
</div>
<div class="text-center">
<button on:click={re} class="bg-red-100 rounded p-1 m-2">
Reset!
</button>
</div>
