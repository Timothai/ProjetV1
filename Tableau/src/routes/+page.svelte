<script>
    
    let nom=" ";
    let prenom=" ";
    let age=" ";

    let valider=false;

    let vide =[
        {id: 1, nom:""},
        {id: 2, nom:""},
        {id: 3, nom:""}
    ];

    // @ts-ignore
    function tout(event){

        event.preventDefault(); 
        nom = event.target.querySelector('#nom').value;
        prenom = event.target.querySelector('#prenom').value;
        age = event.target.querySelector('#age').value;

        if( nom.trim() === " "|| prenom.trim() ===" " || age.trim() ===" ")
        alert("veuillez remplir tous les champs")

        valider = nom!==" " && prenom!==" "&& age!==" "
        if (valider){
            vide = [];
        }
    }

</script>

<title> Tableau </title>

<h1>Voici le méga tableau</h1>

<p>Non mais c'est vrai</p>

<table>
    <thead>
        <tr>
            <th>Nom</th>
            <th>Prenom</th>
            <th>Age</th>
        </tr>
    </thead>
    <tbody>
        <tr>  
            {#each vide as donnees (donnees.id)}
                <td>{donnees.nom}</td>
            {/each}

            {#if valider}
                <td>{nom}</td>
                <td>{prenom}</td>
                <td>{age}</td>
            {/if}
        </tr>   
    </tbody>
</table>

<form on:submit={tout}>

    <lable for="nom"> Ecris ton nom </lable>
    <input type="nom" id="nom" placeholder="Nom ?"/>
    <br>
    <lable for='prenom'> Ecris ton prenom </lable>
    <input type='prenom' id='prenom' placeholder="Prenom ?"/>
    <br>
    <label for='age'>Ecris ton âge</label>
    <input type='age' id='age' placeholder="Age ?"/>

    <button type="submit" ></button>
</form>

<style>

    table{
        border-collapse: collapse;
    }

    td{
        padding:10px;
        border: 1px solid black;
    }

    th{
        padding: 10px;
        border: 2px solid black;
    }

</style>