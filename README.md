

# 1er cas : affichage ligne / colonne

Partons d'une mise en page avec 2 blocs cote à cote avec la hiérarchie suivante de 3 divs :
```html
<div class="conteneur">
    <div class="a">
        A
    </div>

    <div class="b">
        B
    </div>
</div>
```

En utilisant la fonctionnalité flex, on peut dire à A et B de s'afficher cote à cote : 

=> 01.html


```css
.conteneur {
    display:flex;
    flex-direction : row;
}
        
.a {
    width: 50%;
}

.b {
    width: 50%;
}
```




Mais au bout d'un moment, en réduisant la taille d'écran vers un smartphone, on va vouloir les afficher l'un dessous l'autre :

=> 02.html

```css
.conteneur {
    display:flex;
    flex-direction : column;
}
        
.a {
    width: 90%;
}

.b {
    width: 90%;
}
```

Ce qui s'écrit en se disant que la largeur d'un smartphone c'est 500px :

```css
/* Desktop */
@media screen and (min-width: 500px) {
    .conteneur {
        display:flex;
        flex-direction : row;
    }
    
    .a {
        width: 50%;
    }
    
    .b {
        width: 50%;
    }
}

/* Smartphone */
@media screen and (max-width: 500px) {
    .conteneur {
        display:flex;
        flex-direction : column;
    }
    
    .a {
        width: 90%;
    }
    
    .b {
        width: 90%;
    }
}
```

# 2ème cas : cacher un menu sur le coté

C'est le cas classique d'un menu qui a la place d'être affiché en desktop et pas en mobile :

=> 03.html

```css

/* Partie commune */
.conteneur {
        display:flex;
        flex-direction : row;
    }


/* Desktop */
@media screen and (min-width: 500px) {
    
    
    .a {
        width: 70%;
    }
    
    .b {
        width: 20%;
    }
}

/* Smartphone */
@media screen and (max-width: 500px) {
    .a {
        width: 100%;
    }
    
    .b {
        display:none
    }
}
```