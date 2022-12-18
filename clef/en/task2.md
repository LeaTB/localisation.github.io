# SimpleText@CLEF-2022 Tâches

[Accueil](./) | [Call for papers](./CFP) | [Dates importantes](./dates) | [Tâches](./tasks)  | [Outils](./tools)  
[Programme](./program) | [Publications](./publications) | [Organisateurs](./organisers) | [Contacts](./contact) | [CLEF-2023](https://simpletext-project.com/2023/clef)


---

## Directives pour les tâches SimpleText

Nous vous invitons à soumettre à la fois des exécutions automatiques et manuelles ! Les interventions manuelles doivent être signalées.

---

<button>[Accès](./tasks)</button> | <button>[Tâche 1](./task1)</button> | <button>[Tâche 2](./task2)</button> | <button>[Tâche 3](./task3)</button>| <button>[Tâche 4](./task4)</button>

<br>

## Tâche 2 : Qu'est-ce qui n'est pas clair ? Étant donné un passage et une requête, classez les termes/concepts qui doivent être expliqués pour comprendre ce passage (définitions, contexte, applications,..).

L'objectif de cette tâche est de déterminer quels termes (jusqu'à 5) nécessitent une explication et une contextualisation pour aider un lecteur à comprendre un texte scientifique complexe - par exemple, en ce qui concerne une requête, les termes qui doivent être contextualisés (avec une définition, un exemple et/ou un cas d'utilisation). 
Pour chaque passage, les participants doivent fournir une liste classée des termes difficiles avec les notes correspondantes sur l'échelle 1-3 (3 pour les termes les plus difficiles, tandis que le sens des termes notés 1 peut être déduit ou deviné) et sur l'échelle 1-5 (5 pour les termes les plus difficiles). 
Les passages (phrases) sont considérés comme indépendants, c'est-à-dire que la répétition de termes difficiles est autorisée. Le regroupement des termes et des mesures automatiques (précision de la classification binaire des termes, NDCG pour le classement des termes, statistiques de kappa...) seront utilisés pour évaluer ces résultats.

**Format d'entrée:** 
Les données de formation et de test sont fournies dans les formats JSON et CSV avec les champs suivants :
* `snt_id` : un identifiant unique de passage (phrase)
* `source_snt` : texte du passage
* `doc_id` : un identifiant unique du document source
* `query_id` : un identifiant de requête
* `query_text` : les termes difficiles à extraire des phrases par rapport à cette requête.

*Exemple de saisie:*

```
{"snt_id":"G06.2_2548923997_3",
"source_snt":"Ces systèmes de communication rendent les véhicules à conduite autonome vulnérables à de nombreux types d'attaques malveillantes, telles que les attaques Sybil, les dénis de service (DoS), les trous noirs, les trous gris et les trous de ver.",
"doc_id":2548923997,
"query_id":"G06.2",
"query_text":"conduite autonome"}
```

**Format de sortie:** 

Liste des termes à contextualiser dans un format **JSON** ou un fichier tabulé TSV (pour les exécutions manuelles) avec les champs suivants :
* `run_id` : ID de l'exécution commençant par **team_id_task_id_**.
* `manual` : Si l'exécution est manuelle {0,1}
* `snt_id` : Un identifiant unique de passage (phrase) du fichier d'entrée. 
* `term` : Terme ou autre phrase à expliquer
* `term_rank_snt` : rang de difficulté du terme dans la phrase donnée
* `score_5` : score de difficulté du terme sur une échelle de 1 à 5 (5 étant le terme le plus difficile)
* `score_3` : note de difficulté du terme sur une échelle de 1 à 3 (3 étant le terme le plus difficile).

*Exemple de sortie* :

```{json}
{"run_id":"NP_task_2_run1",
"manual":1,
"snt_id":"G06.2_2548923997_3",
"terme" : "attaque par trou noir",
"term_rank_snt":1,
"score_5":5,
"score_3":3},

{"run_id":"NP_task_2_run1",
"manual":1,
"snt_id":"G06.2_2548923997_3",
"terme" : "attaque par trou gris",
"term_rank_snt":2,
"score_5":5,
"score_3":3},

{"run_id":"NP_task_2_run1",
"manual":1,
"snt_id":"G06.2_2548923997_3",
"term" : "Sybil attack",
"term_rank_snt":3,
"score_5":5,
"score_3":3},

{"run_id":"NP_task_2_run1",
"manual":1,
"snt_id":"G06.2_2548923997_3",
"term" : "attaque par trou de ver",
"term_rank_snt":4,
"score_5":5,"score_3":3},

{"run_id":"NP_task_2_run1",
"manual":1,
"snt_id":"G06.2_2548923997_3",
"term" : "Attaque par déni de service",
"term_rank_snt":5,
"score_5":4,
"score_3":3}
```

*Vérification du format de sortie*

Vous pouvez utiliser ce script python3 pour vérifier le format de sortie. Ce script nécessite Python 3 et la bibliothèque Pandas :
[Download python output checker](../check_format.py)

**Disclaimer:** En téléchargeant et en utilisant ces données, vous acceptez les conditions d'utilisation. Toute utilisation des données à des fins autres que la recherche universitaire constituerait une violation de l'utilisation prévue de ces données. 

Par conséquent, en téléchargeant et en utilisant ces données, vous donnez les assurances suivantes concernant les données SimpleText :
1. Vous n'utiliserez pas et ne permettrez pas à d'autres d'utiliser les données dans les ensembles de données SimpleText de quelque manière que ce soit, sauf pour les cours et la recherche universitaire.
2. Vous ne divulguerez, ne donnerez ou ne transmettrez à aucun moment (de quelque manière ou forme que ce soit ou à quelque fin que ce soit) les données (ou toute partie de celles-ci) à tout endroit ou personne, y compris, mais sans s'y limiter, la mise à disposition des données sur Internet et la copie des données sur tout système de stockage basé sur le cloud.
3. Vous ne libérerez pas et ne permettrez pas à d'autres de libérer l'ensemble des données ou toute partie de celles-ci à toute personne. 

En cas de violation des conditions d'accès aux données à des fins scientifiques, cet accès peut être retiré à l'entité de recherche et/ou au chercheur. L'entité de recherche peut également être tenue de payer des dommages et intérêts à des tiers ou être invitée à prendre des mesures disciplinaires à l'encontre du chercheur fautif. 


### Évaluation
Le regroupement des termes et les métriques automatiques (précision de la classification binaire des termes, NDCG pour le classement des termes, statistiques de kappa...) seront utilisés pour évaluer ces résultats.

### Soumission des résultats :
Les participants doivent placer leurs résultats d'exécution dans le dossier Documents créé pour leur utilisateur et **soumettre les résultats par email** à *contact@simpletext-project.com*.

L'objet du courriel doit être au format **[CLEF TASK 2] TEAM_ID**. 

Les exécutions doivent être soumises sous la forme d'un dossier <ins>ZIP des fichiers JSON correspondants</ins>. Les runs manuels peuvent être soumis au format CSV. 

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
