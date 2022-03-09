# Security Policy <!-- omit in toc -->

- [Version d'Unreal Engine](#version-dunreal-engine)
- [.git](#git)
  - [.gitignore](#gitignore)
  - [Branches](#branches)
    - [Pour créer une branche](#pour-créer-une-branche)
    - [Outils graphique pour les branches](#outils-graphique-pour-les-branches)
  - [Pull request](#pull-request)
    - [Créer un Pull request](#créer-un-pull-request)
  - [Merge](#merge)
    - [Commit Merge](#commit-merge)
    - [Squash and merge](#squash-and-merge)
    - [Rebase](#rebase)
  - [Setup .git avec Unreal Engine](#setup-git-avec-unreal-engine)
- [Nommenclature](#nommenclature)
  - [Dans Unreal](#dans-unreal)
    - [Préfixes](#préfixes)
    - [Suffixes](#suffixes)
      - [Textures](#textures)

# Version d'Unreal Engine

| Version  | Supported            |
| -------- | -------------------- |
| > 4.27.x | non                  |
| 4.27.3   | à éviter si possible |
| 4.27.2   | oui                  |
| 4.27.1   | à éviter si possible |
| < 4.27.x | non                  |

# .git

- Taille du repo max : 5 Go
- Taille d'un fichier max : 100 Mb

**Aucun transfert de fichier en dehors de GitHub, pas par discord, pas par clé USB, uniquement par GitHub** (sauf grosse urgence).

## [.gitignore](.gitignore)

Le [.gitignore](.gitignore) permet de ne pas commit certains fichiers (eg : fichier temporaires, fichiez non désirés...)

```ignore
# ext = extension de fichier (.cs, .fbx, .png...)
# Un fichier que je veux ignorer
fichierQueJIgnore.ext

# Une extension que je veux ignorer
*.ext

# Un dossier que je veux ignorer
MonDossier/*

# Avec les crochet [Aa], peut importe si c'est une majuscule ou une minuscule
[Mm]onFichier.ext
[Mm]onDossier/*

# Ignorer un dossier sauf un fichier
MonDossier/*
!MonDossier/MonFichierQueJeVeuxPasIgnorer.ext
```

## Branches

### Pour créer une branche

1. Cliquez sur [Current branch] dans GitHub Desktop
2. Sélectionner la [default branch] (en général *main* ou *master*)
3. Re-cliquez [Current branch] et cliquez sur [new branch]
4. Nommer votre branche par votre nom (eg : *MichenaudMelvin*)
5. Vous pouvez travaillez sur votre branche

### Outils graphique pour les branches

- [Git Graph](https://marketplace.visualstudio.com/items?itemName=mhutchie.git-graph) pour [VScode](https://code.visualstudio.com/)
- [SourceTree](https://www.sourcetreeapp.com/)

## Pull request

Un pull request est une demande d'ajout/modification de fichiers.

### Créer un Pull request

1. Aller dans [Branches](https://github.com/MichenaudMelvin/ProjetSemestriel/branches).
2. Cliquer sur [New Pull Request].
3. Sélectionner la branche que qui vous intéresse et sélectionner sur quelle branche ajouter le contenu.
4. [Merge](#merge) votre branche.

## Merge

- Se fait grâce à un pull request.
- Un merge permet la fusion de fichier texte.
- Pour merge un fichier binaire (images, .max, .psd...) il faudra supprimer 1 des 2 fichiers.

### Commit Merge

- Se fait après un pull request depuis [github.com](https://github.com/).
- Si il y a des conflits, se fait depuis [GitHub Desktop].

### Squash and merge

On utilisera probablement pas.

### Rebase

**Pour les Rebase Commit, utilisez [SourceTree](https://www.sourcetreeapp.com/)** *(github desktop gère mal les rebase*).

Permet de récupérer des anciens commit présente sur d'autres branche.

Pensez à faire des Rebase commit de votre branche sur main pour récupérer des update du repo.

## Setup .git avec Unreal Engine

1. Installer [.git](https://git-scm.com/downloads).
2. Cliquez sur [Source Control] --> [Connect to Source Control...] --> [Provider].
3. Selectionnnez .git.
4. Cliquez sur [Accept Settings]

# Nommenclature

Nommenclature classique : camelCase

## Dans Unreal

**Pour les maps/levels/scenes : pas de préfix/sufixes mais doivent être placé dans un dossier le dossier "Maps"**

*Si non dispo, ajoutez ([REF](https://www.gamecoderblog.com/en/unreal-engine4/ue4-recommended-files-naming-convention))*

Pensez à rajouter le sufixe "_01" pour les assets (pour le reste c'est moins utile)

*eg : Si plusieurs staticMesh de maison*
- SM_maison_01
- SM_maison_02
- SM_maison_03

### Préfixes

| Type              | Préfix  |
| ----------------- | ------- |
| AnimationBP       | AnimBP_ |
| Animation         | Anim_   |
| Blackboard        | BB_     |
| BehaviorTree      | BT_     |
| Blueprint         | BP_     |
| StaticMesh        | SM_     |
| Particle          | P_      |
| ParticleSystem    | PS_     |
| LensFlare         | LF_     |
| Sound             | S_      |
| SoundCues         | Cue_    |
| SoundEffect       | AS_     |
| MusicFile         | AM_     |
| Material          | M_      |
| PhysicsMat        | PhysM_  |
| PhysicalMaterial  | PM_     |
| SkeletalMesh      | SK_     |
| Sprite            | SP_     |
| TextureC          | T_      |
| TextureCube       | TC_     |
| UIImage           | Img_    |

### Suffixes

#### Textures

Obligatoire de rajouter "_01"

| Texture type      | Sufix |
| ----------------- | ----- |
| Diffuse           | _D    |
| Base Color        | _BC   |
| Metallic          | _MT   |
| Specular          | _S    |
| Roughness         | _R    |
| Normal            | _N    |
| Displacement      | _DP   |
| Ambient Occlusion | _AO   |
| Height Map        | _H    |
| Flow Map          | _FM   |
| Light Map         | _L    |
| Mask              | _M    |

*eg : Si pour une texture de sol vous avez une diffuse, une metallic et une normale :*  
- T_maTextureDeSol_01_D
- T_maTextureDeSol_01_MT
- T_maTextureDeSol_01_N
