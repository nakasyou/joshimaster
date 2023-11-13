<script lang="ts">
  import malko_ from '../assets/malko.json'
  import wordDatas_ from '../assets/words.json'
  const malko: Record<string, string[] | undefined> = malko_
  const wordDatas: Record<string, {
    body: string
    joshi?: string | undefined
  }> = wordDatas_

  const malkoEntries = Object.entries(malko)
  let words: {
    word: string
    joshi: string
  }[] = []
  words.push(...malkoEntries[Math.floor(malkoEntries.length * Math.random())][0].split(' ').map(entry => {
    return {
      word: entry,
      joshi: wordDatas[entry].joshi || ''
    }
  }))

  for (let i = 0; i !== 10000; i++) {
    const key = words.slice(-2).join(' ')
    
    const nextEntries = malko[key]
    if (!nextEntries) {
      break
    }
    const nextEntry = nextEntries[Math.floor(Math.random() * nextEntries.length)]
    words.push({
      word: nextEntry,
      joshi: wordDatas[entry].joshi || ''
    })
  }
</script>
<div>
  {#for}
  { words.join('') }
</div>