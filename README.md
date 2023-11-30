# Memo_Debuter_avec_JavaScript  
 
## ***__Introduction a javascript__***  

- ### ***Présentation de JavaScript***  

    - #### ***Introduction***  

        - ***Un exemple rapide à quoi du code JavaScript***  

            ```JS
            // Fonction pour calculer le périmètre d’un rectangle 
            function perimetreR (a, b) {
                return 2 * a + 2 * b;
            }

            // Fonction pour calculer l’aire d’un rectangle 
            function aireR (a, b) {
                return a * b
            }
            
            // Fonction pour comparer avec un if l’aire de 2 rectangles
            function compareAire(rectangleOne, rectangleTwo) {
                if (aireR(rectangleOne[0], rectangleOne[1]) < aireR(rectangleTwo[0], rectangleTwo[1])) {
                    alert("Le rectangle 1 est plus petit que le rectangle 2")
                }
                else if ((aireR(rectangleOne[0], rectangleOne[1]) > aireR(rectangleTwo[0], rectangleTwo[1]))) {
                    alert("Le rectangle 1 est plus grand que le rectangle 2")
                }
                else {
                    alert("Les rectangles ont la même aire")
                }
            }

            var rectangle1 = [10, 4]
            var rectangle2 = [8, 5]

            //Appel de la fonction compareAire en passant en paramètre les 2 tableaux contenant les valeurs des côtés des rectangles 
            compareAire(rectangle1, rectangle2);
            ```

    - #### ***Langage côté client***  

        - ***Côté client ou côté serveur***  

            - JavaScript est, au même titre que HTML et CSS, un langage côté client. A la différence que JavaScript est un vrai langage de programmation.  

            - Ces deux termes définissent comme nous l’avons dit le « lieu » où sont exécutées les instructions de code.  

                - Côté client : Un langage côté client est exécuté sur la machine du client, grâce au navigateur. Le navigateur va communiquer avec un serveur distant pour recevoir les informations nécessaires, mais les instructions seront exécutées sur la machine de l’utilisateur et non sur le serveur. C’est le cas de JavaScript.  

                - Côté serveur : le navigateur web communique avec des serveurs distants (des ordinateurs qui stockent les données) par le biais d’un protocole :  

                    - le protocole HTTP.  

                        - Lorsque l’on visite un site réalisé avec un langage côté serveur, le navigateur envoie par le biais de ce protocole des requêtes aux serveurs distants. Il peut ainsi, par exemple, accéder à des bases de données distantes (qui ne sont pas stockées sur son ordinateur).  
                        
                        - Le navigateur n’accède pas aux bases de données de manière directe, mais par le biais du serveur distant. Les scripts sont exécutés sur le serveur distant.  

        - ***Document Object Model HTML***  

            - JavaScript est un langage permettant d’aborder la programmation orientée objet.  

            - La programmation orientée objet est une manière spécifique d’aborder la programmation. Les objets sont assimilables à des concepts de la réalité.  
            
            - Ils sont définis par leurs attributs (des valeurs qui les définissent) et des méthodes (des actions qu’ils peuvent utiliser).  

            - Prenons un exemple simple de la vie de tous les jours pour que vous puissiez mieux vous représenter ce concept.  

                - Une voiture est un objet. Il a des attributs, par exemple :  

                    - marque = "Ford"  

                    - roues = 4  

                    - nombre_litre_reservoir = 45  

                        - Mais il a aussi des fonctions. elle peut par exemple démarrer, s’arrêter, allumer ces feux, etc. On peut comparer ces fonctions à des méthodes de l’objet voiture.  

            - JavaScript est donc un langage qui va permettre de programmer en orienté objet. Les langages JavaScript et HTML vont pouvoir interagir grâce à cette logique.  

            - Le Document Object Model est une convention qui permet de créer des représentations sous la forme d’objets, notamment dans des documents HTML.  

            - Via le DOM HTML, JavaScript va pouvoir accéder aux différents objets du document HTML et interagir avec eux. JavaScript est donc un langage extrêmement lié à HTML.

    - #### ***Langage interprété vs langage compilé***  

        - ***Langage interprété et langage compilé***  

            - ces 2 termes sont liés à la manière dont va être traduit un code en langage machine (binaire) pour qu’il soit exécuté :  

                - Un langage interprété est un langage où le code source (code écrit dans ce langage) est lu puis exécuté dans l’ordre des lignes du script. Un interpréteur lit chaque instruction du code source, et l’exécute.  

                - Un langage compilé n’est pas traité de la même manière, il nécessite un compilateur.  

                    - Un compilateur va lire toutes les instructions d’un code source pour créer à partir de l’ensemble un code objet, c’est-à-dire un fichier lisible par la machine.  

                    - Ce fichier indépendant du code source pourra être stocké dans un fichier exécutable par la machine.  

            - On comprend donc que la stratégie de traitement d’un code source n’est pas la même pour un langage interprété et pour un langage compilé.  

            - JavaScript est classé parmi les langages interprétés. En effet, lorsque l’on exécute un script JavaScript, le code est exécuté de haut en bas, chaque instruction est traduite une par une en langage machine et exécutée.  

        - ***Différence entre interprétation et compilation***  

            - Prenons un exemple d’un script très simple :

                ```JS
                console.log(1);
                console.log(2);
                consolelog(3);
                console.log(4);
                console.log(5);
                ```  

                - Dans ce script, qui a pour objectif d’afficher dans la console les nombres 1 2 3 4 5, on peut constater une erreur à la ligne consolelog(3). En effet, il manque un point. Donc, si on intègre ce script dans un code HTML, la console va afficher :

                    ```JS
                    1
                    2
                    // ReferenceError: Can't find variable: consolelog
                    ```

                    - Le moteur JavaScript lie chaque instruction et à chaque fois l’exécute, jusqu’à ce qu’il rencontre l’erreur.  
                    
                    - La console affiche donc les 2 premières valeurs et l’exécution s’arrête dès que l’erreur est rencontrée.  
                    
                    - On peut voir que le comportement n’aurait pas été le même si JavaScript avait été compilé.  
                    
                    - En effet, dans ce dernier cas, le compilateur aurait analysé le programme dans son ensemble. Étant donné qu’il rencontre une erreur, il n’aurait même pas compilé le script, et il n’y aurait eu aucune exécution.  
            
        - ***Comment est exécuté JavaScript ?***  

            - Le JavaScript s’exécute comme suit :  

                - Le navigateur récupère et charge les codes d’une page web (HTML/CSS/JS).  

                - Le navigateur transforme toute la page en notre fameux Document Object Model, dans lequel il crée une représentation de chaque élément HTML.  

                - Le moteur JavaScript du navigateur convertit le code JS en un code intermédiaire entre le code source et la machine d’exécution, ***le bytecode***.  

                - Les évènements comme les clics de souris qui sont reliés à des blocs de code en JS déclenchent leur exécution. Le moteur JavaScript procède à l’interprétation du bytecode généré pour les blocs de code appelés et apporte les modifications visées sur le Document Object Model.  

                - Le nouveau Document Object Model est alors affiché.  

            - On peut voir que, conformément à ce système, les navigateurs web peuvent utiliser des scripts JavaScript pour modifier le DOM d’une page web, et donc mettre à jour son affichage.
            
        - ***Modules***  

            - Il faut par ailleurs savoir que JavaScript est un langage modulable. De nombreuses bibliothèques sont facilement utilisables, et permettent d’accroître et d’optimiser l’utilisation de JavaScript.  
            
        - ***Bibliothèque***  

            - En programmation, une bibliothèque (ou une librairie) est un ensemble de fonctions que l’on peut importer.  

            - Ces fonctions sont finalement des ensembles de codes déjà écrits et que l’on pourra appeler et donc utiliser sans avoir à les écrire nous-mêmes. Voici quelques exemples de bibliothèques que l’on peut utiliser avec JavaScript :  

                - Ajout de fonctions permettant de manipuler le Document Object Model (DOM) :  

                    - [JQuery](https://jquery.com/)  

                    - [Umbrella JS](https://umbrellajs.com/)  

                - Ajout de fonctions de visualisation des données :  

                    - [Chart.js](https://www.chartjs.org/)  

                    - [Algolia places](https://www.algolia.com/blog/product/)  

                - Ajout de fonctions de formulaires :  

                    - [wForms](https://code.google.com/archive/p/wforms/)  

                    - [Validanguage](https://github.com/gcao/validanguage)  
            
        - ***Frameworks***  

            - Un framework est comme une grande bibliothèque, mais qui va constituer en quelques sortes un espace de travail pour les projets de code. Un framework va donc jouer un rôle dans l’organisation du projet et impacter toute sa conception.

            - Il existe plusieurs frameworks JavaScript :  

                - React Native : pour le développement d’applications JS pour Android et IOS  

                - Angular JS : pour les applications web plus complètes  

                - Bootstrap : pour la création de designs en responsive  

                - Node.js : pour créer des applications côté serveur  

- ### ***Histoire et ECMAScript6***  

    - #### ***Histoire et ECMAScript6***  

        - ***Les débuts de JavaScript***  

            - JavaScript a vu le jour en 1995 grâce à Brendan Eich, informaticien américain travaillant à ce moment-là pour l’entreprise Netscape Communication Corporation.  

            - JavaScript s’inspire du célèbre langage Java, mais l’objectif était de simplifier la syntaxe afin de le rendre plus accessible.  

            - L’objectif a été de concevoir un langage de programmation côté client qui soit intégrable dans le navigateur web de Netscape.  

            - En 1996, Netscape intègre JavaScript dans le navigateur web de sa conception : NetScape Navigator 2.0. La concurrence émerge, Microsoft sort un langage de programmation, JScript, qu’il intègre dans sa version 3.0 d’Internet Explorer.  

            - La standardisation de JavaScript est confiée à l’organisation européenne ECMA international (European association for standardizing information and communication systems).  

            - C’est en juin 1997 que naît le premier standard de JavaScript appelé ECMAScript, qui est la première édition du standard appelé ECMA-262.  

            - Ce standard sera transmis en 1998 à l’Organisation Internationale de Normalisation, qui publiera un standard international.  

            - En 2012, tous les navigateurs web prennent en charge la version 5.1 d’ECMAScript. En 2015, la sixième version d’ECMAScript est publiée, ECMAScript 2015 (ou ECMAScript 6 voir ES6).

        - ***Intérêt de JavaScript***  

            - JavaScript a vu le jour comme un langage de programmation côté client, permettant d’introduire de l’interactivité et du dynamisme dans la mise en page du web.  

            - JavaScript présente de nombreux avantages :  

                - Sa simplicité d’utilisation, JavaScript a été conçu pour être accessible  

                - Il peut exécuter plusieurs instructions simultanément  

                - Il permet de concentrer des tâches sur l’environnement de l’utilisateur, libérant ainsi les serveurs des tâches qui seront alors exécutées du côté client  

                - Il permet de concevoir des sites internet intuitifs et plus accessibles  

                - Il peut être exécuté à l’aide de n’importe quel navigateur web  

                - Il contient de nombreuses bibliothèques facilement importables et fonctionnelles  

                - Il peut être utilisé par le biais de frameworks  

                - Il sert au fonctionnement d’API comme Node.js  

        - ***ECMAScript 6***  

            - ECMAScript est le standard de JavaScript. Il contient entre autres la définition de :  

                - La syntaxe de JavaScript  

                - Les types des variables  

                - Les fonctions et les objets dits natifs (de base)  

                - Les mécanismes assurant le traitement des erreurs  

                - Le fonctionnement de l’héritage  

                - L’objet dit global, c’est-à-dire l’objet qui va contenir toutes les propriétés, les fonctions et les variables qui seront accessibles à n’importe quel endroit d’un code. Dans un navigateur web, cet objet est l’objet window.
            
            - Qu’apporte en 2015 ECMAScript 6 ?

                - ECMAScript 6 apporte des commandes qui font de JavaScript un langage assimilable visuellement au C++ ou à Java, en termes de syntaxe.  

                - Le système de POO devient plus accessible en JavaScript, même si les modifications ne portent globalement que sur l’aspect visuel de la syntaxe.  

                - On ne peut pas dire que JavaScript est « autant » inscrit dans la logique orientée objet que Java ou C++. Mais ces fonctionnalités s’en rapprochent, au moins visuellement, et permettent d’aborder la POO en JavaScript.
            
            - D’autres modifications et ajouts sont opérés, par exemple :  

                - La possibilité d’importer des modules (bibliothèques, etc.)  

                - L’ajout de structures de données (tableaux associatifs, etc.)  

                - Les promesses concernant les systèmes asynchrones  

            - ECMAScript 6 constitue ainsi une mise à jour considérable de JavaScript, et un évènement dans son histoire.  

##  
## ***__Syntaxe et intégration de JS__***  

- ### ***Syntaxe de JavaScript et 2 méthodes possibles d’intégration en HTML***  

    - #### ***Syntaxe de JavaScript et 2 méthodes possibles d’intégration en HTML***  

        - ***Syntaxe générale de JavaScript***  

            - Voici une liste non exhaustive de règles de syntaxe en JavaScript :  

                - La hiérarchie des instructions est représentée via le système d’indentation (tab)  

                - Chaque ligne d’instructions se termine par un ***« ; »***  

                - Les paramètres d’une fonction sont inscrits entre parenthèses et séparés par des virgules : ***(paramètre 1, paramètre 2)***  

                - Le corps d’une fonction est inscrit entre accolades : ***{corps d’une fonction}***  

                - Les commentaires sont précédés des caractères : ***« // »***  

        - ***Intégration d’un script directement dans un document HTML (intégration interne)***  

            - La première méthode que nous pouvons utiliser pour intégrer un script JavaScript est de l’écrire directement dans notre document HTML (intégration interne). Pour cela, nous allons utiliser la balise ***`<script>`***.  

                - Exemple :  

                    ```HTML
                    <!DOCTYPE html>
                    <html lang="en">
                        <head>
                            <meta charset="UTF-8">
                            <meta http-equiv="X-UA-Compatible" content="IE=edge">
                            <meta name="viewport" content="width=device-width, initial-scale=1.0">
                            <title>Document</title>
                        </head>

                        <body>
                        
                            <header>
                                <h1>Blog</h1>
                            </header>
                            
                            <section>
                                <article>
                                    <p>Voici</p>
                                </article>
                                
                                <article>
                                    <p>“Votre texte”</p>
                                </article>
                            </section>
                            
                            <footer></footer>

                            <script>
                                //script JavaScript
                                alert("Hello World !");
                            </script>

                        </body>
                    </html>
                    ```

        - ***Intégration d’un script via un lien dans un document HTML (intégration externe)***  

            - Il faut simplement utiliser la balise ***`<script>`*** et définir l’attribut ***src*** sur l’adresse du fichier ***.js***. On va donc, dans notre exemple, créer un dossier ***« scripts »*** dans lequel on va créer un fichier ***« script.js »***. Puis dans le fichier ***script.js***, on insère l’instruction :  

                ```JS
                alert("Hello World !");
                ``````

            - On peut modifier le fichier .html pour qu’il intègre le script :  

                ```HTML
                <!DOCTYPE html>
                <html lang="en">
                    <head>
                        <meta charset="UTF-8">
                        <meta http-equiv="X-UA-Compatible" content="IE=edge">
                        <meta name="viewport" content="width=device-width, initial-scale=1.0">
                        <title>Document</title>
                    </head>

                    <body>
                    
                        <header>
                            <h1>Blog</h1>
                        </header>
                        
                        <section>
                            <article>
                                <p>Voici</p>
                            </article>
                            
                            <article>
                                <p>“Votre texte”</p>
                            </article>
                        </section>
                        
                        <footer></footer>

                        <script src="scripts/script.js"></script>

                    </body>
                </html>               
                ```

        - ***Syntaxe des chemins relatifs***  

            - Dans notre exemple, nous avons utilisé l’attribut src en spécifiant un chemin relatif.  
            
            - Si le document HTML se trouve dans un sous dossier, il faudra sortir du sous-dossier pour se placer dans le dossier parent, pour ensuite se déplacer dans le sous-dossier « scripts ».  
            
            - Pour sortir du dossier et donc se placer dans le dossier parent, il faut commencer le chemin par : « ../ ». Cette inscription permet de se déplacer dans le dossier parent.  

- ### ***Appliquer la convention et éviter une erreur courante***  

    - #### ***Appliquer la convention et éviter une erreur courante***  

        - d’un point de vue conventionnel, il est conseillé d’insérer les scripts (avec l’attribut src) dans la balise ***\<head>***.  

            - Exemple ci-dessous :  

                ```HTML
                <!DOCTYPE html>
                <html lang="en">
                    <head>
                        <meta charset="UTF-8">
                        <meta http-equiv="X-UA-Compatible" content="IE=edge">
                        <meta name="viewport" content="width=device-width, initial-scale=1.0">
                        <link rel="stylesheet" href="styles/style.css">  
                        <script src="scripts/script.js"></script> <!-- Insertion du script.js -->
                        <title>Document</title>
                    </head>
                    <body>
                        <header>
                            <h1>Blog</h1>
                        </header>
                        <section>
                            <article>
                                <p>“Votre texte”</p>
                            </article>
                            <article>
                                <p>“Votre texte”</p>
                            </article>
                        </section>
                        <footer></footer>
                    </body>
                </html>
                ```

        - ***Ordre des métadonnées***  

            - Il est préférable, voire indispensable, de placer dans le head les liens vers les feuilles de style avant les scripts, pour afficher correctement et rapidement le visuel du site.  

            - L’attribut ***defer*** de la balise ***`<script>`*** permet d’indiquer que le script doit être exécuté de manière différée, donc une fois que le document est analysé.  
            
            - Cet attribut doit être utilisé uniquement dans le cas où un attribut ***src*** est spécifié.  

                ```HTML
                <script src="scripts/script.js" defer></script> <!-- Ajouter "defer" à la suite du fichier script.js -->
                ```

##
## ***__Les variables en JS__***  

- ### ***Introduction aux variables et exemples d'utilisation en JS***  

    - #### ***Introduction***  

        - Visual Studio Code (VScode) est un éditeur de code source léger, mais puissant, qui s'exécute sur votre bureau et qui est disponible pour Windows, macOS et Linux. Il intègre la prise en charge de JavaScript, TypeScript et Node.js. Il dispose d'un riche écosystème d'extensions pour d'autres langages et environnements d'exécution (tels que C++, C#, Java, Python, PHP, Go, .NET).  

            - Pour le télécharger, suivez ce lien : [Visual Studio Code](https://code.visualstudio.com/Download)  

            - Pour consulter la documentation : [Documentation Visual Studio Code](https://code.visualstudio.com/docs)

    - #### ***Définition d’une variable***  

        - Une variable est un élément fondamental en programmation qui permet de stocker, manipuler et référencer des données dans un programme.  

        - Dans le contexte de JavaScript, une variable est un conteneur pour une valeur qui peut être de différents types, tels que :  

            - Des nombres  
            
            - Des chaînes de caractères  
            
            - Des objets  
            
            - Des tableaux  
            
            - Des fonctions, etc.  
        
        - Une variable est définie par un identifiant (son nom) et une valeur.

        - L'identifiant est utilisé pour accéder à la valeur stockée dans la variable et pour modifier cette valeur si nécessaire.  

        - En JavaScript, les variables peuvent être déclarées en utilisant les mots-clés 'var', 'let' et 'const'. Chacun de ces mots-clés possède des propriétés et des comportements spécifiques qui influencent la portée, l’assignation et la déclaration des variables.

    - #### ***Utilité des variables***  

        - Les variables jouent un rôle essentiel dans la programmation, car elles permettent aux développeurs de stocker, organiser et manipuler des données de manière flexible et efficace.  

        - Parmi leurs principales utilisations, on trouve le stockage de données, où les variables conservent des informations pour une utilisation ultérieure dans le programme et peuvent contenir divers types de données.  

        - les variables contribuent à la réutilisation du code, réduisant ainsi la redondance en stockant des valeurs ou des références fréquemment utilisées.  

        - Les variables simplifient également les calculs en facilitant les opérations mathématiques et logiques complexes, en stockant les résultats intermédiaires ou en agissant comme des compteurs.  

        - Au niveau de l'organisation du code, les variables aident à structurer et à regrouper des informations connexes, améliorant ainsi la lisibilité et la maintenabilité du code en permettant aux développeurs de donner des noms significatifs aux données.  

    - #### ***Types de variables***  

        - ***Les nombres à virgule Flottante (Float)***  

            - Les nombres à virgule flottante, également connus sous le nom de nombres décimaux, sont utilisés en JavaScript pour représenter des nombres avec des valeurs décimales.  

            - Les variables de ce type sont utilisées pour stocker des nombres réels, tels que des nombres décimaux ou des nombres avec une partie décimale.  
            
            - En JavaScript, les nombres à virgule flottante sont représentés par le type de données ***"number"***.  

            - Exemple :  

                ```JS
                let pi = 3.14159; // Déclaration d'une variable avec un nombre à virgule flottante
                console.log(pi); // Affiche : 3.14159
                ```

        - ***Les nombres entiers (Integer)***  

            - Integer est utilisé en JavaScript pour représenter un nombre entier sans partie décimale.  

            - Ce type de variable est utilisé pour stocker des nombres entiers, tels que des nombres de comptages ou des identifiants.  

            - En JavaScript, les entiers sont également représentés par le type de données ***"number"***.  

            - Exemple :  

                ```JS
                let age = 25; // Déclaration d'une variable avec un nombre entier
                console.log(age); // Affiche : 25
                ```

        - ***Les chaînes de caractères (String)***  

            - On retrouve les chaînes de caractères en JavaScript pour représenter du texte.  
            
            - Les variables de ce type sont utilisées pour stocker des séquences de caractères, comme des mots, des phrases ou des adresses électroniques.  
            
            - En JavaScript, les chaînes sont représentées par le type de données ***"string"*** et peuvent être déclarées avec des guillemets simples (' ') ou doubles (" ").

            - Exemple :  

                ```JS
                let nom = 'Alice'; // Déclaration d'une variable avec une chaîne de caractères
                console.log(nom); // Affiche : Alice
                ```

        - ***Les Booléens (Boolean)***  

            - Les valeurs booléennes sont utilisées en JavaScript pour représenter des valeurs de vérité, c'est-à-dire des valeurs qui sont vraies ou fausses.  
            
            - Ce type de variable est utilisé pour stocker des états logiques, tels que des conditions ou des options d'activation/désactivation.  
            
            - En JavaScript, les valeurs booléennes sont représentées par le type de données ***"Boolean"***.

            - Exemple : 

                ```JS
                let estActif = true; // Déclaration d'une variable avec une valeur booléenne
                console.log(estActif); // Affiche : true
                ```

        - ***Les tableaux (Array)***  

            - En JavaScript, les tableaux sont utilisés pour stocker plusieurs valeurs dans une seule variable.  
            
            - Ce type de variable est utilisé pour représenter une collection de données, comme une liste d'éléments ou une série de valeurs.  
            
            - En JavaScript, les tableaux sont représentés par le type de données ***"array"*** et peuvent contenir des valeurs de différents types.  

            - Exemple :  

                ```JS
                let nombres = [1, 2, 3, 4, 5];
                nombres.forEach((nombre) => {
                console.log(nombre);
                }); // Affiche : 1,2,3,4,5
                ```

    - #### ***Déclaration de variables en JavaScript***  

        - ***Utilisation de 'var'***  

            - L'utilisation de ***'var'*** en JavaScript concerne la déclaration de variables qui peuvent être réaffectées et dont la portée est définie par la fonction englobante.  

            - 'var' ait été le mot-clé standard pour déclarer des variables dans les versions antérieures de JavaScript, l'introduction de ***'let'*** et ***'const'*** dans ECMAScript 2015 (ES6) a rendu son utilisation moins courante en raison de certaines limitations.  

            - Exemple :  

                ```JS
                // Déclaration et initialisation d'une variable avec 'var'
                var age = 25;
                // Réaffectation d'une nouvelle valeur à la variable
                age = 26;
                console.log(age); // Affiche "26"
                ```

                - Dans cet exemple, nous déclarons une variable appelée age avec la valeur 25. Ensuite, nous réaffectons la valeur 26 à la variable et affichons la nouvelle valeur.  

            - Cependant, il est important de noter que l'utilisation de ***'var'*** présente certaines limitations.  
            
            - Par exemple, les variables déclarées avec ***'var'*** sont accessibles en dehors du bloc dans lequel elles sont définies, tant qu'elles restent dans la fonction englobante. Cela peut entraîner des problèmes de lisibilité et des erreurs involontaires.

            - Voici d’ailleurs une erreur type de l’utilisation de ***“var”*** :  

                ```JS
                function testFunction() {
                if (false) {
                    var testVariable = "Hello world";
                }
                console.log(testVariable);
                }
                
                testFunction(); // Résultat : "undefined"
                ```
                - Dans cet exemple, la variable testVariable est déclarée dans une condition qui ne sera jamais satisfaite, car la condition if (false) ne sera jamais vraie. Cependant, la variable est toujours accessible en dehors de cette condition, car elle est déclarée avec le mot-clé ***"var"***.  

                - Lorsque la fonction testFunction() est appelée, elle affiche la valeur de la variable test avec console.log(). Comme la variable est déclarée avec "var" dans la fonction, elle est accessible tout au long de la fonction, même si elle n'a jamais été définie.  

            - Un autre exemple :  

                ```JS
                if (true) {
                    var prenom = "Alice";
                }
                console.log(prenom); // Affiche "Alice" même si la variable est déclarée dans le bloc if
                ```

                - La Variable ***"prenom"*** sera affichée par le console.log même si elle est déclarée dans la condition.  

            - De plus, les variables déclarées avec 'var' ont une particularité concernant leur portée : elles sont traitées comme si elles étaient déclarées au début de la fonction englobante, même si elles sont définies plus loin dans le code. Ce phénomène peut provoquer des comportements inattendus.  

                - Exemple :  

                    ```JS
                    console.log(monNom); // Affiche "undefined" au lieu de générer une erreur
                    var monNom = "Alice";
                    ```

            - Malgré ces limitations, ***'var'*** est toujours pris en charge pour des raisons de compatibilité avec les anciens codes. Cependant, pour les débutants, il est recommandé d'apprendre et d'utiliser ***'let'*** et ***'const'*** pour déclarer des variables, car ils offrent une meilleure gestion de la portée et préviennent les erreurs liées au ***hoisting***.

                - Le ***hoisting*** est un comportement en JavaScript où les déclarations de variables et de fonctions sont déplacées au début de leur portée respective, c'est-à-dire que la variable ou la fonction peut être utilisée avant d'être déclarée.  
                
                - Cela signifie que même si une variable est déclarée plus tard dans le code, elle peut être utilisée avant sa déclaration en raison du ***hoisting***.

        - ***Utilisation de 'let'***  

            - L'utilisation de ***'let'*** en JavaScript concerne la déclaration de variables qui peuvent être réaffectées et dont la portée est définie par le bloc englobant.  

            - ***'let'*** a été introduit dans ECMAScript 2015 (ES6) et est devenu un choix préféré pour déclarer des variables, en particulier pour les débutants, en raison de sa gestion améliorée de la portée et de l'absence de hoisting.  

            - Exemple :  

                ```JS
                // Déclaration et initialisation d'une variable avec 'let'
                let age = 25;
                // Réaffectation d'une nouvelle valeur à la variable
                age = 26;
                console.log(age); // Affiche "26"
                ```

                - Dans cet exemple, nous déclarons une variable appelée age avec la valeur 25. Ensuite, nous réaffectons la valeur 26 à la variable et affichons la nouvelle valeur.  

            - Contrairement à 'var', les variables déclarées avec 'let' ont une portée de bloc, ce qui signifie qu'elles ne sont accessibles qu'à l'intérieur du bloc dans lequel elles sont définies.  

            - Exemple :  

                ```JS
                if (true) {
                    let prenom = "Alice";
                }
                console.log(prenom); // Erreur : prenom n'est pas défini à l'extérieur du bloc if
                ```

        - ***Utilisation de 'const'***  

            - L'utilisation de ***'const'*** en JavaScript concerne la déclaration de variables dont la valeur ne peut pas être modifiée une fois qu'elles ont été initialisées.  

            - ***'const'*** a été introduit dans ECMAScript 2015 (ES6) et est devenu un choix préféré pour déclarer des variables immuables, en raison de sa gestion améliorée de la portée et de l'absence de hoisting.  

            - Exemple :  

                ```JS
                // Déclaration et initialisation d'une variable avec 'const'
                const age = 25;
                // Tentative de réaffectation d'une nouvelle valeur à la variable
                age = 26; // Erreur : tentative de réaffecter une valeur à une constante
                ```

                - Dans cet exemple, nous déclarons une variable appelée age avec la valeur 25 en utilisant 'const'. Si nous essayons de réaffecter la valeur 26 à la variable, cela générera une erreur, car la valeur d'une constante ne peut pas être modifiée une fois qu'elle a été initialisée.

            - ***Il est recommandé d'utiliser 'const' pour déclarer des variables immuables et de se familiariser avec 'let' pour les variables dont la valeur doit être modifiée.***  

    - #### ***Comparaison entre 'var', 'let' et 'const'***  

        - En ce qui concerne la portée, il convient de noter que ***'var'*** a une portée de fonction, c'est-à-dire qu'elle peut être appelée n'importe où dans la fonction où elle est déclarée.  

        - En revanche, ***'let'*** et ***'const'*** ont une portée de bloc, ce qui signifie qu'elles sont uniquement accessibles dans le bloc de code où elles sont déclarées, généralement un couple de ***{ }***.  

        - En ce qui concerne la réaffectation, il est important de noter que ***'var'*** et ***'let'*** peuvent être réaffectées à tout moment, ce qui signifie que leur valeur peut être modifiée après leur déclaration.  
        
            - En revanche, une fois que ***'const'*** a été déclarée et initialisée, elle ne peut pas être réaffectée.  

        - En ce qui concerne le hoisting, cela signifie que la déclaration de ***'var'*** et ***'let'*** sont élevées en haut de leur scope, c'est-à-dire qu'elles peuvent être appelées avant leur déclaration effective. Toutefois, seule la déclaration de ***'var'*** est ***"hoisted"***, pas son affectation.

            - En revanche, ***'const'*** n'est pas soumise au hoisting.

        - Le ***"scope"*** se réfère à la portée ou à l'étendue des variables déclarées en JavaScript. En d'autres termes, le scope détermine où dans le code une variable peut être utilisée ou référencée.

- ### ***Bonnes pratiques et exercices de compréhension***  

    - #### ***Bonnes pratiques pour déclarer et utiliser les variables en JavaScript***  

        - La première bonne pratique consiste à nommer les variables de manière significative.  

        - Évitez les noms génériques tels que 'a', 'b' ou 'x' qui peuvent entraîner des erreurs et rendre le code difficile à comprendre.  

        - Il est essentiel d'utiliser la portée de variable appropriée. En JavaScript, la portée d'une variable définit où elle peut être utilisée dans un programme.  

        - Il est également recommandé d'éviter les variables globales autant que possible. En effet, les variables globales sont accessibles depuis n'importe où dans le programme, ce qui peut rendre le code difficile à comprendre et à maintenir.  

        - Toutes les variables doivent être déclarées avant leur utilisation dans un programme.  

        - Il est conseillé d'utiliser ***'const'*** pour les valeurs constantes telles que les nombres pi ou les adresses URL qui ne changent pas tout au long du programme.  

        - Pour les variables qui changent de valeur tout au long du programme, il est recommandé d'utiliser ***'let'***.  

##  
## ***__Les opérateurs__***  

- ### ***Opérateurs arithmétiques et d’affectation***  

  - #### ***Introduction***  

    - Nous nous intéresserons à des exemples numériques, puis nous verrons quels opérateurs peuvent nous être utiles lorsqu’on manipule des chaînes de caractères.   

  - #### ***Opérateurs arithmétiques***  

    - Les opérateurs arithmétiques vont nous permettre de réaliser des opérations mathématiques simples. Nous utiliserons la commande console.log afin d’afficher dans la console les résultats des opérations mathématiques réalisées.  

    - ***L’opérateur « + »***  

        - L’opérateur + permet simplement d’additionner 2 valeurs.  

            ```JS
            let a = 2;
            let b = 567.42;
            console.log(a + b);
            ```  
            - Dans ce cas, console.log(a + b) affichera dans la console : 569,42.  
            
    - ***L’opérateur « - »***  

        - L’opérateur - permet simplement de soustraire une valeur à une autre.  

            ```JS
            let a = 567.42;
            console.log(a - 25);
            ```
            - Dans ce cas, console.log(a - 25) affichera dans la console : 542,42.  

    - ***L’opérateur « * »***  

        - L’opérateur * permet d’obtenir le produit de 2 nombres (multiplication).  

            ```JS
            let a = 2 * 4.5;
            console.log(a);
            ```
            - Dans ce cas, console.log(a) affichera dans la console : 9.  

    - ***L’opérateur « / »***  

        - L’opérateur / permet de diviser un nombre par un autre nombre :  

            ```JS
            console.log(58 / 2);
            ```
            - Dans ce cas, console.log(58/2) affichera dans la console : 29.  

    - ***L’opérateur « % »***  

        - L’opérateur % (qu’on appelle en général « modulo ») permet d’obtenir le reste d’une division euclidienne :  

            ```JS
            let a = 90;
            let b = 11;
            console.log(a % b);
            ```
            - Dans ce cas, console.log(a % b) affichera dans la console : 2.  

            - Pour bien comprendre, si on fait une division euclidienne avec 90 comme dividende et 11 comme diviseur, on obtient :  

                - 90 = 11 x 8 + 2  
                
                - On a donc un quotient égal à 8 et un reste égal à 2.  

    - ***L’opérateur « ** » ***  

        - L’opérateur ** permet d’élever un nombre à une puissance. Par exemple, si on veut obtenir l’écriture décimale de 18**4, on fera :  

            ```JS
            console.log(18 ** 4);
            ```
            - Dans ce cas, console.log(18 ** 4) affichera dans la console : 104 976.  

            - 18**4 = 18 x 18 x 18 x18 = 104 976  

    - ***L’opérateur « ++ » et « -- »***  

        - L’opérateur ++ qu’on appelle « opérateur d’incrémentation » permet d’ajouter l’entier 1 à une valeur (on dit qu’il incrémente une variable).  

            ```JS
            let a = 2;
            a ++;
            console.log(a);
            ```
            - Dans ce cas, console.log(a) affichera dans la console : 3.  

            - En effet, l’incrémentation de a revient à écrire :  

                ```JS
                let a = 0
                a = a + 1;
                ```
                - L’opérateur -- est quant à lui appelé « opérateur de décrémentation ». Il fonctionne exactement comme l’opérateur d’incrémentation, mais permet en revanche de retirer 1 à une valeur :  

                    ```JS
                    let a = 3;
                    a --;
                    console.log(a);
                    ```
                    - Dans ce cas, console.log(a) affichera dans la console : 2.  

  - #### ***Opérateurs d’affectation***  

    - ***L’opérateur « = »***  

        - L’opérateur = est dit « opérateur d’assignement simple ». Il est utilisé pour définir la valeur d’une variable. Voici un exemple simple :  

            ```JS
            let a = 2;
            console.log(a);
            ```
            - Ici, on assigne l’entier 2 à la variable a, avec l’opérateur d’assignement =. La ligne console.log(a) affichera donc dans la console : 2.  

    - ***Les opérateurs « += », « -= », « *= » et « /= »***  

        - L’opérateur += peut être appelé « opérateur d’affectation après addition ». Il va permettre d’affecter à une variable sa propre valeur à laquelle on ajoute celle d’une seconde valeur :  

            ```JS
            let a = 2;
            a += 8;
            console.log(a);
            ```
            - Ici, console.log(a) affiche 10 dans la console. C’est comme si on avait fait :  

                ```JS
                let a = 0
                a = a + 8;
                ```

        - L’opérateur d’affectation après soustraction -= fonctionne exactement de la même manière, mais renvoie la différence du premier nombre par le second :  

            ```JS
            let a = 18;
            a -= 4;
            console.log(a);
            ```
            - Ici, a sera égal à lui-même moins 4, donc à 18 - 4, c’est-à-dire 14.  

        - Les opérateurs d’affectation après multiplication (*=) et après division (/=) fonctionnent de la même manière, mais permettent respectivement d’affecter à une variable la valeur de la multiplication d’elle-même par un autre nombre et la valeur de la division d’elle-même par un autre nombre.  

        - On comprend que les opérateurs vont nous permettre de modifier les valeurs des nombres. Mais ils vont aussi nous permettre de modifier d’autres types de données, comme les chaînes de caractères.  

        - Les autres opérateurs d’affectation sont listés à l’adresse : [developer.mozilla.org](https://developer.mozilla.org/fr/docs/Web/JavaScript/Guide/Expressions_and_Operators#op%C3%A9rateurs_daffectation)

  - #### ***Opérateurs à utiliser pour les chaînes de caractères***  

    - Les chaînes de caractères permettent de représenter des textes.  
    
    - Ce sont, comme leur nom l’indique, des ensembles de caractères, assemblés les uns à la suite des autres.  
    
    - 2 opérateurs vont être très utiles pour modifier des chaînes de caractères : l’opérateur de concaténation et l’opérateur d’affectation après concaténation.  

    - ***L’opérateur de concaténation « + »***  

        - Le symbole + n’est pas utilisé uniquement pour additionner des nombres.  

        - Il peut servir à la fois d’opérateur d’addition (pour les nombres), mais aussi d’opérateur de concaténation (pour les chaînes de caractères). La concaténation, c’est le fait d’assembler plusieurs chaînes de caractères en une seule. Prenons un exemple simple :  

            ```JS
            let nom = "Parker";
            let prenom = "Peter";
            let nomComplet = prenom + " " + nom;
            console.log(nomComplet);
            ```
            - Ici, nous avons concaténé 3 chaînes de caractères dans la variable nomComplet : la chaîne "Peter" contenue dans la variable prenom, la chaîne " " (qui contient un espace) et enfin la chaîne "Parker" contenue dans la variable nom. La variable nomComplet contient donc la chaîne "Peter Parker".  

    - ***L’opérateur d’affectation après concaténation « += »***  

        - Le symbole += peut aussi être utilisé pour concaténer des chaînes. Quand il est utilisé avec des chaînes, il ne sert pas d’opérateur d’affectation après addition mais on peut dire « d’opérateur d’affectation après concaténation ». Prenons un exemple tout simple :  

            ```JS
            let nom = "Peter";
            nom += " Parker";
            console.log(nom);
            ```
            - La chaîne de caractères qui est placée après l’opérateur est ajoutée à la fin de la chaîne. Donc la variable nom contiendra la chaîne "Peter Parker".  

- ### ***Opérateurs de comparaison et opérateurs logiques***  

  - #### ***Opérateurs de comparaison***  

    - ***Les opérateurs « == » et « != »***  

        - ’opérateur d’égalité == vérifie si 2 valeurs sont égales ou non. Si elles le sont, l’expression renverra true, sinon false :  

            ```JS
            let a = "Ordinateur";
            let b = "Telephone";
            let c = "Ordinateur";
            console.log(a == b);
            console.log (a == c);
            ```
            - On peut voir que console.log(a == b) affiche false car les 2 chaînes ne sont pas égales tandis que console.log (a == c) affiche true car les deux chaînes sont égales.  

        - L’opérateur d’inégalité != vérifie quant à lui si 2 valeurs ne sont pas égales :  

            ```JS
            let a = 17.2;
            let b = 17.5;
            let c = 17.2;
            console.log(a != b);
            console.log (a != c);
            ```
            - Dans ce cas, console.log(a != b) affiche dans la console true puisque a et b ne sont pas égaux. Cependant, console.log (a != c) affiche false car a et c sont égaux.  

    - ***Les opérateurs « === » et « !== »***  

        - Les opérateurs === (d’égalité stricte) et !== (d’inégalité stricte) vérifient respectivement si une valeur est égale ou inégale à une autre, mais prennent aussi en compte le type de la valeur (entier, booléen, chaîne de caractères, etc.).  
        
        - L’opérateur === vérifie si une valeur est égale à une autre et si leur type sont les mêmes. Dans ce cas, il renvoie true. L’opérateur !== renvoie true dans le cas où il y a au moins une différence de type ou de valeur entre les 2 valeurs.  

            ```JS
            let a = 1;
            let b = "1";
            console.log(a == b); //egalite : true
            console.log(a === b); //egalite stricte : false
            console.log(a != b); //inegalite : false
            console.log (a !== b); ////inegalite stricte : true
            ```

    - ***Les opérateurs « < », « > », « <= » et « >= »***  

        - Pour bien comprendre, listons et expliquons chacun de ces opérateurs :  

            - ***<*** : stricte infériorité. Vérifie si une valeur est strictement inférieure à une autre  

            - ***>*** : stricte supériorité. Vérifie si une valeur est strictement supérieure à une autre  

            - ***<=*** : infériorité. Vérifie si une valeur est inférieure ou égale à une autre  

            - ***>=*** : supériorité. Vérifie si une valeur est supérieure ou égale à une autre

                - Prenons un exemple simple :  

                    ```JS
                    let a = 17.2;
                    let b = 17.5;
                    let c = 17.2;
                    console.log(a < b); //true
                    console.log (a <= c); //true
                    console.log (a > b); //false
                    console.log (a >= c); //true
                    ```
                    - Pour chaque ligne console.log, un commentaire spécifie dans le code le booléen affiché. On voit que c’est cohérent.

  - #### ***Opérateurs logiques***  

    - ***L’opérateur « && »***  

        - L’opérateur && signifie littéralement « et ».  
        
        - Dans le cas où on utilise un && au milieu de deux expressions renvoyant un booléen, l’opérateur renverra true si les deux expressions renvoient true, sinon, il renverra false.  
        
        - Donc, quand on utilise l’opérateur &&, on vérifie si deux expressions sont « vraies ». Si une seule l’est, alors, l’opérateur renverra false. Voyons un exemple concret :  

            ```JS
            let a = 17.5;
            let b = 17.5;
            let c = 17.2;
            console.log(a > c && a < b); //false
            console.log(a == b && a > c); //true
            ```
            - L’instruction console.log(a > c && a < b) affiche dans la console false car les deux expressions ne sont pas vraies. Même si l’expression a > c est vérifiée, l’expression a < b est fausse.  

            - En revanche, l’instruction console.log(a == b && a > c) affiche true car les expressions a == b et a > c sont toutes les deux vraies.

    - ***L’opérateur « || »***  

        - L’opérateur || signifie littéralement « ou ». Dans le cas où on utilise un || au milieu de deux expressions renvoyant un booléen, l’opérateur renverra true si au moins une des deux expressions est juste, sinon, il renverra false :  

            ```JS
            let a = 17.5;
            let b = 17.5;
            let c = 17.2;
            console.log(a == b || a < c); //true
            console.log(a < c || a == c); //false
            ```
            - L’instruction console.log(a == b || a > c) affiche dans la console true car une des deux expressions renvoie true (l’expression a == b est vérifiée). Si les deux expressions étaient vraies, l’instruction aurait aussi affiché true.  

            - En revanche, l’instruction console.log(a < c || a == c) affiche false car aucune des deux expressions n’est vraie.  

    - ***L’opérateur « ! »***  

        - L’opérateur ! signifie littéralement « non ». On l’utilise pour renvoyer true si une expression renvoie false et inversement :  

            ```JS
            let a = 17.5;
            let b = 17.5;
            let c = 17.2;
            let d = true;
            let e = false;
            console.log(!(a == b)); //false
            console.log(!(a > b)); //true
            console.log(! d); //false
            console.log(! e); //true
            ```
            - Dans les deux premiers console.log, on place les expressions a == b et a > b entre parenthèses pour indiquer que si l’expression en entier renvoie true, alors, c’est false qui sera affiché et inversement.  
            
            - Les parenthèses permettent d’inverser le booléen renvoyé par toute l’expression et pas seulement la variable qui vient tout de suite après l’opérateur : !.  

##
## ***__Structures de contrôle en JS__***

- ### ***Structure de contrôle if/else***

    - ***Utilisation de la condition if***  

        - Comme vous le savez, des opérateurs de comparaison peuvent renvoyer un booléen : true ou false. On peut les utiliser pour vérifier si une valeur est égale, inégale, supérieure, etc., à une autre.  

            ```JS
            let a = 1;
            let b = 1;
            console.log(a == b);
            ```  
            - L’expression a == b renverra un booléen, ici true, puisque les deux variables sont égales. Si ce n’était pas le cas, elle renverrait false.  

        - nous allons pouvoir utiliser cette structure de contrôle en spécifiant en paramètre une condition, c’est-à-dire une expression qui va renvoyer true ou false. Si et uniquement si cette expression renvoie true, alors l’instruction ou les instructions spécifiées seront exécutées.  
        
        - Mais comment écrire une condition if ?  

            ```JS
            if (/*condition*/) {
                //instructions;
            }
            ```

            - Prenons un exemple tout simple de condition :  

                ```JS
                const nombre = 11;
                if (nombre > 10) {
                    console.log("Le nombre " + nombre + " est plus grand que 10");
                }
                ```
                - On peut voir que l’on spécifie comme condition l’expression nombre > 10. Comme la constante nombre a pour valeur 11, et que 11 est plus grand que 10, alors l’instruction console.log("Le nombre" + nombre + " est plus grand que 10"); est exécutée. Donc la console affiche : le nombre 11 est plus grand que 10.  

                - En revanche, on peut voir que, si on définit nombre sur 10 par exemple :  

                ```JS
                const nombre = 10;
                if (nombre > 10) {
                    console.log("Le nombre " + nombre + " est plus grand que 10");
                }
                ```
                - Étant donné que nombre n’est pas strictement supérieur à 10, alors l’expression nombre > 10 va renvoyer false. Donc l’instruction console.log("Le nombre " + nombre + " est plus grand que 10"); ne sera pas exécutée. La console n’affichera rien dans ce cas. On peut voir qu’on peut insérer plusieurs lignes de codes qui seront exécutées si la condition renvoie true.

            - Prenons un autre exemple :  

                ```JS
                const marque = "Peugeot";
                const cv = 120;
                const portes = 5;
                let prix;
                if (marque == "Peugeot" || marque == "BMW") {
                    prix = (cv * 100 + portes * 30);
                    console.log ("Prix = " + prix);
                }
                ```
                - Dans ce cas, l’expression marque == "Peugeot" || marque == "BMW" va renvoyer true puisque la variable marque est définie sur la chaîne de caractères "Peugeot". Les deux lignes dans le corps du if (c’est-à-dire les lignes présentes dans les accolades du if) sont donc exécutées, le prix est calculé et affiché dans une chaîne, via la console.  

            - Finalement, cette condition permet d’exécuter les deux lignes du corps de la condition if uniquement si la marque est Peugeot ou BMW. Si on prend la marque Renault par exemple :

                ```JS
                const marque = "Renault";
                const cv = 120;
                const portes = 5;
                let prix;
                if (marque == "Peugeot" || marque == "BMW") {
                    prix = (cv * 100 + portes * 30);
                    console.log ("Prix = " + prix);
                }
                ```
                - On peut voir qu’aucune des deux instructions du corps de la condition if ne sont exécutées.


    - ***Utilisation du mot clé else***  

        - Le mot clé else (qui signifie littéralement « sinon ») permet de dire en quelques sortes : « Si (if) une condition est vérifiée, exécuter les premières instructions, sinon (else), exécuter les secondes instructions ». Pour faire simple, le mot clé else va permettre d’indiquer les instructions à exécuter si l’expression de la condition précédente renvoie false. La syntaxe est très simple :  

            ```JS
            if (/*condition*/) {
                //instructions;
            }
            else {
                //instructions;
            }
            ```  
        
        - Reprenons l’exemple précédent et rajoutons un else pour afficher dans la console une chaîne de caractères si la marque n’est ni Peugeot, ni BMW.  

            ```JS
            const marque = "Renault";
            const cv = 120;
            const portes = 5;
            let prix;
            if (marque == "Peugeot" || marque == "BMW") {
                prix = (cv * 100 + portes * 30);
                console.log ("Prix = " + prix);
            }
            else {
                console.log("La marque " + marque + " n'est pas valide");
            }
            ```
            - Dans ce cas, comme l’expression de la condition renvoie false, c’est l’instruction du else qui est exécutée.  
                
                - Donc la console affiche : La marque Renault n'est pas valide  


        - Si l’on change la marque et que l’on écrit BMW :  

            ```JS
            const marque = "BMW";
            const cv = 120;
            const portes = 5;
            let prix;
            if (marque == "Peugeot" || marque == "BMW") {
                prix = (cv * 100 + portes * 30);
                console.log ("Prix = " + prix);
            }
            else {
                console.log("La marque " + marque + " n'est pas valide");
            }
            ```
            - Alors, ce sont les premières instructions (celles du if) qui sont exécutées.  
            
                - La console affiche : Prix = 12150  


    - ***Utilisation de else if***  

        - Maintenant, nous pouvons parler de l’instruction else if, littéralement « sinon si ». La structure else if va nous permettre de rajouter une condition si l’expression de la condition précédente renvoie false.  

        - La syntaxe n’est pas bien plus compliquée :  

            ```JS
            if (/*condition 1*/) {
                //instructions;
            }
            else if (/*condition 2*/) {
                //instructions;
            }
            else {
                //instructions;
            }
            ```
        
        - Pour prendre un exemple, on peut améliorer notre script précédent pour que la structure de contrôle exécute :

            - « ***Si (if)*** la marque est "Peugeot" ou "BMW" et si le nombre de cv est inférieur ou égal à 150, calculer le prix et afficher le prix, ***sinon si (else if)*** la marque est "Peugeot" ou "BMW", calculer le prix en ajoutant une taxe de 2 000 € , et afficher le prix taxé, ***sinon (else)***, afficher que la marque n’est pas valide. » Cette condition est cohérente, nous pouvons donc réaliser notre script :  

                ```JS
                const marque = "Peugeot";
                const cv = 180;
                const portes = 5;
                let prix;
                if ((marque == "Peugeot" || marque == "BMW") && cv <= 150) {
                    prix = (cv * 100 + portes * 30);
                    console.log ("Prix = " + prix);
                }
                else if (marque == "Peugeot" || marque == "BMW") {
                    prix = ((cv * 100 + portes * 30) + 2000);
                    console.log ("Prix taxé = " + prix);
                }
                else {
                    console.log("La marque " + marque + " n'est pas valide");
                }
                ```  
                - Dans cet exemple, la condition vérifie si la marque est « Peugeot » ou « BMW », et si le nombre de cv est inférieur ou égal à 150. Comme le nombre de cv n’est pas inférieur ou égal à 150, l’expression de la condition renvoie ***false***. Les instructions du ***if*** ne sont pas exécutées et la condition du ***else if*** est donc traitée. Comme la marque est égale à **Peugeot**, l’expression de la condition (du ***else if***) est validée, elle renvoie ***true*** et les instructions du corps du ***else if*** sont exécutées : le prix est calculé avec une taxe de 2 000 et le prix taxé est affiché.  

                - Le ***else*** aurait été appelé uniquement si la condition du ***else if*** avait été fausse, donc dans le cas présent si la marque n’avait été ni Peugeot, ni BMW.  

                - Bien évidemment, on peut rajouter autant de else if que l’on veut.  

- ### ***Structure de contrôle switch***

    - ***Introduction à switch***

        - En programmation, la structure de contrôle switch existe dans de nombreuses technologies.  
        
        - Mais qu’est-ce que c’est au juste ?  
        
            - Le terme switch peut se traduire littéralement par « interrupteur » ou le verbe « changer ». 
            
            - En programmation, la structure switch, aussi souvent appelée switch/case, permet de facilement répertorier plusieurs valeurs possibles renvoyées par une expression et de définir les instructions pour chaque cas.  

            - La Syntaxe :  

                ```JS
                switch (/*expression*/) {
                case /*valeur 1*/:
                    //instructions 1;
                break;
                case /*valeur 2*/:
                    //instructions 2;
                break;
                case /*valeur 3*/:
                    //instructions 3;
                break;
                case /*valeur 4*/:
                    //instructions 4;
                break;
                }
                ```  

        - Prenons un exemple très simple. Nous avons une variable marque qui correspond à la marque d’un téléphone et on souhaite générer un console.log spécifique pour chaque marque. Voici un script qui fonctionne :  

            ```JS
            const marque = "Huawei";
            
            switch (marque) {
            case "Apple":
                console.log ("Smarhphone haut de gamme avec système IOS");    
                break;

            case "Samsung":
                console.log ("Smartphone haut de gamme avec système Android");  
                break;
            
            case "Xiaomi":
                console.log ("Smartphone bon marché avec système Android"); 
                break;
            
            case "Huawei":
                console.log ("Smartphone bon marché avec système Android");
                break;
            }
            ```  
            - Dans ce cas, le switch va vérifier à chaque case (à chaque cas) si marque est égale à "Huawei". Si ce n’est pas le cas, elle passe au traitement du case suivant. C’est donc pour le case "Huawei" que l’instruction va être déclenchée, donc c’est l’instruction console.log "Smartphone bon marché avec système Android;" qui est exécutée.  

    - ***La clause default***  

        - La clause ***default*** permet d’indiquer les instructions qui seront exécutées « par défaut », c’est-à-dire dans le cas où aucun cas spécifié ne correspond à la valeur renvoyée par l’expression de référence.  
        
        - Bien qu’elle soit facultative, il est fortement préconisé de l’utiliser dans un switch. Pour bien comprendre, appliquons cette notion à notre exemple :  
        
            ```JS
            const marque = "Motorola";
            switch (marque) {

            case "Apple":
                console.log("Smartphone haut de gamme avec système IOS");
                break;

            case "Samsung":
                console.log("Smartphone haut de gamme avec système Android");
                break;

            case "Xiaomi":
                console.log("Smartphone bon marché avec système Android");
                break;

            case "Huawei":
                console.log("Smartphone bon marché avec système Android");
                break;

            default:
                console.log("Marque non référencée");
                break;
            }
            ```  

        - On peut voir qu’en spécifiant la clause ***default***, on indique quelles instructions va exécuter le switch dans le cas où aucun des case ne correspond à la valeur de marque.  

            - On peut cependant constater que notre switch pourrait être amélioré. En effet, pour les marques « Xiaomi » et « Huawei », les instructions sont exactement les mêmes. Il n’y a donc pas besoin de les répéter deux fois. Comment appliquer la même instruction à deux case ?

    - ***Appliquer une même suite d’instructions pour plusieurs cas***  

        - Pour appliquer une même suite d’instructions pour plusieurs cas, il nous faut simplement préciser chaque ***case*** concerné avant d’écrire la suite d’instructions, en respectant la syntaxe. Pour bien comprendre, appliquons cette notion à notre exemple :

            ```JS
            const marque = "Huawei";
            switch (marque) {
                case "Apple":
                console.log("Smartphone haut de gamme avec système IOS");
                break;
            case "Samsung":
                console.log("Smartphone haut de gamme avec système Android");
                break;
                case "Xiaomi":
            case "Huawei":
                console.log("Smartphone bon marché avec système Android");
                break;
            default:
                console.log("Marque non référencée");
                break;
            }
            ```
            - On peut voir que ça fonctionne, les instructions exécutées seront les mêmes pour les marques « Xiaomi » et « Huawei », à savoir :

                ```JS
                console.log("Smartphone bon marché avec système Android");
                break;
                ```

##
## ***__Les boucles__***  

- ### ***Boucle for***  

  - #### ***Console log***  

    - Dans le cadre de ce cours, vous serez amené à utiliser nos exemples pour comprendre de quoi il retourne et avoir un retour visuel sur le code. Pour ce faire, vous devez :  

        - Effectuer un clic droit sur la page  

        - Sélectionner l’option « Inspecter »  

        - Vous rendre dans « Console »  

    - Cela fait, vous aurez un aperçu des informations supposées se trouver dans console.log().  

  - #### ***Première utilisation de la boucle for***  

    - ***La boucle for***  

        - La boucle for est une boucle vraiment importante en programmation.  
        
        - Pour faire simple, disons qu’on peut l’utiliser dans tous les cas où, juste avant l’exécution de la boucle, le nombre d’itérations (de tours de boucle) est fixé.  
        
        - Autrement dit, le nombre d’itérations ne changera pas ou ne sera pas déterminé lors de l’exécution des itérations de la boucle.  

    - ***Première façon d’utiliser la boucle for***  

        - La première manière d’utiliser la boucle for se fait avec cette syntaxe :  

            ```JS
            for (/*initialisation*/; /*condition*/; /*incrementation*/) {
                //instructions;
            }
            ```
            - Dans les paramètres du for, nous allons spécifier :  

                1. Initialisation : nous allons initialiser une variable qui servira de compteur à notre boucle.  

                1. Condition : nous allons définir la condition qui déterminera le nombre d’itérations.  

                1. Incrémentation : nous allons définir l’incrémentation de notre compteur.  


        - Pour bien comprendre, voyons un exemple simple :  

            ```JS
            for (let i = 1; i <= 10; i ++) {
                console.log (i);
            }
            ```
            - Dans cet exemple, dans les paramètres du for, nous initialisons le compteur i en le définissant sur le nombre 1.  
            
            - Nous indiquons ensuite que la boucle devra se répéter tant que i est inférieure ou égale à 10.  
            
            - Enfin, nous incrémentons à chaque tour de boucle la variable i. L’instruction à réitérer est l’affichage dans la console de la variable i. On peut voir que la boucle fonctionne ainsi :  

                1. Le programme vérifie si i est inférieure ou égale à 10. Or i est égale à 1. L’expression i <= 10 renvoie donc true. Une première itération de la boucle est lancée et la console affiche i, donc 1.  
                
                1. Le programme vérifie si i est inférieure ou égale à 10. Or, i a été incrémentée et est maintenant égale à 2. L’expression i <= 10 renvoie donc true. Une deuxième itération de la boucle est lancée et la console affiche i, donc 2.  

                1. Etc.  

            - Finalement, lorsque 10 tours de boucles ont été effectués, la variable i est incrémentée et vaut 11. L’expression i <= 10 renvoie donc false. La boucle s’arrête alors.  

            - On peut constater qu’avant chaque tour de boucle, la condition est testée et le résultat détermine si une nouvelle itération aura lieu ou non.  

    - ***Tableau***  

        - Pour faire simple, en JavaScript, un tableau est une liste d’éléments ordonnés stockés dans une variable. On utilise les crochets pour stocker des valeurs dans un tableau.  

        - Par exemple :  

            ```JS
            let tableau = ["valeur 1", "valeur 2"];
            ```
            - Chaque élément du tableau est accessible via son index, sachant que le premier élément du tableau à pour index 0, le second 1, le troisième 2, etc.  

        - On peut récupérer un élément de ce tableau comme ceci :  

            ```JS
            tableau[1]; // = "valeur 2"
            ```

        - Maintenant prenons un autre exemple de boucle for interagissant avec un tableau :  

            ```JS
            const nombre = 10;
            let table = [];
            for (let i = 1; i <= 10; i ++) {
                let resultat = nombre * i;
                table.push(resultat)
            };
            ```
            - Ici, l’objectif de notre boucle est de dresser à l’intérieur d’un tableau et plus particulièrement dans notre cas faire la table de multiplication d’un nombre.  
            
            - Nous commençons par définir la variable ***nombre***, puis nous déclarons un tableau (avec les crochets) que nous appelons ***table***.  

            - Celui-ci contiendra tous les nombres de la table de ***nombre***. Dans le ***for***, on ne change rien, car on souhaite que la première valeur de i soit 1 et qu’il y ait 10 itérations. À chaque tour de boucle, nous déclarons et définissons une variable ***resultat*** qui stockera le produit de ***nombre*** par ***i*** (qui vaudra 1 puis 2, puis 3, etc., jusqu’à 10).  

            - On ajoute ensuite à chaque itération le résultat dans notre tableau table. On peut voir que ce script fonctionne bien, d’ailleurs, si on fait un console.log de la 4e valeur de table (donc avec l’index 3), on obtient :  

                ```JS                
                const nombre = 10;
                let table = [];
                for (let i = 1; i <= 10; i ++) {
                    let resultat = nombre * i;
                    table.push(resultat);
                }
                console.log(table[3]); // = 40 (10 x 4)
                ```

  - #### ***Utiliser for/in***  

    - Le système ***for/in*** va nous permettre d’utiliser la boucle ***for*** à travers les propriétés d’un objet. La syntaxe est la suivante :  

        ```JS
        for (/*variable*/ in /*objet*/) {
            //instructions;
        }
        ```
    - Le concept d’objet en programmation ne vous est peut-être pas familier et c’est normal. Pour l’instant, sans rentrer dans les détails, dites-vous qu’un objet est une entité ; un ensemble de données qui contient des propriétés qui le caractérisent. Prenons un exemple :  

        ```JS
        let animation = new Animation();
        for (let i in animation) {
            console.log(i);
        }
        ```
        - Ici, nous créons un objet que l’on appelle ***animation*** (c’est le nom de la variable) et il est de type ***Animation***.  
        
        - Cet objet a de nombreuses propriétés, et, avec la boucle ***for***, on peut parcourir chacune de ces propriétés pour en afficher une par une leur nom (et non leur valeur).  
        
        - Dans les paramètres, nous déclarons la variable ***i*** qui représentera à chaque tour de boucle une propriété dans l’objet ***animation***. On peut voir que la console affiche le nom de toutes les propriétés de l’objet. Toutefois, ce concept reste peut-être un peu flou. Voyons ce que cela donne si on parcourt un tableau avec cette méthode :  

            ```JS
            let tableau = ["Apple", "HP", "Acer"];
            for (let i in tableau) {
                console.log(i);
            }
            ```
            - On peut voir que la console affiche 0, 1, 2.  
            
            - Pourquoi ? Tout simplement parce que mon tableau a 3 propriétés correspondant aux index des éléments qui le composent. En ce sens, cela pourrait être intéressant d’utiliser ce système pour afficher la valeur des éléments de notre tableau comme ceci :

            ```JS
            let tableau = ["Apple", "HP", "Acer"];
            for (let i in tableau) {
                console.log(tableau[i]);
            }
            ```
            - Effectivement, cela fonctionne, la console affiche chaque valeur du tableau. 
            
            - Cependant, il n’est pas préconisé de procéder ainsi pour récupérer les valeurs d’un tableau.  
            
            - Pourquoi ? Tout bonnement parce que le ***in*** permet de parcourir les propriétés du tableau. Si l’on ajoute des propriétés à notre tableau (qui ne sont pas nécessairement des éléments du tableau), alors la boucle for les parcourra aussi, ce qui posera un problème (puisqu’on aura les éléments du tableau et les autres propriétés).  
            
            - En ce sens, quand on veut parcourir un tableau, il est important d’utiliser le système ***for/of***.  

  - #### ***Utiliser for/of***  

    - La boucle for/of permet de parcourir un objet itérable et de récupérer ses valeurs. C’est le cas par exemple des tableaux. Si l’on reprend notre exemple précédent et que l’on cherche à afficher dans la console chaque élément du tableau, on peut faire simplement :  

        ```JS
        let tableau = ["Apple", "HP", "Acer"];
        for (let i of tableau) {
            console.log(i);
        }
        ```
        - Cela fonctionne, car à chaque tour de boucle, i prend la valeur d’un élément de tableau, et la boucle parcourt tous les éléments du tableau. Avec la boucle for/of, on peut donc rapidement récupérer les valeurs d’un tableau.  

    - Modifions-la pour que notre programme permette de concaténer dans une chaîne de caractères les valeurs des différents éléments du tableau :  

        ```JS
        let tableau = ["Apple", "HP", "Acer"];
        let marques = "";
        for (let i of tableau) {
            marques += i + ", ";
        }
        console.log (marques);
        ```
        - On peut voir que la console affiche : Apple, HP, Acer,

        - À chaque tour de boucle, le programme ajoute à la fin de la chaîne de caractères marques la valeur de i qui contient une valeur d’un élément du tableau. Tous les éléments du tableau sont parcourus.

- ### ***Boucle while***  

    - #### ***Boucle while***  

        - À la différence de la boucle for, nous utiliserons en général la boucle while quand, juste avant l’exécution de la première itération de la boucle, le nombre d’itérations n’est pas encore fixé.  
        
        - Cette règle n’est toutefois pas absolue. En réalité, dans de nombreux cas où l’on utilise une boucle for, il est également possible d’utiliser une boucle while. Voyons comment utiliser la boucle while.

        - ***Utilisation de la boucle while***  

            - La syntaxe de la boucle while est :  

                ```JS
                while (/*condition*/) {
                    //instructions;
                }
                ```
                - On indique simplement en paramètre du while la condition pour qu’une itération se produise.  
                
                - Le programme commence par vérifier si la condition renvoie true et si c’est le cas, elle exécute les instructions de la boucle.  
                
                - Puis, le programme vérifie à nouveau la condition et si elle renvoie true, alors, les instructions sont à nouveau exécutées, ainsi de suite.  

        - On voit que le système de while est assez simple à comprendre. Prenons un exemple simple :  

        ```JS
        let nombre = 1;
        while (nombre <= 10) {
            console.log ("Le nombre est : " + nombre);
            nombre += 2;
            nombre -=0.5;
        }
        console.log (nombre)
        ```
        - Ici, nous définissons une variable nombre sur la valeur de 1.  
        
        - Puis, dans le while, nous passons en paramètre l’expression conditionnelle nombre <= 10. 
        
        - Tant que nombre sera inférieure ou égale à 10, alors la boucle continuera de s’exécuter.  
        
        - On peut voir que dans les instructions, on commence par afficher le nombre dans une chaîne concaténée, puis on lui ajoute 2 et on lui retire 0,5.  
        
        - Cet ensemble d’instructions sera exécuté à chaque itération. Toutefois, en quel sens peut-on dire que le nombre d’itérations n’est pas fixé avant la première itération ?

            - Si on regarde la boucle, on peut voir que, hors instructions (c’est-à-dire hors du corps de la boucle), le nombre d’itérations est inconnu.  
            
            - Ce sont, dans cet exemple, les instructions de la boucle qui permettent de déterminer le nombre d’itérations en fonction de la condition (car on modifie la variable nombre dans les instructions du while, tandis que la condition porte sur cette même variable nombre).  
            
            - Dans ce cas, il est donc judicieux d’utiliser la boucle while. À la différence, quand nous utilisons la boucle for, le nombre d’itérations est fixé dans les paramètres de la boucle (sauf si on ajoute des instructions de type break ou continue que nous aborderons).  
            
            - Pour notre while, la console affichera donc :  

                1. Le nombre est : 1

                1. Le nombre est : 2.5

                1. Le nombre est : 4

                1. Le nombre est : 5.5

                1. Le nombre est : 7

                1. Le nombre est : 8.5

                1. Le nombre est : 10

                1. 11.5

                     - On peut voir qu’après la 7e itération, le programme vérifie la valeur de nombre qui est maintenant égale à 11.5. La variable nombre étant supérieure à 10, le programme sort de la boucle.

        - ***Utilisation de la boucle do/while***  

            - Comme vous avez pu le voir, lorsque l'on utilise un while, le programme commence par vérifier la condition puis, si l’expression conditionnelle renvoie true, il lance une première itération de la boucle, sinon, aucune itération n’est lancée.  

            - Prenons l’exemple suivant :  

            ```JS
            let cv = 100;
            while (cv > 100 && cv <= 110) {
                console.log ("La voiture a " + cv + " cv");
                cv ++
            }
            ```
            - On peut voir dans ce script que la condition du while est que cv soit strictement supérieure à 100 et inférieure ou égale à 110. Concrètement, la boucle ne va jamais se lancer, car cv est égale à 100.  

            - Le programme vérifie l’expression cv > 100 && cv <= 110 et, étant donné qu’elle renvoie false, alors aucune itération de la boucle n’est opérée.  
            
            - Il nous faudrait donc un système qui lance une première itération de la boucle avant de contrôler l’expression conditionnelle. C’est ce que permet le do/while.  

        - ***Do/while***  

            - Syntaxe :  

                ```JS
                do {
                    //instructions; 
                } while (/*condition*/);
                ```

            - Si on modifie notre exemple :  

                ```JS
                let cv = 100;
                do {
                    console.log ("La voiture a " + cv + " cv");
                    cv ++;
                } while (cv > 100 && cv <= 110);
                ```
                - Le do/while permet donc d’opérer une première itération de la boucle avant de vérifier la condition.  


        - ***Éviter les boucles infinies***  

            - Abordons maintenant une erreur à éviter, les boucles infinies.  

            - Un problème qui peut avoir lieu est celui des boucles infinies : des boucles qui ne s’arrêtent jamais et qui font planter le programme.  
            
            - Une boucle infinie a lieu quand l’expression de la condition d’un while ne cesse jamais de renvoyer true, c’est-à-dire qu’il n’y a aucune instruction qui va rendre cette condition fausse.  

            ```JS
            let a = 120;
            while (typeof(a) == "number" && (a >= 100 && a <= 140)) {
                console.log(a);
            }
            ```
            - Dans cet exemple, la condition du while spécifie que le type de la variable a doit être un nombre, et que a doit être comprise entre 100 (inclus) et 140 (inclus).  
            
            - Étant donné que la variable a est égale à 120, cette condition renvoie true. Toutefois, le problème est qu’aucune instruction ne vient dans le while changer la valeur de a.  
            
            - La condition sera alors toujours vérifiée (elle renverra toujours true), et la boucle ne s’arrêtera pas tant que le programme n’est pas stoppé. 
            
            - En revanche, si l’on ajoute une incrémentation de la variable dans la boucle, la boucle ne sera plus infinie et le code fonctionnera correctement.  

                - Exemple :  

                    ```JS
                    let a = 120;
                    while (typeof(a) == "number" && (a >= 100 && a <= 140)) {
                        console.log(a);
                        a ++;
                    }
                    ```

        - ***Utilisation de break et continue***  

            - Le mot clé ***break*** permet de sortir d’une boucle, tandis que le mot clé ***continue*** permet de reprendre l’exécution d’une boucle, de passer directement à l’instruction suivante.  

            - Prenons l’exemple où on insère une condition dans une boucle while par exemple :  

                ```JS
                let a = 110;
                while (a >= 100 && a <= 150) {
                console.log(a);
                a += 10;
                if (a == 130) {
                    continue;
                }
                else if (a == 140) {
                    break;
                }
                console.log("nv");
                }
                console.log("fini");
                ```

                - Essayons de comprendre comment fonctionne le programme. La console affiche :  

                    1. 110
                    1. nv
                    1. 120
                    1. 130
                    1. fini

                - La variable a a pour valeur 110. Le while vérifie la condition a >= 100 && a <= 150 qui renvoie true. Une première itération de la boucle est donc lancée. La variable a est affichée dans la console (donc 110) et le programme lui ajoute 10 (a est maintenant égale à 120). Les deux conditions vérifient si a est égale à 130 et si a est égale à 140, mais ce n’est pas le cas. Le programme passe à l’instruction suivante console.log("nv") qui affiche donc « nv » dans la console.

                - Le while vérifie à nouveau la condition a >= 100 && a <= 150. Elle renvoie true, donc une nouvelle itération de la boucle est exécutée. La variable a est affichée dans la console (donc 120) et le programme lui ajoute 10 (a est maintenant égale à 130). La condition if vérifie si a est égale à 130.  Comme c’est le cas, l’instruction du if est exécutée, donc continue. Cette instruction permet de ne pas exécuter la suite de l’itération et de passer à la prochaine itération de la boucle.  

                - Le while vérifie à nouveau la condition a >= 100 && a <= 150. Elle renvoie true, donc une nouvelle itération de la boucle est exécutée. La variable a est affichée dans la console (donc 130) et le programme lui ajoute 10 (a est maintenant égale à 140). La condition if vérifie si a est égale à 130, mais ce n’est pas le cas, le else if est donc traité. Le programme vérifie si a est égale à 140, et c’est bien le cas, donc l’instruction du else if est exécutée, c’est-à-dire le break. Cette instruction fait s’arrêter la boucle et continue le script (après la boucle).  

                - Le console.log("fini") est donc exécuté et la console affiche cette chaîne.  

                - Voilà, c’est un exemple assez basique, mais on peut voir que les instructions break et continue vont permettre de rajouter du potentiel aux boucles. Bien évidemment, ces mots clés peuvent être utilisés avec la boucle for.

##  
## ***__Les fonctions en JS__***  

- ### ***Utilisation et définition de fonctions***  

  - #### ***Utilisation et définition de fonctions***  

    - ***Fonctions prédéfinies***  

        - En JavaScript et en général dans tous les langages de programmation, il existe des fonctions prédéfinies. Il existe plusieurs fonctions natives, que l’on peut appeler n’importe où dans un code JS. Par exemple la fonction eval(). Elle permet d’évaluer un script JavaScript contenu dans une chaîne de caractères. Par exemple, si nous écrivons un script dans une chaîne :  

            ```JS
            // "const nombre = 15; console.log(nombre * 2) ;"
            ```

        - Nous pouvons appeler la fonction eval() en indiquant dans les parenthèses la chaîne :  

            ```JS
            // eval("const nombre = 15; console.log(nombre * 2);")
            ```
        
        - Nous pouvons voir qu’avec cette fonction, le code inscrit dans la chaîne est évalué et donc exécuté. La console affiche 30. C’est un exemple tout simple de fonction native. On trouve une liste des fonctions natives sur la documentation Mozilla à l’adresse : developer.mozilla.org dans la partie « Fonctions Prédéfinies ». Mais intéressons-nous à la définition de « fonctions personnalisées ».  

    - ***Syntaxe de la définition de fonctions***  

        - Pour définir des fonctions en JavaScript, il faut respecter cette syntaxe :  

            ```JS
            function nomDeLaFonction(paramètres) {
                instructions;
            }```

        - On utilise le mot clé ***function*** pour définir une fonction. Les paramètres (dans le cas où il y en a) sont déclarés dans les parenthèses, et les instructions sont définies dans les accolades. Mais comment appeler notre fonction, afin d’exécuter les instructions qu’elle contient ?

    - ***Syntaxe de l’appel d’une fonction***  

        - Pour appeler une fonction en JavaScript, on peut utiliser la syntaxe :  

            ```JS
            // nomDeLaFonction(paramètres);
            ```

    - ***Première définition d’une fonction***  

        - Nous souhaitons créer une fonction qui calcule le double d’un nombre et qui l’affiche dans une chaîne de caractères. Nous définissons une fonction que nous appellerons calcDouble() :  

            ```JS
            const nombre = 100;
            function calcDouble() {
                let double = nombre * 2;
                console.log("Le double du nombre " + nombre + " est " + double);
            }
            ```

        - Nous définissons donc la fonction calcDouble. Mais si nous exécutons ce code, il ne se passe pas grand-chose. Il faut que nous appelions notre fonction pour que ses instructions soient exécutées :  

            ```JS
            const nombre = 100;
            function calcDouble() {
                let double = nombre * 2;
                console.log("Le double du nombre " + nombre + " est " + double);
                }
            
            calcDouble(); // Appel de la fonction
            ```

        - Nous pouvons voir que ça fonctionne, la console affiche : "Le double du nombre 100 est 200". Maintenant, admettons que nous changions la valeur de la variable nombre (nous changeons le const en let) et que nous la définissions sur 40 par exemple. Nous voulons à nouveau calculer le double de nombre. Mais est-ce que nous avons besoin de réécrire les instructions permettant de calculer le double de nombre ? Non, nous n’avons qu’à appeler à nouveau la fonction calcDouble() :  

            ```JS
            let nombre = 100;
            function calcDouble() {
                let double = nombre * 2;
                console.log("Le double du nombre " + nombre + " est " + double);
            }

            calcDouble();
            nombre = 40;
            calcDouble();
            ```

            - Nous pouvons voir que ça fonctionne, la console affiche :  

                - Le double du nombre 100 est 200  
                - Le double du nombre 40 est 80  

        - Nous pouvons donc appeler autant de fois que nécessaire la fonction calcDouble(), sans avoir à écrire à chaque fois les mêmes instructions.

- ### ***Paramètres, valeur de retour et expressions de fonctions***  

  - #### ***Paramètres, valeur de retour et expressions de fonctions***  

    - ***Paramètres***  

        - Qu’est-ce qu’un paramètre ? C’est un nom, on peut dire une variable qui est indiquée dans les parenthèses de la fonction. L’intérêt d’un paramètre est qu’il permet d’importer un argument dans une fonction, c’est-à-dire une valeur précise qui sera définie lors de l’appel de la fonction. Pour faire simple, lorsqu’on a un paramètre d’une fonction, on va pouvoir définir sa valeur lors de l’appel de la fonction. On pourra donc définir une valeur différente à chaque appel. Reprenons l’exemple que nous avons pris précédemment :  

            ```JS
            let nombre = 100;
            function calcDouble() {
                let double = nombre * 2;
                console.log("Le double du nombre " + nombre + " est " + double);
            }
            calcDouble();
            nombre = 40;
            calcDouble();
            ```  
        - Admettons que dans cet exemple, on veuille calculer le double d’un nombre passé en paramètre. Ça nous évitera d’avoir à déclarer hors de la fonction une variable nombre et d’avoir à changer sa valeur à chaque fois. Donc si on enlève cette variable, on obtient :  

            ```JS
            function calcDouble(?) {
                let double = ? * 2;
                console.log("Le double du nombre " + ? + " est " + double);
            }
            calcDouble(?);
            calcDouble(?);
            ```  
            - On a placé des points d’interrogation pour indiquer les emplacements où il manque une valeur. Comment faire pour initialiser un paramètre qui stockera la valeur d’un nombre ? Prenons un exemple mathématique :  

                - f(x) = x * 2  

            - Ici, nous avons une fonction mathématique. On peut voir que x est un paramètre de la fonction. Si on calcule f(4), alors tous les x prennent la valeur 4 :  

                - f(4) = 4 * 2  

        - C’est le même principe pour les fonctions en programmation. On va initialiser un paramètre qu’on va par exemple appeler nb. On pourrait l’appeler x ou a, bref, lui donner n’importe quel nom. Puis lors de l’appel, on spécifie l’argument, c’est-à-dire la valeur que va prendre le paramètre nb :

            ```JS
            function calcDouble(nb) {
                let double = nb * 2;
                console.log("Le double du nombre " + nb + " est " + double);
            }
            calcDouble(100); //Le double du nombre 100 est 200
            calcDouble(40); //Le double du nombre 40 est 80
            ```
        
        - Nous pouvons voir que ça fonctionne et que nous pouvons appeler la fonction un nombre de fois illimité en passant en paramètre le nombre pour lequel le double sera calculé. Lorsque nous définissons une fonction, nous pouvons passer plusieurs paramètres. Par exemple, définissons une fonction permettant de calculer le périmètre d’un rectangle :  

            ```JS
            function perimetreRectangle(largeur, longueur) {
                let perimetre = 2 * largeur + 2 * longueur;
                console.log("Le perimetre du rectangle est de " + perimetre + " cm2");
            }
            ```  
        - Quand nous appelons notre fonction, il suffit de spécifier les arguments, donc les valeurs correspondant à la largeur et à la longueur, dans l’ordre correspondant au passage des paramètres :  

            ```JS
            function perimetreRectangle(largeur, longueur) {
                let perimetre = 2 * largeur + 2 * longueur;
                console.log("Le perimetre du rectangle est de " + perimetre + " cm2");
            }

            perimetreRectangle(4, 5);
            perimetreRectangle(2, 4);
            perimetreRectangle(1, 2);
            perimetreRectangle(18, 20);
            ```
            - Nous pouvons voir que les différents appels de la fonction permettent d’afficher le périmètre d’un rectangle de largeur 4 et longueur 5, de largeur 2 et longueur 4, etc.

        - Qu’est-ce qu’une valeur de retour ? Vous vous en rappelez, tout à l’heure nous avons pris un exemple d’une fonction mathématique :  

            - f(x) = x * 2  

        - Dans ce cas, il y a un paramètre spécifié qui est x. Mais à quoi peut correspondre la valeur de retour ? On peut dire que la valeur de retour de cette fonction est f(x). Dans le cas où x = 4, on a :  

            - f(4) = 4 * 2 = 8  

                - Dans le cas où x = 4, la valeur de retour de la fonction sera donc 8.  

                - La valeur de retour de la fonction est donc x * 2.  

        - Jusque-là, nous n’avons pas défini de valeur de retour. Mais on pourrait se demander : est-ce que les fonctions que nous avons définies ont une valeur de retour ? La valeur de retour d’une fonction est renvoyée par l’expression permettant d’appeler une fonction. Par exemple, la valeur de retour de perimetreRectangle(4, 5) est renvoyée par l’expression perimetreRectangle(4, 5).  

        - Voyons donc si notre fonction a une valeur de retour en faisant un console.log de l’expression perimetreRectangle(4, 5).  

            ```JS
            function perimetreRectangle(largeur, longueur) {
                let perimetre = 2 * largeur + 2 * longueur;
                console.log("Le perimetre du rectangle est de " + perimetre + " cm2");
            }
            console.log(perimetreRectangle(4, 5));
            ```
            - On peut voir que la fonction est appelée, mais qu’elle renvoie (ou « que sa valeur de retour est ») undefined. Notre fonction n’a donc pas de valeur de retour explicite, c’est une fonction que l’on peut qualifier « de procédure ». Mais imaginons qu’on veuille que la valeur de retour de notre fonction soit justement le périmètre de notre rectangle. Ce serait plus logique puisque c’est la valeur que l’on cherche à obtenir avec la fonction perimetreRectangle(). On peut (bien que ce ne soit pas obligatoire) retirer le console.log affichant la chaîne de caractères avec le périmètre. Pour définir la valeur de retour d’une fonction, on utilise le mot clé return :  

                ```JS
                function perimetreRectangle(largeur, longueur) {
                let perimetre = 2 * largeur + 2 * longueur;
                return perimetre;
                }
                console.log(perimetreRectangle(4, 5));
                ```

        - Dans ce dernier exemple, la fonction perimetreRectangle() a pour valeur de retour la valeur de la variable  perimetre.  

        - L’expression perimetreRectangle(4, 5) va donc renvoyer 2 * 4 + 2 * 5, donc 18. Comme on affiche perimetreRectangle(4, 5) dans la console, la console affiche 18. On peut tester la fonction avec de nombreux arguments comme suit :  

            ```JS
            function perimetreRectangle(largeur, longueur) {
            let perimetre = 2 * largeur + 2 * longueur;
            return perimetre;
            }
            console.log(perimetreRectangle(4, 5)); //18
            console.log(perimetreRectangle(8, 5)); //26
            console.log(perimetreRectangle(4.4, 1.67)); //12.14
            console.log(perimetreRectangle(64, 45)); //218
            ```

    - ***Utilisation du mot clé return***  

        - Le mot clé return met fin à l’exécution de la fonction et définit la valeur de retour.  

        - Voilà, vous savez maintenant utiliser le mot clé return pour renvoyer une valeur. À noter qu’en règle générale, il est préconisé de définir dans une fonction, une valeur de retour. Tous les exemples que nous avons pu voir dans la première partie ne sont donc pas forcément préconisés. Maintenant que vous savez définir une valeur de retour, prenez donc l’habitude d’utiliser le mot clé return dans vos fonctions.  

    - ***Créer une fonction grâce à une expression de fonction***  

        - Dans tous les exemples de ce cours, nous avons déclaré des fonctions en utilisant une instruction (d’un point de vue syntaxique). Mais il est aussi possible de créer une fonction en passant par une expression. Une expression est une unité de code qui renvoie une valeur. Par exemple, l’expression suivante renvoie 4.  

            - 2 * 2  

        - On peut affecter la valeur renvoyée par cette expression à une variable par exemple :  

            ```JS
            let a = 2 * 2 ; 
            ```
        
        - Mais comment créer une fonction via une expression ? Voici un exemple tout simple :  

        ```JS
        let racine = function racineCarree (nombre) {return Math.sqrt(nombre);};
        ```

    - Nous pouvons voir que nous affectons à la variable racine l’expression de notre fonction racineCarree(). Cette fonction a simplement pour objectif de renvoyer la racine du nombre passé en paramètre, grâce au Math.sqrt(). Dans ce cas, nous créons la fonction grâce à une expression de fonction. Mais nous pouvons aussi grâce à ce système créer une fonction anonyme, c’est-à-dire une fonction qui n’a pas de nom :  

        ```JS
        let racine = function (nombre) {return Math.sqrt(nombre);};
        ```
    
    - Dans les deux cas, nous pouvons appeler notre fonction en passant par la variable racine. Par exemple :  

        ```JS
        console.log(racine(9));
        ```
        - La console affiche donc 3.

##  
## ***__Les types de données__***  

- ### ***Types numériques***  
    
    - #### ***Types numériques***  

        - ***Le type Number***  

            - Le type Number permet de représenter des nombres. Cependant, les nombres représentables grâce au type Number sont compris dans un intervalle précis. Les nombres décimaux entre 2**-1074 et 2**1024 peuvent être représentés. L’intervalle comprenant les nombres entiers représentables d’une manière « safe » est plus restreint.  
            
            - Prenons une valeur numérique et affichons son type :  

                ```JS
                const nombre = 154.78;
                console.log (typeof nombre);
                ```
                - On voit que la console affiche number. Donc nombre est bien de type Number.  

            - On peut noter que les nombres entiers représentables de manière « safe » avec le type Number vont de - (2\**53 - 1) à 2\**53 - 1. Mais que se passe-t-il si on écrit un nombre entier très grand ? Voyons un exemple :  

                ```JS
                const nombre = 100071992549200345;
                console.log (nombre);
                ```

            - On peut voir que la console affiche le nombre 100071992549200350. Mais ce n’est pas le même nombre. Pour quelle raison ? Sans rentrer dans les détails, ce problème d’arrondi est dû au fait que le nombre entier est trop grand pour être représenté par le type Number. Mais alors, comment représenter ce nombre ? En utilisant le type Bigint.  

        - ***Le type BigInt***  

            - Le type Bigint permet de représenter des entiers plus grands que ceux représentables par le biais de Number. Essayons de représenter l’entier précédent avec le type Bigint. Pour cela, nous pouvons utiliser un n que nous ajoutons à la fin du nombre :  

                ```JS
                const nombre = 100071992549200345n;
                console.log (nombre);
                ```
                - Là ça fonctionne, la console affiche : 100071992549200345n.  

                - D’ailleurs, si on affiche le type de nombre :  

                    ```JS
                    const nombre = 100071992549200345n;
                    console.log (typeof nombre);
                    ```
                    - La console affiche : bigint. Le nombre est donc bien de type Bigint.  

            - Quand on va réaliser des opérations arithmétiques, il faudra bien veiller à traiter ensemble des valeurs de même type, pour éviter les erreurs. Nous pouvons voir par exemple que si nous réalisons une addition d’un Bigint avec un Number : 

                ```JS
                const a = 16370197019808913673160913870317n;
                const b = 16879361;
                let addition =  a + b;
                console.log (addition);
                ```

                - Nous pouvons voir que ce code génère une erreur due à une incompatibilité de types dans une opération. On veillera donc à ce que les deux opérandes d’une opération mathématique soient du même type. Pour corriger ce code, nous pouvons par exemple faire de b un BigInt :  

                    ```JS
                    const a = 16370197019808913673160913870317n;
                    const b = 16879361n;
                    let addition =  a + b;
                    console.log (addition);
                    ```

            - À noter que la génération de BigInt doit être raisonnée, car avec de grands nombres, elle peut demander beaucoup de ressources et affecter les performances du programme.  

        - ***NaN***  

            - NaN est un terme, une propriété qu’on va retrouver quand le résultat d’une opération arithmétique n’est pas un nombre. Ce terme signifie littéralement « Not a Number ». Si par exemple, nous essayons de multiplier un nombre par un texte :  

                ```JS
                const nombre = 12456 * "caractères";
                console.log(nombre); //NaN
                ```

            - Un point intéressant en JS, c’est que si nous réalisons une opération arithmétique avec deux nombres dont un est une chaîne de caractères, JS convertit automatiquement la chaîne en nombre, et renvoie le résultat de l’opération :  

                ```JS
                const nombre = 12456 * "10";
                console.log(nombre); //124560
                ```
            
                - Dans ce dernier cas, l’opération renverra 124560 et non NaN, puisque la chaîne « 10 » aura été convertie en nombre et que le calcul aura été opéré.  

            - On peut noter que NaN est une valeur assez spéciale en JavaScript. En effet elle est unique, d’ailleurs, elle n’est même pas égale à elle-même :  

                ```JS
                console.log (NaN === NaN); //false
                ```

- ### ***Autres types primitifs***  

    - #### ***Autres types primitifs***  

        - ***Type Boolean***  

            - Vous connaissez déjà le type booléen. Une variable de type booléen peut avoir pour valeur true ou false. Donc pour définir une variable de type booléen, on peut simplement définir une variable sur true ou false. Par exemple :  

                ```JS
                const variable = true;
                console.log(variable); //true
                console.log(typeof variable); //boolean
                ```

                - Comme vous le savez, les booléens sont utilisés comme valeurs de retour de conditions. Ils permettent donc de comparer les données.  

        - ***Type String***  

            - Le type String (chaîne de caractères) permet de représenter du texte. Les chaînes de caractères sont des ensembles de valeurs ordonnées, et indexées. La première valeur à l’indice 0, la seconde 1, etc. Pour définir une chaîne de caractères, nous pouvons définir une variable sur une valeur ou un ensemble de valeurs comprises entre guillemets :  

                ```JS
                const a = "caractères"
                console.log(a); //caractères
                console.log(typeof a); //string
                ```

            - Voyons un exemple de concaténation de chaînes avec l’opérateur += par exemple :  

                ```JS
                let a = "caractères";
                a += " écris";
                console.log(a); //caractères “écris”
                console.log(typeof a); //string
                ```

                - Ici ça fonctionne, on dirait qu’on modifie la chaîne "caractères". Mais vous vous en rappelez, nous avons dit que les types primitifs définissent des valeurs immuables, c’est-à-dire des valeurs qu’on ne peut pas modifier une fois définies. Pourtant, String est bien un type primitif qui définit les chaînes de caractères qui sont donc des valeurs primitives. "caractères" est une valeur primitive. Donc en théorie, on ne peut pas modifier la valeur d’une chaîne. Mais alors comment fonctionnent les opérateurs de concaténation ?  

                - En réalité, la chaîne initiale n’est pas modifiée. L’opérateur += va créer une nouvelle chaîne qui concatène les chaînes « caractères » et « écris ». La variable a sera alors définie sur cette nouvelle chaîne, mais la chaîne de départ « caractères » n’aura pas été modifiée. C’est le même principe pour les opérateurs d’incrémentation ou d’affectation après addition avec les numbers.  

            - Il est préconisé d’utiliser les chaînes de caractères uniquement pour les textes.  

        - ***Type Symbol***  

            - Un symbole est une valeur unique et qui ne peut pas être changée. Les symboles peuvent être utilisés pour créer des clés uniques ciblant une propriété d’un objet, et ainsi éviter les conflits pouvant exister avec des propriétés créées par d’autres instructions de code. C’est peut-être un peu complexe à comprendre comme ça, mais concentrons-nous sur comment créer un symbole. Pour créer un symbole, il nous faut utiliser une fonction : Symbol(). Cette fonction va nous permettre de créer une valeur de type Symbol.  

                ```JS
                let sy1 = Symbol('marque');
                console.log(sy1); //Symbol(marque)
                console.log(typeof sy1); //symbol
                ```

                - On voit qu’on crée un symbole sy1 défini sur Symbol('marque'). Créons un deuxième symbole que nous définirons aussi sur Symbol('marque'), et comparons ces valeurs :  

                    ```JS
                    let sy1 = Symbol('marque');
                    let sy2 = Symbol('marque');
                    console.log (sy1 ===  sy2); //false
                    ```

                    - C’est intéressant, on définit les deux variables sur la même expression, et les deux symboles ne sont pas égaux. Ça confirme bien qu’un symbole à la caractéristique d’être unique.  

                    - Les symboles vont nous permettre de créer des clés de propriétés uniques et non énumérables (ces propriétés ne seront pas répertoriées lorsqu’on parcourra les propriétés d’un objet avec la boucle for/in). C’est un concept peut être un peu complexe à comprendre pour l’instant, mais ne vous inquiétez pas, contentez-vous pour l’instant de retenir que les symboles nous serviront dans la création de clés de propriétés.  

        - ***Type Null***  

            - La valeur null est une valeur primitive représentant simplement l’absence de valeurs. null doit être définie pour indiquer l’absence de valeur. Par exemple, si nous écrivons :  

                ```JS
                let variable = null;
                console.log (variable); //null
                ```

                - La console affiche null. On peut noter un bug si on cherche à afficher le type de variable :  

                    ```JS
                    let variable = null;
                    console.log (typeof variable); //object
                    ```
                
                - On peut voir que le type renvoyé n’est pas null mais object. C’est un bug de JavaScript qui existe depuis pas mal de temps, mais qui n’a pas été corrigé visiblement pour des raisons de compatibilité.  

        - ***Type Undefined***

            - À la différence de null, la valeur primitive undefined (définie par le type undefined) est renvoyée par défaut lorsqu’on cherche à récupérer une valeur non définie ou une propriété inexistante. Par exemple, si nous écrivons :  

                ```JS
                let variable;
                console.log (variable); //undefined
                console.log (typeof variable); //undefined
                ```
            
                - Nous pouvons voir que c’est automatiquement ce qui est renvoyé par l’expression variable, cette variable n’étant pas définie. À la différence du type null, nous n’avons pas besoin de définir ma variable sur undefined pour qu’elle renvoie undefined, c’est l’expression renvoyée par défaut par JavaScript.  

##  
## ***__L'objet JavaScript Number__***  

- ### ***Découverte de l’objet JS Number***  

    - #### ***Découverte de l’objet JS Number***  

        - ***Explication du concept d’objet***  

            - Un objet est une entité qui se caractérise par un type qui le définit, ainsi que des propriétés. C’est exactement le même principe que dans la réalité. Prenons un objet exemple : un ordinateur, plus précisément un ordinateur de la marque HP. Voici les caractéristiques de notre objet :  

                - Type : Ordinateur  

                - Propriétés : Marque = « HP »  

                - Ram = 8  

                - Stockage = 256  

                - Processeur = « Intel »  

                - Démarrage : démarrage de l’ordinateur  

                - Extinction : extinction de l’ordinateur  

            - Nous pouvons constater que notre objet est de type Ordinateur. Il a plusieurs propriétés (appelées aussi attributs) qui correspondent aux différentes informations caractérisant notre objet. Mais nous pouvons voir que les deux dernières propriétés ne sont pas de simples valeurs, ce sont des mécanismes, déclenchables via l’objet (il est possible de démarrer et d’éteindre l’ordinateur).

            - De manière très similaire, nous pouvons dire que les objets ont des propriétés qui peuvent être soit :  

                - Des variables, définies sur une valeur (appelées souvent attributs en POO).  

                - Des fonctions, c’est-à-dire des ensembles d’instructions qu’il est possible d’appeler via notre objet. Ces fonctions (associées à des objets) s’appellent des méthodes.  
            
            - Si nous traduisons en code le descriptif de notre ordinateur, nous pouvons l’écrire ainsi :  

                ```JS
                let ordi1 = new Object(); //nous construisons notre objet
                ordi1 = {
                marque: "HP",
                ram: 8,
                stockage: 256,
                processeur: "Intel",
                demarrage: function() {
                    console.log("Démarrage de l'ordinateur");
                },
                extinction: function() {
                    console.log("Extinction de l'ordinateur");
                }
                }
                ```

                - Ici, nous pouvons voir que nous créons un objet que nous stockons via la variable ordi1. Ne vous attardez pas pour l’instant sur l’expression new Object(), nous aborderons ce point en temps voulu. Comprenez simplement que cette instruction permet de créer un objet. Puis, nous définissons les propriétés de notre objet parmi lesquelles figurent les attributs (les variables), ainsi que les méthodes demarrage() et extinction(). Nous pouvons voir que pour définir les propriétés, nous utilisons une syntaxe spécifique. Il existe toutefois d’autres moyens de procéder, mais nous ne les verrons pas dans ce cours pour ne pas nous égarer.  

            - Nous pouvons donc accéder aux différentes propriétés de notre objet ordi1, simplement en écrivant ordi1 suivi d’un point « . » et du nom de la propriété.  

                - Prenons un exemple :  

                    ```JS
                    let ordi1 = new Object(); //nous construisons notre objet
                    ordi1 = {
                    marque: "HP",
                    ram: 8,
                    stockage: 256,
                    processeur: "Intel",
                    demarrage: function() {
                        console.log("Démarrage de l'ordinateur");
                    },
                    extinction: function() {
                        console.log("Extinction de l'ordinateur");
                    }
                    }
                    console.log(ordi1.marque); //HP
                    console.log(ordi1.ram); //8
                    ordi1.demarrage(); //Démarrage de l'ordinateur
                    ```

                    - Si nous affichons le type de notre objet avec : console.log(typeof ordi1), la console va afficher object et non « Ordinateur ». C’est tout à fait normal, nous avons construit un objet via l’expression new Object(), nous faisons appel au constructeur Object.  

            - Nous verrons rapidement ce qu’est un constructeur dans les paragraphes suivants. Simplement, dans notre exemple, nous n’avons pas défini de sous-type Ordinateur, mais nous avons créé un objet de type Object, ce qui explique le résultat de : console.log(typeof ordi1).

        - ***Introduction à l’objet Number***  

            - Maintenant que nous avons compris globalement ce qu’est un objet, intéressons-nous à l’objet Number. Comme vous le savez, le type primitif Number définit des valeurs primitives immuables. Cependant, par défaut, un objet n’est pas immuable, car il est possible de modifier ses propriétés après l’avoir créé. Mais alors qu’est-ce que l’objet Number ?  

            - Un objet Number est un objet qui enveloppe un type primitif Number. C’est donc un objet constitué de propriétés, c’est un objet muable, mais qui stocke un type primitif Number. Un objet Number permet donc de manipuler des nombres comme des objets. Avant de voir quelques caractéristiques de l’objet Number, voyons comment créer un objet Number.

        - ***Créer un objet Number***  

            - Pour créer un objet Number, il va nous falloir appeler une méthode dont nous avons parlé très brièvement : un constructeur. Les constructeurs sont des méthodes permettant comme leur nom l’indique de construire un objet.  

            - Pour appeler le constructeur de Number, nous pouvons procéder ainsi :  

                ```JS
                const nombre = new Number(1426.156)
                console.log(nombre);
                ```

                - Dans cet exemple, nous créons un objet Number, en appelant le constructeur de Number. Le mot clé new est indispensable. Nous passons comme argument du constructeur le nombre qui sera enveloppé dans notre objet.  

        - ***Les valeurs possibles de Number***  

            - Un objet Number peut représenter des valeurs numériques comprises dans certaines limites. Ces limites sont définies dans des propriétés par défaut de Number. Pour les récupérer, nous pouvons les afficher via le constructeur Number :  

                ```JS
                console.log(Number.MIN_VALUE);
                console.log(Number.MAX_VALUE);
                ```

                - Number.MIN_VALUE est la valeur minimale qu’un objet Number peut contenir. Number.MAX_VALUE est à l’inverse la valeur maximale qu’un objet Number peut contenir.  

        - ***Opérations arithmétiques***  

            - Nous pouvons réaliser sans problème des opérations arithmétiques avec des objets Number. Pourtant, les objets ne sont pas des valeurs primitives numériques. Nous ne pouvons pas normalement réaliser des opérations arithmétiques entre deux objets, mais uniquement entre deux valeurs numériques. Nous verrons en fin de seconde partie comment JavaScript rend possibles les opérations arithmétiques avec comme opérandes des objets Number, comme dans cet exemple :  

                ```JS
                const a = new Number(18);
                const b = new Number(17);
                console.log(a + b); //35
                console.log (a - b); //1
                console.log(a * b); //306
                console.log (a % b); //1
                ```

                - Il est donc possible de réaliser des opérations arithmétiques très facilement avec les objets Number.

- ### ***Méthodes de Number***  

    - #### ***Méthodes de Number***  

        - ***Types de méthode***  

            - Maintenant que nous comprenons un peu mieux le concept d’objet Number, parlons de quelques-unes de ses méthodes.  

            - Nous pouvons distinguer deux types de méthodes : les méthodes statiques, c’est-à-dire les méthodes que nous pouvons appeler directement via le mot Number, et les méthodes accessibles via les objets créés grâce au constructeur Number. Les objets créés grâce à un constructeur sont appelés des « instances ». Donc, pour faire simple, il existe :  

                - Les méthodes dites « statiques », que nous pouvons appeler directement via le mot Number.  

                - Les méthodes non statiques, que nous pouvons appeler via un objet, c’est-à-dire est une instance de Number.  

            - Les méthodes statiques n’ont donc pas besoin d’instance de Number pour être appelées.

        - ***Les méthodes Number.is…()***  

            - Intéressons-nous à 4 méthodes statiques :  

                - Number.isNaN() : [developer.mozilla.org : Number isNaN()](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Global_Objects/Number/isNaN)  

                - Number.isFinite() : [developer.mozilla.org : Number/isFinite()](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Global_Objects/Number/isFinite)  

                - Number.isInteger() : [developer.mozilla.org : Number/isInteger()](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Global_Objects/Number/isInteger)  

                - Number.isSafeInteger() : [developer.mozilla.org : Number/isSafeInteger()](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Global_Objects/Number/isSafeInteger)  

            - Chacune de ses méthodes va renvoyer un booléen. La première va renvoyer true si l’expression passée comme argument n’est pas un nombre. La seconde va renvoyer true si le nombre passé en argument est fini. La troisième va renvoyer true si le nombre est un entier et la quatrième si le nombre est un entier représentable de manière « safe » avec Number.  

            - Voici quelques exemples d’appel de ces méthodes statiques :  

                ```JS
                console.log(Number.isNaN(62378)); //false
                console.log(Number.isFinite(5817629)); //true
                console.log(Number.isInteger(5817629.872)); //false
                console.log(Number.isSafeInteger(5817629)); //true
                ```

        - ***L’objet Number.prototype***  

            - Parlons maintenant de méthodes accessibles via des objets créés via le constructeur Number, donc des instances de Number. Ces méthodes ne sont donc pas statiques. Pour bien comprendre, il nous faut nous intéresser rapidement au concept de prototype.  

            - En JavaScript, chaque objet a une propriété appelée prototype. Cette propriété est en fait un objet qui contient les propriétés héritées par chaque instance, par chaque objet de son type. Le prototype est en quelques sortes un modèle pour les instances, c’est-à-dire les objets d’un type. Donc, la propriété Number.prototype est un objet qui contient des propriétés, dont des méthodes accessibles à toutes les instances de Number, ainsi qu’à tous les objets Number.  

            - Il est possible d’afficher les propriétés principales de l’objet Number.prototype en utilisant la méthode Object.getOwnPropertyNames() :  

                ```JS
                console.log(Object.getOwnPropertyNames(Number.prototype));
                ```

                - Nous pouvons constater que la console affiche différentes propriétés (qui sont en l’occurrence des méthodes) de l’objet Number.prototype.  

            - Ces méthodes sont donc héritées par toutes les instances de Number. Nous pouvons donc accéder aux méthodes héritées du prototype en écrivant : nomDeLobjet.nomDeLaMethode(), JavaScript fait le reste.
        
        - ***Les méthodes to…()***  

            - Voyons deux exemples de méthodes :  

                - toExponential()  

                - toString()  

            - La méthode toExponential() permet de renvoyer une chaîne contenant le nombre stocké dans l’objet Number avec une notation exponentielle (avec une puissance). Nous pouvons passer en argument le nombre de chiffres décimaux (chiffres après la virgule). Par défaut, si nous ne passons pas d’arguments, la méthode considérera le nombre de chiffres décimaux nécessaires pour que le nombre soit représenté. Si nous spécifions un argument, nous pouvons nous attendre à ce que le résultat soit un nombre arrondi.  

                - Par exemple :  

                    ```JS
                    const nombre = new Number(13578);
                    console.log(nombre.toExponential()); //1.3578e+4
                    console.log(nombre.toExponential(2)); //1.36e+4
                    ```

                    - Dans le premier appel de la méthode, aucun argument n’est passé. La méthode utilise le nombre de chiffres décimaux nécessaires pour représenter le nombre avec la notation exponentielle (ici 4 : 3578). Dans le second appel, nous passons comme argument 2. Donc, le résultat contient deux chiffres décimaux : 36. Nous pouvons voir qu’il y a un arrondi, le résultat est donc moins précis.  

            - La méthode toString() permet quant-à-elle de renvoyer une chaîne de caractères contenant la valeur du nombre de l’objet Number.  

                - Prenons un exemple :  

                    ```JS
                    const nombre = new Number(13578);
                    let nombreChaine = nombre.toString();
                    console.log(nombreChaine); //13578
                    console.log(typeof nombreChaine); //string
                    ```

                    - Nous pouvons voir que le type de nombreChaine est bien string, c’est une chaîne de caractères.

        - ***La méthode ValueOf***  

            - Dans le dernier exemple, nous avons récupéré la valeur du nombre d’un objet Number en le convertissant en chaîne de caractères. Mais dans certains cas, nous voudrons récupérer la valeur de notre nombre avec le type primitif Number, et non sous la forme d’une chaîne de caractères.  

                - Prenons un exemple. Si nous faisons :     

                    ```JS
                    const nombre = new Number(13578);
                    let nombreRecup = nombre;
                    console.log(nombreRecup); //Number 13578
                    ```
                    
                    - Nous voyons que nombreRecup est une référence vers l’objet, et non vers la valeur de son nombre. nombreRecup est donc un objet, et non une valeur primitive de type Number. En fait, c’est la méthode valueOf() du prototype qui va nous permettre de récupérer la valeur du nombre, avec le type primitif Number.  

                        - Prenons un exemple :  

                            ```JS
                            const nombre = new Number(13578);
                            let nombreRecup = nombre.valueOf();
                            console.log(nombreRecup); //13578
                            console.log(typeof nombreRecup); //number
                            ```
                            
                            - Donc, avec la méthode valueOf(), nous pouvons récupérer la valeur primitive qui a été enveloppée  dans l’objet Number. La méthode valueOf() va être essentielle à utiliser dans les cas où nous voulons accéder au nombre stocké dans un objet Number.  

##  
## ***__Les objets JavaScript String et Array__***  

- ### ***Concepts string et array***  
  - #### ***Concepts string et array***  
    - ***Le concept string en JavaScript***  

        - En langage de programmation, le terme « string » (qui signifie « chaîne » en anglais) désigne une séquence de caractères. Les chaînes de caractères sont considérées comme un type de données primitif en programmation. En JavaScript, les chaînes de caractères peuvent être représentées soit sous forme de types de données primitifs, soit sous forme d'objets string.  

        - Toutes les valeurs littérales placées entre des guillemets simples ('), des guillemets doubles (") ou des backticks (`) sont considérées comme des chaînes de caractères primitives en JavaScript.  

        - La distinction entre les chaînes de caractères primitives et les objets string est la suivante : en JavaScript, les chaînes de caractères primitives sont des valeurs simples qui ne possèdent pas de méthodes ou de propriétés associées. En revanche, les objets string sont créés en utilisant le constructeur string (avec ou sans le mot-clé « new »), et ils possèdent des méthodes et des propriétés spécifiques. Comme nous l’avons dit, un objet string permet d’envelopper (« wrapper ») une valeur primitive string. Il permet d'utiliser des méthodes et des propriétés spécifiques des objets sur la valeur primitive enveloppée.  

        - Prenons un exemple pour mieux comprendre:  

            ```JS
            let str_primi = "mandarine" ;
            let str_obj = new String(str_primi) ;
            console.log (typeof str_primi) ;
            console.log (typeof str_obj) ;
            ```

            - L'affichage console sera :  

                - String  

                - Object  

            - Explications :  

                - La première ligne crée une variable str_primi contenant une chaîne de caractères primitive « mandarine ». La deuxième ligne crée une variable str_obj qui contient un objet string créé à partir de la variable str_primi.  

                - Les deux dernières lignes utilisent la fonction typeof pour afficher le type de chaque variable dans la console. La première ligne affichera « string », ce qui indique que la variable str_primi contient une chaîne de caractères primitive. La deuxième ligne affichera « object », ce qui indique que la variable str_obj contient un objet string.  

                - Ainsi, l'exemple montre que même si les deux variables contiennent la même chaîne de caractères, l'une est une chaîne de caractères primitive et l'autre est un objet string.  

    - ***Comment utiliser la propriété « length » pour obtenir la longueur d'une chaîne de caractères en JavaScript ?***  

        - Les objets string en JavaScript sont des objets qui possèdent des propriétés et des méthodes qui leur sont propres. Il est important de les connaître pour pouvoir les utiliser efficacement. L'une des propriétés principales d’un objet string est « length ». Cette propriété permet de déterminer la longueur de la chaîne primitive enveloppée en retournant le nombre exact de caractères qu'elle contient. Mais cette propriété est aussi accessible via le type primitif string. En effet, lorsque nous cherchons à accéder à une méthode sur une chaîne de caractères primitive, JavaScript crée un objet temporaire qui enveloppe cette chaîne, afin d’appeler cette méthode. C’est ce principe qui permet d’appeler des méthodes comme length sur des valeurs primitives string.  

        - Il existe deux façons courantes d'utiliser la propriété « length » sur une chaîne de caractères primitive. La première consiste à créer une variable qui contient la chaîne de caractères, par exemple :  

            ```JS
            let str = 'abcd';
            ```

            - Ensuite, pour obtenir la longueur de la chaîne, nous utilisons la propriété « length » de cette manière :  

                ```JS
                console.log(str.length);
                ```
        
        - La deuxième méthode consiste à créer une nouvelle chaîne de caractères directement dans l’argument du console.log, comme ceci :  

            ```JS
            console.log('efghi'.length);
            ```

            - Dans cette méthode, la nouvelle chaîne de caractères doit être placée entre guillemets simples.

        - Dans les deux cas, nous obtiendrons respectivement les valeurs quatre et cinq, qui correspondent à la longueur de la chaîne stockée dans la variable str et celle de la nouvelle chaîne créée directement dans l'argument du console.log.  

    - ***Méthodes les plus couramment utilisées pour manipuler les chaînes de caractères***  

        - Une chaîne de caractères en JavaScript possède plusieurs méthodes qui permettent de la manipuler de différentes manières. Il est important de connaître les méthodes les plus couramment utilisées, telles que CharAt(), indexOf(), lastIndexOf(), slice(), split(), etc. Ces méthodes peuvent être utiles pour ajouter ou extraire des éléments d'une chaîne.  

        - D’abord, nous allons voir comment échapper certains caractères. Si nous ne les échappons pas correctement, le navigateur peut confondre ces caractères et cela peut causer des erreurs.  

        - Il vous faut savoir comment les caractères sont positionnés à l'intérieur d'une chaîne de caractères, car cela peut affecter le fonctionnement de certaines méthodes. Nous aborderons cela plus en détail lorsque nous parlerons de la manipulation de l'objet string à l'aide de méthodes.  

        - L’échappement de certains caractères  

            - Des caractères sont reconnus comme une chaîne parce qu’ils sont placés entre des guillemets simples ou entre des guillemets doubles. Si une chaîne est entourée de guillemets simples, il peut y avoir une confusion lorsque nous insérons des apostrophes, par exemple. Pour l’éviter, il est nécessaire de placer le backslash avant cette apostrophe pour l’échapper.  

        - L’échappement de l’apostrophe, des doubles guillemets et des antislashs  

            ```JS
            let str = 'C\'est un exemple d\'utilisation de l\'échappement de caractères';
            ```

            - Dans cet exemple, nous avons échappé les apostrophes en les précédant d'un caractère backslash. Cela permet à JavaScript de reconnaître que ces caractères font partie de la chaîne de caractères, et non pas de la syntaxe du langage.

    - ***Comprendre le positionnement des caractères***  

         - Une chaîne de caractères est constituée de n caractères où n représente le nombre de caractères. Chaque caractère dans une chaîne de caractères (string) est associé à une position numérique appelée « index ». L'index du premier caractère dans la chaîne est généralement 0, l'index du deuxième caractère est 1, l'index du troisième caractère est 2, et ainsi de suite. Dans une chaîne de caractères composée de n caractères, le dernier caractère est situé à la position n-1. Par exemple, si la chaîne de caractères contient vingt caractères, alors le dernier caractère est situé à la position 19. En effet, les chaînes de caractères sont construites comme des tableaux composées de différents caractères, avec un index pour chaque caractère.  

            - Comprendre le positionnement des caractères  

                ```JS
                const str = "iuhzefpj";
                console.log(str[0]); //i
                console.log(str[3]); //z
                ```

                - En fin de compte, nous avons appris qu'une chaîne de caractères (string) est composée d'une séquence de caractères dont nous pouvons déterminer la longueur et la position individuelle. Il est important de veiller à bien échapper les caractères spéciaux afin d'éviter toute confusion pour le navigateur.  

    - ***Distinction entre chaînes primitives et objets string en JavaScript***  

        - Il est essentiel de distinguer les objets string des valeurs primitives string. Les valeurs littérales entre guillemets simples, doubles ou backticks sont des chaînes primitives. Cependant, les objets string permettent d’envelopper des valeurs primitives de type string dans un objet. Comme nous l’avons vu précédemment, lorsque nous utilisons une propriété comme length avec une valeur primitive string, JavaScript crée automatiquement un objet temporaire string qui enveloppe la valeur primitive pour donner accès à la propriété appelée. Mais nous pouvons aussi directement créer un objet string qui enveloppe une chaîne de caractères primitive afin d’accéder constamment aux propriétés et méthodes de string. Pour cela, il va falloir appeler le constructeur string.  

            - Chaînes primitives et d'objets string :  

                ```JS
                let str1 = "Chaîne de caractères primitive entre doubles quotes" 
                let str2 = 'Chaîne de caractères primitive entre simples quotes';
                let str3 = `Chaîne de caractères primitive entre backticks`;
                let str4 = new String("Chaîne de caractères"); //objet String
                ```  

                - Dans de nombreux cas, les valeurs primitives et les objets chaînes de caractères peuvent être utilisés de manière interchangeable. Les valeurs littérales pour les chaînes sont indiquées par des guillemets simples, doubles ou des backticks. Les backticks permettent de définir des littéraux de gabarits de chaînes pour interpoler des expressions à l'intérieur d'une chaîne.

    - ***Comprendre les tableaux en JavaScript***  

        - En JavaScript, les tableaux (array) sont une structure de données spéciale qui nous permet de stocker des collections ordonnées de valeurs. À la différence des chaînes, il n'existe pas de type primitif array. Les array sont des objets. Ils sont indispensables lorsque nous avons besoin de stocker une liste d'éléments, tels que des noms d'utilisateurs. Les tableaux nous permettent de conserver l'ordre des éléments et de les manipuler facilement.  

        - Pour créer un tableau en JavaScript, nous pouvons utiliser des crochets et nous séparons les éléments par des virgules. Par exemple, si nous voulons stocker une liste de noms d'utilisateurs, nous pouvons écrire :  

            - Les éléments d’un tableau :  

                ```JS
                let utilisateurs = ['John', 'Peter', 'Chris'] ;
                ```

                - Dans cet exemple, la variable utilisateurs contient un tableau avec trois éléments : « John », « Peter » et « Chris ». Nous pouvons accéder aux éléments du tableau en utilisant leur position dans le tableau, également appelée « index ». Par exemple, pour accéder au deuxième élément (qui est « Peter »), nous pouvons utiliser l'index 1 :  

                    ```JS
                    console.log(utilisateurs[1]); // affiche "Peter"
                    ```

        - Il est aussi possible d’appeler le constructeur array pour construire un tableau :  

            ```JS
            let utilisateurs = new Array('John', 'Peter', 'Chris');
            ```

            - Notre tableau est un objet qui contient plusieurs valeurs entre crochets séparées par des virgules. Les objets array peuvent être stockés via des variables. L’intérêt des array est que nous pouvons utiliser individuellement chacune de ces valeurs. Sans tableau, chaque valeur doit être attribuée à une variable, ce qui peut être fastidieux si nous en avons des centaines. De plus, nous pouvons utiliser une boucle pour parcourir plusieurs valeurs d’un tableau stockées dans une même variable.  

            - Les tableaux seront donc utiles lorsque nous stockerons plusieurs données ordonnées via un même objet.

    - ***Propriétés et méthodes utiles pour manipuler des tableaux en JavaScript***  

        - Il est important de connaître ces méthodes de array, car elles nous permettent d'ajouter, de supprimer, de trier et de manipuler les éléments du tableau de manière efficace.  

        - Parmi les méthodes les plus couramment utilisées, on peut citer concat(), join(), pop(), push(), shift(), unshift(), slice(), splice() et reverse(). Chacune de ces méthodes peut être utilisée pour résoudre des problèmes spécifiques en matière de manipulation de tableaux.  

        - Pour avoir une idée de la syntaxe, voici comment procéder :  

            ```JS
            let tableau = ['a', 'b', 'c'];
            let autreTableau = tableau.push('d', 'e');
            console.log(autreTableau);
            console.log(tableau);
            ```

            - Ce code crée un tableau appelé « tableau » contenant les valeurs 'a', 'b' et 'c'. Ensuite, il crée un autre tableau appelé « autreTableau » en utilisant la méthode push() qui ajoute les valeurs 'd' et 'e' à la fin du tableau « tableau ». La méthode push() renvoie également la nouvelle longueur du tableau, qui est stockée dans la variable autreTableau.  

            - Ensuite, le code utilise la fonction console.log pour afficher les deux tableaux dans la console du navigateur ou de l'éditeur de code. La première ligne de code affiche la nouvelle longueur du tableau « autreTableau » (qui est maintenant 5), tandis que la deuxième ligne affiche le tableau « tableau » mis à jour, qui contient maintenant les valeurs 'a', 'b', 'c', 'd' et 'e'.

- ### ***Manipulation des chaînes de caractères (strings) et des tableaux (arrays)***  

  - #### ***Manipulation des chaînes de caractères (strings) et des tableaux (arrays)***  

    - ***Manipulation des chaînes de caractères***  

        - Dans cette seconde partie, un accent particulier sera mis sur les manipulations des objets string et array. Pour cela, nous allons insister sur l’association variable et propriété ou méthode afin d’effectuer certaines actions avec nos données. Il est donc nécessaire d'en savoir davantage sur les propriétés et méthodes de deux types de données.  

        - Les objets string sont utilisés pour représenter et manipuler des chaînes de caractères, qui sont utiles pour stocker des données sous forme de texte. Plusieurs opérations courantes sont disponibles pour manipuler les chaînes de caractères, telles que vérifier la longueur avec length, concaténer avec les opérateurs + et +=, rechercher des sous-chaînes avec les méthodes includes() ou indexOf(), et extraire des sous-chaînes avec la méthode substring().  

        - Nous allons examiner deux méthodes : la méthode slice() et la méthode split() pour respectivement extraire une sous-chaîne ou découper une chaîne en sous-chaînes.  

            - Extraction d’une sous-chaîne d’une chaîne et découpage d’une chaîne en sous-chaînes  

                ```JS
                let historique = new String("(réf : 775533) commandé le 25/03/2020 10 sacs riz");
                console.log(historique.slice(7, 13));
                console.log(historique.split(""));
                ```

                - Nous stockons une chaîne dans un objet string. Puis, nous faisons un alert avec comme argument la méthode slice(7, 13) de notre objet historique. Il nous est renvoyé une sous-chaîne extraite entre les index 7 ( compris) et 13 (non compris), soit 775533. Quant à la méthode split(""), rien qu’avec les simples quotes, elle va découper notre chaîne de caractères en sous-chaînes et tout mettre dans un tableau de 49 caractères. Elle considère le caractère passé comme caractère séparateur.  

        - D’autres tests de manipulation de l’objet string  

            - Nous allons nous entraîner à concaténer et à manipuler un string avec les méthodes courantes telles que charAt() ou indexof().  

                ```JS
                let concat = 'Hello ' + ' World !';
                console.log(concat) ;
                let nom = "Paul";
                let age = 44;
                console.log('Je m\’appelle ' + nom + ', et j\’ai ' + age + ' ans.');
                ```
                
                - Dans ces deux exemples, nous avons utilisé l’opérateur « + » pour concaténer nos chaînes de caractères.  

        - Utilisons maintenant la méthode charAt() pour comprendre son fonctionnement. La méthode charAt() permet de renvoyer le caractère d’une chaîne pour l’index passé comme argument.

            ```JS
            let chaine = new String('Comment ça fonctionne ?');
            let index = 4;
            console.log(`Le caractère à l’index ${index} est ${chaine.charAt(index)}`);
            ```

            - Nous avons fait un console.log et entre parenthèses nous avons utilisé entre les backticks, une chaîne de caractères et l’interpolation pour insérer les variables. Nous écrivons le symbole dollar avec des accolades, ${} à l’intérieur desquels nous plaçons nos expressions. La première fois, nous avons simplement interpolé la variable index. Mais la deuxième fois, nous interpolons la valeur de retour de la méthode charAt() de l’objet chaîne puis nous passons la variable index comme argument. Au final, nous est renvoyée la phrase : le caractère à l’index 4 est e. La manipulation a réussi. Parlons maintenant de la méthode indexOf().  

                ```JS
                let chaine1 = 'Le renard brun et rapide saute par-dessus le chien endormi.';
                let chaine2 = 'chien';
                let chaine3 = chaine1.indexOf(chaine2) ;
                console.log(`l’index du ${chaine2} à partir du commencement est ${chaine3}`);
                ```

                - L’indexOf() nous aide à trouver la position d’une sous-chaîne dans une chaîne de caractères. Dans cet exemple, nous ne créons pas d’objet string, mais c’est JavaScript qui créera un objet string temporaire lors de l’appel de la méthode indexOf().

                - Notre première variable chaine1 contient une chaîne de caractères entre des guillemets. La deuxième variable chaine2 stocke une autre chaîne contenant « chien ». Quel est l’index du mot chien dans la première variable ? Nous avons créé une troisième variable chaine3 et l’avons défini sur la valeur de retour de chaine1.indexOf(chaine2). Pour terminer par un console.log, entre parenthèses nous avons mis le backticks du texte avec l’interpolation de chaine2 puis une autre interpolation avec chaine3. Voilà ce que cela a donné : l’index du ‘chien’ à partir du commencement est 45. La méthode indexOf() permet donc de connaître l’index d’une sous-chaîne dans une chaîne de caractères.

    - ***La manipulation d’un tableau par ses propriétés et méthodes***  

        - Pour connaître le nombre d'éléments d'un tableau, tout comme pour une chaîne de caractères, nous utilisons la propriété length. Cette propriété est de type entier et nous indique le nombre d'éléments présents dans un tableau.  

        - Les développeurs ont souvent recours aux boucles pour parcourir les éléments d'un tableau. Par exemple, la boucle for est très courante. Ainsi, si la propriété length nous aide à déterminer la taille d'un tableau, la boucle for est un outil plus pratique pour récupérer la liste de tous les éléments du tableau.  

        - L’exemple ci-dessus nous sert d’illustration :  (La propriété length est utilisée dans la boucle for)  

            ```JS
            let chiffre = ['un', 'deux', 'trois', 'quatre', 'quinze'];
            for (let element of chiffre) {
            console.log(element);
            }
            ```
            
            - Nous utilisons le mot clé « of » pour parcourir chaque valeur du tableau.  
        
        - L’ajout et la suppression d’un élément par les méthodes push() et pop()

             - Pour ajouter ou supprimer un élément, nous pouvons utiliser push() et pop(). Pour cela, nous allons créer un tableau et lui appliquer ces deux méthodes.  

                ```JS
                let monTableau = ['Paris', 'Marseille', 'Lyon', 'Bordeaux', 'Toulouse'];
                monTableau.push('Lille', 'Strasbourg');
                monTableau.pop();
                console.log (monTableau);
                ```  

                - Nous pouvons voir que push() permet d’ajouter des éléments tandis que pop() supprime le dernier élément.  

        - Utiliser les méthodes shift() et unshift()  

            ```JS
            let nombres = [1, 2, 3, 4];
            nombres.shift();
            console.log(nombres); //2,3,4
            nombres.unshift(0);
            console.log(nombres);//0,2,3,4
            ```

            - Le principe est assez simple, unshift() permet de rajouter un élément au début du tableau tandis que shift() supprime le premier élément du tableau.  

        - Autres manipulations possibles avec les méthodes split(), length, toString()  

            - Il existe de nombreuses autres méthodes pour manipuler les tableaux en JS. En voici quelques-unes :  

                ```JS
                // Crée une chaîne de caractères contenant les noms des villes séparées par des virgules
                let mesDonnees = 'Paris, Londres, Berlin, Rome, Madrid';

                // Utilise la méthode split() pour transformer la chaîne en un tableau en se basant sur le séparateur (la virgule suivie d'un espace)
                let monTableau = mesDonnees.split(', ');
                
                // Affiche la longueur du tableau (le nombre d'éléments)
                console.log(monTableau.length);
                
                // Affiche la chaîne de caractères initiale (mesDonnees)
                console.log(mesDonnees);
                
                // Affiche le tableau créé à partir de la chaîne de caractères (monTableau)
                console.log(monTableau);
                
                // Affiche le premier élément du tableau (l'index 0)
                console.log(monTableau[0]);
                
                // Affiche le dernier élément du tableau (l'index égal à la longueur du tableau moins 1)
                console.log(monTableau[monTableau.length - 1]);
                
                // Utilise la méthode join() pour fusionner les éléments du tableau en une nouvelle chaîne de caractères (myNewString)
                let myNewString = monTableau.join(', ');
                console.log(myNewString);
                
                // Crée un tableau contenant les noms des joueurs
                let nomsDesJoueurs = ["Neymar", "Kylian", "Cristiano", "Lionel"];
                
                // Utilise la méthode toString() pour convertir le tableau des noms des joueurs en une chaîne de caractères
                console.log(nomsDesJoueurs.toString());
                ```  
        
        - Tableau multidimensionnel  

            - Un tableau multidimensionnel est un tableau qui, comme son nom l’indique, a plusieurs dimensions, par exemple, l’axe des colonnes et l’axe des lignes. Créons un tableau multidimensionnel.  

                ```JS
                let voitures = [["Peugeot", "208"], ["Renault", "Clio"]];
                console.log(voitures[1][0]); //"Renault"
                ```  

                - Dans cet exemple, nous créons un tableau à deux dimensions. Les crochets imbriqués représentent des lignes. Nous avons dans cet exemple deux lignes et deux colonnes. Nous cherchons à accéder à l’index 1 de notre tableau, qui correspond à ["Renault", "Clio"]. Puis nous cherchons à récupérer l’index 0 de ["Renault", "Clio"], qui est donc la valeur « Renault ».
