
<script>
import {lang} from "../store.js"



let clicked=false;
let infos = [
    {
        icon:"./imgs/icons/call.svg",
        titleEN: "Phone",
        titleFR:"Téléphone",
        subtitle: "+216 26 612 708"
    },
    {
        icon:"./imgs/icons/email.svg",
        titleEN: "Email",
        titleFR:"Email",
        subtitle: "contact.ahmedbm@gmail.com"
    },
    {
        icon:"./imgs/icons/globe.svg",
        titleEN: "Website",
        titleFR:"Site Web",
        subtitle: "https://ahmedbm.com"
    },
    {
        icon:"./imgs/icons/pin.svg",
        titleEN: "Area",
        titleFR:"Emplacement",
        subtitle: "66 Avenue Ibn Khaldoun, Kélibia, Nabeul, Tunisia"
    }
];

let languages = [
    {
        EN:"Arabic",
        FR:"arabe",
        score:5
    },
    {
        EN:"English",
        FR:"Anglais",
        score:4
    },
    {
        EN:"French",
        FR:"Français",
        score:4
    },
    {
        EN:"German",
        FR:"Allemande",
        score:2
    },
]
let skills = ["JS","HTML","CSS","Svelte","Firebase","Netlify","Wordpress","Git","Java","C","Python","Photoshop","Illustrator","Figma","Video Editing","Ms Office"]

</script>

<style>
:root {
  --Yellow: #F1BB1B;
  --black: #424242;
  --gray : #7C7C7C;
}
.container{
    background-color: #FAFAFA;
    margin: 0;
    padding: 0;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    font-family: ProximaNovaRegular;
    color: var(--black) !important
}
.cv{
    width: 21cm;
    min-height: 29.7cm;
    height: 29.7cm;
    padding:0.3cm 1cm 1cm 1cm;
    margin: 1cm 0;
    border: 1px #D3D3D3 solid;
    border-radius: 5px;
    background: white;
    box-shadow: 0 0 5px rgba(0, 0, 0, 0.1);
    display: flex;
    flex-direction: column;
    position: relative;
}
.topPart{
    display: flex;
    align-items: center;
    position: relative;
    margin-bottom: 10px;
    margin-left: 1cm;
}
.topPart,.bottomPart{
    z-index: 1;
}
.topPart .imagePart{
    width: 30%;
    display: flex;
    justify-content: center;
}
.topPart .img{
    width: 150px;
    height: 150px;
    overflow: hidden;
    border-radius: 50%;
}
.topPart .img img{
    width: 150px;
}

 .rectangle{
    position: absolute;
    top: 0;
    left: 0;
    width: 2cm;
    height: 11.2cm;
    background-color: var(--Yellow);
    z-index: 0;
}



.topPart .namePostContainer{
    width: 70%;
    display: flex;
    justify-content: center;
}
.topPart .namePost{
    position: relative;
    text-align: center;
    border: 3px solid var(--black);
    padding: 25px 20px;


}
.namePost .name{
    font-size: 40px;
    font-family: ProximaNovaExtraBold;
}
.namePost .post{
    position: absolute;
    font-size: 20px;
    font-family: ProximaNovaBold;
    background-color: white;
    height: 20px;
    width: max-content;
    padding: 10px;
    bottom: -15px;
    left: 50%;
    transform: translateX(-50%);
}

.bottomPart{
    display: flex;
    flex-direction: row;
}

.bottomPart .leftPart{
width: 30%;
padding-right: 0.5cm;
}
.info{
    display: flex;
    margin: 20px 0;
    align-items: center;
}
.info .icon img{
    width: 20px;
}
.infoContainer{
   margin-left: 1cm; 
}
.infoContainer .title{
    font-family: ProximaNovaExtraBold;
}
.infoContainer .subtitle{
    font-family: ProximaNovaRegular;
    font-size: 14px;
}

