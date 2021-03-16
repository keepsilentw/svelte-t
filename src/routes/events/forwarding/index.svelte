<script>
  import Outer from './outer.svelte'

  function handleMessage(event) {
    alert(event.detail.text)
  }
</script>

<Outer on:message={handleMessage}/>
