<script>

    import Carre from './Sources/Carre.svelte'
    import {fade} from 'svelte/transition';

    let MotDePasse = ''
    let NomUtilisateur = '';
    let oui = 0;

    async function good (){
        if (NomUtilisateur === 'Timothe' && MotDePasse == 'Foutry'){
            oui = 1;
            await new Promise(resolve => setTimeout(resolve,4000));
            window.location.href = '/Newpage';
        }
        else{
            oui = 2;
            await new Promise(resolve => setTimeout(resolve,4000));
            oui = 0;
        }
    }

</script>

<title> Connexion </title>

<body>

<title> <img src="./LOGO-MADIC.png" alt="logo madic"></title>

<div class="milieu">
    <Carre>
        <img class="image" src="./LOGO-MADIC.png" alt="logo madic">
        <br>
    <form id="connexion" on:submit|preventDefault={good}>
        <label class="milieutext1"> 
                Nom d'utilisateur
                <input bind:value={NomUtilisateur} />
        </label>
        <br>
        <label class="milieutext2">
                Mot de passe
                <input
                bind:value={MotDePasse}/>
        </label>
        <button type="submit">Verifier l'identité </button>
    </form>
        <br>
        
            {#if oui ===1}
            <p transition:fade class="texteverif1">Tu es la bonne personne</p> 
            {:else if oui ===0}
            <p></p>
            {:else}
            <p class="texteverif2">ce n'est pas toi</p>
            {/if}
      

        <a href="/Newpage"> Oui </a>

    </Carre>
</div>

</body>

<style>

    .image{

    width: 225px;
    height: 84px;
    margin-left: 140px;
    margin-top: 20px;

    }
    
    .milieu{

        align-items: center;
        display: flex;
        height: 100vh;
        justify-content: center;
    }

    button{

        margin-top: 10px;
        margin-left: 200px;
        width: 121px;
        height: 33px;
        background-color: #B41919;
        stroke-width: 1px;
        stroke: #000;
        filter: drop-shadow(0px 4px 4px rgba(0, 0, 0, 0.25));

        color: #FFF;
        font-family: Istok Web;
        font-size: 12px;
        font-style: normal;
        font-weight: 700;
        line-height: normal;

    }

    .milieutext1{
        
        color: #000;
        font-family: Inter;
        font-size: 16px;
        font-style: normal;
        font-weight: 600;
        line-height: normal;
        margin-top: 20px;
        margin-left: 80px;
        display:block;
    }

    .milieutext2{
        
        color: #000;
        font-family: Inter;
        font-size: 16px;
        font-style: normal;
        font-weight: 600;
        line-height: normal;
        margin-top: 5px;
        margin-left: 110px;
        display:block;
    }

    .texteverif1{

        color: #C10F0F;
        text-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
        font-family: "Times New Roman";
        font-size: 20px;
        font-style: normal;
        font-weight: 400;
        line-height: normal;
        margin-top: 10px;
        margin-left: 200px;

    }

    .texteverif2{

        color: #000;
        text-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
        font-family: Inter;
        font-size: 15px;
        font-style: normal;
        font-weight: 400;
        line-height: normal;
        margin-top: 10px;
        margin-left: 215px;

    }

    body{

        min-zoom: 100%;
        max-zoom: 100%;
        width: 100vw;
        background-color: aliceblue;
    }

</style>