.singleEducation{
    margin-top: 5px;
}
.singleEducation .title{
    font-family: ProximaNovaExtraBold;
    font-size: 16px !important;
    margin-top: 10px;
}
.singleEducation .school{
    font-family: ProximaNovaBold;
    font-size: 14px;
}
.singleEducation .schoolInfo{
    display: flex;
    flex-direction: column;
    color:var(--Yellow)
}
.schoolInfo .speciality{
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    margin: 3px 0;
    
}
hr{
    height: 1px;
    background-color: var(--black);
    border: none;
    margin: 10px 0;
}


.languages .lang {
    display: flex;
    margin: 10px 0;
    justify-content: space-between;
}
.langScore{
    display: flex;
    margin-right: 10px;
}
.completed , .notCompleted{
    border-radius: 50%;
    margin: 0 5px;
    cursor: pointer;
   
}
.langScore .completed{
    width: 17px;
    height: 17px;
    background-color: var(--Yellow); 
}
.langScore .completed:hover{
    box-shadow: 0px 0px 10px var(--Yellow); 
}
.langScore .notCompleted{
    width: 16px;
    height: 16px;
    border: 1px solid var(--Yellow);  
}
.langScore .notCompleted:hover{
    box-shadow: 0px 0px 10px var(--Yellow); 

}
.rightPart {
    width: 70%;
    padding-left: 0.5cm;
}
.section .title{
    font-family: ProximaNovaExtraBold;
    font-size: 28px;
    margin: 10px 0;
}
.skills{
    display: flex;
    flex-wrap: wrap;
}
.skills .singleSkill{
    width: max-content;
    background-color: var(--Yellow);
    border-radius: 5px;
    padding: 5px 5px;
    margin: 5px 3px;
    color: white;
    cursor: pointer;
}
.singleProject,.singlevolunteer{
    margin: 10px 0;
}
 ul{
    list-style: none;
    margin: 5px 0;
    color: var(--gray);
}
 ul li::before {
    content: "\2022";
    color: var(--Yellow);
    font-weight: bold;
    font-size: 25px;
    display: inline-block;
    width: 1em;
    margin-left: -1em;
}
.singleProject .project .projectTitle,.singlevolunteer .project .projectTitle{
    font-family: ProximaNovaBold;
}
.singleProject .project,.singlevolunteer .project{
    display: flex;
}
.singleProject .project .website ,.singlevolunteer .project{
    margin-left: 20px;
}
a{
    color:var(--Yellow)
}
.singleWork{
    margin: 10px 0;
}
.companyDate .workTitle{
    font-family: ProximaNovaBold;
}
.companyDate{
display: flex;
justify-content: space-between
}
.companyDate .date{
    color: var(--Yellow)
}

.infoAboutContainer .aboutMe{
    display:none;
}
.rectangle2{
    position: absolute;
    background-color:var(--Yellow);
    width: 100%;
    height: 20px;
    bottom: 0;
    left: 0;  
}
.downloadBtn{
    position: fixed;
    bottom: 50px;
    right: 20px;
    background-color: var(--Yellow);
    border-radius: 50%;
    width: 25px;
    height: 25px;
    padding: 20px;
    z-index: 5;
    color: white;
    display: flex;
    justify-content: center;
    align-items: center;
    box-shadow: 0 0 25px var(--Yellow);
    cursor: pointer;

}
.downloadBtn img{
    width: 100%;
    filter: invert(100%) sepia(0%) saturate(5257%) hue-rotate(113deg) brightness(105%) contrast(100%);  

}
.downloadBtn:active{
    box-shadow: 0 0 30px var(--Yellow);
    -webkit-touch-callout: none; /* iOS Safari */
    -webkit-user-select: none; /* Safari */
     -khtml-user-select: none; /* Konqueror HTML */
       -moz-user-select: none; /* Old versions of Firefox */
        -ms-user-select: none; /* Internet Explorer/Edge */
            user-select: none; /* Non-prefixed version, currently
                                  supported by Chrome, Edge, Opera and Firefox */
}
.downloadBtn.clicked{
    animation: mymove 1s;
    background-color: #00CE7C;
    box-shadow: 0 0 25px #00CE7C;
}
.downloadBtn.clicked:active{
    box-shadow: 0 0 30px #00CE7C;
}
@keyframes mymove {
  from {
      background-color: var(--Yellow);
    box-shadow: 0 0 25px var(--Yellow);}
  to {
      background-color: #00CE7C;
      box-shadow: 0 0 25px #00CE7C;
  }
}

