<script>
import {navigate} from 'svelte-routing'
import {lang} from "../store.js"
import Typewriter from 'typewriter-effect/dist/core';


let writing = () =>{
    let app = document.getElementById('webDev');
        let typewriter = new Typewriter(app, {
            loop: true
        })
       
        typewriter.typeString({'fr':'Développeur web','en':'Web Developer'}[$lang])
        .pauseFor(1000)
        .deleteAll()
        .typeString({'fr':'Développeur JS','en':'JS Developer'}[$lang])
        .pauseFor(1000)
        .deleteAll(7)
        .typeString({'fr':'Diplômé en administration des affaires','en':'Business Administration Graduate'}[$lang])
        .pauseFor(1000)
        .start(); 
}

let opened= false;
    
$: console.log($lang)
</script>
<style>

#Desktop{
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    padding: 0 40px;
    height: 120px;
    position: absolute;
    z-index: 3;
    width: 100%;
    box-sizing: border-box;
}
nav .logo img{
    width: 60px;
    height: 60px;
}
nav .list{
    width: 80%;
    display: flex;
    justify-content: flex-start;
}
nav .list .el{
    margin: 0 30px;
}
nav .list .el a{
    text-decoration: none;
    color: white;
    font-weight: 600;
    font-size: 20px;
}
nav .list .el a:hover{
    text-decoration: none;
    color: var(--primary);
}
#Mobile{
    display:none
}
nav .open{
    filter: invert(100%) sepia(1%) saturate(0%) hue-rotate(248deg) brightness(103%) contrast(101%);
    width: 25px;
    height: 25px;
    cursor: pointer;
    display: none;
}
nav .open:hover{
    filter: invert(14%) sepia(74%) saturate(6320%) hue-rotate(335deg) brightness(94%) contrast(108%);}
nav .close{
    cursor: pointer;
    display:none;
    position: absolute;
    top: 15px;
    right: 15px;
    width: 22px;
    height: 22px;
    filter: invert(100%) sepia(1%) saturate(0%) hue-rotate(248deg) brightness(103%) contrast(101%);
}
nav .close:hover{
    filter: invert(14%) sepia(74%) saturate(6320%) hue-rotate(335deg) brightness(94%) contrast(108%);
}
#Desktop .lang{
  width: 10%;
  cursor: pointer;
}
#Mobile{
    display:none;
    
}
@media only screen and (max-width: 1100px){
    #Desktop .lang{
    display: none !important;
    }
    #Mobile .lang{
        display: none;
        cursor: pointer;
    }
    #Mobile.opened .lang{
        display: block;
        margin-top: 25px;
        margin-left:20px;
    }
    #Mobile{
    display:flex;
    flex-direction: column;
    position: fixed;
    top: 0;
    right:0;
    background-color: #101010;
    height: 100vh;
    align-items: flex-start;
    z-index: 3;
    width: 250px;
    padding: 30px 10px;
    transition: -webkit-transform .5s ease;
    transition: transform .5s ease;
    -webkit-transform: translateX(300px);
    -ms-transform: translateX(300px);
    transform: translateX(300px);
    }
    #Mobile .list{
        display: none !important;
    }
    #Mobile.opened{
        -webkit-transform: translateX(0px);
        -ms-transform: translateX(0px);
        transform: translateX(0px)
        
    }
    #Mobile.opened .list{
        display: flex !important;
    }
    nav .close.opened{
        display: block;
    }
    nav .open{
        display: block;
    }
    nav .open.opened{
        display: none;
    }
    #Mobile .list.main{
        display: flex;
        flex-direction: column;
        width: unset !important;
        margin-left:80px;
    }
    #Mobile .list.main .el{
        margin: 10px 0;
    }
    #Desktop{
        width: 100%;
    }
    #Desktop .list{
        display: none;
    }
    nav .list.side{
        margin-left:10px;
        margin-top: 110px;
    }
    nav .list.side a{
    margin: 0 10px;
    }
    nav .list.side img{
    width: 23px;
    filter: invert(99%) sepia(56%) saturate(2%) hue-rotate(30deg) brightness(105%) contrast(100%);
    }
    nav .list.side img:hover{
        filter: invert(14%) sepia(74%) saturate(6320%) hue-rotate(335deg) brightness(94%) contrast(108%);
    }
    .list.info{
        display: flex;
        flex-direction: column;
        justify-content: center;
        color:white;
        margin-top: 20px;
        margin-left:20px;
        
    }
    .list.info .el{
        display: flex;
        flex-direction: column;
        font-size: 15px;
        font-weight: 400;
        margin: 8px 0;
    }
   
    .list.info .el a {
        font-size: 15px;
        font-weight: 400;
    }
    .list.info .el .title img {
        width: 20px;
        filter: invert(99%) sepia(56%) saturate(2%) hue-rotate(30deg) brightness(105%) contrast(100%);
    }
}

