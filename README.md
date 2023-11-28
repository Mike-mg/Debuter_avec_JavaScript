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

    - ***Essentiel***  

        - 