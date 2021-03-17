<script>
  import marked from 'marked'

  let name = ''

  let a = 1
  let b = 2

  let yes = false

  let text = `Some words are *italic*, some are **bold**`

  let files

  $: if (files) {
    console.log(files)

    for (const file of files) {
      console.log(`${file.name}: ${file.size} bytes`)
    }
  }
</script>

<style>
  textarea {
    width: 100%;
    height: 200px;
  }
</style>

<input bind:value={name} placeholder="enter your name">
<p>Hello {name || 'stranger'}!</p>

<label>
  <input type="number" bind:value={a} min=0 max=10>
  <input type="range" bind:value={a} min=0 max=10>
</label>

<label>
  <input type="number" bind:value={b} min=0 max=10>
  <input type="range" bind:value={b} min=0 max=10>
</label>

<p>{a} + {b} = {a + b}</p>

<label>
  <input type="checkbox" bind:checked={yes}>
  Yes! Send me regular email spam
</label>

{#if yes}
  <p>Thank you. We will bombard your inbox and sell your personal details.</p>
{:else}
  <p>You must opt in to continue. If you're not paying, you're the product.</p>
{/if}

<button disabled={!yes}>
  Subscribe
</button>

<textarea bind:value={text}></textarea>

{@html marked(text)}

<label for="avater">
  Upload a picture:
</label>

<input
  accept="image/jpeg, image/png"
  bind:files
  id="avater"
  name="avater"
  type="file"
/>

<label for="many">Upload multiple files of any type:</label>
<input type="file" name="" id="">
