# 📸 Hypr-Edit

Un utilitaire de capture d'écran léger et réactif pour **Wayland/Hyprland**, écrit en Python avec **PyQt6**. Il permet d'annoter rapidement une capture avant de l'envoyer dans le presse-papier sans créer de fichiers temporaires.

## ✨ Fonctionnalités

L'outil propose une barre d'outils flottante permettant de modifier la capture à la volée :

*   **Dessin de formes** : Rectangles (`󰇙`) et Cercles (`󰄯`).
*   **Obfuscation** : Un outil de flou pixelisé (`󰝟`) pour masquer les données sensibles.
*   **Surligneur** : Un pinceau semi-transparent (`󰏫`) pour mettre en évidence du contenu.
*   **Sélecteur** : Déplacez les formes déjà créées (`󰆏`).
*   **Palette de couleurs** : Un slider arc-en-ciel dynamique pour changer la couleur de vos annotations.
*   **Gestion du canevas** :
    *   `󰅖` **Tout effacer** : Nettoie l'intégralité des dessins.
    *   `󰆴` **Supprimer** : Supprime uniquement la forme sélectionnée.
    *   `󰄬` **Valider** : Copie l'image finale dans le presse-papier et ferme l'outil.

## 🛠 Dépendances

Assurez-vous d'avoir les outils suivants installés sur votre système :

### Système (Wayland)
*   `grim` : Pour la capture d'écran.
*   `slurp` : Pour la sélection de la zone à l'écran.
*   `wl-clipboard` : Pour la gestion du copier-coller.

### Python & UI
*   `Python 3`
*   `PyQt6` : `pip install PyQt6`
*   **Police** : Une [Nerd Font](https://www.nerdfonts.com/) (ex: *JetBrainsMono Nerd Font*) est requise pour l'affichage des icônes de la barre d'outils.

## 🚀 Installation

1.  Rendez le script exécutable :
    ```bash
    chmod +x hypr-edit.py
    ```
2.  (Optionnel) Déplacez-le dans votre PATH :
    ```bash
    mv hypr-edit.py ~/.local/bin/hypr-edit
    ```

## ⚙️ Configuration Hyprland

Pour utiliser l'outil avec un raccourci clavier, ajoutez la ligne suivante dans votre fichier `~/.config/hypr/hyprland.conf` :

```ini
# Exemple avec SUPER + SHIFT + S
bind =  $ mainMod SHIFT, S, exec, grim -g " $ (slurp)" - | /chemin/vers/votre/script.py
