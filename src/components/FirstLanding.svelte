<script>
    import Nav from "./Nav.svelte"
    import SideNav from "./SideNav.svelte"
    import {lang} from "../store.js"
    import Typewriter from 'typewriter-effect/dist/core';
    import {onMount} from 'svelte'
    import { navigate } from "svelte-routing";

    
    onMount(()=>{

        //change link
        let url = new URL (document.URL);
        let lg = url.searchParams.get("lg");
        if (!lg){
            navigate("/?lg="+$lang )
        }else{
            $lang=lg
            window.history.replaceState({}, '','?lg='+$lang); 
            
        }

       
        writing()
        
        

    })

    AOS.init();

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



</script>

<style>
.container{

}
.bgImg{
    background-color: #101010;
    background-image: url("../imgs/landing.jpg")!important;
    background-position: 50%;
    background-repeat: no-repeat;
    background-size: cover;
    height: 100vh;
    display: flex;
    flex-direction: row;
}
.main{
    display: flex;
    flex-direction: column;
    margin: 230px 0 0 115px;
    justify-content: space-between;
}
.welcomeText{
    color: white;
    font-size: 70px;
    font-weight: 700;
}
.welcome{
    font-size: 22px;
    font-weight: 400;
    color: #7C7E88;
    margin-left: 3px;
}
.webDev{
    color: var(--primary);
}
.build{
    font-size: 50px;

}
.downloadBtn{
    margin-top: 60px;
    background-color: var(--primary);
    color: white  !important;
    width: max-content;
    padding: 10px 18px;
    font-size: 20px;
    border-radius: 8px;
    cursor: pointer;
}
.downloadBtn a{
    text-decoration: none;
    color: white  !important;
    display: flex;
    align-items: center;
}
.downloadBtn img{
    width: 24px;
    filter: invert(100%) sepia(100%) saturate(1%) hue-rotate(305deg) brightness(103%) contrast(101%);
    margin-right: 12px;
}
.downloadBtn a:hover{
    color: var(--primary)  !important;
}
.downloadBtn:hover{
    color: var(--primary)  !important;
    background-color: white;
}
.downloadBtn:hover img{
    filter: invert(15%) sepia(82%) saturate(6030%) hue-rotate(335deg) brightness(94%) contrast(109%);
}
.myInfo{
    display: flex;
    flex-direction: row;
    color: white;
    margin-bottom: 75px;
    background-color: rgba(0,0,0,0.1);
    padding: 10px;
    border-radius: 10px;
}
.myInfo .email, .myInfo .phone {
    padding-right: 60px;
    margin-right: 60px;
    border-right: 1px solid gray;
}
.myInfo .el .title{
    display:flex;   
    align-items: center;
    font-size: 22px;
    font-weight: 600;
    margin-bottom: 10px;
}
.myInfo .el .title img{
    margin-right: 15px;
    width: 25px;
    filter: invert(100%) sepia(1%) saturate(0%) hue-rotate(248deg) brightness(103%) contrast(101%);
}
.myInfo .el .subtitle{
    font-size: 16px;
    font-weight: 400;
}
.myInfo .el .subtitle a{
    text-decoration: none;
    color: white;
}
.myInfo .el .subtitle a:hover{
    color: var(--primary);
}
@media only screen and (max-width: 1500px){
    .bgImg{
        height: 768px;
        background-position: 75%;
    }
    .downloadBtn{margin-top: 50px;}
    .main{margin: 150px 0 0 60px;}
    .myInfo{margin-bottom: 10px;}
    
}
@media only screen and (max-width: 1100px){
    .bgImg{height: 700px;}
    .welcomeText{font-size: 60px;}
    .welcome{font-size: 20px;}
    .build{font-size: 40px;}
    .myInfo .el .title{font-size: 20px;}
    .myInfo .el .subtitle{font-size: 14px;}
    .main{margin: 100px 0 0 60px;}
}

@media only screen and (max-width: 950px){
    .bgImg{height: 500px;}
    .welcomeText{font-size: 40px;}
    .welcome{font-size: 18px;}
    .build{
        font-size: 30px;
    }
    .downloadBtn{margin-top: 30px;}
    .main{margin: 100px 0 0 40px;}
    
    .myInfo .el {
        padding-right: 20px;
        margin-right: 20px;
    }
    .myInfo .el .title{
        font-size: 18px;
    }
    .myInfo .el .subtitle{
        font-size: 12.5px;
    }
}
@media only screen and (max-width: 700px){
    .main{margin: 100px 0 0 40px !important;;}   
}
@media only screen and (max-width: 570px){
    .bgImg{
        height: 100vh;
        background-position: 80%;
        align-items: center;
    }
    .welcomeText{
        font-size: 35px;
    }
    .welcome{font-size: 17px;}
    .build{
        font-size: 24px;
    }
    .downloadBtn{
        margin-top: 15px;
        font-size: 17px;
    }
    .downloadBtn img{
        width: 20px;
    }
   
    .myInfo{
       display:none
    }
    .main{margin: 60px 0 0 20px !important;}
}

</style>
<Nav/>
<div class="container" id="home">
    <div class="bgImg">
        <SideNav/>
        <div class="main">
            <div class="welcomeText">
                <div class="welcome" data-aos="fade-right" data-aos-duration="1000"   >{{"fr":'Bienvenue dans mon monde',"en":"Welcome To My World"}[$lang]}</div>
                <div class="hi" data-aos="fade-right" data-aos-duration="1000" data-aos-delay="400">{{"fr":"Salut! je suis Ahmed","en":"Hi! I'm Ahmed"}[$lang]}</div>
                <div class="webDev" id="webDev" data-aos="fade-right" data-aos-duration="1000" data-aos-delay="400" >{{"fr":"Développeur web","en":"Web Developer"}[$lang]}</div>
                <div class="build" data-aos="fade-right" data-aos-duration="1000" data-aos-delay="700" >{{"fr":"Je construis des choses pour le web","en":"I build things for the web"}[$lang]}</div>

                <div class="downloadBtn" data-aos="fade-up" data-aos-duration="1000" data-aos-delay="1000"><a href="/mycv?lg={$lang}" target="_blank"><img src="./imgs/icons/download.svg" alt="download">{{"fr":"Télécharger le CV","en":"Download CV"}[$lang]}</a></div>
            </div>
            <div class="myInfo">
                <div class="email el" >
                    <div class="title"><img src="./imgs/icons/email.svg" alt="">{{"fr":"Email","en":"Email"}[$lang]}</div>
                    <div class="subtitle"><a href="mailto:contact.ahmedbm@gmail.com">contact.ahmedbm@gmail.com</a> </div>
                </div>
                <div class="phone el" >
                    <div class="title"><img src="./imgs/icons/call.svg" alt="">{{"fr":"Téléphone","en":"Phone"}[$lang]}</div>
                    <div class="subtitle"><a href="tel:+21626612708">+216 26 612 708</a></div>
                </div>
                <div class="location el" >
                    <div class="title"><img src="./imgs/icons/pin.svg" alt="">{{"fr":"Location","en":"Location"}[$lang]}</div>
                    <div class="subtitle">{{"fr":"Tunisie, Kélibia","en":"Tunisia, Kelibia"}[$lang]}</div>
                </div>
            </div>
        </div>
    </div>
    
</div>
