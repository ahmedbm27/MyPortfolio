
<script>

let infos = [
    {
        icon:"./imgs/icons/call.svg",
        title: "Phone",
        subtitle: "+216 26 612 708"
    },
    {
        icon:"./imgs/icons/email.svg",
        title: "Email",
        subtitle: "contact.ahmedbm@gmail.com"
    },
    {
        icon:"./imgs/icons/globe.svg",
        title: "Website",
        subtitle: "https://ahmedbm.com"
    },
    {
        icon:"./imgs/icons/pin.svg",
        title: "Area",
        subtitle: "66 Avenue Ibn Khaldoun, Kélibia, Nabeul, Tunisia"
    }
];

let languages = [
    {
        name:"Arabic",
        score:5
    },
    {
        name:"English",
        score:4
    },
    {
        name:"Frnech",
        score:4
    },
    {
        name:"German",
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
    padding:0.3cm 1cm;
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
button{
    position: absolute;
    bottom: 0 ;
    right: 0;
    z-index: 5;
}
</style>


<div class="container">
    <button on:click="{()=>{downloadPDF()}}">download</button>
    <div class="cv" id="cv">
        <div class="topPart">
            <div class="imagePart">
                <div class="img"><img src="./imgs/portfolio.png" alt=""></div>
            </div>
            <div class="namePostContainer">
                <div class="namePost">
                    <div class="name">Ahmed Ben Mahmoud</div>
                    <div class="post">Full Stack Web Developer</div>
                </div>
            </div>
            
        </div>
        <div class="rectangle"></div>
        <!--End TOP Part-->

        <div class="bottomPart">

            <div class="leftPart">
                <div class="contactInfo">
                    {#each infos as info}
                    <div class="info">
                        <div class="icon"><img src="{info.icon}" alt="{info.title}"></div>
                        <div class="infoContainer">
                            <div class="title">{info.title}</div>
                            <div class="subtitle">{info.subtitle}</div>
                        </div>
                        
                    </div>
                    {/each}

                    <div class="education section">
                        <div class="title">Education</div>
                   
                        <div class="singleEducation">
                            <div class="title">Bachelor of Science in Business Administration</div>
                            <div class="school">Tunis Business School</div>
                            <div class="schoolInfo">
                                <div class="speciality">
                                    <div class="el">Major : IT</div>
                                    <div class="el">Minor: Finance</div>
                                </div>
                                <div class="speciality">
                                    <div class="el">2017 - 2021</div>
                                    <div class="el">GPA : 3.0 / 4.0</div>
                                </div>
                            </div>
                        </div>
                        <!--END TBS-->
                        <div class="singleEducation">
                            <div class="title">Full-stack Web Development</div>
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
                        <div class="title">Skills</div>
                        <div class="skills">
                            {#each skills as skill}
                            <div class="singleSkill">{skill}</div>
                            {/each}
                        </div>
                    </div>
                    <hr>
                     <!--End Skills-->
                    <div class="languages section">
                        <div class="title">Languages</div>
                        {#each languages as lang}
                        <div class="lang">
                            <div class="langName">{lang.name} :</div>
                            
                            <div class="langScore">
                                {#each Array(lang.score) as _,i}
                                <div class="completed"></div>
                                {/each}
                                {#each Array(5 - lang.score) as _,i}
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
                    <div class="title">About Me</div>
                    <div class="paragraph">Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Quis ipsum suspendisse ultrices gravida. Risus commodo viverra maecenas accumsan lacus vel facilisis. accumsan lacus vel facilisis. accumsan lacus vel facilisis. accumsan lacus vel </div>
                </div>
                <hr>
                <div class="personalProjects section">
                    <div class="title">Personal Projects</div>
                    <div class="singleProject">
                        <div class="project">
                            <div class="projectTitle">Devronic ( 09/2019 - Present )</div>
                            <div class="website">
                                Website : <a href="https://devronic.com">Devronic.com</a>
                            </div>
                        </div>
                        <ul>
                            <li>Co-Founder of a web development agency</li>
                        </ul>
                    </div>
                    <div class="singleProject">
                        <div class="project">
                            <div class="projectTitle">Unify startup ( 04/2021 - Present )</div>
                            <div class="website">
                                Website : <a href="https://unify.tn">Unify.tn</a>
                            </div>
                        </div>
                        <ul>
                            <li>Co-Founder of a content creator oriented platfrom</li>
                        </ul>
                    </div>
                </div>
                <hr>
                
                <div class="work section">
                    <div class="title">Work Experience</div>

                    <div class="singleWork">
                        <div class="companyDate">
                            <div class="workTitle">Front end web developer @ Unify.tn</div>
                            <div class="date">10/2020 - Present</div>
                        </div>
                        <ul>
                            <li>Developing the front end of every single page of Unify startup of <a href="https://unify.tn">unify.tn</a> and of <a href="https://creator.unify.tn">creator.unify.tn</a> </li>
                        </ul>
                    </div>
                    <!---->
                    <div class="singleWork">
                        <div class="companyDate">
                            <div class="workTitle">E-Learning Project Manager @ MERIT TBS</div>
                            <div class="date">10/2018 - 10/2020</div>
                        </div>
                        <ul>
                            <li>head of the E-learning project of the MERIT club at Tunis Business School. The project involves teaching members many computer skills in a creative way and making professional videos in our platform.</li>
                        </ul>
                    </div>
                    <!---->
                    <div class="singleWork">
                        <div class="companyDate">
                            <div class="workTitle">Full stack web developer @GigaServices</div>
                            <div class="date">2017 - 2020</div>
                        </div>
                        <ul>
                            <li>Developed gigaservices website : <a href="https://gigaservices.tn">gigaservices.tn</a> and <a href="https://admin.gigaservices.tn">admin.gigaservices.tn</a> </li>
                            <li>Developed gigaservices management system software</li>
                        </ul>
                    </div>
                    <!---->
                    <div class="singleWork">
                        <div class="companyDate">
                            <div class="workTitle">Graphic Design - Web development Coach @MERIT TBS</div>
                            <div class="date">2018 - 2020</div>
                        </div>
                        <ul>
                            <li>Tought IT skills ( ie: photo editing "Adobe Photoshop and Illustrator", Video Editing "Camtasia & After effect", Web Development " HTML,CSS,JS,PHP and WordPress") </li>
                        </ul>
                    </div>
                </div>
               
                
            </div>
            <!--End right Part-->
        </div>
        <!--End Bottom Part-->

    </div>

    <div class="cv" id="cv">
      
       <div class="bottomPart">
            <div class="leftPart">

            </div>
            <div class="rightPart">
                <div class="volunteer section">
                    <div class="title">Volunteer Experience</div>
                    <div class="singlevolunteer">
                        <div class="project">
                            <div class="projectTitle">Diploma Ceremony ( 10/2019 )</div>
                        </div>
                        <ul>
                            <li>Contributed in the preparation of all the banners, roll ups, badges design and check in application System development.</li>
                        </ul>
                    </div>
                    <!---->
                    <div class="singlevolunteer">
                        <div class="project">
                            <div class="projectTitle">Video Editing Trainer ( 10/2018 )</div>
                        </div>
                        <ul>
                            <li>Trained UGTE TBS, a group of more than 20 people video editing basics ( camtasia 9 )</li>
                        </ul>
                    </div>
                </div>
                <hr>
                <div class="achievment section">
                    <div class="title">Achievments</div>
                </div>
                <hr>
            </div>
        </div>
    </div>
</div>




