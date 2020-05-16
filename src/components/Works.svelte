<script>
  import Work from './Work.svelte'
  import SubNav from './SubNav.svelte'

  export let works
  let worksHeight
  let selectedWork = works[0]

  const selectWork = (work) => selectedWork = work
</script>


<div class='works-container' bind:clientHeight={worksHeight}>
  <div class='works'>
    <div class='work-container' style='--max-height: {worksHeight - 104}px'>
      <Work
        header={selectedWork.title}
        body={selectedWork.description}
        media={selectedWork.media}
        outLink={selectedWork.outLink} />
    </div>
    <SubNav
      navItems={works}
      selectedWork={selectedWork}
      selectWork={selectWork} />
  </div>
</div>

<style>
  .works-container {
    display: flex;
    flex-direction: column;
    box-sizing: border-box;
    padding: 20px;
    width: 100%;
    flex: 1;
  }
  .works {
    width: 100%;
    display: flex;
    flex: 1;
    flex-direction: column;
    justify-content: space-between;
    align-items: center;
  }

  .work-container {
    display: flex;
    height: var(--max-height);
  }
</style>
