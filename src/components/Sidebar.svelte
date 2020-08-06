<script>
    import Profile from "./Profile.svelte";
    import Footer from "./Footer.svelte";
    import Stories from "./Stories.svelte";

    export let count;
    export let pages;
    console.log("nombre"+pages);

</script>

<style>
     .Sidebar {
    position: relative;
    padding: 4.5em 0 0 0;
  }
  .Sidebar-container {
    position: fixed;
  }
</style>

<div class="Sidebar">
    <div class="Sidebar-container">
        <Profile {pages} {count}/>
        <Stories/>
        <Footer/>
    </div>
</div>