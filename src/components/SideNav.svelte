

<style>
.sideNav{
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: flex-end;
    width: 145px;
    min-width: 145px;
    height: 100%;
    border-right: 2px solid gray;
    z-index: 2;
}
a{
    margin: 13px 0;
}
a img{
    width: 23px;
    filter: invert(99%) sepia(56%) saturate(2%) hue-rotate(30deg) brightness(105%) contrast(100%);
}
a img:hover{
    filter: invert(14%) sepia(74%) saturate(6320%) hue-rotate(335deg) brightness(94%) contrast(108%);
}
.list{
    margin-bottom: 70px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: flex-end;
}
@media only screen and (max-width:1500px){
    .list{
        margin-bottom: 10px;
    }
}
@media only screen and (max-width: 700px){
   
   .sideNav{
       display: none;
   }
   
   
} 
</style>
<div class="sideNav">
    <div class="list">
        <a href="https://github.com/ahmedbm27" target="_blank" ><img src="./imgs/icons/github.svg" alt="github"></a>
        <a href="https://www.linkedin.com/in/ahmedbm27/" target="_blank"><img src="./imgs/icons/linkedin.svg" alt="linkedin"></a>
        <a href="https://www.instagram.com/ahmedbenmah" target="_blank"><img src="./imgs/icons/instagram.svg" alt="instagram"></a>
        <a href="https://www.facebook.com/profile.php?id=100014229247552" target="_blank"><img src="./imgs/icons/facebook.svg" alt="facebook"></a>
    </div>
    
</div>