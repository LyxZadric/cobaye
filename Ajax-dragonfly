//creation d'un conteneur 
var nav = document.getElementById('nav');
var d = document.createElement('div');
var conteneur = nav.appendChild(d);
conteneur.setAttribute('id', 'cont');
conteneur.style.width = "100%";
conteneur.style.heigth = "auto";
conteneur.style.display = "none";
nav.appendChild(conteneur);

// Création de l'évènement et affichage des données reçues. 
var rchange = document.getElementsByClassName('anav');
rchange[1].addEventListener('mouseover', function(e){
    
    // instanciation d'une requête Ajax afin d'obtenir les données à afficher
var xhr = new XMLHttpRequest();
    xhr.open('GET', "https://www.dragonflybsd.org/recentchanges/");
    xhr.onload = function() {
        
        var parser = new DOMParser();
        var page = parser.parseFromString(this.responseText, "text/html");
        
        var committer = page.getElementsByClassName('committer');
        var change = page.getElementsByClassName('changelog');
        
        conteneur.style.display = "block";
        conteneur.style.border = "1px solid black";
        conteneur.style.backgroundColor = "grey";
        
        for(i = 0; i < 10; i++){
            
            var StrAuteur = [];
            var StrChange = []; 
            StrAuteur[i] = committer[i].innerText;
            StrChange[i] = change[i].innerText;
            conteneur.innerText = StrAuteur[i] + StrChange[i];
            console.log(StrAuteur + StrChange + i);
            }
    };
    xhr.send();
    
}, false);

//Event lorsque la souris quitte le lien 
rchange[1].addEventListener('mouseout', function(){
    
    conteneur.style.display = "none";
});
