# SimpleText@CLEF-2022 Accueil

---

[Accueil](./) | [Call for papers](./CFP) | [Dates importantes](./dates) | [Tâches](./tasks)  | [Outils](./tools)  
[Programme](./program) | [Publications](./publications) | [Organisateurs](./organisers) | [Contacts](./contact) | [CLEF-2023](https://simpletext-project.com/2023/clef)
<!--- <img src="https://github.com/LeaTB/localisation.github.io/blob/francais/clef/logo.png" width="30">https://simpletext-project.com/2022/clef/') --->

---

<img align="left" src="https://github.com/LeaTB/localisation.github.io/blob/francais/clef/logo.png?raw=true" width="100"/>  

## SimpleText : Simplification automatique de textes scientifiques


### Thème et objectifs du laboratoire

SimpleText relève les défis techniques et les défis d'évaluation en fournissant des données et des repères appropriés pour la simplification des textes. 
<br/>Nous proposons les tâches suivantes : 
* [TÂCHE 1 Qu'est-ce qui est dedans (ou dehors) ?](./task1)
Sélectionner les passages à inclure dans un résumé simplifié, étant donné une requête.
* [TÂCHE 2 Qu'est-ce qui n'est pas clair ?](./task2)
A partir d'un passage et d'une question, classer les termes/concepts qui doivent être expliqués pour comprendre ce passage (définitions, contexte, applications,..). 
* [TÂCHE 3 Réécrire ce texte](./task3)
A partir d'une requête, simplifier des passages de résumés scientifiques. 
* [TÂCHE NON DONNEE](./task4)
Nous accueillons toute soumission qui utilise nos données !


Pour faire face à ces défis, SimpleText vise à répondre aux questions de recherche suivantes :  
<br/>RQ1 — Quelle expression textuelle porteuse d'informations doit être simplifiée (document et passage à inclure dans le résumé simplifié) ?
<br/>RQ2 — Quel type d'information de base doit être fourni (quels termes doivent être contextualisés en donnant une définition et/ou une application) ? Quelles sont les informations les plus pertinentes ou les plus utiles ? 
<br/>RQ3 — Comment améliorer la lisibilité d'un texte court donné (par exemple en réduisant le vocabulaire et la complexité syntaxique) avec un taux acceptable de distorsion de l'information ? 

### Signification pour le domaine et pertinence pour CLEF

Avoir une culture scientifique est une capacité importante pour les gens. Elle est l'une
l'une des clés de la pensée critique, de la prise de décision objective et du jugement de la validité et de l'importance des résultats et des arguments.
jugement de la validité et de la signification des résultats et des arguments,
ce qui permet de discerner les faits de la fiction. Ainsi, le fait de posséder des connaissances
connaissances scientifiques de base peut également aider à préserver sa santé, tant
physiologique et mentale. La pandémie de COVID-19 en est un bon exemple.
exemple d'une telle question. Comprendre le problème lui-même, connaître
et appliquer les règles de distanciation sociale et les politiques sanitaires,
choisir d'utiliser ou d'éviter des procédures particulières de traitement ou de prévention
peuvent devenir cruciaux. Dans le contexte d'une pandémie, l'information qualifiée et opportune doit atteindre tout le monde et être accessible.
qualifiée et opportune doit atteindre tout le monde et être accessible. C'est
ce qui motive des projets tels que [EasyCovid](https://easycovid19.org/).

Cependant, les textes scientifiques sont souvent difficiles à comprendre, car ils requièrent
de solides connaissances de base et utilisent une terminologie délicate. Bien que des
récents efforts de simplification des textes, l'élimination de ces
l'élimination automatique de ces barrières de compréhension entre les textes scientifiques et le
public de manière automatique reste un défi à relever. SimpleText
Lab rassemble des chercheurs et des praticiens travaillant sur la
génération de résumés simplifiés de textes scientifiques. Il s'agit d'un nouveau
laboratoire d'évaluation qui fait suite à l'atelier [SimpleText-2021](https://simpletext-project.com/2021/clef/en/). Toutes les
perspectives sur la vulgarisation scientifique automatique sont les bienvenues,
y compris mais sans s'y limiter : Le traitement du langage naturel (NLP),
la recherche d'information (RI), la linguistique, le journalisme scientifique, etc.

### Scénarios

L'objectif est de créer un résumé simplifié de plusieurs documents scientifiques en fonction d'une requête donnée.
scientifiques multiples, basé sur une requête donnée, qui fournit à l'utilisateur une
un résumé simplifié instantané sur un sujet spécifique qui l'intéresse.
ou de générer un résumé quotidien, par exemple pour ArXiv.

### Evaluation setup, metrics, and tasks 

Ensemble de données : Nous utilisons le [Réseau de citations
de citations](https://www.aminer.org/citation): DBLP+Citation, ACM Citation
network. Un index de recherche élastique est fourni aux participants
accessible par une interface utilisateur graphique. Cet index est adéquat pour :
<br/>•	Appliquer des méthodes de base de recherche de passages basées sur des modèles de RI vectoriels ou linguistiques
<br/>•	Générer des modèles d'allocation de Dirichlet latente, 
<br/>•	Entraîner les réseaux neuronaux graphiques pour la recommandation de citations, comme cela est fait dans [Stellar Graph](https://stellargraph.readthedocs.io/) par exemple,
<br/>•	Appliquer des transformateurs bidirectionnels profonds pour l'expansion des requêtes...

Les données sont de deux ordres : *Médecine* et *Science informatique*, deux domaines
parmi les plus populaires dans des forums comme
[ELI5](https://www.reddit.com/r/explainlikeimfive/).


Requêtes en anglais : Pour cette édition, les requêtes sont une sélection de titres de presse récents du Guardian enrichie de mots-clés extraits manuellement du contenu des articles. Il a été vérifié que chaque mot-clé permet d'extraire au moins 5 résumés pertinents. L'utilisation de ces mots-clés est facultative. 
<br/>Format d'entrée pour toutes les tâches :
<br/>•	Les sujets sont au format MD
<br/>•	Articles en texte intégral du Guardian (lien, dossier avec textes intégraux au format MD)
<br/>•	Index ElasticSearch sur le serveur de données
<br/>•	Vidage complet du DBLP au format JSON.GZ
<br/>•	Extraction des résumés DBLP pour chaque sujet dans le format MD suivant (doc_id, année, résumé)

## Comment citer
Si vous étendez ou utilisez ce travail, veuillez citer le [article](https://doi.org/10.1007/978-3-031-13643-6_28) où il a été présenté :
```
Liana Ermakova, Eric SanJuan, Jaap Kamps, Stéphane Huet, Irina Ovchinnikova, Diana Nurbakova, 
Sílvia Araújo, Radia Hannachi, Elise Mathurin, et Patrice Bellot. 2022. 
Vue d'ensemble du laboratoire SimpleText de la CLEF 2022 : Simplification automatique de textes scientifiques.  
Dans Experimental IR Meets Multilinguality, Multimodality, and Interaction: 13th International 
Conference of the CLEF Association, CLEF 2022, Bologne, Italie, September 5–8, 2022, Compte rendu. 
Springer-Verlag, Berlin, Heidelberg, 470–494. https://doi.org/10.1007/978-3-031-13643-6_28
```
[Paper](https://doi.org/10.1007/978-3-031-13643-6_28)

[Dowload .BIB](../../BibTeX/ermakova_overview_2022.bib)

---

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<img src="https://github.com/LeaTB/localisation.github.io/blob/francais/clef/en/clef_logo_2022.png?raw=true" width="300">](http://www.clef-initiative.eu/) &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <img src="https://github.com/simpletext-madics/2021/blob/main/clef/logo-clef-initiative.png?raw=true" width="200">
