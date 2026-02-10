# Ultimate Sprite Cutter ✂️

**Ultimate Sprite Cutter** est une application de bureau écrite en Python (Tkinter) conçue pour découper des **Sprite Sheets**, des **Tilesets** ou des grilles d'images en fichiers individuels.

Contrairement aux outils basiques, il offre des fonctionnalités avancées pour les développeurs de jeux et les artistes : détection automatique des sprites (Smart Split), gestion des marges (padding/gap), prévisualisation d'animation et export de métadonnées JSON.

---

## ✨ Fonctionnalités Clés

* **3 Modes de Découpe :**
    * 🔢 **Grille :** Divisez l'image en $X$ lignes et $Y$ colonnes.
    * 📏 **Taille Fixe :** Découpez des cases de taille précise (ex: 64x64 px).
    * ⚡ **Smart Auto-Detect :** Analyse la transparence pour détecter et détourer automatiquement les sprites isolés.
* **Gestion des Espacements :**
    * **Offset (X/Y) :** Définissez un décalage de départ (marge externe).
    * **Gap (X/Y) :** Gérez l'espace vide entre chaque tuile (marge interne).
* **Interaction Visuelle :**
    * **Zoom & Pan :** Naviguez facilement dans les grandes images.
    * **Sélection :** Clic gauche pour ignorer/exclure certaines tuiles de l'export.
    * **Preview Animation :** Vérifiez vos cycles de marche/animation directement dans l'outil.
* **Export Pro :**
    * **Formats :** PNG (avec transparence), JPG, WEBP.
    * **JSON Data :** Génère un fichier `.json` contenant les coordonnées de chaque sprite.
    * **Deduplication :** Option pour ne pas sauvegarder les doublons (ex: tuiles d'herbe identiques).
    * **Performance :** Export multi-threadé avec barre de progression.

---

## 🚀 Installation

### Prérequis
* Python 3.8 ou supérieur.
* Bibliothèque `Pillow` (PIL).

### Installation rapide

1.  Assurez-vous d'avoir Python installé.
2.  Installez la dépendance graphique :
    ```bash
    pip install pillow
    ```
    *(Note : Tkinter est inclus par défaut avec Python sur Windows/macOS. Sur Linux : `sudo apt-get install python3-tk`)*.

3.  Lancez l'application :
    ```bash
    python super_sprite_cutter.py
    ```

---

## 📖 Guide d'Utilisation

### 1. Chargement et Navigation
* Cliquez sur **"📂 Ouvrir Image"** pour charger un fichier.
* **Zoom :** Utilisez la molette de la souris.
* **Déplacer (Pan) :** Maintenez la molette enfoncée (ou `Shift` + `Clic Gauche`) et glissez.

### 2. Choisir le Mode de Découpe

#### A. Mode Grille (Grid)
Idéal si vous connaissez le nombre de cases (ex: une planche de 4 lignes sur 5 colonnes).
* Réglez le nombre de **Lignes** et **Colonnes**.

#### B. Mode Taille Fixe (Size)
Idéal pour les Tilesets standards (ex: RPG Maker, Tiled).
* Réglez la **Largeur** et la **Hauteur** des tuiles en pixels (ex: 32x32).

#### C. Mode Smart Auto
Idéal pour les planches de sprites non alignés ou en vrac.
* Cliquez sur **"⚡ Lancer Détection Auto"**.
* L'algorithme scanne l'image et crée des rectangles autour des zones non-transparentes.

### 3. Ajustements (Marges & Gaps)
Si votre grille ne s'aligne pas parfaitement avec l'image :
* **Départ X / Y (Offset) :** Déplace le point de départ de la grille (utile si l'image a une bordure).
* **Espace X / Y (Gap) :** Ajoute de l'espace vide entre chaque case de la grille.

### 4. Sélection
* Les cases encadrées en **Vert** seront exportées.
* **Cliquez (Clic Gauche)** sur une case pour l'ignorer. Elle deviendra **Rouge** (avec une croix) et ne sera pas sauvegardée.

### 5. Export
1.  **Préfixe :** Choisissez le nom de base des fichiers (ex: `hero_run`).
2.  **Options :**
    * `Générer JSON` : Crée un fichier descriptif pour l'intégration moteur.
    * `Suppr. Doublons` : Compare le contenu des images et ne sauvegarde qu'une seule copie des sprites identiques.
3.  Cliquez sur **"💾 EXPORTER TOUT"**. Les fichiers seront créés dans un dossier `/output` situé au même endroit que l'image source.

---

## 📂 Structure du JSON (Optionnel)

Si vous cochez l'option "Générer JSON", vous obtiendrez un fichier structuré ainsi :

```json
{
  "source": "personnage.png",
  "sprites": [
    {
      "filename": "hero_000.png",
      "x": 0,
      "y": 0,
      "w": 64,
      "h": 64
    },
    {
      "filename": "hero_001.png",
      "x": 70,
      "y": 0,
      "w": 64,
      "h": 64
    }
  ]
}
```
## ⌨️ Raccourcis Clavier
| Action | Raccourci
| Zoom Avant/Arrière | Molette Souris
| Panoramique (Déplacer) | Clic Molette (Maintenir) OU Shift + Clic Gauche
| Sélectionner/Désélectionner | Clic Gauche sur une tuile

##📝 LicenceCe projet est libre de droits pour un usage personnel et éducatif.Développé avec ❤️ en Python.
