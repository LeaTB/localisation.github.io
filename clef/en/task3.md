# SimpleText@CLEF-2022 Tâches

[Accueil](./) | [Call for papers](./CFP) | [Dates importantes](./dates) | [Tâches](./tasks)  | [Outils](./tools)  
[Programme](./program) | [Publications](./publications) | [Organisateurs](./organisers) | [Contacts](./contact) | [CLEF-2023](https://simpletext-project.com/2023/clef)


---

## Directives pour les tâches SimpleText

Nous vous invitons à soumettre à la fois des exécutions automatiques et manuelles ! Les interventions manuelles doivent être signalées.

---

<button>[Accès](./tasks)</button> | <button>[Tâche 1](./task1)</button> | <button>[Tâche 2](./task2)</button> | <button>[Tâche 3](./task3)</button>| <button>[Tâche 4](./task4)</button>

<br>

## Tâche 3 : Réécrivez ceci ! En fonction d'une requête, simplifiez des passages de résumés scientifiques. 

Le but de cette tâche est de fournir une version simplifiée de passages de texte (phrases) par rapport à une requête. Les participants recevront des requêtes et des résumés d'articles scientifiques. Les résumés peuvent être divisés en phrases. Les passages simplifiés seront évalués manuellement avec l'utilisation éventuelle de métriques d'agrégation.

**Format d'entrée:** 
Les données de formation et de test sont fournies dans les formats JSON et CSV avec les champs suivants :
* *snt_id* : un identifiant unique de passage (phrase).
*source_snt* : texte du passage
*doc_id* : un identifiant unique du document source
*query_id* : un identifiant de requête
*query_text* : la simplification doit être faite par rapport à cette requête.

*Exemple d'entrée:*

*{"snt_id" : "G11.1_2892036907_2", "source_snt" : "Avec le nombre croissant de véhicules aériens sans pilote participant à des activités dans le domaine civil et commercial, il existe un besoin accru d'autonomie dans ces systèmes également.", "doc_id":2892036907, "query_id" : "G11.1", "query_text" : "drones"}*

**Format de sortie:** 
Liste des termes à contextualiser dans un format **JSON** ou un fichier tabulé TSV (pour les exécutions manuelles) avec les champs suivants :
* *run_id* : ID de l'exécution commençant par **team_id_task_3_**.
* *manual* : Si l'exécution est manuelle {0,1}
*snt_id* : un identifiant unique de passage (phrase) du fichier d'entrée. 
*snt_simplifié* : Texte du passage simplifié 

*Exemple de sortie* :
{"run_id" : "BTU_task_3_run1", "manual":1, "snt_id" : "G11.1_2892036907_2", "simplified_snt" : "Les drones sont de plus en plus utilisés dans le domaine civil et commercial et doivent être autonomes."}

*Vérificateur de format de sortie*

Vous pouvez utiliser ce script python3 pour vérifier le format de sortie. Ce script nécessite Python 3 et la bibliothèque Pandas :
[Télécharger le vérificateur de sortie python](../check_format.py)

**Disclaimer:** En téléchargeant et en utilisant ces données, vous acceptez les conditions d'utilisation. Toute utilisation des données à des fins autres que la recherche universitaire constituerait une violation de l'utilisation prévue de ces données. 

Par conséquent, en téléchargeant et en utilisant ces données, vous donnez les assurances suivantes concernant les données SimpleText :
1. Vous n'utiliserez pas et ne permettrez pas à d'autres d'utiliser les données dans les ensembles de données SimpleText de quelque manière que ce soit, sauf pour les cours et la recherche universitaire.
2. Vous ne divulguerez, ne donnerez ou ne transmettrez à aucun moment (de quelque manière ou forme que ce soit ou à quelque fin que ce soit) les données (ou toute partie de celles-ci) à tout endroit ou personne, y compris, mais sans s'y limiter, la mise à disposition des données sur Internet et la copie des données sur tout système de stockage basé sur le cloud.
3. Vous ne libérerez pas et ne permettrez pas à d'autres de libérer l'ensemble des données ou toute partie de celles-ci à toute personne. 

En cas de violation des conditions d'accès aux données à des fins scientifiques, cet accès peut être retiré à l'entité de recherche et/ou au chercheur. L'entité de recherche peut également être tenue de payer des dommages et intérêts à des tiers ou être invitée à prendre des mesures disciplinaires à l'encontre du chercheur fautif. 

### Évaluation
Les passages simplifiés seront évalués manuellement avec l'utilisation éventuelle de métriques d'agrégation.

### Soumission des résultats :
Les participants doivent placer leurs résultats d'exécution dans le dossier Documents créé pour leur utilisateur et **soumettre les résultats par email** à *contact@simpletext-project.com*.

L'objet du courriel doit être au format **[CLEF TASK 3] TEAM_ID**. 

Les runs doivent être soumis sous forme de <ins>Dossier ZIP des fichiers JSON correspondants</ins>. Les runs manuels peuvent être soumis au format CSV. 

Un courriel de confirmation sera envoyé dans les 2 jours suivant la date limite de soumission. 

## Comment citer
Si vous étendez ou utilisez ce travail, veuillez citer le [papier] (https://doi.org/10.1007/978-3-031-13643-6_28) où il a été présenté :
```
Liana Ermakova, Eric SanJuan, Jaap Kamps, Stéphane Huet, Irina Ovchinnikova, Diana Nurbakova, 
Sílvia Araújo, Radia Hannachi, Elise Mathurin, et Patrice Bellot. 2022. 
Aperçu du laboratoire SimpleText de CLEF 2022 : Simplification automatique de textes scientifiques. 
In Experimental IR Meets Multilinguality, Multimodality, and Interaction : 13th International 
Conference of the CLEF Association, CLEF 2022, Bologna, Italy, September 5-8, 2022, Proceedings. 
Springer-Verlag, Berlin, Heidelberg, 470-494. https://doi.org/10.1007/978-3-031-13643-6_28
```
[Article](https://doi.org/10.1007/978-3-031-13643-6_28)

[Télécharger .BIB](../../BibTeX/ermakova_overview_2022.bib)
