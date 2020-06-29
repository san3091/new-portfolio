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
    position: absolute;
    height: 100%;
    display: flex;
  }

  .works {
    width: 100%;
    padding: 20px;
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

  @media only screen and (max-width: 1000px) {
    .works {
      flex-direction: column-reverse;
    }
  }
</style>
