<script>
  import Works from './components/Works.svelte'

  let uid = 1
  const tech = [

  ]
</script>

<div class='tech'>
  <Works works={tech} />
</div>

<style>
  .tech {
    display: flex;
    flex-direction: column;
    box-sizing: border-box;
    padding: 20px;
    width: 100%;
    height: 100%;
    position: absolute;
  }
</style>
