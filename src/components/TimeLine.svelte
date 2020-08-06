<script>
import Card from './Card.svelte';
import App from '../containers/App.svelte';
import Comments from './Comments.svelte';
import Footer from './Footer.svelte';

export let posts = [];

</script>

<style>
      .TimeLine {
    padding: 4em 0 0 0;
  }
</style>

<div class="TimeLine">
   <div class="TimeLine-container">
     {#each posts as post }
        <Card {...post}/>
     {:else}
      <p>Loading...</p>
     {/each}
      
   </div>
</div>