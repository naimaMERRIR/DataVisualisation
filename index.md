## 1.Dans Ma Rue - Anomalies signalées
En 2012, la mairie de Paris a lancé une application mobile intitulée “Dans ma rue” afin de permettre aux citoyens de  transmettre directement des anomalies depuis les rues et les jardins de Paris. L'application mobile facilite l'ajout de photos qui permettent aux équipes de terrain de mieux comprendre et traiter les anomalies transmises. Comment ça marche ? l’utilisateur remplit un formulaire pour déclarer une anomalie : nid de poule dans la chaussée, arbre en mauvais état, un jeu d’enfants abîmé, objets encombrants laissés à l’abandon, une signalisation routière défectueuse, dépôts d’encombrants ou de détritus, etc. Un nouvel onglet spécifique dans la catégorie « graffitis », permet aux Parisien·ne·s de signaler les inscriptions haineuses dans les rues de la Ville afin qu'elles soient effacées au plus vite. L’application permet en quelques clics et une photo d’informer les services gestionnaires.[DansMaRue] (https://teleservices.paris.fr/dansmarue/jsp/site/Portal.jsp?page=fodansmarue)
L’open data de la ville de Paris  collecte des données via cette application pour les publier sous forme d’un jeu de données.La platefrome publie le corpus des anomalies signalées par les utilisateurs de cette application de 2012 à 2022.[OpenData.Paris] (https://opendata.paris.fr/explore/dataset/dans-ma-rue/information)

Pour cette première présentation j’ai décidé de travailler sur une visualisation des anomalies signalée en 2022 ce qui représente 742 480 lignes de données en fichier csv. Après avoir bien visualiser le corpus avec l'outil Openrefine, j'ai remarqué que le mois de juin de l'année 2022 est le mois le plus élevé en termes de signalements (80 639) tandis que le mois de Novembre est le plus bas (24 366 signalements). J'ai donc opter pour une analyse comparative entre ces deux mois pour répondre aux questions suivantes : 
Quel est l’arrondissement de Paris qui souffre le plus d'anomalies ? Quels sont les origines de ces anomalies ? Pourquoi le nombre de signalements est aussi élevé au mois de juin et bas au mois de Novembre ?  
J’ai commencé par récupérer les données qui m'intéressent dont : l'arrondissement, calculer le nombre total d’anomalies par arrondissement (des milliers de signalements par jour), récupérer les codes INSEE des arrondissements Parisiens à l’aide d’ une requête SPARQL. Ce qui donne les tableaux suivant : 

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
## 2.Première datavisualisation avec une Carte (Datawrapper) 

Ces tableaux sont utilisés pour générer des représentations sous forme de cartes sur Datawrapper. Le choix de cette outil se justifie par la disponibilité de la carte des arrondissments de Paris.Le but de ces 2 cartes est de montrer les anomalies signalées par arrondissements en 2022 pour le mois de Juin puis le mois de Novembre. Le code INSEE ainsi que le nombre total de signalements pour  chaque arrondissement sont les valeurs qui m’ont permis de construire cette visualisation. En cliquant sur un élément de la légende, on aperçoit à quoi ça correspond sur la carte. 

**Anomalies signalées par arrondissements en mois de Juin 2022**

<iframe title="Anomalies signalées par arrondissements en 2022 " aria-label="Map" id="datawrapper-chart-FytoW" src="https://datawrapper.dwcdn.net/FytoW/2/" scrolling="no" frameborder="0" style="border: none;" width="600" height="444" data-external="1"></iframe>


**Anomalies signalées par arrondissements en mois de Novembre 2022**

<iframe title="Anomalies signalées par arrondissements en mois de Novembre 2022 " aria-label="Map" id="datawrapper-chart-1gUT1" src="https://datawrapper.dwcdn.net/1gUT1/1/" scrolling="no" frameborder="0" style="border: none;" width="600" height="471" data-external="1"></iframe>

**Analyse** 
On constate que le 10 éme  le 11 ème  arrondissement de Paris sont à la tête du classement puisqu'en juin on retrouve 8680 signalements (10éme)  et en Novembre on retrouve 2432   signalements (11éme). Pour expliquer ces premiers résultats je met en évidence l’hypothèse suivante : 
Si le 10ème et le 11ème arrondissement de Paris ont un nombre important de signalements, cela signifie qu’ils sont les deux arrondissements les plus peuplés et les plus grands en superficie. 
Maintenant, la question qu’il faut se poser c’est comment prouver ou rejeter cette hypothèse ? 
