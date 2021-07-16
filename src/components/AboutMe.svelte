<script>
import {lang} from "../store.js"
</script>

<style>
.aboutMe{
    display:flex;
    justify-content: center;
    align-items: flex-start;
    padding: 80px 0;
    color: white;
    position: relative;
}
.title
{
    margin: 0px 150px 0 0;
}
.content p{
font-size: 22px;
max-width: 750px;
}
.title h1{
font-size: 60px;
margin: 0;
font-weight: 800;
}
ul{
    display: flex;
    flex-wrap: wrap;
    flex-direction: column;
    max-height: 180px;
    font-size: 18px;
    font-weight: 600;
}
li{
    list-style: none;
    display: flex;
    align-items: center;

}
ul li::before {
  content: "\2022";
  color: var(--primary);
  font-weight: bold;
  display: inline-block; 
  width: 1em;
  margin-left: -1em;
  font-size: 35px;
}
.p1,.p2{
    position: absolute;
    filter: invert(9%) sepia(100%) saturate(5593%) hue-rotate(335deg) brightness(117%) contrast(110%);  
}
.p1{
    width: 350px;
    top: 330px;
    left: -145px;
    transform: rotate(126deg);
}
.p2{
    width: 400px;
    top: 80px;
    right: -171px;
    transform: rotate(-80deg);
    
}
@media only screen and (max-width:1450px){
.aboutMe{
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding: 80px 250px;
}
.content{
    display: flex;
    flex-direction: column;
    align-items: center;
}
.content p{
    max-width: unset;
}
.content .here{
    width: 100%;
}
.title{
    margin: 0;
    text-align: center;
}
ul{
    width: 50%;
}
}
@media only screen and (max-width:1100px){
.aboutMe{
    padding:80px 200px
}
ul{
    width: 100%;
}
.p1{
    width: 300px;
}
.p2{
    width: 370px;
}
}
@media only screen and (max-width:950px){
.aboutMe{
    padding:80px 130px
}

ul{
    width: 50%;
    font-size: 15px;
}
.title h1{
    font-size: 40px;
}
.content p {
    font-size: 18px;
}
.p1{
    width: 260px;
}
.p2{
    width: 350px;
}

}

@media only screen and (max-width:764px){
    ul{
    width: 100%;
    }
}
@media only screen and (max-width:530px){
ul{
max-height: unset;   
}
.aboutMe{
    padding:80px 80px
}
.p1{
    width: 200px;
}
.p2{
    width: 300px;
}
}

</style>

<div class="aboutMe" id="#aboutMe">
<img class="p1" src="./imgs/patterns/p1.png" alt="pattern">
<img class="p2" src="./imgs/patterns/p4.png" alt="pattern">
   
    <div class="title">
        <h1>{{
            "en":"About me",
            "fr":"À propos de moi"
            }[$lang]}
        </h1>
        <h1>
            {{
            "en":"more...",
            "fr":"plus ..."
            }[$lang]}
        </h1>
    </div>
    <div class="content">
        <p>
            {{
            "en":"Enthusiastic and motivated Front end developer holding a lifelong experience in the IT sector with all its dimensions (Web, Mobile Apps, Web Scraping, Python automation, Youtube and content creation...etc), and more than 4 years of experience as front-end web developer. I am seeking job opportunities that help me improve my IT skills and be a senior front-end developer.",
            "fr":"Enthousiaste et motivé fraîchement diplômé en administration des affaires de TBS, Développeur Front-end ayant une longue expérience dans le secteur informatique avec toutes ses dimensions (Web, Mobile Apps, Web Scraping, Python automation, Youtube et création de contenu...etc), et plus de 4 ans d'expérience en tant que développeur web front-end. Je suis à la recherche d'opportunités d'emploi qui m'aideront à améliorer mes compétences informatiques et à devenir un développeur front-end senior."
            }[$lang]}
            
        </p>
        <p class="here">
            {{
                "en":"Here are a few technologies I've been working with recently:",
                "fr":"Voici quelques technologies que je travaille avec récemment:"
                }[$lang]}
            
        </p>
        <ul>
            <li>JavaScript</li>
            <li>Svelte</li>
            <li>Firebase</li>
            <li>HTML5 / CSS3</li>
            <li>Node.js</li>
            <li>WordPress</li>
        </ul>
    </div>  

</div>