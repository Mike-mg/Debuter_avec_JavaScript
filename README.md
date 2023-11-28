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

