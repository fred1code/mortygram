<script>
import {onMount} from 'svelte';
import Header from '../components/Header.svelte';
import Main from '../components/Main.svelte';
import TimeLine from '../components/TimeLine.svelte';
import Sidebar from '../components/Sidebar.svelte';
import Card from '../components/Card.svelte';
import Comments from '../components/Comments.svelte';
import Footer from '../components/Footer.svelte';

let rand =  getRandom();
let data ={};
let API = `https://rickandmortyapi.com/api/character/?page=${rand}`;
console.log(API);
onMount(async()=>{
    const response = await fetch(API);
    data = await response.json();
    console.log(data.results[0]);  
});

console.log(rand);


function getRandom(){
    return Math.round(Math.random() * (30 - 1) + 1);
}

</script>

<style>
    @import url('https://fonts.googleapis.com/css2?family=Lato:wght@300;400&display=swap');
    @import url('https://fonts.googleapis.com/css2?family=Pacifico&display=swap');
    :global(body){
        font-family: "Lato", sans-serif;
        background-color: #fafafa;
        color: rgba(38, 38, 38, 0.7);
        margin: 0;
        padding: 0;        
    }
    :global(h1,h2,h3){
        margin: 0;
        padding: 0;
    }
</style>

<Header/>
<Main>
<TimeLine posts={data.results}/>
<Sidebar {...data.info}/>
</Main>