# Guide de biologie pour l'enseignant

> **Pour qui ?** Pour toi, qui connais l'IA et la data science, mais pas le vocabulaire biologique.
> Ce guide décode **uniquement** les mots dont tu as besoin pour animer ce module — rien de plus.
> Il n'est pas destiné aux étudiants : eux connaissent déjà cette partie.

**Comment l'utiliser :** lis la section 1 une fois (10 minutes, elle débloque tout le reste), garde la
section 7 (les pièges) sous les yeux avant chaque séance, et consulte la section du jour juste avant
d'entrer en salle.

---

## Sommaire

1. [La biologie en 10 minutes](#1-la-biologie-en-10-minutes)
2. [Ordres de grandeur](#2-ordres-de-grandeur)
3. [Les 20 acides aminés](#3-les-20-acides-aminés)
4. [Vocabulaire séance par séance](#4-vocabulaire-séance-par-séance)
5. [Les notations qui déroutent](#5-les-notations-qui-déroutent)
6. [Les bases de données citées](#6-les-bases-de-données-citées)
7. [Les 12 pièges à éviter](#7-les-12-pièges-à-éviter)
8. [Questions d'étudiants, réponses prêtes](#8-questions-détudiants-réponses-prêtes)
9. [Index alphabétique](#9-index-alphabétique)

---

## 1. La biologie en 10 minutes

### Le dogme central, version informaticien

Toute la biologie moléculaire de ce module tient dans une seule chaîne :

```
ADN  ──transcription──►  ARN messager  ──traduction──►  Protéine
```

L'analogie qui marche vraiment :

| Biologie | Équivalent informatique |
|---|---|
| **ADN** | le **code source**, archivé, **identique dans toutes tes cellules** |
| **Gène** | une **fonction** dans ce code source |
| **ARN messager (ARNm)** | une **copie de travail** de cette fonction, produite à la demande |
| **Protéine** | le **programme qui s'exécute** et fait réellement le travail |
| **Expression génique** | **quelles fonctions sont appelées, et combien de fois** |
| **Génome** | le dépôt complet |
| **Transcriptome** | le **log des appels** à un instant donné ← *c'est ça, le RNA-seq* |
| **Protéome** | l'ensemble des processus réellement actifs |
| **Mutation** | une **faute de frappe** dans le code source |

**La conséquence qui compte pour le module :** un neurone et un globule blanc ont **exactement le même
ADN**. Ce qui les différencie, c'est **quels gènes sont exprimés**, et à quel niveau. C'est précisément
ce que mesure la séance 2 — et c'est pour ça qu'on peut retrouver les types cellulaires par clustering.

### Les quatre objets que tu manipules dans le module

| Objet | Ce que c'est | Séance |
|---|---|:---:|
| Une **molécule** (petite) | un composé chimique de quelques dizaines d'atomes : médicament, polluant, pesticide | 1 |
| Un **transcriptome** | le comptage de chaque ARNm dans une cellule | 2 |
| Une **séquence protéique** | une chaîne de lettres parmi 20 (les acides aminés) | 3, 5 |
| Une **image de cellules** | une matrice de pixels, typiquement un marquage fluorescent | 4 |

### La cellule en 6 mots

| Terme | Ce que c'est | Pourquoi ça compte ici |
|---|---|---|
| **Membrane plasmique** | l'enveloppe qui sépare la cellule de l'extérieur | une protéine « membranaire » y est plantée (séance 3) |
| **Cytoplasme** | le liquide intérieur, où tout flotte | les protéines y sont fabriquées |
| **Noyau** | le coffre-fort qui contient l'ADN | les protéines « nucléaires » y vont (séance 3) ; c'est lui qu'on voit en microscopie (séance 4) |
| **Mitochondrie** | la centrale énergétique, avec son **propre petit ADN** | le % d'ARN mitochondrial sert d'indicateur de cellule mourante (séance 2) |
| **Réticulum endoplasmique + Golgi** | la chaîne de montage et d'expédition | les protéines **sécrétées** y transitent (séance 3) |
| **Protéine sécrétée** | protéine expédiée **hors** de la cellule | hormones, anticorps, enzymes industrielles (séance 3) |

---

## 2. Ordres de grandeur

Utile pour répondre « c'est grand comment ? » sans hésiter.

| Objet | Taille | Repère |
|---|---|---|
| Atome | 0,1 nm = **1 ångström (Å)** | l'unité des structures 3D (séance 5) |
| Molécule de médicament | ~1 nm | ~300 g/mol, ~20 atomes lourds |
| Protéine moyenne | 3 à 10 nm | 300 à 500 acides aminés |
| Ribosome | ~25 nm | la machine qui fabrique les protéines |
| Mitochondrie | ~1 µm | |
| **Noyau cellulaire** | **5 à 10 µm** | ce que tu segmentes en séance 4 |
| Cellule humaine | 10 à 30 µm | |
| Globule rouge | 7 µm | séance 4, bonus paludisme |

| Quantité | Nombre | Repère |
|---|---|---|
| Gènes humains codant des protéines | ~20 000 | moins qu'attendu avant 2003 |
| Gènes mesurés en RNA-seq | ~33 000 | on compte aussi les non-codants |
| Gènes exprimés dans **une** cellule | ~2 000 à 10 000 | d'où 95 % de zéros dans la matrice |
| Acides aminés différents | **20** | l'alphabet de la séance 3 |
| Protéines dans Swiss-Prot (vérifiées) | ~570 000 | |
| Structures prédites dans AlphaFold DB | > 200 millions | |

---

## 3. Les 20 acides aminés

C'est l'alphabet des séances 3 et 5. Tu n'as pas à les retenir, mais **comprendre les 5 familles**
suffit à expliquer 90 % des résultats du module.

| Famille | Lettres | Propriété | Conséquence que tu peux expliquer |
|---|---|---|---|
| **Hydrophobes** | `A V L I M` | fuient l'eau | s'enfouissent au **cœur** de la protéine ; forment les segments **transmembranaires** |
| **Aromatiques** | `F W Y` | gros cycles plats | cœur hydrophobe aussi ; `W` et `Y` sont de bons marqueurs structuraux |
| **Polaires** | `S T N Q C` | aiment l'eau | plutôt en **surface** ; `C` forme des **ponts disulfures** (agrafes) |
| **Chargés +** | `K R H` | positifs | se lient à l'**ADN** (négatif) → fréquents dans les protéines **nucléaires** |
| **Chargés −** | `D E` | négatifs | surface, sites actifs |
| **Les deux cas à part** | `G P` | `G` très flexible, `P` rigide | une **proline** au mauvais endroit **casse** une hélice ou un feuillet |

**Les trois phrases à retenir pour la séance 5 :**

- Mettre un acide aminé **chargé** (`D E K R`) dans le **cœur hydrophobe** → très déstabilisant.
- Mettre une **proline** (`P`) au milieu d'une hélice ou d'un feuillet → casse la structure.
- Changer un acide aminé **en surface** → souvent sans effet… *sauf exception, et la drépanocytose
  est justement cette exception* (voir § 7, piège 11).

---

## 4. Vocabulaire séance par séance

### Séance 1 — Toxicité des molécules

| Terme | Traduction |
|---|---|
| **Tox21** | programme public américain (NIH, EPA, FDA) qui a testé ~8 000 molécules sur 12 tests cellulaires |
| **Essai (assay)** | un test en laboratoire ; ici automatisé sur des cellules en plaque |
| **Criblage à haut débit** | des robots testent des milliers de molécules par jour |
| **Récepteur** | une protéine qui « reçoit » une molécule et déclenche une réaction. Pense à un **callback** : un ligand arrive, un programme se déclenche |
| **Ligand** | la molécule qui vient se fixer sur le récepteur |
| **AhR** (*aryl hydrocarbon receptor*) | le récepteur étudié : un **facteur de transcription activé par un ligand**. Il capte des composés de l'environnement (polluants **plats et aromatiques**), puis entre dans le **noyau** et y allume des gènes. Son activation est un **signal d'alerte toxicologique** |
| **Facteur de transcription** | une protéine qui **allume ou éteint des gènes**. AhR en est un |
| **Dioxine (TCDD)** | polluant très toxique, le ligand de référence d'AhR |
| **HAP** | hydrocarbures aromatiques polycycliques : fumée, goudron, barbecue. Cancérogènes |
| **CYP1A1** | une enzyme produite quand AhR est activé → c'est le signal qu'on mesure |
| **Cancérogénèse** | le processus qui mène au cancer |
| **in vitro** | « dans le verre » : sur des cellules, en boîte |
| **in vivo** | sur un animal ou un humain entier |
| **in silico** | sur ordinateur ← **c'est ce que fait tout ce module** |
| **Règle des 3R** | Remplacer, Réduire, Raffiner l'expérimentation animale. **L'argument éthique qui justifie le module** |
| **SMILES** | notation **texte** d'une molécule : `CCO` = éthanol. C'est de la chimie, pas de la biologie |
| **logP** | **lipophilie** : tendance à préférer les graisses à l'eau. Élevé = traverse les membranes, s'accumule dans les tissus gras |
| **TPSA** | surface polaire : liée à l'absorption par l'organisme |
| **Lipinski (règle des 5)** | critères empiriques d'un bon médicament **avalable** |
| **QSAR** | relation structure–activité : prédire l'effet d'une molécule depuis sa structure. **Le nom du jeu de la séance 1** |

> **L'intuition biologique à transmettre :** AhR a une poche de liaison **plate**. Les molécules
> **planes, aromatiques, peu « 3D »** y rentrent. C'est exactement ce que le Random Forest redécouvre
> seul : `cycles_aromatiques` ↑ et `fraction_sp3` ↓ (peu de carbones « 3D ») chez les molécules actives.

---

### Séance 2 — Transcriptomique

| Terme | Traduction |
|---|---|
| **RNA-seq** | technique qui **compte les ARN messagers** → mesure l'activité des gènes |
| **Bulk RNA-seq** | un échantillon = **un tissu entier** → une moyenne sur des millions de cellules |
| **Single-cell RNA-seq** | un échantillon = **une cellule** ← notre cas |
| **PBMC** | *Peripheral Blood Mononuclear Cells* : les cellules immunitaires du sang |
| **Matrice de comptages** | lignes = cellules, colonnes = gènes, valeur = nombre d'ARN détectés |
| **UMI** | étiquette moléculaire qui évite de compter deux fois le même ARN |
| **Dropout** | un gène réellement exprimé mais **non détecté** → une des causes des 95 % de zéros |
| **Normalisation** | ramener toutes les cellules à une profondeur comparable (sinon on compare des torchons et des serviettes) |
| **Gène marqueur** | gène exprimé **spécifiquement** par un type cellulaire → sert à l'identifier |
| **Biomarqueur** | marqueur mesurable d'un état biologique (maladie, réponse à un traitement) |
| **Nomenclature CD** | `CD3`, `CD14`, `CD20`… : un catalogue standard de marqueurs de surface des cellules immunitaires. **`CD` = cluster of differentiation**, pas une abréviation à deviner |
| **Effet de lot (*batch effect*)** | biais technique entre manips → peut créer de faux clusters |

**Les types cellulaires du sang, et leur marqueur :**

| Type | Rôle en une phrase | Marqueur |
|---|---|---|
| Lymphocyte **T CD4** | chef d'orchestre de la réponse immunitaire | `IL7R`, `CD3E` |
| Lymphocyte **T CD8** | tueur de cellules infectées | `CD8A`, `CCL5` |
| Lymphocyte **B** | fabrique les **anticorps** | `MS4A1`, `CD79A` |
| Cellule **NK** | tueur « naturel », sans apprentissage préalable | `GNLY`, `NKG7` |
| **Monocyte** | éboueur : avale les débris et les microbes | `CD14`, `LYZ` |
| Cellule **dendritique** | présente les antigènes aux lymphocytes | `FCER1A` |
| **Plaquette** | bouche les plaies ← **pas une vraie cellule, un fragment sans noyau** | `PPBP`, `PF4` |

> **Le point pédagogique de la séance :** c'est le petit groupe de **plaquettes** que l'algorithme isole.
> En bulk RNA-seq, leur signal serait **noyé** dans la moyenne. C'est tout l'intérêt du single-cell.

---

### Séance 3 — Séquences protéiques

| Terme | Traduction |
|---|---|
| **Séquence primaire** | la chaîne de lettres, c'est tout |
| **Localisation subcellulaire** | **où** la protéine va travailler dans la cellule ← ce qu'on prédit |
| **Adressage** | le mécanisme qui envoie la protéine au bon endroit |
| **Peptide signal** | une « étiquette d'expédition » de 15–30 acides aminés **au début** de la séquence, avec un cœur **hydrophobe**. Dit : « cette protéine part à l'extérieur ». **Coupée** après livraison |
| **Peptide de transit** | même idée, mais destination **mitochondrie**. Riche en `R` et `K`, pauvre en `D` et `E` |
| **NLS** | *Nuclear Localization Signal* : petit motif **basique** (`K`/`R`) qui envoie au **noyau**. Peut être **n'importe où** dans la séquence |
| **Hélice transmembranaire** | segment d'environ 20 acides aminés **hydrophobes** qui traverse la membrane |
| **Hydrophobicité** | « fuit l'eau ». L'échelle de **Kyte-Doolittle** la chiffre acide aminé par acide aminé |
| **Homologue** | deux protéines de **même ancêtre évolutif** → séquences ressemblantes |
| **Famille de protéines** | groupe d'homologues partageant structure et fonction |
| **FASTA** | format texte : une ligne `>` d'en-tête, puis la séquence |
| **Swiss-Prot** | la partie d'UniProt **vérifiée à la main** par des experts (~570 000 entrées) |
| **TrEMBL** | la partie annotée **automatiquement** (> 200 millions). Moins fiable |

> **Pourquoi ESM-2 gagne, en une phrase que tu peux dire telle quelle :** la composition en acides
> aminés fait une **moyenne sur toute la protéine** et dilue le peptide signal, qui ne fait que 20
> lettres au début. ESM-2 lit la séquence **dans l'ordre et en contexte** : il voit le signal là où il
> est. D'où 63 % → 84 % d'exactitude.
>
> **Le piège d'évaluation à mentionner :** des protéines **homologues** réparties entre apprentissage
> et test permettent au modèle de reconnaître la *famille* au lieu d'apprendre le *signal*. Nos scores
> sont donc optimistes. Les études sérieuses regroupent d'abord les séquences par similarité.

---

### Séance 4 — Imagerie cellulaire

| Terme | Traduction |
|---|---|
| **Microscopie à fluorescence** | on fixe une molécule fluorescente sur une cible, on l'éclaire, elle réémet de la lumière |
| **Fluorophore** | la molécule qui brille |
| **DAPI / Hoechst** | deux fluorophores qui se fixent sur l'**ADN** → ils marquent les **noyaux**. C'est ce que tu vois sur l'image du notebook |
| **Canal** | une image par fluorophore (noyaux en bleu, membrane en vert…) |
| **Champ** | une zone photographiée. Une lame en contient des dizaines |
| **Mitose** | la **division cellulaire**. L'ADN se **condense** → le noyau devient **petit et très lumineux**. ← ce que l'Isolation Forest détecte comme anomalie |
| **Apoptose** | mort cellulaire programmée (propre, contrôlée). Noyau fragmenté |
| **Nécrose** | mort accidentelle (sale, la cellule éclate) |
| **Morphologie** | la forme : surface, allongement, régularité du contour |
| **Ploïdie** | nombre de copies de chromosomes. Anormale dans beaucoup de cancers → noyaux plus gros |
| **Criblage à haut contenu** | des robots qui acquièrent des dizaines de milliers d'images pour tester des molécules |
| **Anatomopathologie** | l'analyse de tissus au microscope pour diagnostiquer (ex. cancer) |
| **Frottis sanguin** | une goutte de sang étalée en couche fine sur une lame |
| **Paludisme / *Plasmodium*** | maladie parasitaire transmise par le moustique. Le parasite **entre dans les globules rouges** → visible comme une tache sombre (bonus du notebook) |
| **Giemsa** | la coloration classique des frottis sanguins (le violet des images du bonus) |

> **L'argument qui justifie la séance :** compter des cellules à la main est **lent et subjectif** —
> deux opérateurs ne trouvent pas le même nombre. L'IA n'est pas « plus intelligente », elle est
> **reproductible**. C'est ça, la vraie valeur ajoutée.

---

### Séance 5 — Structure 3D et mutations

| Terme | Traduction |
|---|---|
| **Repliement (*folding*)** | la chaîne linéaire se replie **spontanément** en une forme 3D précise |
| **Structure primaire** | la séquence |
| **Structure secondaire** | les motifs locaux : **hélice α** (ressort) et **feuillet β** (ruban plissé) |
| **Structure tertiaire** | la forme 3D complète d'**une** chaîne |
| **Structure quaternaire** | l'assemblage de **plusieurs** chaînes (l'hémoglobine = 4 chaînes) |
| **Cœur hydrophobe** | l'intérieur de la protéine, où se cachent les acides aminés qui fuient l'eau. **C'est lui qui tient la structure** |
| **Anfinsen** | a montré (Nobel 1972) que **la séquence suffit** à déterminer le repliement |
| **Paradoxe de Levinthal** | il y a tellement de conformations possibles qu'un essai exhaustif prendrait plus que l'âge de l'univers — pourtant la protéine se replie en millisecondes |
| **Cristallographie aux rayons X** | méthode **expérimentale** de référence. Plusieurs mois de travail |
| **Cryo-EM** | microscopie électronique à très basse température. L'autre méthode moderne |
| **RMN** | résonance magnétique nucléaire, pour les petites protéines en solution |
| **Ångström (Å)** | 0,1 nm. L'unité des distances atomiques |
| **RMSD** | écart moyen entre deux structures superposées. **< 2 Å = quasi identiques** |
| **MSA** | alignement de milliers de séquences **homologues**. **La matière première d'AlphaFold** |
| **Coévolution** | si deux acides aminés sont **en contact** en 3D, une mutation de l'un est souvent compensée par l'autre au fil de l'évolution. **C'est le signal que lit AlphaFold pour deviner les contacts** |
| **pLDDT** | auto-évaluation de confiance d'AlphaFold, **par résidu**, de 0 à 100 |
| **PAE** | erreur attendue sur la **position relative** de deux résidus |
| **Résidu** | synonyme d'« acide aminé dans une chaîne ». Dis « résidu 43 » comme un pro |
| **Région désordonnée** | partie de protéine **sans forme fixe** (c'est normal et fonctionnel). pLDDT bas |
| **Mutation ponctuelle** | un seul acide aminé changé |
| **Mutation faux-sens (*missense*)** | une mutation qui **remplace** un acide aminé par un autre ← notre cas |
| **Mutation non-sens (*nonsense*)** | crée un stop prématuré → protéine tronquée |
| **ΔΔG** | mesure de l'effet d'une mutation sur la **stabilité**. Négatif = déstabilise |
| **Drépanocytose** | maladie génétique du globule rouge, causée par **une seule mutation** de l'hémoglobine |
| **GB1** | petite protéine modèle de 56 acides aminés, très étudiée. Notre cobaye |
| **Ingénierie des protéines** | modifier une protéine pour l'améliorer (enzyme plus résistante, anticorps plus efficace) |
| **DSF / dichroïsme circulaire** | deux mesures **expérimentales** de stabilité → la validation que tes étudiants doivent proposer en conclusion du mini-projet |

---

## 5. Les notations qui déroutent

| Notation | Comment la lire |
|---|---|
| `E6V` | « le **glutamate** (E) en position **6** devient une **valine** (V) ». Lettre d'origine, position, lettre nouvelle |
| `p.Glu6Val` | exactement la même chose, en nomenclature clinique (HGVS) |
| `W43A` | tryptophane 43 → alanine. L'alanine est le « remplacement neutre » standard en labo |
| **E6V ou E7V ?** | **Le piège de numérotation.** La protéine mature a perdu sa méthionine initiale. La clinique compte sur la protéine mature (**E6V**), UniProt compte depuis le `M` initial (**E7V**). Les deux sont justes, dans leur référentiel |
| `NR-AhR` | `NR` = le **panel** Tox21 « *Nuclear Receptor signaling* », `AhR` = le récepteur testé. Les essais `SR-` forment le panel « *Stress Response* ». ⚠️ **Nuance** : AhR est rangé dans le panel NR, mais ce n'est **pas** un récepteur nucléaire au sens strict — c'est un facteur de transcription de la famille **bHLH-PAS**. Ne dis pas « AhR est un récepteur nucléaire » devant un biochimiste |
| `MT-CO1` | un gène **mitochondrial** (préfixe `MT-`) |
| `log2FC` | log₂ du rapport d'expression. `+1` = **doublé**, `−1` = **divisé par 2** |
| `CD3E` | le gène ; la protéine correspondante s'écrit CD3ε. Les gènes humains s'écrivent **en majuscules** |
| `1PGA` | un code **PDB** à 4 caractères = une structure expérimentale précise |
| `P68871` | un **accession UniProt** = une protéine précise |
| pLDDT 90 vs RMSD 2 Å | **pLDDT monte = mieux** (c'est une confiance), **RMSD monte = pire** (c'est une erreur) |

---

## 6. Les bases de données citées

| Base | Ce qu'elle contient | L'équivalent mental |
|---|---|---|
| **UniProt** | séquences de protéines + annotations | le registre officiel des protéines |
| **PDB** (RCSB) | structures 3D **expérimentales** | les mesures de terrain |
| **AlphaFold DB** | structures 3D **prédites** (> 200 M) | les mesures simulées |
| **Tox21 / MoleculeNet** | résultats de tests de toxicité | un jeu de données étiqueté standard |
| **ChEMBL** | activité biologique de molécules | le catalogue pharma |
| **PubChem** | fiches de molécules chimiques | « Wikipédia des molécules » (c'est là que tes étudiants iront chercher un SMILES) |
| **10x Genomics datasets** | jeux single-cell de référence | les datasets publics du domaine |
| **BBBC** | images de microscopie annotées | l'ImageNet de la biologie cellulaire |
| **GeneCards** | fiche synthèse d'un gène humain | la page de doc d'une fonction |

---

## 7. Les 12 pièges à éviter

Ce sont les erreurs qui te feraient perdre en crédibilité devant des étudiants en biotechnologie.

| # | ❌ Ne dis pas | ✅ Dis plutôt |
|:---:|---|---|
| 1 | « le gène produit l'effet » en parlant d'une protéine | Le **gène** est l'information, la **protéine** fait le travail. Garde la distinction stricte |
| 2 | « on séquence l'ADN » en séance 2 | En RNA-seq on mesure l'**ARN**, donc **l'activité**, pas le patrimoine génétique |
| 3 | « ces cellules ont un ADN différent » | **Même ADN**, expression différente. C'est tout le principe de la séance 2 |
| 4 | « séquencer » pour dire « mesurer l'expression » | **Séquencer** = lire les lettres. **Quantifier l'expression** = compter les copies |
| 5 | « AlphaFold calcule la physique du repliement » | Il **reconnaît des régularités** apprises sur les structures connues. Il ne simule pas la physique |
| 6 | « le pLDDT mesure la qualité de la structure » | C'est une **auto-évaluation du modèle**, pas une mesure expérimentale. Un pLDDT élevé sur une prédiction fausse reste possible |
| 7 | « la structure prédite montre que le mutant est stable » | AlphaFold prédit presque toujours **le même repliement** pour un mutant. Ça ne dit **rien** sur la stabilité |
| 8 | « Tox21 mesure la toxicité chez l'humain » | C'est un test **in vitro sur cellules**. Entre ça et la toxicité humaine, il y a la dose, le métabolisme, l'exposition |
| 9 | « les plaquettes sont des cellules » | Ce sont des **fragments de mégacaryocytes**, **sans noyau**. (Elles gardent un peu d'ARN, d'où leur présence dans les données) |
| 10 | « in vitro » et « in vivo » employés au hasard | **in vitro** = en boîte · **in vivo** = dans l'organisme · **in silico** = sur ordinateur |
| 11 | « une mutation en surface est sans effet » | **Contre-exemple central du module** : la drépanocytose vient d'une mutation **en surface** qui ne change pas le repliement, mais rend l'hémoglobine **collante** → elle polymérise en fibres |
| 12 | « la séquence détermine la structure, point » | C'est vrai **en principe** (Anfinsen), mais *in vivo* des **chaperons** aident au repliement, et l'environnement (pH, membrane, partenaires) compte |

---

## 8. Questions d'étudiants, réponses prêtes

> **« Pourquoi le modèle dit que le paracétamol est toxique ? »**
> Parce qu'il ne voit que 12 descripteurs globaux. Un petit cycle aromatique plan suffit à le faire
> « ressembler » aux actifs. C'est un **faux positif**, et c'est exactement pourquoi un criblage
> informatique **trie** des candidats mais ne **conclut** jamais seul.

> **« Est-ce qu'AlphaFold remplace la cristallographie ? »**
> Non. Il donne une **hypothèse de structure** en minutes au lieu de mois, ce qui est énorme pour
> orienter les expériences. Mais il prédit **une** conformation statique, sans ligand, sans membrane,
> sans dynamique. La structure expérimentale reste la référence.

> **« Pourquoi UMAP plutôt que l'ACP ? »**
> L'ACP est **linéaire** : elle écrase les structures complexes. UMAP préserve les **voisinages** et
> sépare visuellement les populations. Mais attention : on **visualise** avec UMAP, on **calcule** sur
> les composantes de l'ACP. Les distances entre îlots UMAP n'ont pas de sens quantitatif.

> **« Comment être sûr que ce cluster, c'est vraiment des plaquettes ? »**
> On ne l'est pas par le calcul seul. On regarde ses **gènes marqueurs** (`PPBP`, `PF4`), on les
> compare à la littérature, et on **valide expérimentalement** (cytométrie en flux). Le clustering
> propose, le biologiste dispose.

> **« Pourquoi ESM-2 est bon alors qu'il n'a jamais vu d'étiquette de localisation ? »**
> Parce qu'il a appris à **deviner des acides aminés masqués** sur des millions de séquences. Pour y
> arriver, il a dû intérioriser les régularités de l'évolution — dont les peptides signaux. La
> localisation est un **sous-produit** de cette compréhension.

> **« Je peux utiliser ça pour ma thèse / mon stage ? »**
> Oui pour explorer et prioriser. Mais avec trois réflexes : vérifier que tes données ressemblent aux
> données d'entraînement (**domaine d'applicabilité**), comparer à une **référence simple** avant de
> crier victoire, et **valider expérimentalement** toute conclusion.

> **« Pourquoi 95 % de zéros dans la matrice ? C'est un bug ? »**
> Non, deux causes : **biologique** (une cellule n'exprime que 2 000 à 10 000 gènes sur 33 000) et
> **technique** (le *dropout* : l'ARN présent n'est pas toujours capturé).

> **« L'IA va remplacer les biologistes ? »**
> Elle remplace les tâches **répétitives et subjectives** (compter 300 noyaux). Elle ne formule pas
> l'hypothèse, ne conçoit pas l'expérience, et ne sait pas quand elle se trompe — la séance 5 en donne
> la démonstration avec la drépanocytose.

---

## 9. Index alphabétique

**Acide aminé** §3 · **Adressage** §4.3 · **AhR** §4.1 · **Anfinsen** §4.5 · **Ångström** §2 ·
**Apoptose** §4.4 · **Assay (essai)** §4.1 · **Batch effect** §4.2 · **Biomarqueur** §4.2 ·
**Bulk RNA-seq** §4.2 · **Cancérogénèse** §4.1 · **CD (nomenclature)** §4.2 · **Coévolution** §4.5 ·
**Cristallographie** §4.5 · **Cryo-EM** §4.5 · **CYP1A1** §4.1 · **Cytoplasme** §1 · **DAPI** §4.4 ·
**Dioxine** §4.1 · **Dogme central** §1 · **Drépanocytose** §4.5 · **Dropout** §4.2 ·
**Expression génique** §1 · **Facteur de transcription** §4.1 · **FASTA** §4.3 · **Feuillet β** §4.5 ·
**Fluorophore** §4.4 · **Frottis** §4.4 · **GB1** §4.5 · **Gène** §1 · **Giemsa** §4.4 ·
**Hélice α** §4.5 · **Hélice transmembranaire** §4.3 · **Homologue** §4.3 · **Hydrophobicité** §3, §4.3 ·
**in vitro / in vivo / in silico** §4.1 · **Levinthal** §4.5 · **Ligand** §4.1 · **Lipinski** §4.1 ·
**logP** §4.1 · **Localisation subcellulaire** §4.3 · **Marqueur** §4.2 · **Membrane** §1 ·
**Mitochondrie** §1 · **Mitose** §4.4 · **MSA** §4.5 · **Mutation faux-sens** §4.5 · **NLS** §4.3 ·
**Noyau** §1 · **PAE** §4.5 · **PBMC** §4.2 · **PDB** §6 · **Peptide signal** §4.3 ·
**Plaquette** §4.2, §7 · **pLDDT** §4.5 · **Ploïdie** §4.4 · **Protéine** §1 · **QSAR** §4.1 ·
**Récepteur** §4.1 · **Repliement** §4.5 · **Résidu** §4.5 · **RMSD** §4.5 · **RNA-seq** §4.2 ·
**SMILES** §4.1 · **Single-cell** §4.2 · **Structure (1aire à 4aire)** §4.5 · **Swiss-Prot** §4.3 ·
**Tox21** §4.1 · **TPSA** §4.1 · **Transcriptome** §1 · **TrEMBL** §4.3 · **UMI** §4.2 ·
**UniProt** §6 · **3R** §4.1 · **ΔΔG** §4.5

---

*Ce guide accompagne le module [Intelligence Artificielle et Biotechnologie](https://nevermind78.github.io/IA_Biotech/).
Le [glossaire du site](https://nevermind78.github.io/IA_Biotech/glossaire.html) couvre, lui, le vocabulaire
**IA** destiné aux étudiants — les deux sont complémentaires.*