.changeLang{
    position: fixed;
    bottom: 150px;
    right: 10px;
    border-radius: 20px;
    width: 80px;
    padding: 5px 5px;
    z-index: 5;
    color: white;
    display: flex;
    justify-content: center;
    align-items: center;
    
    background-color: var(--Yellow);

}
.changeLang .lang{
margin-left: 10px;
margin-right: 10px;
}
.changeLang img{
    cursor: pointer;
}

@media  only screen and (max-width:900px){
.infoAboutContainer{
    display: flex;
}
.infoAboutContainer .aboutMe{
    display:block;
    margin-left: 0.5cm;
    width: none;
}
.rightPart .aboutMe{
    display: none;
}
.infoAboutContainer .infoDiv {
    margin-right: 0.5cm;
    width: none;
}
.bottomPart{
    flex-direction: column
}
.cv2 .bottomPart{
    flex-direction: column-reverse
}
.bottomPart .leftPart,.bottomPart .rightPart{
    width: 100%;
    padding: 0;
}

.cv{
    width: 85%;
    height: 100%;
}
.namePost{
    padding: 15px 10px;
}
.namePost .name{
font-size: 30px;
}
.namePost .post{
font-size: 20px;
}
.imagePart .img{
    width: 100px;
    height: 100px;
}
.imagePart .img img{
    width: 100px;
}

.rectangle{
    height: 10.2cm;
}
}


@media  only screen and (max-width:650px){
.infoAboutContainer .aboutMe{
    display:none;
    
}
.rightPart .aboutMe{
    display: block;
}
.topPart{
    flex-direction: column-reverse;
}
.imagePart {
    width: 100% !important;
}
.imagePart .img{
    margin-top: 20px;
}
.namePostContainer {
    width: 100% !important;
}
.cv{
    margin: 0;
}
.rectangle{
    height: 12.5cm;
}
.namePost{
    padding: 10px 6px;
}
.namePost .name{
font-size: 20px;
}
.namePost .post{
font-size: 15px;
}
}

</style>


