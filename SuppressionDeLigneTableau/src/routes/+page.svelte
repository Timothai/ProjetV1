<script>
    let tableauDonnees = [
        { id: 1, nom: 'John', prenom: 'Doe', age: 30 },
        { id: 2, nom: 'Jane', prenom: 'Smith', age: 25 },
        { id: 3, nom: 'Bob', prenom: 'Johnson', age: 35 }
    ];

    function supprimerLigne(id) {
        // Filtrer le tableau pour supprimer la ligne avec l'ID donné
        tableauDonnees = tableauDonnees.filter(item => item.id !== id);
    }
</script>

<main>
    <h1>Tableau de données</h1>
    <table>
        <thead>
            <tr>
                <th>ID</th>
                <th>Nom</th>
                <th>Prénom</th>
                <th>Âge</th>
                <th>Action</th>
            </tr>
        </thead>
        <tbody>
            {#each tableauDonnees as donnees (donnees.id)}
                <tr>
                    <td>{donnees.id}</td>
                    <td>{donnees.nom}</td>
                    <td>{donnees.prenom}</td>
                    <td>{donnees.age}</td>
                    <td><button on:click={() => supprimerLigne(donnees.id)}>Supprimer</button></td>
                </tr>
            {/each}
        </tbody>
    </table>
</main>
