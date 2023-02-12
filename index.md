# Dans Ma Rue - Anomalies signalées dans les arrondissements de Paris 

![Anomalie sur l'espace public](https://www.leparisien.fr/resizer/gNLMMqzyYqQ3bg4ZKr-BPuYCUL0=/932x582/arc-anglerfish-eu-central-1-prod-leparisien.s3.amazonaws.com/public/NV6GDD5ARUDRYB2GRX234I2BTM.jpg)

## Sommaire
1. [Présentation du projet : Dans Ma Rue - Anomalies signalées](#Jeudedonnees)
2. [Première datavisualisation avec une Carte (Datawrapper)](#Datawrapper)
3. [Deuxième datavisualisation avec Bar Chart Race (Flourish story)](#story)
4. [Troisème datavisualisation : Grid of Donut Charts avec Flourish](#Donut)
5. [Quatriéme datavisualisation avec Datawrapper ](#resolution)
6. [Conclusion](#conclusion)









## 1. Présentation du projet : Dans Ma Rue - Anomalies signalées<a name="Jeudedonnees"></a>

En 2012, la mairie de Paris a lancé une application mobile intitulée “Dans ma rue” afin de permettre aux citoyens de  transmettre directement des anomalies depuis les rues et les jardins de Paris. L'application mobile facilite l'ajout de photos qui permettent aux équipes de terrain de mieux comprendre et traiter les anomalies transmises.

Comment ça marche ? l’utilisateur remplit un formulaire pour déclarer une anomalie : nid de poule dans la chaussée, arbre en mauvais état, un jeu d’enfants abîmé, etc. Un nouvel onglet spécifique dans la catégorie « graffitis », permet aux Parisien·ne·s de signaler les inscriptions haineuses dans les rues de la Ville afin qu'elles soient effacées au plus vite. L’application permet en quelques clics et une photo d’informer les services gestionnaires. [DansMaRue] (https://teleservices.paris.fr/dansmarue/jsp/site/Portal.jsp?page=fodansmarue)

L’open data de Paris collecte des données via cette application et les publie sous forme de jeux de données depuis 2012 à 2022.
[OpenData.Paris] (https://opendata.paris.fr/explore/dataset/dans-ma-rue/information)

Pour cette première présentation j’ai décidé de travailler sur une visualisation des anomalies signalée en 2022 ce qui représente 742 480 lignes de données en fichier csv. La manipulation d’un fichier de telle taille avec des outils gratuits accessible par tout le monde est une mission très difficile. Après avoir visualiser le corpus avec l'outil Openrefine, j'ai remarqué que le mois de juin de l'année 2022 est le mois le plus élevé en termes de signalements (80 639) tandis que le mois de Novembre est le plus bas (24 366 signalements). J'ai donc opter pour une analyse comparative entre ces deux mois et les questions qui me sont venue en  tête sont les  suivantes : 
Quels sont les arrondissements de Paris qui souffrent le plus d'anomalies ? De quelles types sont ces anomalies ? Pourquoi le nombre de signalements est aussi élevé au mois de juin et bas au mois de Novembre ?  

## 2.Première datavisualisation avec une Carte (Datawrapper)<a name="Datawrapper"></a>

J’ai commencé par récupérer les données qui m'intéresse dont : l'arrondissement, calculer le nombre total d’anomalies par arrondissement (des milliers de signalements par jour), récupérer les codes INSEE des arrondissements Parisiens à l’aide d’une requête SPARQL. Ce qui donne : 

```sparql
#Recupérer les codes INSEE des arrondissements de Paris 
PREFIX wikibase: <http://wikiba.se/ontology#>
PREFIX wd: <http://www.wikidata.org/entity/>
PREFIX wdt: <http://www.wikidata.org/prop/direct/>

SELECT ?arrondissements ?INSEE 
WHERE
{

?arrondissements wdt:P131 wd:Q90. #arrondissements de Paris 
?INSEE wdt:P3295 wd:Q156705. #les codes INSEE 

  SERVICE wikibase:label {
	bd:serviceParam wikibase:language "fr,en"}
}

```



**Mois de Juin** 
<table class="tg">
<thead>
  <tr>
    <th class="tg-0pky">Arrondissement</th>
    <th class="tg-0pky">INSEE </th>
    <th class="tg-0pky">Anomalies </th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-0pky">1</td>
    <td class="tg-0pky">75101</td>
    <td class="tg-0pky">7721</td>
  </tr>
  <tr>
    <td class="tg-0pky">2</td>
    <td class="tg-0pky">75102 </td>
    <td class="tg-0pky">0</td>
  </tr>
  <tr>
    <td class="tg-0pky">3</td>
    <td class="tg-0pky">75103&nbsp;&nbsp;&nbsp; </td>
    <td class="tg-0pky">0</td>
  </tr>
  <tr>
    <td class="tg-0pky">4</td>
    <td class="tg-0pky">75104&nbsp;&nbsp;&nbsp; </td>
    <td class="tg-0pky">0</td>
  </tr>
  <tr>
    <td class="tg-0pky">5</td>
    <td class="tg-0pky">75105</td>
    <td class="tg-0pky">1763</td>
  </tr>
  <tr>
    <td class="tg-0pky">6</td>
    <td class="tg-0pky">75106&nbsp;&nbsp;&nbsp; </td>
    <td class="tg-0pky">1721</td>
  </tr>
  <tr>
    <td class="tg-0pky">7</td>
    <td class="tg-0pky">75107 </td>
    <td class="tg-0pky">1201</td>
  </tr>
  <tr>
    <td class="tg-0pky">8</td>
    <td class="tg-0pky">75108&nbsp;&nbsp;&nbsp; </td>
    <td class="tg-0pky">1722</td>
  </tr>
  <tr>
    <td class="tg-0pky">9</td>
    <td class="tg-0pky">75109&nbsp;&nbsp;&nbsp; </td>
    <td class="tg-0pky">3647</td>
  </tr>
  <tr>
    <td class="tg-0pky">10</td>
    <td class="tg-0pky">75100 </td>
    <td class="tg-0pky">8680</td>
  </tr>
  <tr>
    <td class="tg-0pky">11</td>
    <td class="tg-0pky">75110&nbsp;&nbsp;&nbsp; </td>
    <td class="tg-0pky">7142</td>
  </tr>
  <tr>
    <td class="tg-0pky">12</td>
    <td class="tg-0pky">75112&nbsp;&nbsp;&nbsp; </td>
    <td class="tg-0pky">4185</td>
  </tr>
  <tr>
    <td class="tg-0pky">13</td>
    <td class="tg-0pky">75113&nbsp;&nbsp;&nbsp; </td>
    <td class="tg-0pky">4063</td>
  </tr>
  <tr>
    <td class="tg-0pky">14</td>
    <td class="tg-0pky">75114&nbsp;&nbsp;&nbsp; </td>
    <td class="tg-0pky">2353</td>
  </tr>
  <tr>
    <td class="tg-0pky">15</td>
    <td class="tg-0pky">75115 </td>
    <td class="tg-0pky">6555</td>
  </tr>
  <tr>
    <td class="tg-0pky">16</td>
    <td class="tg-0pky">75116&nbsp;&nbsp;&nbsp; </td>
    <td class="tg-0pky">3718</td>
  </tr>
  <tr>
    <td class="tg-0pky">17</td>
    <td class="tg-0pky">75117&nbsp;&nbsp;&nbsp; </td>
    <td class="tg-0pky">6816</td>
  </tr>
  <tr>
    <td class="tg-0pky">18</td>
    <td class="tg-0pky">75118 </td>
    <td class="tg-0pky">6931</td>
  </tr>
  <tr>
    <td class="tg-0pky">19</td>
    <td class="tg-0pky">75119&nbsp;&nbsp;&nbsp; </td>
    <td class="tg-0pky">5260</td>
  </tr>
  <tr>
    <td class="tg-0pky">20</td>
    <td class="tg-0pky">75120 </td>
    <td class="tg-0pky">7161</td>
  </tr>
</tbody>
</table>


**Mois de Novembre** 
<table class="tg">
<thead>
  <tr>
    <th class="tg-0pky">Arrondissement</th>
    <th class="tg-0pky">INSEE </th>
    <th class="tg-0pky">Anomalies </th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-0pky">1</td>
    <td class="tg-0pky">75101</td>
    <td class="tg-0pky">2010</td>
  </tr>
  <tr>
    <td class="tg-0pky">2</td>
    <td class="tg-0pky">75102 </td>
    <td class="tg-0pky">0</td>
  </tr>
  <tr>
    <td class="tg-0pky">3</td>
    <td class="tg-0pky">75103&nbsp;&nbsp;&nbsp; </td>
    <td class="tg-0pky">0</td>
  </tr>
  <tr>
    <td class="tg-0pky">4</td>
    <td class="tg-0pky">75104&nbsp;&nbsp;&nbsp; </td>
    <td class="tg-0pky">0</td>
  </tr>
  <tr>
    <td class="tg-0pky">5</td>
    <td class="tg-0pky">75105</td>
    <td class="tg-0pky">460</td>
  </tr>
  <tr>
    <td class="tg-0pky">6</td>
    <td class="tg-0pky">75106&nbsp;&nbsp;&nbsp; </td>
    <td class="tg-0pky">367</td>
  </tr>
  <tr>
    <td class="tg-0pky">7</td>
    <td class="tg-0pky">75107 </td>
    <td class="tg-0pky">245</td>
  </tr>
  <tr>
    <td class="tg-0pky">8</td>
    <td class="tg-0pky">75108&nbsp;&nbsp;&nbsp; </td>
    <td class="tg-0pky">508</td>
  </tr>
  <tr>
    <td class="tg-0pky">9</td>
    <td class="tg-0pky">75109&nbsp;&nbsp;&nbsp; </td>
    <td class="tg-0pky">1451</td>
  </tr>
  <tr>
    <td class="tg-0pky">10</td>
    <td class="tg-0pky">75100 </td>
    <td class="tg-0pky">1985</td>
  </tr>
  <tr>
    <td class="tg-0pky">11</td>
    <td class="tg-0pky">75110&nbsp;&nbsp;&nbsp; </td>
    <td class="tg-0pky">2432</td>
  </tr>
  <tr>
    <td class="tg-0pky">12</td>
    <td class="tg-0pky">75112&nbsp;&nbsp;&nbsp; </td>
    <td class="tg-0pky">1348</td>
  </tr>
  <tr>
    <td class="tg-0pky">13</td>
    <td class="tg-0pky">75113&nbsp;&nbsp;&nbsp; </td>
    <td class="tg-0pky">1224</td>
  </tr>
  <tr>
    <td class="tg-0pky">14</td>
    <td class="tg-0pky">75114&nbsp;&nbsp;&nbsp; </td>
    <td class="tg-0pky">681</td>
  </tr>
  <tr>
    <td class="tg-0pky">15</td>
    <td class="tg-0pky">75115 </td>
    <td class="tg-0pky">2003</td>
  </tr>
  <tr>
    <td class="tg-0pky">16</td>
    <td class="tg-0pky">75116&nbsp;&nbsp;&nbsp; </td>
    <td class="tg-0pky">1431</td>
  </tr>
  <tr>
    <td class="tg-0pky">17</td>
    <td class="tg-0pky">75117&nbsp;&nbsp;&nbsp; </td>
    <td class="tg-0pky">2032</td>
  </tr>
  <tr>
    <td class="tg-0pky">18</td>
    <td class="tg-0pky">75118 </td>
    <td class="tg-0pky">1875</td>
  </tr>
  <tr>
    <td class="tg-0pky">19</td>
    <td class="tg-0pky">75119&nbsp;&nbsp;&nbsp; </td>
    <td class="tg-0pky">2118</td>
  </tr>
  <tr>
    <td class="tg-0pky">20</td>
    <td class="tg-0pky">75120 </td>
    <td class="tg-0pky">2196</td>
  </tr>
</tbody>
</table>

> Tableau généré avec [Tables Generator](https://www.tablesgenerator.com)



Ces tableaux sont utilisés pour générer des représentations sous forme de cartes sur Datawrapper. Le choix de cette outil se justifie par la disponibilité de la carte des arrondissments de Paris. Le but de ces 2 cartes est de montrer les anomalies signalées par arrondissements en 2022 pour le mois de Juin puis le mois de Novembre. Le code INSEE ainsi que le nombre total de signalements pour chaque arrondissement sont les valeurs qui m’ont permis de construire cette visualisation. 

**Anomalies signalées par arrondissements en mois de Juin 2022**

<iframe title="Anomalies signalées par arrondissements en 2022 " aria-label="Map" id="datawrapper-chart-FytoW" src="https://datawrapper.dwcdn.net/FytoW/2/" scrolling="no" frameborder="0" style="border: none;" width="600" height="444" data-external="1"></iframe>


**Anomalies signalées par arrondissements en mois de Novembre 2022**

<iframe title="Anomalies signalées par arrondissements en mois de Novembre 2022 " aria-label="Map" id="datawrapper-chart-1gUT1" src="https://datawrapper.dwcdn.net/1gUT1/1/" scrolling="no" frameborder="0" style="border: none;" width="600" height="471" data-external="1"></iframe>

**Analyse** 

On constate que le 10 éme  le 11 ème  arrondissement de Paris sont à la tête du classement puisqu'en juin on retrouve 8680 signalements (10éme)  et en Novembre on retrouve 2432 signalements (11éme). En revanche, il y a aucun signalement pour les 2éme, 3éme et 4ème arrondissements. J’ai vérifié les corpus et j’ai consulté l’application mais il n'y a aucune explication à ça.
Pour analyser ces premiers résultats je met en évidence les hypothèses suivantes : 

Si les 10ème et  11ème arrondissements de Paris ont un nombre important de signalements, c'est qu’ils sont les deux arrondissements les plus peuplés et les plus grands en superficie. 

Si les 2éme, 3éme et 4ème arrondissements n’ont aucun signalement, c’est qu’ils sont les moins peuplés et les plus petits en superficie. 

## 3.Deuxième datavisualisation avec Bar Chart Race (Flourish story)<a name="story"></a>

Maintenant, la question qu’il faut se poser c’est comment prouver ou rejeter ces hypothèses ? 

Tout simplement, j’ai commencé par collecter des données sur la superficie et la population des arrondissements de Paris (2022). Ces données seront croisées avec les données du corpus des signalements. OpenRefine est utilisé durant cette étape de croisement des données pour assurer la cohérence entre les données et corriger les erreurs signalé par Flourish tels que les espace en début de cellules, la suppression de colonnes tel que le code INSEE, effectuer plusieurs modifications en un seul passage,comparer les valeurs de 2 colonnes,etc. 

**Voici le tableau généré par OpenRefine**

<html>
<head>
<meta charset="utf-8" />
</head>
<body>
<table>
<tr><th>﻿Arrondissements</th><th>Superficie (Hectare)</th><th>Population (Habitants)</th><th>Anomalies en Juin</th><th>Anomalies en Novembre</th></tr>
<tr><td>Paris 1er arrondissement</td><td>183</td><td>17 100</td><td>7721</td><td>2010</td></tr>
<tr><td>Paris 2e arrondissement</td><td>99</td><td>22 390</td><td>0</td><td>0</td></tr>
<tr><td>Paris 3e arrondissement</td><td>117</td><td>35 991</td><td>0</td><td>0</td></tr>
<tr><td>Paris 4e arrondissement</td><td>160</td><td>27 769</td><td>0</td><td>0</td></tr>
<tr><td>Paris 5e arrondissement</td><td>254</td><td>60 179</td><td>1763</td><td>460</td></tr>
<tr><td>Paris 6e arrondissement</td><td>215</td><td>43 224</td><td>1721</td><td>367</td></tr>
<tr><td>Paris 7e arrondissement</td><td>409</td><td>57 092</td><td>1201</td><td>245</td></tr>
<tr><td>Paris 8e arrondissement</td><td>388</td><td>38 749</td><td>1722</td><td>508</td></tr>
<tr><td>Paris 9e arrondissement</td><td>218</td><td>59 474</td><td>3647</td><td>1451</td></tr>
<tr><td>Paris 10e arrondissement</td><td>289</td><td>94 474</td><td>8680</td><td>1985</td></tr>
<tr><td>Paris 11e arrondissement</td><td>367</td><td>155 006</td><td>7142</td><td>2432</td></tr>
<tr><td>Paris 12e arrondissement</td><td>637</td><td>144 925</td><td>4185</td><td>1348</td></tr>
<tr><td>Paris 13e arrondissement</td><td>715</td><td>182 386</td><td>4063</td><td>1224</td></tr>
<tr><td>Paris 14e arrondissement</td><td>564</td><td>141 102</td><td>2353</td><td>681</td></tr>
<tr><td>Paris 15e arrondissement</td><td>848</td><td>238 190</td><td>6555</td><td>2003</td></tr>
<tr><td>Paris 16e arrondissement</td><td>791</td><td>167 613</td><td>3718</td><td>1431</td></tr>
<tr><td>Paris 17e arrondissement</td><td>567</td><td>170 156</td><td>6816</td><td>2032</td></tr>
<tr><td>Paris 18e arrondissement</td><td>601</td><td>201 374</td><td>6931</td><td>1875</td></tr>
<tr><td>Paris 19e arrondissement</td><td>679</td><td>186 116</td><td>5260</td><td>2118</td></tr>
<tr><td>Paris 20e arrondissement</td><td>598</td><td>197 311</td><td>7161</td><td>2196</td></tr>
</table>
</body>
</html>

[vikidia](https://fr.vikidia.org/wiki/Arrondissements_de_Paris)

**Datavisualisation avec Flourish**


<iframe src='https://flo.uri.sh/story/1825374/embed' title='Interactive or visual content' class='flourish-embed-iframe' frameborder='0' scrolling='no' style='width:100%;height:600px;' sandbox='allow-same-origin allow-forms allow-scripts allow-downloads allow-popups allow-popups-to-escape-sandbox allow-top-navigation-by-user-activation'></iframe><div style='width:100%!;margin-top:4px!important;text-align:right!important;'><a class='flourish-credit' href='https://public.flourish.studio/story/1825374/?utm_source=embed&utm_campaign=story/1825374' target='_top' style='text-decoration:none!important'><img alt='Made with Flourish' src='https://public.flourish.studio/resources/made_with_flourish.svg' style='width:105px!important;height:16px!important;border:none!important;margin:0!important;'> </a></div>

**Conculision** :

Pour répondre à la première hypothèse d’après cette visualisation, le plus grand et le plus peuplé arrondissement de Paris est le 15ème avec une superficie de 848 hectares et une population qui s'élève à 238,190 habitants.
Alors que le 10éme est parmi les plus petits avec une superficie de 289 hectares (la moyenne est de 434,95 hectares) et une population qui s'élève à  94,474. Même chose pour le 11ème arrondissement qui a 367 hectares mais une population un peu plus élevée que le 10éme arrondissement (155 006 habitants). Donc les 8680 signalements du mois de juin ne peuvent pas être justifiés par la superficie ni le nombre d’habitants de cet arrondissement.
Ensuite, pour le mois de Novembre on a dit que l’arrondissement qui a le plus de signalement est le 11ème(2432 anomalies), or d'après cette visualisation cet arrondissement est loins d'être le plus grand ou le plus peuplé car il n’a que  367 hectares avec une population qui s'élève à 155,006 habitants (un peu plus élevée que celle du 10éme arrondissement). 

**On conclut que l'hypothèse suivante est rejeté** : 

“Si les 10ème et 11ème arrondissements de Paris ont un nombre important de signalements, c'est qu’ils sont les deux arrondissements les plus peuplés et les plus grands en superficie.”

Pour répondre à la deuxième hypothèse d’après cette visualisation, les 2éme, 3éme et 4ème arrondissements de Paris sont bien les plus petits en superficie et les moins peuplés puisqu’en première position on a le 2éme arrondissement : 99 hectares, 22,390 habitants.Ensuite,le 3éme arrondissement : 117 hectares, 35,991 habitants. Enfin, le 4ème arrondissement : 160 hectares, 27,769 habitants.Pour rappel, le nombre d’anomalies signalées pour ces 3 arrondissements est de zéro. 

**On conclut que l'hypothèse suivante peut être vrai** : 

“Si les 2éme, 3éme et 4ème arrondissements n’ont aucun signalement, c’est qu’ils sont les moins peuplés et les plus petits en superficie.”

## 4.Troisème datavisualisation : Grid of Donut Charts avec Flourish<a name="Donut"></a>

Cette visualisation réalisée sous forme de Donut nous permet de  visualiser les types d’anomalies signalées en mois de Juin et en mois de Novembre. Pour la réaliser, j’ai récupéré le champ : type d’anomalie et j’ai calculé le total d’anomalie pour chaque type pour les deux mois (Juin et Novembre). Ce qui donne le tableau suivant : 

**a.Tableau** 


| Type d'anomalie                              | Total signalements (Juin) | Total juin en % | Total signalements (Novembre) | Total Novembre en % |
|----------------------------------------------|---------------------------|-----------------|-------------------------------|---------------------|
| Activités   commerciales et professionnelles | 3861                      | 4,8%            | 804                           | 3,6%                |
| Arbres,   végétaux et animaux                | 1167                      | 1,4%            | 239                           | 1,1%                |
| Autos, motos, vélos...                       | 9221                      | 11,4%           | 2214                          | 9,8%                |
| Eau                                          | 651                       | 0,8%            | 104                           | 0,5%                |
| Éclairage / Électricité                      | 455                       | 0,6%            | 297                           | 1,3%                |
| Graffitis,   tags, affiches et autocollants  | 26737                     | 33,2%           | 8226                          | 36,5%               |
| Mobiliers urbains                            | 1861                      | 2,3%            | 540                           | 2,4%                |
| Objets abandonnés                            | 21513                     | 26,7%           | 5788                          | 25,6%               |
| Propreté                                     | 12549                     | 15,6%           | 3546                          | 15,7%               |
| Voirie et espace public                      | 2624                      | 3,3%            | 808                           | 3,6%                |

> Tableau généré avec [Tables Generator](https://www.tablesgenerator.com)



**b.Grid of Donut Charts**

<iframe src='https://flo.uri.sh/visualisation/12721462/embed' title='Interactive or visual content' class='flourish-embed-iframe' frameborder='0' scrolling='no' style='width:100%;height:600px;' sandbox='allow-same-origin allow-forms allow-scripts allow-downloads allow-popups allow-popups-to-escape-sandbox allow-top-navigation-by-user-activation'></iframe><div style='width:100%!;margin-top:4px!important;text-align:right!important;'><a class='flourish-credit' href='https://public.flourish.studio/visualisation/12721462/?utm_source=embed&utm_campaign=visualisation/12721462' target='_top' style='text-decoration:none!important'><img alt='Made with Flourish' src='https://public.flourish.studio/resources/made_with_flourish.svg' style='width:105px!important;height:16px!important;border:none!important;margin:0!important;'> </a></div>

**c.Analyse**


On constate que les utilisateurs de l’application “Dans ma rue” signalent beaucoup les graffitis, tags, affiches et autocollants. Ce qui représente 36,5% des anomalies signalées au mois de Novembre et 33,2% des anomalies signalées pour le mois de juin. Finalement, l'ajout de cette option dans l'applicaion est très utile.   

## 5.Quatriéme datavisualisation avec Datawrapper :<a name="resolution"></a>

**Les anomalies résolu et non résolu**

Après avoir  visionner et représenter les données du mois de juin et Novembre de l’année 2022. Il était temps de revoir le corpus dans sa globalité et se poser la question suivante : Est ce que toutes ces anomalies signalées par les utilisateurs de cette application ont été résolues ou pas ? 
Pour répondre à cette question, je me suis appuyé sur le jeu de données de 2022 mais plus précisément les champs : type d'anomalie et intervenant. J’ai  calculé le nombre total d’interventions pour chaque anomalie et j’ai considéré que là ou il n y a pas le nom de l'intervenant champ vide) égale à une non résolution de l’anomalie. Ceci peut être faux parce que par exemple le nom de l'intervenant n’a pas encore été saisi,  comme ça peut être vrai. Je suis partie de l'idée que le jeu de données en question est mis à jour quotidiennement comme indiqué dans la barre d’information de l’open data de Paris donc les champs vides signifient qu’il y a pas eu d'intervention pour résoudre le problème. D’autant plus que c'est des signalements de 2022 et non 2023. Ce qui donne le tableau suivant : 

<html>
<head>

<meta charset="utf-8" />
</head>
<body>
<table>
<tr><th>Anomalie</th><th>Résolu</th><th>Non résolu</th></tr>
<tr><td>Arbres, végétaux et animaux</td><td>1018.0</td><td>149.0</td></tr>
<tr><td>Activités commerciales et professionnelles</td><td>3861.0</td><td>0.0</td></tr>
<tr><td>Autos, motos, vélos...</td><td>9221.0</td><td>0.0</td></tr>
<tr><td>Eau</td><td>651.0</td><td>0.0</td></tr>
<tr><td>Éclairage / Électricité</td><td>455.0</td><td>0.0</td></tr>
<tr><td>Graffitis, tags, affiches et autocollants</td><td>26737.0</td><td>0.0</td></tr>
<tr><td>Mobiliers urbains</td><td>1861.0</td><td>0.0</td></tr>
<tr><td>Objets abandonnés</td><td>21513.0</td><td>0.0</td></tr>
<tr><td>Propreté</td><td>12549.0</td><td>0.0</td></tr>
<tr><td>Voirie et espace public</td><td>2624.0</td><td>0.0</td></tr>
</table>
</body>
</html>


**Graphe**

<iframe title="Les anomalies résolu et non résolu année 2022 " aria-label="Tracé de la série" id="datawrapper-chart-vryof" src="https://datawrapper.dwcdn.net/vryof/1/" scrolling="no" frameborder="0" style="border: none;" width="600" height="292" data-external="1"></iframe>

**Analyse**


Le nombre total de signalements pour l’année 2022 est de 80639. On constate que la plupart des anomalies ont été résolu sauf pour : Arbres, végétaux et animaux 1018 d’anomalies ont été traité et 149 anomalies n’ont pas été traité. On conclut que l’application est une bonne initiative, cependant 

![2023-02-12 15_35_30-DansMaRue - Paris dans l’App Store](https://user-images.githubusercontent.com/122401240/218317752-5d8592ab-09c4-4d93-af78-c1cb0405f9bc.png)


##6.Conclusion : <a name="conclusion"></a>