<div class="container">
    <div class="downloadBtn" 
    class:clicked
    on:click="{() =>{
        clicked=true;
        let url = {
            "fr" : "https://drive.google.com/uc?export=download&id=1s8uN-7zWgMiVda8APu2jH-V8tP9v-eGA",
            "en" : "https://drive.google.com/uc?export=download&id=1KzWa48ne9cadSAo-5cK6fbl6f0NGAuMA"
            }[$lang]
        window.open(url,'_blank');
        }}">
    {#if !clicked}
    <img src="./imgs/icons/download.svg" alt="download">
    {/if}
    {#if clicked}
    <img src="./imgs/icons/success.svg" alt="success">
    {/if}
    </div>

    <div class="changeLang">
        {#if $lang == 'fr'}
                <img
                    on:click={() => {
                        $lang = 'en';
                    }}
                    src="/imgs/icons/france-circle.png"
                    alt="fr" />
                    <div class="lang">FR</div>
            {:else if $lang == 'en'}
                <img
                    on:click={() => {
                        $lang = 'fr';
                    }}
                    src="/imgs/icons/uk-circle.png"
                    alt="en" />
                    <div class="lang">EN</div>
            {/if}
    </div>
    <div class="cv" id="cv">
        <div class="topPart">
            <div class="imagePart">
                <div class="img"><img src="./imgs/portfolio.jpg" alt=""></div>
            </div>
            <div class="namePostContainer">
                <div class="namePost">
                    <div class="name">Ahmed Ben Mahmoud</div>
                    <div class="post">
                        {{
                        "fr" : "Développeur Web Front-end",
                        "en" :"Front End Web Weveloper"
                        }[$lang]}
                        
                    </div>
                </div>
            </div>
            
        </div>
        <div class="rectangle"></div>
        <div class="rectangle2"></div>
        <!--End TOP Part-->

        <div class="bottomPart">

            <div class="leftPart">
                <div class="contactInfo">
                    <div class="infoAboutContainer">

                        <div class="infoDiv">
                            {#each infos as info}
                            <div class="info">
                                <div class="icon"><img src="{info.icon}" alt="{info.titleEN}"></div>
                                <div class="infoContainer">
                                    <div class="title">{{"fr" : info.titleFR , "en" : info.titleEN}[$lang]}</div>
                                    <div class="subtitle">{info.subtitle}</div>
                                </div>
                            </div>
                            {/each}
                        </div>

                        <div class="aboutMe section" >
                            <div class="title">
                                {{
                                "fr" : "À propos de moi",
                                    "en" :"About Me"
                                }[$lang]}</div>
                                <div class="paragraph">
                                    {{
                                        "fr" :"Développeur Front end enthousiaste et motivé possédant une longue expérience dans le secteur informatique dans toutes ses dimensions (Web, Mobile Apps, Web Scraping, Python automation, Youtube et création de contenu...etc), et plus de 3 ans d'expérience en tant que front-end développeur web. Je suis à la recherche d'opportunités d'emploi qui m'aideront à améliorer mes compétences informatiques et à devenir un développeur front-end senior.",
                                        "en" : "Enthusiastic and motivated Front end developer holding a lifelong experience in the IT sector with all its dimensions (Web, Mobile Apps, Web Scraping, Python automation, Youtube and content creation...etc), and  more than 3 years of experience as front-end web developer. I am seeking job opportunities that help me improve my IT skills and be a senior front-end developer."}[$lang]}
                                </div>
                        </div>
                        <hr>
                    </div>
                   

                    <div class="education section">
                        <div class="title">
                            {{
                                "fr" : "Education",
                                    "en" :"Education"
                                }[$lang]}</div>
                   
                        <div class="singleEducation">
                            <div class="title">
                                {{
                                "fr" : "Bachelor de sciences en administration d'affaires",
                                "en" :"Bachelor of Science in Business Administration"
                                }[$lang]}</div>
                            <div class="school">Tunis Business School</div>
                            <div class="schoolInfo">
                                <div class="speciality">
                                    <div class="el">
                                        {{
                                            "fr" : "principale : Informatique",
                                            "en" :"Major : IT"
                                            }[$lang]}</div>
                                    <div class="el">
                                        {{
                                            "fr" : "secondaire : Finance",
                                            "en" :"Minor: Finance"
                                            }[$lang]}</div>
                                </div>
                                <div class="speciality">
                                    <div class="el">2017 - 2021</div>
                                    <div class="el">
                                        {{
                                            "fr" : "moyenne : 3.0 / 4.0",
                                            "en" :"GPA : 3.0 / 4.0"
                                            }[$lang]}</div>
                                </div>
                            </div>
                        </div>
                        <!--END TBS-->
                        <div class="singleEducation">
                            <div class="title">
                                {{
                                    "fr" : "Développement web full stack",
                                    "en" :"Full-stack Web Development"
                                    }[$lang]}</div>
                            <div class="school">Holberton School</div>
                            <div class="schoolInfo">
                                <div class="speciality">
                                    <div class="el">2021 - 2023</div>                                </div>
                            </div>
                        </div>
                        <!--END Holberton School-->
                        <hr>
                    </div>
                    <!--End Education-->

                    <div class="Skills section">
                        <div class="title">
                            {{
                                "fr" : "Compétences",
                                "en" :"Skills"
                                }[$lang]}</div>
                        <div class="skills">
                            {#each skills as skill}
                            <div class="singleSkill">{skill}</div>
                            {/each}
                        </div>
                    </div>
                    <hr>
                     <!--End Skills-->
                    <div class="languages section">
                        <div class="title">
                            {{
                                "fr" : "Langues",
                                    "en" :"Languages"
                                }[$lang]}</div>
                        {#each languages as lng}
                        <div class="lang">
                            <div class="langName">{
                                {"fr":lng.FR,
                                "en":lng.EN
                                }[$lang]} :</div>
                            
                            <div class="langScore">
                                {#each Array(lng.score) as _,i}
                                <div class="completed"></div>
                                {/each}
                                {#each Array(5 - lng.score) as _,i}
                                <div class="notCompleted"></div>
                                {/each}
                            </div>
                           
                            
                        </div>
                        {/each}
                    </div>
                    <!--End languagess-->
                    
                   
                   
                    
                </div>
            </div>
            <!--End Left Part-->

            <div class="rightPart">
                <div class="aboutMe section">
                    <div class="title">
                        {{
                            "fr" : "À propos de moi",
                                "en" :"About Me"
                            }[$lang]}
                        </div>

                    <div class="paragraph">
                        {{
                            "fr" :"Développeur Front end enthousiaste et motivé possédant une longue expérience dans le secteur informatique dans toutes ses dimensions (Web, Mobile Apps, Web Scraping, Python automation, Youtube et création de contenu...etc), et plus de 3 ans d'expérience en tant que front-end développeur web. Je suis à la recherche d'opportunités d'emploi qui m'aideront à améliorer mes compétences informatiques et à devenir un développeur front-end senior.",
                            "en" : "Enthusiastic and motivated Front end developer holding a lifelong experience in the IT sector with all its dimensions (Web, Mobile Apps, Web Scraping, Python automation, Youtube and content creation...etc), and  more than 3 years of experience as front-end web developer. I am seeking job opportunities that help me improve my IT skills and be a senior front-end developer."}[$lang]}
                    </div>
                </div>
                <hr>
                <div class="personalProjects section">
                    <div class="title">
                        {{
                            "fr" : "Projets personnels",
                            "en" :"Personal Projects"
                        }[$lang]}</div>
                    <div class="singleProject">
                        <div class="project">
                            <div class="projectTitle">Devronic ( 09/2019 - Present )</div>
                            <div class="website">
                                {{
                                    "fr" : "Site Web",
                                        "en" :"Website"
                                    }[$lang]} : <a href="https://devronic.com" target="_blank">Devronic.com</a>
                            </div>
                        </div>
                        <ul>
                            <li>
                                {{
                                    "fr" : "Co-fondateur d'une agence de développement web",
                                    "en" :"Co-Founder of a web development agency"
                                    }[$lang]}</li>
                        </ul>
                    </div>
                    <div class="singleProject">
                        <div class="project">
                            <div class="projectTitle">Unify startup ( 04/2021 - Present )</div>
                            <div class="website">
                                {{
                                    "fr" : "Site Web",
                                        "en" :"Website"
                                    }[$lang]} : <a href="https://unify.tn" target="_blank">Unify.tn</a>
                            </div>
                        </div>
                        <ul>
                            <li>
                                {{
                                    "fr" : "Co-fondateur d'une plateforme orientée créateur de contenu",
                                    "en" :"Co-Founder of a content creator oriented platform"
                                    }[$lang]}</li>
                        </ul>
                    </div>
                </div>
                <hr>
                
                <div class="work section">
                    <div class="title">
                        {{
                            "fr" : "L'expérience professionnelle",
                                "en" :"Work Experience"
                            }[$lang]}</div>

                    <div class="singleWork">
                        <div class="companyDate">
                            <div class="workTitle">
                                {{
                                    "fr" : "Développeur web front-end",
                                        "en" :"Front end web developer"
                                    }[$lang]} @ Unify.tn</div>
                            <div class="date">10/2020 - Present</div>
                        </div>
                        <ul>
                            <li>
                                {{
                                    "fr" : "Développé le front-end de chaque page du startup Unify de",
                                        "en" :"Developed the front end of every single page of Unify startup of"
                                    }[$lang]} <a href="https://unify.tn" target="_blank">unify.tn</a> 
                                    {{"fr" : "et de",
                                    "en" :"and of"
                                }[$lang]} <a href="https://creator.unify.tn" target="_blank">creator.unify.tn</a> </li>
                        </ul>
                    </div>
                    <!---->
                    <div class="singleWork">
                        <div class="companyDate">
                            <div class="workTitle">
                                {{"fr" : "Chef de projet e-learning",
                                    "en" :"E-Learning Project Manager"
                                }[$lang]}
                                 @ MERIT TBS</div>
                            <div class="date">10/2018 - 10/2020</div>
                        </div>
                        <ul>
                            <li>
                                {{"fr" : "responsable du projet E-learning du club MERIT à Tunis Business School. Le projet consiste à enseigner aux membres de nombreuses compétences informatiques de manière créative et à réaliser des vidéos professionnelles sur notre plateforme.",
                                "en" :"head of the E-learning project of the MERIT club at Tunis Business School. The project involves teaching members many computer skills in a creative way and making professional videos in our platform."
                                }[$lang]}
                               </li>
                        </ul>
                    </div>
                    <!---->
                    <div class="singleWork">
                        <div class="companyDate">
                            <div class="workTitle">
                                {{"fr" : "Développeur web full stack",
                                "en" :"Full stack web developer"
                                }[$lang]} @GigaServices</div>
                            <div class="date">2017 - 2020</div>
                        </div>
                        <ul>
                            <li>
                                {{"fr" : "J'ai développé le site gigaservices :",
                                "en" :"I Developed gigaservices website :"
                                }[$lang]} <a href="https://gigaservices.tn" target="_blank">gigaservices.tn</a> {{"fr" : "et :","en" :"and"}[$lang]} <a href="https://admin.gigaservices.tn" target="_blank">admin.gigaservices.tn</a> </li>
                            <li>
                                {{"fr" : "J'ai développé le logiciel du gestion de gigaservices",
                                "en" :"I Developed gigaservices software management "
                                }[$lang]}</li>
                        </ul>
                    </div>
                    <!---->
                    <div class="singleWork">
                        <div class="companyDate">
                            <div class="workTitle">
                                {{"fr" : "Design graphique - Coach en développement Web",
                                "en" :"Graphic Design - Web development Coach"
                                }[$lang]}
                                 @MERIT TBS</div>
                            <div class="date">2018 - 2020</div>
                        </div>
                        <ul>
                            <li>
                                {{"fr" : "J'ai enseigné des compétences informatiques (en : retouche photo 'Adobe Photoshop et Illustrator', montage vidéo 'Camtasia & After effect', développement Web 'HTML,CSS,JS,PHP et WordPress')",
                                "en" :'I Taught IT skills ( ie: photo editing "Adobe Photoshop and Illustrator", Video Editing "Camtasia & After effect", Web Development " HTML,CSS,JS,PHP and WordPress") '
                                }[$lang]}</li>
                        </ul>
                    </div>
                </div>
               
                
            </div>
            <!--End right Part-->
        </div>
        <!--End Bottom Part-->

    </div>

    <div class="cv cv2" id="cv">
        <div class="rectangle2"></div>
       <div class="bottomPart">
            <div class="leftPart">
                <div class="Links section">
                    <div class="title">
                        {{
                            "fr" : "Liens Utiles",
                                "en" :"Useful Links"
                        }[$lang]}</div>
                    <ul>
                        <li>Linkedin : <a href="https://www.linkedin.com/in/ahmedbm27" target="_blank">/ahmedbm27</a></li>
                        <li>Github : <a href="https://github.com/ahmedbm27" target="_blank">/ahmedbm27</a></li>                    
                        <li>
                            {{
                                "fr" : "Site web : ",
                                    "en" :"Website : "
                            }[$lang]}<a href="https://ahmedbm.com" target="_blank">ahmedbm.com</a></li>
                    </ul>
                </div>
            </div>
            <div class="rightPart">
                <div class="volunteer section">
                    <div class="title">
                        {{"fr" : "Expérience de bénévolat",
                        "en" :'Volunteer Experience'
                            }[$lang]}</div>
                    <div class="singlevolunteer">
                        <div class="project">
                            <div class="projectTitle">
                                {{"fr" : "Cérémonie de Diplôme ",
                        "en" :'Diploma Ceremony '
                            }[$lang]}( 10/2019 )</div>
                        </div>
                        <ul>
                            <li>
                                {{"fr" : "Contribution à la préparation de toutes les bannières, roll ups, conception de badges et le Développement de l'application de contrôle des visiteurs",
                        "en" :'Contributed in the preparation of all the banners, roll ups, badges design and check in application development.'
                            }[$lang]}</li>
                        </ul>
                    </div>
                    <!---->
                    <div class="singlevolunteer">
                        <div class="project">
                            <div class="projectTitle">
                                {{"fr" : "Formateur en montage vidéo ",
                        "en" :'Video Editing Trainer '
                            }[$lang]}
                                 ( 10/2018 )</div>
                        </div>
                        <ul>
                            <li>
                                {{"fr" : "J'ai formé UGTE TBS, un groupe de plus de 20 personnes aux bases du montage vidéo ( camtasia 9 )",
                        "en" :'Trained UGTE TBS, a group of more than 20 people video editing basics ( camtasia 9 )'
                            }[$lang]}
                                </li>
                        </ul>
                    </div>
                </div>
                <hr>
                <div class="achievment section">
                    <div class="title">
                        {{"fr" : "Réalisations",
                        "en" :'Achievements'
                            }[$lang]}</div>

                        <div class="singlevolunteer">
                            <div class="project">
                                <div class="projectTitle">
                                    {{"fr" : "Camp de développement de jeu pour les jeunes",
                                    "en" :'Youth Game Development Camp'
                                }[$lang]}
                                    ( 09/2017 )</div>
                            </div>
                            <ul>
                                <li>
                                    {{"fr" : "Premier prix du meilleur jeu dans un camp organisé par ",
                                "en" :'First Award for the best game in a camp organized by '
                                }[$lang]}
                                <a href='https://gomycode.com/' target="_blank">GoMyCode</a>
                                {{"fr" : "et ",
                                "en" :'and '
                                }[$lang]}
                                <a href='https://mentornations.org/#/' target="_blank">MentorNations</a>
                                @GoMyCode
                                    </li>
                            </ul>
                        </div>


                        <div class="singlevolunteer">
                            <div class="project">
                                <div class="projectTitle">
                                    {{"fr" : "Formateur en développement Web",
                                    "en" :'Web Development Trainer'
                                }[$lang]}
                                    ( 01/2019 )</div>
                            </div>
                            <ul>
                                <li>
                                    {{"fr" : "Un Certificat de formateur en développement web (WordPress) dans un camp organisé par le club Merit TBS",
                                "en" :'A Certificate as a trainer in web development (WordPress) in a camp organized by the Merit TBS club'
                                }[$lang]}
                                
                                    </li>
                            </ul>
                        </div>

                        <div class="singlevolunteer">
                            <div class="project">
                                <div class="projectTitle">
                                    {{"fr" : "Organisateur de camp de hackathon numérique",
                                    "en" :'Digital Hackathon Camp Organizer'
                                }[$lang]}
                                    ( 01/2019 )</div>
                            </div>
                            <ul>
                                <li>
                                    {{"fr" : "Séances intensives de coaching Wordpress & e-commerce avec un hackathon.",
                                "en" :'Intensive Wordpress & e-comerce coaching sessions with a hackathon.'
                                }[$lang]}
                                
                                    </li>
                            </ul>
                        </div>
                </div>
                <hr>
            </div>
        </div>
    </div>
</div>




