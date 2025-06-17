<script lang="js">
  import Home from './routes/Home.svelte';
  import TutorialHome from './routes/TutorialHome.svelte';
  import Tutorials from './routes/Tutorials.svelte';
  import {Router, Route} from 'svelte-routing';
  import NavBar from './components/NavBar.svelte';
  import Academics from './routes/Academics.svelte';
  import CSENGlossary from './routes/CSENGlossary.svelte';
  import PastMeetings from './routes/PastMeetings.svelte';
  import Career from './routes/Career.svelte';
  import ResumeGuide from './routes/ResumeGuide.svelte';

  export let url = "";
  let hidden = true;

  function scrollContainer() {
    return document.documentElement || document.body;
  }

  function handleOnScroll() {
    if (!scrollContainer()) {
      return;
    }

    if (scrollContainer().scrollTop > 150) {
      hidden = false;
    } else {
      hidden = true;
    }
  }

  
</script>

<svelte:window on:scroll={handleOnScroll} />

<Router {url}>
  <header>
    <h1>ACM Wiki</h1>
    <NavBar/>
  </header>
  <button class="up" on:click={() => {document.body.scrollIntoView()}} class:hidden>↑</button>

  <div class="container-fluid">
    <Route path="tutorials"> <TutorialHome/></Route>
    <Route path="tutorials/:name" let:params> <Tutorials name="{params.name}"/></Route>
    <Route path="/"><Home /></Route>
    <Route path="academics"><Academics/></Route>
    <Route path="academics/csen-glossary"> <CSENGlossary/> </Route>
    <Route path="acmhistory"> <PastMeetings/> </Route>
    <Route path="career"><Career/></Route>
    <Route path="career/resume-guide"> <ResumeGuide/> </Route>
  </div>
</Router>



<style>
  :global(main) {
    margin-inline: 2rem;
    margin-top: 2rem;
    display: flex;
    flex-direction: column;
  }
  :global(a) {
    text-decoration: none;
  }
  header {
    background-color: #08347A;
    top: 0;
    flex-direction: row;
    align-items: flex-start;
    display: flex;
    height: 4rem;
    z-index: 1000;
  }
  h1 {
    margin-block: auto;
    margin-inline: 1rem;
  }
  button.up {
    position: fixed;
    border-radius: 50%;
    display: block;
    height: 2em;
    width: 2em;
    bottom: 2rem;
    align-content: center;
    right: 2rem;
    padding: 0;
  }
  button.up.hidden {
    display: none;
  }

</style>
