<script>

import AboutMe from "../components/AboutMe.svelte";

</script>

<style>
    .container{
        background-color: black;
        width: 100vw;
        height: 100vh;
        font-size: 70px;
        display: flex;
        justify-content: center;
        align-items: center;
        position: relative;
        color: white;
        font-weight: 600;
    }
    .p1,.p2{
    position: absolute;
    filter: invert(9%) sepia(100%) saturate(5593%) hue-rotate(335deg) brightness(117%) contrast(110%);  
    }
    .p1{
        width: 450px;
        top: 330px;
        left: -145px;
        transform: rotate(126deg);
    }
    .p2{
        width: 500px;
        top: 80px;
        right: -171px;
        transform: rotate(-80deg);
        
}
</style>
<div class="container">
    <img class="p1" src="../imgs/patterns/p1.png" alt="pattern">
    <img class="p2" src="../imgs/patterns/p4.png" alt="pattern">
    UNDER CONSTRUCTION...
</div>