@media only screen and (max-width: 800px){
#Desktop{
    width: 100%;
}
#Desktop .logo img{
    width: 40px;
    height: 40px;
}
#Desktop{
    height:70px
}
}
</style>
<nav id="Desktop">
    
    <div class="logo">
        <img src="./imgs/logo.svg" alt="logo">
    </div>
    <img 
    on:click="{()=>{opened=!opened}}"
    class="open" class:opened src="./imgs/icons/menu.svg" alt="">
    
    <div class="list">
        <div class="el"><a href="#Portfolio">Portfolio</a></div>
        <div class="el"><a href="#aboutMe">About me</a></div>
        <div class="el"><a href="#work">Work</a></div>
        <div class="el"><a href="#Education">Education</a></div>
        <div class="el"><a href="#Experience">Experience</a></div>
        <div class="el"><a href="#Contact">Contact</a></div>
    </div>

    <div class="lang">
        {#if $lang == 'fr'}
                <img
                    on:click={() => {
                        $lang ='en'
                        window.history.replaceState({}, '','?lg='+$lang); 
                        writing()
                        
                    }}
                    src="/imgs/icons/france-circle.png"
                    alt="fr" />
            {:else if $lang == 'en'}
                <img
                    on:click={() => {
                        $lang ='fr'
                        window.history.replaceState({}, '','?lg='+$lang); 
                        writing()
                        
                    }}
                    src="/imgs/icons/uk-circle.png"
                    alt="en" />
            {/if}
    </div>
</nav>
<nav id="Mobile" class:opened>
    <img 
    on:click="{()=>{opened=!opened}}"
    class="close" class:opened src="./imgs/icons/cancel.svg" alt="">
    <div class="list main">
        <div class="el"><a href="#Portfolio">Portfolio</a></div>
        <div class="el"><a href="#aboutMe">About me</a></div>
        <div class="el"><a href="#work">Work</a></div>
        <div class="el"><a href="#Education">Education</a></div>
        <div class="el"><a href="#Experience">Experience</a></div>
        <div class="el"><a href="#Contact">Contact</a></div>
    </div>
    <div class="list side">
        <a href="https://github.com/ahmedbm27" target="_blank"><img src="./imgs/icons/github.svg" alt="github"></a>
        <a href="https://www.linkedin.com/in/ahmedbm27/" target="_blank"><img src="./imgs/icons/linkedin.svg" alt="linkedin"></a>
        <a href="https://www.instagram.com/ahmedbenmah" target="_blank"><img src="./imgs/icons/instagram.svg" alt="instagram"></a>
        <a href="https://www.facebook.com/profile.php?id=100014229247552" target="_blank"><img src="./imgs/icons/facebook.svg" alt="facebook"></a>
    </div>

    <div class="list info">
        <div class="el">
            <div class="title"><img src="./imgs/icons/email.svg" alt=""></div> <a href="mailto:contact.ahmedbm@gmail.com">contact.ahmedbm@gmail.com</a>
        </div>
        <div class="el">
            <div class="title"><img src="./imgs/icons/call.svg" alt=""></div> <a href="tel:+21626612708">+216 26 612 708</a>
        </div>
        <div class="el">
            <div class="title"><img src="./imgs/icons/pin.svg" alt=""></div> {{"fr":"Tunisie, Kélibia","en":"Tunisia, Kelibia"}[$lang]}
        </div>

    </div>

    <div class="lang">
        {#if $lang == 'fr'}
                <img
                    on:click={() => {
                        $lang ='en'
                        window.history.replaceState({}, '','?lg='+$lang); 
                        writing()
                        
                        
                    }}
                    src="/imgs/icons/france-circle.png"
                    alt="fr" />
            {:else if $lang == 'en'}
                <img
                    on:click={() => {
                        $lang ='fr'
                        window.history.replaceState({}, '','?lg='+$lang); 
                        writing()
                        
                    }}
                    src="/imgs/icons/uk-circle.png"
                    alt="en" />
            {/if}
    </div>

</nav>