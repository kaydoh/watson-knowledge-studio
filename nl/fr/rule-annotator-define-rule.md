---

copyright:
  years: 2015, 2018
lastupdated: "2018-04-04"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}
{:pre: .pre}
{:codeblock: .codeblock}
{:screen: .screen}
{:javascript: .ph data-hd-programlang='javascript'}
{:java: .ph data-hd-programlang='java'}
{:python: .ph data-hd-programlang='python'}
{:swift: .ph data-hd-programlang='swift'}

Cette documentation concerne {{site.data.keyword.knowledgestudiofull}} on {{site.data.keyword.cloud}}.
Pour consulter la documentation de la version précédente de {{site.data.keyword.knowledgestudioshort}} on {{site.data.keyword.IBM_notm}} Marketplace, [cliquez sur ce lien ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://console.bluemix.net/docs/services/knowledge-studio/rule-annotator-define-rule.html){: new_window}.
{: tip}

# Définir une règle
{: #wks_rule_creation}

Pour définir des règles, utilisez l'éditeur de règle.
{: shortdesc}

## A propos de cette tâche

Evitez que plusieurs utilisateurs n'éditent simultanément des règles, classes ou expressions régulières, sous peine d'écrasements ou duplications inattendus.


## Procédure

Pour définir une règle, effectuez les étapes suivantes : 

1. Connectez-vous en tant qu'administrateur ou chef de projet {{site.data.keyword.knowledgestudioshort}} et ouvrez la page **Règles**.

1. Cliquez sur le signe plus (+) à côté de Documents pour ajouter un document. 

    Pour les détails, consultez [Ajouter des documents pour définir des règles](/docs/services/watson-knowledge-studio/rule-annotator-add-doc.html). 

    Par exemple, vous pourriez ajouter un document nommé `Mon document`, contenant cette unique ligne de texte : 

    ```
    A 50-year-old driver was driving the 2017 Example Horizon.
    ```
    {: screen}

1. Si vous comptez définir une expression régulière ou ajouter un dictionnaire, créez une classe à lui associer. 

    1. Dans le panneau **Classe**, cliquez sur le signe plus (+) à côté de Classe. 
    1. Ajoutez un nom de classe. 

        S'il est prévu d'associer la classe à une expression régulière ou à un dictionnaire, nommez-la de façon à pouvoir facilement identifier son origine. Par exemple, si vous comptez utiliser une expression régulière pour définir un motif repérant le premier nombre dans la phrase ci-dessus, vous pouvez créer une classe nommée AGE_REGEX. Si vous prévoyez d'utiliser un dictionnaire pour annoter le constructeur automobile dans la phrase, vous pouvez ajouter une classe nommée MANUFACTURER_DICT (ou DICO_CONSTRUCTEUR). 

        Choisissez les noms en vous conformant à ces règles : 
        - Le premier caractère d'un nom de classe doit être une lettre.
        - Utilisez seulement les caractères ASCII alphanumériques suivants et le trait de soulignement (touche 8) dans les valeurs que vous ajoutez aux classes : A à Z, a à z, 0 à 9.
        - Les noms ne peuvent pas contenir d'espaces. 
        - Les noms ne peuvent pas comporter plus de 64 caractères.

1. Optionnel : pour accélérer l'annotation des classes dans le document, vous pouvez associer un dictionnaire à l'éditeur de règle. Tous les termes figurant dans le texte du document qui correspondent à des entrées du dictionnaire seront automatiquement annotés avec la classe appropriée. 

    1. Cliquez sur l'onglet **Dictionnaires** dans le panneau.

        Les dictionnaires que vous avez créés sont affichés.

        Si vous n'avez pas ajouté de dictionnaire, pour en ajouter un, ouvrez l'onglet **Dictionnaires** à partir de la barre de navigation principale. Pour plus d'informations, consultez [Créer des dictionnaires](/docs/services/watson-knowledge-studio/dictionaries.html).

    1. Cliquez sur un dictionnaire et définissez une association de classe pour lui, puis cliquez sur **Sauvegarder**.

        Par exemple, si vous avez un dictionnaire contenant des noms d'organismes ou de sociétés, vous pouvez l'associer à la règle et lui attribuer la classe DICO_ORGANISATIONS. Ainsi, tous les noms d'organisations apparaissant dans vos exemples de documents seront annotés comme instances de la classe DICO_ORGANISATIONS. 

    Plus tard, si vous voulez dissocier ce dictionnaire de l'éditeur de règles, il vous suffira de supprimer l'association de la classe, en choisissant l'entrée vide en haut de la liste déroulante. 

1. Optionnel : pour définir une expression régulière pour la construction de votre règle, cliquez sur **Expressions régulières** dans la barre de navigation.

    1. Cliquez sur le signe plus (+) à côté de Expression régulière pour ajouter une expression régulière. 
    1. Donnez un nom à l'expression régulière. Par exemple, RegExAge.

        Le nom ne peut pas comporter plus de 64 caractères.

    1. Associez l'expression à une classe. Par exemple, AGE_REGEX.
    1. Cliquez sur **Ajouter une entrée**.
    1. Ajoutez l'expression. 

        Par exemple, pour capturer un nombre représentant un âge (jusqu'à 99), vous pourriez spécifier `[0-9]{1,2}`. Pour capturer des expressions d'heure au format anglo-saxon telles que *12:30 AM*, vous pourriez spécifier l'expression régulière suivante : 

        ```
        (1[0-2]|0?[1-9]):([0-5][0-9])(\s+[AaPp][Mm])?
        ```
        {: screen}

        Au besoin, vous pouvez changer le nombre minimum et le nombre maximum d'unités lexicales (mots). Dans les langues telles que le français ou l'anglais, les unités lexicales sont souvent assimilées à des mots délimités par des espaces dans une phrase. La correspondance exacte entre unités lexicales et mots n'est cependant pas systématique. Il existe en effet des cas où d'autres éléments textuels ont valeur d'unités lexicales. Par exemple, les traits d'union dans le terme *sur-le-champ* comptent chacun pour une unité lexicale, si bien qu'il y a au total 5 unités lexicales dans ce terme. Le texte *12:30 PM* contient quant à lui 4 unités lexicales. (`12 | : | 30 | PM`)

        Cliquez sur **Ajouter**. 

    1. Répétez les deux étapes précédentes si vous voulez ajouter d'autres expressions.
    1. Cliquer sur **Sauvegarder**.

    L'éditeur d'expression régulière se ferme et le document apparaît. La classe que vous avez définie pour l'expression régulière doit normalement être appliquée au texte que l'expression est censée trouver. Si ce n'est pas le cas, contrôlez votre expression. Elle a peut-être besoin d'être corrigée afin de concorder avec le texte prévu. 

    ![L'éditeur de règle montrant l'onglet "Expression régulière" sélectionné, une expression régulière nommée "Age" qui est associée à la classe "AGE_REGEX", et un document dans lequel le texte "50" est surligné en jaune. Le texte surligné correspond à l'expression régulière qui a été créée.](images/rule_step3.jpg)

1. Pour définir une règle, cliquez sur **Règles** dans la barre de navigation.
1. Ouvrez le document contenant le motif que vous voulez capturer sous forme de règle. Par exemple, si vous avez créé un document intitulé `Mon document` avec l'échantillon de texte contenant le syntagme `50-year-old`, ouvrez ce document. 
1. Dans le texte du document, sélectionnez les caractères illustrant le motif que vous voulez capturer. Par exemple, vous pouvez sélectionner les mots et traits d'union suivants :

    ```
    50-year-old
    ```
    {: screen}

    Les caractères étant sélectionnés, vous pouvez ajouter une règle.

1. Cliquez sur le signe plus (+) dans le panneau **Règles**.

    L'éditeur de règle représente le texte sélectionné sur deux rangées de cellules. Les cellules de la rangée du haut sont celles où vous annotez les classes des unités lexicales sous-jacentes. La rangée du bas sert à définir les conditions dans lesquelles les unités lexicales participent au motif. 

    ![L'éditeur de règle montrant à quoi ressemble le panneau "Créer une règle" lorsque vous cliquez sur le signe plus dans le panneau "Règles" après avoir sélectionné le texte dans le document. Les éléments graphiques suivants sont représentés : le champ "Nom de la règle", dans lequel le terme "AGE" a été entré, le panneau "Créer une règle" et le panneau "Classe". Dans le panneau "Créer une règle", des cellules en pointillés sont disposées horizontalement dans la rangée du haut. Il y a une cellule par unité lexicale du texte qui a été sélectionné. C'est dans ces cellules que vous annotez les classes des unités lexicales. Toujours dans le panneau "Créer une règle", des cellules en traits pleins sont disposées horizontalement dans la rangée du bas. Chaque cellule contient une unité lexicale du texte sélectionné, "50-year-old". Les unités lexicales sont "50", "-" (trait d'union), "year", "-" et "old". Chaque cellule en traits pleins est surmontée de deux icônes que vous pouvez utiliser pour ajuster la condition du mot ou de l'annotation.](images/rule_step4.jpg)

1. Définissez dans quelles conditions chaque unité lexicale participe au motif. 

    Dans la rangée de cellules du bas, cliquez sur la première unité lexicale pour examiner ses conditions. Si vous voulez indiquer que n'importe quelle unité lexicale peut figurer à la position actuelle dans le motif, cliquez sur **Ouvrir les propriétés** et sélectionnez **Autoriser toute unité lexicale**. Cliquez sur **Fermer les propriétés**. Si à la place d'une unité lexicale figure une expression régulière, comme c'est le cas avec `AGE_REGEX` dans l'exemple ci-dessus, l'option **Autoriser toute unité lexicale** n'est pas disponible. 

    > **Remarque :** Le nombre de cellules de groupe pouvant participer au motif est limité à 15 lorsque chaque cellule a une valeur de répétition de 1 ou moins. On entend par cellules de groupe les unités lexicales seules, les annotations et les positions où toute unité lexicale est autorisée. Au total, 20 unités lexicales sont autorisées dans un motif. Lorsque vous définissez votre motif, pour être sûr de ne pas dépasser cette limite, tenez compte de la valeur de répétition de chaque cellule. Par exemple, vous pouvez définir un motif incluant 15 unités lexicales lorsque chaque cellule a une valeur de répétition de 1 ou moins. En revanche, vous ne pouvez pas inclure plus de 4 unités lexicales dans le motif si chacune est configurée avec une valeur de répétition de 1 ou plus, car elles peuvent alors se répéter jusqu'à 4 fois (cinq occurrences de chaque). Avec cinq occurrences possibles de quatre unités lexicales, vous atteignez la limite de 20 unités lexicales dans un même motif. 

    Pour indiquer qu'un type particulier d'unité lexicale est nécessaire, vous pouvez définir les conditions suivantes : 
    - **Paramètre de répétition **: permet d'indiquer combien de fois l'unité lexicale actuelle peut ou doit être incluse dans le motif. Plusieurs options sont proposées, mais pour chaque unité lexicale, une seule peut être sélectionnée. Les options sont décrites dans le tableau suivant.

    <table cellpadding="4" cellspacing="0" summary="" border="1" class="simpletable">
      <tr class="sthead">
        <th valign="bottom" align="left" id="d27028e471" class="stentry thleft thbot">Option</th>
        <th valign="bottom" align="left" id="d27028e473" class="stentry thleft thbot">Description</th>
      </tr>
      <tr class="strow">
        <td valign="top" headers="d27028e471" class="stentry">
          <p class="p wrapper">Obligatoire (exactement 1)</p>
        </td>
        <td valign="top" headers="d27028e473" class="stentry">
          <p class="p wrapper">Cette unité lexicale doit apparaître exactement une fois (pas plus, pas moins)
            dans le motif. C'est l'option appliquée par défaut, mais vous pouvez en changer.
</p></td>
      </tr>
      <tr class="strow">
        <td valign="top" headers="d27028e471" class="stentry">
          <p class="p wrapper">Se répète 1 ou plusieurs fois</p>
        </td>
        <td valign="top" headers="d27028e473" class="stentry">
          <p class="p wrapper">Cette unité lexicale doit apparaître au moins une
            fois dans le motif, et elle peut être répétée plusieurs fois. </p>
        </td>
      </tr>
      <tr class="strow">
        <td valign="top" headers="d27028e471" class="stentry">
          <p class="p wrapper">Se répète 0 ou plusieurs fois</p>
        </td>
        <td valign="top" headers="d27028e473" class="stentry">
          <p class="p wrapper">Cette unité lexicale peut être répétée plusieurs
            fois dans le motif, mais cela n'a rien d'obligatoire. </p>
        </td>
      </tr>
      <tr class="strow">
        <td valign="top" headers="d27028e471" class="stentry">
          <p class="p wrapper">Se produit 0 ou 1 fois</p>
        </td>
        <td valign="top" headers="d27028e473" class="stentry">
          <p class="p wrapper">Cette unité lexicale est optionnelle.</p>
        </td>
      </tr>
      <tr class="strow">
        <td valign="top" headers="d27028e471" class="stentry">
          <p class="p wrapper">Avancé : _personnalisé_</p>
        </td>
        <td valign="top" headers="d27028e473" class="stentry">
          <p class="p wrapper">Cette unité lexicale doit se répéter dans le motif
            le nombre de fois spécifié ici. Pour définir
            une expression de répétition personnalisée, cliquez sur
             <b>Ouvrir les propriétés</b>,
            sélectionnez **Avancé**, puis indiquez le nombre exact de répétitions ou l'intervalle souhaité.</p>
          <p class="note">
Une unité lexicale peut être répétée jusqu'à cinq fois.</p>
        </td>
      </tr>
    </table>

    - **Paramètre de fonction** : au moins une des caractéristiques doit être définie. Vous pouvez en ajouter plus pour compléter les conditions à remplir par le texte pour qu'il corresponde au motif. Les options sont décrites dans le tableau suivant.

    <table cellpadding="4" cellspacing="0" summary="" border="1" class="simpletable">
      <tr class="sthead">
        <th valign="bottom" align="left" id="d27028e512" class="stentry thleft thbot">Option</th>
        <th valign="bottom" align="left" id="d27028e514" class="stentry thleft thbot">Condition ajoutée</th>
      </tr>
      <tr class="strow">
        <td valign="top" headers="d27028e512" class="stentry">
          <p class="p wrapper">Texte</p>
        </td>
        <td valign="top" headers="d27028e514" class="stentry">
          <p class="p wrapper">La condition à remplir est que le texte corresponde exactement à celui de cette
            unité lexicale. C'est l'option appliquée par défaut. Vous pouvez
            l'ôter, mais seulement si vous ajoutez une autre option de condition à la place
            ou si vous appliquez le réglage Toute unité lexicale. </p>
        </td>
      </tr>
      <tr class="strow">
        <td valign="top" headers="d27028e512" class="stentry">
          <p class="p wrapper">Longueur</p>
        </td>
        <td valign="top" headers="d27028e514" class="stentry">
          <p class="p wrapper">La condition à remplir est que le texte soit de la même longueur (même nombre de caractères) que le texte de cette
            unité lexicale. La longueur est comptée en commençant à 0 une position
            avant le premier caractère. </p>
        </td>
      </tr>
    </table>

    Le reste des options diffère selon le type d'unité lexicale.

    - **Unité lexicale non annotée qui ne correspond ni à une expression régulière, ni à un terme du dictionnaire **: Les options suivantes sont disponibles pour ces unités lexicales. 

    <table cellpadding="4" cellspacing="0" summary="" border="1" class="simpletable">
      <tr class="sthead">
        <th valign="bottom" align="left" id="d27028e535" class="stentry thleft thbot">Option</th>
        <th valign="bottom" align="left" id="d27028e537" class="stentry thleft thbot">Description</th>
      </tr>
      <tr class="strow">
        <td valign="top" headers="d27028e535" class="stentry">
          <p class="p wrapper">Partie du discours</p>
        </td>
        <td valign="top" headers="d27028e537" class="stentry">
          <p class="p wrapper">La condition à remplir est que le texte soit de la même partie du discours
            que celui de cette unité lexicale. Les types suivants sont disponibles :</p>
          <ul class="ul bullets">
            <li class="li">
              <p class="p wrapper">adjectif</p>
            </li>
            <li class="li">
              <p class="p wrapper">apposition</p>
            </li>
            <li class="li">
              <p class="p wrapper">adverbe</p>
            </li>
            <li class="li">
              <p class="p wrapper">conjonction</p>
            </li>
            <li class="li">
              <p class="p wrapper">déterminant</p>
            </li>
            <li class="li">
              <p class="p wrapper">interjection</p>
            </li>
            <li class="li">
              <p class="p wrapper">nom</p>
            </li>
            <li class="li">
              <p class="p wrapper">chiffre (numéral)</p>
            </li>
            <li class="li">
              <p class="p wrapper">pronom</p>
            </li>
            <li class="li">
              <p class="p wrapper">résiduel</p>
            </li>
            <li class="li">
              <p class="p wrapper">verbe
</p>
            </li>
          </ul>
        </td>
      </tr>
      <tr class="strow">
        <td valign="top" headers="d27028e535" class="stentry">
          <p class="p wrapper">Lemme</p>
        </td>
        <td valign="top" headers="d27028e537" class="stentry">
          <p class="p wrapper">La condition à remplir est que le texte ait le même lemme
que celui de cette unité lexicale.
</p>
        </td>
      </tr>
      <tr class="strow">
        <td valign="top" headers="d27028e535" class="stentry">
          <p class="p wrapper">Type de caractère</p>
        </td>
        <td valign="top" headers="d27028e537" class="stentry">
          <p class="p wrapper">La condition à remplir est que le texte soit du même type de caractère
que celui de cette unité lexicale.
Les types suivants sont disponibles :</p>
          <ul class="ul bullets">
            <li class="li">
              <p class="p wrapper">Arabic : contient une séquence de caractères arabes.
</p>
            </li>
            <li class="li">
              <p class="p wrapper">ChineseNumeral : contient seulement les nombres chinois.</p>
            </li>
            <li class="li">
              <p class="p wrapper">ClauseEndingPunctuation : caractères de ponctuation séparant une clause ou une phrase
de la suivante</p>
            </li>
            <li class="li">
              <p class="p wrapper">Han : contient les caractères Han</p>
            </li>
            <li class="li">
              <p class="p wrapper">Hangul : contient les caractères syllabiques hangul du coréen</p>
            </li>
            <li class="li">
              <p class="p wrapper">Hebrew : contient une séquence de caractères hébreux.
</p>
            </li>
            <li class="li">
              <p class="p wrapper">Hiragana : contient les caractères syllabiques hiragana du japonais.</p>
            </li>
            <li class="li">
              <p class="p wrapper">Ideographic : contient un idéogramme, ou symbole représentant une idée ou une chose.</p>
            </li>
            <li class="li">
              <p class="p wrapper">Katakana : contient les caractères syllabiques katakana du japonais.</p>
            </li>
            <li class="li">
              <p class="p wrapper">Lowercase : contient seulement les caractères alphabétiques minuscules.</p>
            </li>
            <li class="li">
              <p class="p wrapper">Numeric : contient seulement les caractères numériques.</p>
            </li>
            <li class="li">
              <p class="p wrapper">Punctuation : un ou plusieurs caractères servant de ponctuation dans le texte.</p>
            </li>
            <li class="li">
              <p class="p wrapper">Syllabic : contient les caractères syllabiques.</p>
            </li>
            <li class="li">
              <p class="p wrapper">Thai : contient les caractères de l'alphabet thaï.</p>
            </li>
            <li class="li">
              <p class="p wrapper">Titlecase : commence par un caractère alphabétique majuscule suivi d'un ou de plusieurs caractères alphabétiques minuscules.</p>
            </li>
            <li class="li">
              <p class="p wrapper">Uppercase : unité lexicale contenant seulement des caractères alphabétiques majuscules.</p>
            </li>
          </ul>
        </td>
      </tr>
    </table>

    - **Correspondance de règle :**

    <table cellpadding="4" cellspacing="0" summary="" border="1" class="simpletable">
      <tr class="sthead">
        <th valign="bottom" align="left" id="d27028e617" class="stentry thleft thbot">Option</th>
        <th valign="bottom" align="left" id="d27028e619" class="stentry thleft thbot">Description</th>
      </tr>
      <tr class="strow">
        <td valign="top" headers="d27028e617" class="stentry">
          <p class="p wrapper">Correspondance de règle</p>
        </td>
        <td valign="top" headers="d27028e619" class="stentry">
          <p class="p wrapper">La condition à remplir est que le texte corresponde à la classe désignée.
Souvenez-vous, une classe peut être dérivée d'une expression régulière, d'un dictionnaire ou
d'une règle.
Si la classe spécifiée ici a été dérivée d'une expression régulière,
par exemple, alors cette unité lexicale doit correspondre au motif de recherche
de l'expression.
</p>
        </td>
      </tr>
    </table>

1. Pour les unités lexicales dont les annotations ont été ajoutées indirectement par une annotation de dictionnaire ou une correspondance d'expression régulière, vous pouvez choisir si le motif doit imposer la présence de n'importe quel mot ayant le même type d'annotation ou s'il doit exiger la présence des mots sous-jacents qui ont été annotés. 

    Dans la rangée de cellules du bas, les cellules incluses dans le motif sont reliées les unes aux autres par une trait horizontal. Il y a une scission aux endroits où une annotation a été appliquée. La cellule contenant le mot d'origine est surmontée d'une cellule dans laquelle figure l'étiquette d'annotation. Vous pouvez cliquer sur l'une ou l'autre des cellules superposées pour changer le trajet du trait et donc agir sur les cellules incluses dans le motif. 

    Par exemple, vous pourriez choisir d'inclure le texte fixe 50 dans le motif au lieu de lui faire utiliser l'expression régulière AGE_REGEX. 

    ![Le panneau "Créer une règle" montrant une édition de l'unité lexicale "50", qui utilise l'annotation "AGE_REGEX" dans la règle. Par défaut, c'est l'annotation "AGE_REGEX" qui est utilisée, mais vous pouvez éditer le motif afin que le mot sous-jacent "50" soit utilisé à la place.](images/rule_step5.jpg)

1. Après avoir défini l'ordre des éléments du motif, vous pouvez annoter les unités lexicales dans le texte.

    Dans la rangée du haut, cliquez sur les cellules qui représentent les unités lexicales à annoter, puis appliquez-leur une étiquette de classe. Pour sélectionner plusieurs cellules à la fois, cliquez sur l'une d'elles, appuyez sur la touche **Majuscule** et, sans la relâcher, cliquez tour à tour sur chaque autre cellule à inclure dans la sélection. 

    Affectez une classe à votre sélection de cellule(s). Si la classe voulue n'existe pas encore, vous pouvez l'ajouter. Tapez simplement le nom de classe souhaité dans le champ **Affecter une classe** et appuyez sur **Entrée**.

    > **Remarque :** Il n'est pas possible d'ajouter plus de 10 classes pour une même règle.

    ![La section "Créer une règle" montrant la fenêtre "Affecter une classe" qui s'ouvre lorsque vous cliquez sur une unité lexicale. Cette fenêtre contient un champ dans lequel vous pouvez entrer le nom d'une nouvelle classe ou sélectionner une classe existante dans la liste associée.](images/rule_step6.jpg)

1. Donnez un nom à la règle. 

    Un nom de règle ne peut pas comporter plus de 64 caractères.

1. Pour sauvegarder la règle, cliquez sur **Sauvegarder** dans le panneau Règles.

