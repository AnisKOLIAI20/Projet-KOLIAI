# Les flux d'immigration dans le monde 
<a href="https://goopics.net/i/dj6acf"><img src="https://i.goopics.net/dj6acf.jpg" alt="Image"></a>
**En tant qu’immigrer j’ai trouvé intéressant de m’orienter vers ces jeux donnés, les jeux données que j'ai utilisé sont en langue française.** 

# Table des matières
1. [Traitement des données sur le flux d'immigration par pays](#1-Traitement-des-données-sur-le-flux-d'immigration-par-pays)
2. [Première datavisualisation avec type chart column chart (Datawrapper)](#2-Première-datavisualisation-avec-type-chart-column-chart-Datawrapper)
3. [datavisualisation avec une carte (Datawrapper)](3-datavisualisation-avec-une-carte-(Datawrapper)) 
4. [Troisième datavisualisation avec Bar chart race (Flourish)](#4troisième-datavisualisation-avec-bar-chart-race-flourish)
5. [Visualisation de la capitale de l'Algerie avec Wikidata Query Service](#5-Visualisation-avec-Wikidata-Query-Service) 

## 1. Traitement de données sur le flux d'immigration par pays
Le données des flux on été trouvé sur le site [open Data](https://www.data.gouv.fr/fr/#consulté). j'ai décidé de faire sortir que les information utile et interéssante tel que les pays, année, population, nombre de flux par pays etc. Quelque fois y'avais un manque de donné j'ai utilisé excel pour ajouté des information on les cherchant sur Google et on nettoyant les données et suprimer les information inutile. 
## 2. Datavisualisation avec une column chart (Datawrapper)
Pour réalisé le visuel des données réuni, j'ai décidé d'utiliser le graphique  "column chart" avec trois paramètres le premier c'est Refine j'ai selectionné la colomne que je voulais avec l'apparence et la couleur que j'ai choisi et aussi l'annotation et la mise en page. Ensuite, 

## 2. Première datavisualisation avec type chart column chart (Datawrapper)

<iframe title="Flux d'immigration 2012" aria-label="Graphique en colonnes" id="datawrapper-chart-4zZTr" src="https://datawrapper.dwcdn.net/4zZTr/1/" scrolling="no" frameborder="0" style="width: 0; min-width: 100% !important; border: none;" height="330" data-external="1"></iframe><script type="text/javascript">!function(){"use strict";window.addEventListener("message",(function(e){if(void 0!==e.data["datawrapper-height"]){var t=document.querySelectorAll("iframe");for(var a in e.data["datawrapper-height"])for(var r=0;r<t.length;r++){if(t[r].contentWindow===e.source)t[r].style.height=e.data["datawrapper-height"][a]+"px"}}}))}();
</script>

  **3. datavisualisation avec une carte (Datawrapper)** 
  

j'ai décidé d'illustrer la densité de population avec une carte pour voir les pays les plus peuplés d'immigrant.Cette datavisualisation a été réalisé en choisissant une carte d'europe sur datawrapper et j'ai téléchargé les données avec quelque modification la premiére en texte et la deuxiemme colomne devait correspondre au nombre etc. Grace a la visualisation cartographique, nous pouvons visualiser les pays qui ont le plus d'immigrant.
  

 <iframe title="Flux d'immigration en Europe 2012" aria-label="Map" id="datawrapper-chart-xJZio" src="https://datawrapper.dwcdn.net/xJZio/1/" scrolling="no" frameborder="0" style="width: 0; min-width: 100% !important; border: none;" height="595" data-external="1"></iframe><script type="text/javascript">!function(){"use strict";window.addEventListener("message",(function(e){if(void 0!==e.data["datawrapper-height"]){var t=document.querySelectorAll("iframe");for(var a in e.data["datawrapper-height"])for(var r=0;r<t.length;r++){if(t[r].contentWindow===e.source)t[r].style.height=e.data["datawrapper-height"][a]+"px"}}}))}();</script>
  
Comme vous pouvez le voir, les pays sont coloré en cercle j'ai pris une carte de l'Europe. En constate que les flux sont importants vers l’Italie, le Royaume-Uni, L'allemagne, L'autriche le Pays-bas et la France.Cette étude a été l’une de ma première analyse approfondie sur l’immigration et constitue des données importantes pour savoir le nombre d'immigrant dans certin pays.
  
  **4. Troisième datavisualisation avec Bar Chart Race (Flourish)**
  
  Pour visualiser cet ensemble de données, j'ai décidé d'utiliser Bar Chart Race sur Flourish, ce qui m'a  permit d'avoir la visualisation dynamique de l'évolution de la migrationdes au fil des années (2000 - 2012 ). Les données de l'évolution migratroire au fil des années ont été trouvées sur [INSEE](https://www.insee.fr/fr/statistiques/3633212#consulter).
  
  <div class="flourish-embed flourish-bar-chart-race" data-src="visualisation/12654251"><script src="https://public.flourish.studio/resources/embed.js"></script></div>
  
  **4. Données provisoires, issues d'estimations avancées de la population. (2021)**
 
  
<div class="flourish-embed flourish-chart" data-src="visualisation/12663173"><script src="https://public.flourish.studio/resources/embed.js"></script></div>
  
   En 2021, 47.5 % d’ immigrés vivant en France sont nés en Afrique, grace a cet histogramme on peut le visualisé.
    
  **5. Visualisation de la capitale de l'Algerie, Alger avec Wikidata Query Service**
 
  Avec l'aide de de Wikidata, j'ai pu visualiser cette galerie d'image qui represente ma ville natale et son architecture
  
```sparql
#defaultView:ImageGrid
#Capitale D'Algerie

SELECT
  ?arr
  (SAMPLE (?titleL) AS ?title)
  (SAMPLE (?img) AS ?image)
  (SAMPLE (?coord) AS ?coordinates) {

{
  SELECT DISTINCT ?arr {
    ?arr  wdt:P131 wd:Q3561;}
}
# title
OPTIONAL { ?arr rdfs:label ?titleL filter (lang(?titleL) = "fr") }

# image
OPTIONAL { ?arr wdt:P18 ?img }

# coordinates
OPTIONAL { ?arr wdt:P149 ?coord }
    
} GROUP BY ?arr
LIMIT 1500
```
  
<iframe style="width: 80vw; height: 50vh; border: none;" src="https://query.wikidata.org/embed.html#%23defaultView%3AImageGrid%0A%23Capitale%20D'Alger%0A%0ASELECT%0A%20%20%3Farr%0A%20%20(SAMPLE%20(%3FtitleL)%20AS%20%3Ftitle)%0A%20%20(SAMPLE%20(%3Fimg)%20AS%20%3Fimage)%0A%20%20(SAMPLE%20(%3Fcoord)%20AS%20%3Fcoordinates)%20%7B%0A%0A%7B%0A%20%20SELECT%20DISTINCT%20%3Farr%20%7B%0A%20%20%20%20%3Farr%20%20wdt%3AP131%20wd%3AQ3561%3B%7D%0A%7D%0A%23%20title%0AOPTIONAL%20%7B%20%3Farr%20rdfs%3Alabel%20%3FtitleL%20filter%20(lang(%3FtitleL)%20%3D%20%22fr%22)%20%7D%0A%0A%23%20image%0AOPTIONAL%20%7B%20%3Farr%20wdt%3AP18%20%3Fimg%20%7D%0A%0A%23%20coordinates%0AOPTIONAL%20%7B%20%3Farr%20wdt%3AP149%20%3Fcoord%20%7D%0A%20%20%20%20%0A%7D%20GROUP%20BY%20%3Farr%0ALIMIT%201500%20%0A" referrerpolicy="origin" sandbox="allow-scripts allow-same-origin allow-popups"></iframe>
  
  **Conclusion**
  toute ces outils que j'ai eu la chance d'utilisé et m'anipuler m'on permis de fouiller les données et de faire sortir des informations intéréssante et de faire apparaître les résultats d'un traitement d'information. en plus de ça ce jeux de données pour moi à un intéret particulier. en partant des données brutes, j'ai réussi à les adapter à mes besoins, en les modifiant ce qui m'a permis de les visualiser et publier sur la page github. j'ai trouvé ce projet trés instructif car ça m'a permis de me confronter plus en détails à la manipulation des différents outils de la datavisualisation.



    
