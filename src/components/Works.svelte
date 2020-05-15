<script>
  import Work from './Work.svelte'
  import SubNav from './SubNav.svelte'

  export let works
  let selectedWork = works[0]

  const selectWork = (work) => selectedWork = work
</script>

<div class='works'>
  <Work
    header={selectedWork.title}
    body={selectedWork.description}
    media={selectedWork.media} />
  <SubNav
    navItems={works}
    selectedWork={selectedWork}
    selectWork={selectWork} />
</div>

<style>
  .works {
    width: 100%;
    display: flex;
    flex: 1;
    flex-direction: column;
    justify-content: space-between;
    align-items: center;
  }
</style>
