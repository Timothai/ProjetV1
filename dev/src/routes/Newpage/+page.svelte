<script>

async function Retour(){

    await new Promise(resolve => setTimeout(resolve,50));
    window.location.href = '/';

}

</script>

<button on:click={Retour}>Retour</button>


<p class="text">Tu es&nbsp;<strong>l'élue </strong> </p>
<title>l'élue c'est toi</title>


<style>

.text{

    text-align: center;
    align-items: center;
    display: flex;
    height: 100vh;
    justify-content: center;
}

</style>