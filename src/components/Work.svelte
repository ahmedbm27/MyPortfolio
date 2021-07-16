<script>
import {hexToRgb,convert} from "../filter.js"
import {onMount} from "svelte"
import {lang} from "../store.js"
let colors =["#F9004D","#40D774","#ECAF02","#F74539","#017FDD","#9E37AA","#F1BB1B","#FF0000"]
let patterns = ["p1","p2","p3","p4"]
let done = false
onMount(async()=>{

    await works.map(el =>{
        el.color=randomFromArray(colors)
    })
    done=true
})



let works = 
[
    {
        link:"unify",
        title:"Unify.tn",
        type:"Content Creator Oriented Startup",
        typeFR:"Startup orientée créateur de contenu",
        date:"2020 - Present",
        dateFR:"2020 - Présent",
        technologies:["Firebase","Svelte","Netlify","Express.js"],
        github:"https://github.com/OmG3r/unify",
        demo:"https://unify.tn",
        logo:"./imgs/work/unify.png",
    },
    {
        link:"messenger_clone",
        title:"Messenger",
        type:"Messenger Chat App Clone",
        typeFR:"Clone de l'application de Chat Messenger  ",
        dateFR:"2021 - Présent",
        date:"2021 - Present",
        technologies:["Firebase","Svelte","Netlify","Firechat"],
        github:"https://github.com/ahmedbm27/Messenger-Clone",
        demo:"https://svelte.messenger.ahmedbm.com",
        logo:"./imgs/work/messenger.png",
        color:""
    },
    {
        link:"youtube_clone",
        title:"Youtube",
        type:"Youtube Landing and Video Player Clone",
        typeFR:"Youtube Landing et lecteur vidéo Clone",
        dateFR:"2021 - Présent",
        date:"2021 - Present",
        technologies:["Firebase","Svelte","Netlify","Youtube API"],
        github:"https://github.com/ahmedbm27/Youtube_clone",
        demo:"https://svelte.youtube.ahmedbm.com",
        logo:"./imgs/work/youtube.png",
        color:""
    },
    {
        link:"gigaservices",
        title:"Gigaservices",
        type:"GSM Recharge Cards Wholesale",
        typeFR:"Cartes de recharge GSM en gros",
        date:"2017 - 2020",
        dateFR:"2017 - 2020",
        technologies:["Firebase","Svelte"],
        github:"https://github.com/ahmedbm27/gigaservices",
        demo:"https://gigaservices.tn",
        logo:"./imgs/work/gigaservices.png",
        color:""
    },
    {
        link:"hana_boukhris",
        title:"Hana Boukhris",
        type:"Personal Portfolio",
        typeFR:"Portefeuille personnel",
        dateFR:"2020",
        date:"2020",
        technologies:["Wordpress","Oxahost"],
        github:"",
        demo:"https://hanaboukhris.com/",
        logo:"./imgs/work/hana.png",
        color:""
    }
]

const randomFromArray = (array) =>{
    return array[Math.floor(Math.random() * array.length)]
}
const hoverMe = (color) =>{
    let filter = convert(color).replace('filter:','').replace(";","");
    document.documentElement.style.setProperty('--hover', color);
    document.documentElement.style.setProperty('--hoverFilter', filter);   
}

</script>
<style>
.work{
    color: white;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding: 50px 0px;

}
h1{
    font-size: 50px;
    font-weight: 800;
    margin: 0;
}
h2{
    
    font-size: 30px;
}
.workCards{
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    

}
.singleCard{
    display: flex;
    flex-direction: column;
    padding: 25px;
    position: relative;
    background-color: #212023;
    border-radius: 15px;
    margin: 15px;
    overflow: hidden;
    width: 21%;
    justify-content: space-between;
}
.logo{
background-color: #F9004D;
border-radius: 10px;
padding: 15px;
width: max-content;
display: flex;
justify-content: center;
align-items: center;
position: absolute;
top: 20px;
left: 20px;
width: 45px;
height: 45px;
}
.logo img{
    width: 45px;
}
.viewDetails{
border-radius: 10px;
padding: 8px 12px;
background-color:#66A559;
width: max-content;
font-size: 18px;
font-weight: 600;
position: absolute;
top: 20px;
right: 20px;
cursor: pointer;
}
.viewDetails:hover{
border:1px solid #66A559;
background-color:transparent;
padding: 7px 11px;
}
.viewDetails:hover a{
color: #66A559;

}
.viewDetails a{
    text-decoration: none;
    color: white;
}
.pattern{
position: absolute;
bottom: 0;
right: 0;
filter: invert(73%) sepia(75%) saturate(447%) hue-rotate(78deg) brightness(91%) contrast(83%);
width: 40%;
}
.title{
margin-top: 100px;
font-weight: 400;
font-size: 17px;
}
.type{
    margin: 0;
    width: 80%;
    font-size: 25px;
}
.date{
    font-weight: 400;
    font-size: 20px;
    margin: 10px 0 0 0 ;
}
.technologies{
    display: flex;
    flex-wrap: wrap;
    font-size: 13px;
    margin-top: 20px;
    font-family: 'Roboto Mono', monospace;
    width: 65%;
}
.technologies .el{
    margin: 0 25px 10px 0;
    cursor: pointer;
}
.technologies .el:hover{
    color: var(--hover)
}

.links img{
width: 20px;
filter: invert(100%) sepia(76%) saturate(0%) hue-rotate(336deg) brightness(109%) contrast(101%);
margin:30px 20px 0 0;
cursor: pointer;
}
.links a:hover img{
filter: var(--hoverFilter)
}

@media only screen and (max-width:1200px){
    .singleCard{
        width: 40%;
    }

}
@media only screen and (max-width:800px){
    .singleCard{
        width: 55%;
    }

}
@media only screen and (max-width:600px){
    .singleCard{
        width: 100%;
    }

}
</style>

<div class="work" id="work">


<h1>{{"en":"/Projects","fr":"/Projets"}[$lang]}</h1>
<h2>{{"en":"Some Things I've Built","fr":"Quelques choses que j'ai construit"}[$lang]}</h2>
{#if done}
<div class="workCards">

    {#each works as work}
    <div class="singleCard">
        <div class="logo" style="background-color:{work.color} !important">

            <img src="{work.logo}" alt="logo">
        </div>
        <div class="viewDetails"><a href="/works/{work.link}" target="_blank">{{"en":"View Details","fr":"Voir les détails"}[$lang]}</a> </div>

        <img 
        class="pattern" 
        style="filter:{convert(work.color).replace('filter:','').replace(";","")}"
        src="./imgs/patterns/{randomFromArray(patterns)}.png" 
        alt="Pattern">

        <h4 class="title">{work.title}</h4>
        <h2 class="type">{{"en":work.type,"fr":work.typeFR}[$lang]}</h2>
        <h3 class="date">{{"en":work.date,"fr":work.dateFR}[$lang]}</h3>
        <div class="technologies">
            {#each work.technologies as tech}
            <div on:mouseover="{()=>hoverMe(work.color)}"  class="el">{tech}</div>
            {/each}
        </div>
        <div class="links">
            {#if work.github !==""}
            <a href="{work.github}" target="_blank"><img on:mouseover="{()=>hoverMe(work.color)}" src="./imgs/icons/github.svg" alt="github" ></a>
            {/if}
            <a href="{work.demo}" target="_blank"><img on:mouseover="{()=>hoverMe(work.color)}" src="./imgs/icons/link.svg" alt="link" ></a>
            
        </div>
    </div>
    {/each}
</div>
{/if}


</div>

