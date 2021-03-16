<script>
  import Inner from './inner.svelte'

  function handleMessage(event) {
    alert(event.detail.text)
  }
</script>

<Inner on:message={handleMessage}/>
