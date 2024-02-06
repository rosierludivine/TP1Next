# Semaine NextJS

NextJS est un framwork gratuit et open source qui s'appuie sur la bibliotheque ReactJS. Il a était développer par Vercel et mis à disposition en octobre en 2016.

Framwork est une regroupement de composant, qui a un rendu final un produit fonctionel pour la prod. 




### Les avantages : 
- permettre d'écrire facilement des applications universelles avec react 
- facile 
- efficace 
- Nous pouvons avoir base de données, ... gratuitement directement sur le site. 

### Les désavantages:
- 


##   Définition 

**Server-Side Rendering(SSR):**  Next.js permet le rendu côté serveur des pages web, ce qui améliore la performance et le SEO. 
Le rendu il est coter client car ces le javascript dans le navigateur ce qui permet de changer l'html. 

**Static Site Genration(SSG):** Possibilité de générer des sites statiques pour une vitesse de chargement rapide. 

Routing Automatique: Les fichiers  dans le dossier pages deviennent automatiquement automatiquement des routes. 

**Optimisation des Performances:** nEXT.JS inclut des fonctionnalités comme l'optimisation automatique des images 

Faciliteé de Déploiement: Intégration simple avec des plateformes comme Vercel pour un déploiement rapide.

## Installation de l'application 

```powershell 
#Installation de l'application , latest (la plus récente)
npx create-next-app@latest
#Entrer le nom de l'application 
#Entrer la configuration 
```

les dossier 
packages-lock.jsonn


tsconfig.json est le fichier de configuration de typescript. Typescript est la pour rendre plus robuste au moment du dev. 

global.css est un fichier qui change le css global. 

### Conseil 

SRC tout le code source 
Page.TSX contient le code react qui est afficher a l'ecran 

contrainte du jsx a la racine nous devons avoir avoir une balise unique a la racine 
 

# Résumer apres le TP 

Les hooks react ou meme next sont a utiliser coter clients !

 ### Qu'est ce que le routeur 

 Le systeme de routing de Next.JS est de basé sur le systeme de fichier. Le repertoire app est le point d'entree de l'application. Les fchiers dans ce repertoire sont accessibkles via l'url racine de l'application 

 -**Role des dossiers**: c'est de definir les routes de l'application. Une route est un enchainement de dossiers imbriqués. 
 - **Role des fichier** : c'est de definir le contenu de la page. 

![Alt text](image.png)


 Next fourni toute une liste de dossier et de fichier pour definir les rpute de l'application.

 Voici la liste des fichiers dont le nom est réservé pour definir les routes de l'application: 
 ![Alt text](image-1.png)

 Pour créer une router imbriqué, il suffit d'imbriquer des dossiers.Par exemple, pour créer une route /about, il suffit de créer un dossier about dans le dossier app et de creer le composant `route.tsx`dans ce dossier. 

 ## Routing: Pages & Layout 

### Pages 
 Une page c'est l'UI associé à une route. dans le code on la représente par un composant React exporté par un fichier appelé `route.tsx`

 ![Alt text](image-2.png)

 Par defaut toutes les pages sont des composants Server, il faut utiliser 'use client" pour les rendre des composants client; 

 ### layouts 

 Un layouts est une parti d'UI partagée entre plusieurs pages. Par exemple, un header, un footer, une sidebar, etc. Son but est de préservé la cohérence de l'UI entre les pages. On ne modifie pas le layout à chaque changement de page. 

 Comme les pages on êut imbriquer des layouts.Par exemple, un laoyt peut contenir un autre layout. 

  ![Alt text](image-3.png)

  Pour créer un layout, il suffit de créer un composant React exporté par un fichier appelé `layout.tsx`.
  Le root layout est obligatoire .Il doit forcement contenir les tags: 
  `html`et `body`.
  Il est possible de crée un layout pour chaque pages, mais il est aussi possible de créer un layout pour un groupes de pages. 

  #### Imbriquer des layouts 

   ![Alt text](image-4.png)

   #### Grouper des routes : 'Route Groups'

   A l'interieur du repertoire app on peut directement mapper l'imbrication des dosssiers sur les routes de l'application . Il est possible de creer des dossier speciaux (route group) qui seront ignores par le routing Next. 
   
   Le mettre entre parenthese permet de le comprimer exemple le (marketing) n'a pas besoin de mettre `marketing`dans l'URL (ignorer dans la construction de l'URL )

   ![Alt text](image-5.png)

   On peut ainsi creer un layout pour un groupe de pages. 
   
   ![Alt text](image-6.png)

   Ou encore plusieurs rot layout :

   ![Alt text](image-7.png)

   ### Route dynamique 

   Pour creer une route dynamique, il suffit de créer un dossier dont le nom est entre crocehts. Par exemple [id], cette information sera passée a la props  `params` des fonctions : page, roouter, layout et generateMetadata. 

   ![Alt text](image-9.png)

   Dans l'exemple ci-dessous, on peut recuperer la valeur de [slug] de cette maniere dans le composant `page.tsx`: 

   ```tsx
        export default function Page({params} : {params: {slug:string}}){
            return <h1>Page {params.slug}</h1>s
        }
   ```

   #### Le segment de route dynamique `catch-all`

   On peut aussi rendre dynalique le nombre de parametre au seins de'uune routz dynamique, pour cela il faut proceder le nom de la route dynamique par `...`
   ![Alt text](image-10.png)


   ## Routing: Navigation 

   Il existe 4 lethodes pour naviger entre les pages:

   - **Link** : composant 
   - **useRouteur** : hook 
   - **Redirect** : fonction
   - l'API History 

   ### Link 
   Link est  un composant fournit par Next qui est en réalité un wrapper autour de la balise html `<a>`. Il permet de naviguer entre les pages sans recharger la page. 

   ```tsx
   import Link from 'next/link'

   export default function Page(){
    return <Link href="/about">About</Link>
   }
   ```

   ### Le hook usePathname 

   Le hook usePathname permet de recuperer le pathname de la page courante. Il permet par exemple de mettre en subbrillance le lien de la page courante . Pour utiliser un hook au sein d'un composant Next il faut utiliser la la directive `use client`. 
   
   ![Alt text](image-8.png)

   ### Le hook useRouter 

   ce hook permet de changer par le code la rooute courante de l'application. Il permet aussi de recuperer les parametre de la rooute courante.

   


   
