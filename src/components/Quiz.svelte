<script lang="ts">
  import malko_ from '../assets/malko.json'
  const malko: Record<string, string[] | undefined> = malko_
  const malkoEntries = Object.entries(malko)
  let words: {
  }[] = []
  words.push(...malkoEntries[Math.floor(malkoEntries.length * Math.random())][0].split(' '))

  for (let i = 0; i !== 10000; i++) {
    const key = words.slice(-2).join(' ')
    
    const nextEntries = malko[key]
    if (!nextEntries) {
      break
    }
    const nextEntry = nextEntries[Math.floor(Math.random() * nextEntries.length)]
    words.push(nextEntry)
  }
</script>
<div>
  { words.join('') }
</div>