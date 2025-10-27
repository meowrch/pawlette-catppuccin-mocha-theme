# 🎨 Pawlette Catppuccin Mocha
Набор тем, иконок и обоев, сделанных под единый стиль - catppuccin-mocha lavender.

## Что используется?
- Icon-theme: [Tela-circle-dracula (dark)](https://github.com/vinceliuice/Tela-circle-icon-theme)
- GTK-theme: [Catppuccin-gtk](https://github.com/brycewalkerdev/catppuccin-gtk) (mocha-lavender)
- Cursor:
    - [Bibata-Modern-Classic](https://github.com/ful1e5/Bibata_Cursor)
    - [Bibata-Modern-Classic-hyprcursor](https://github.com/rtgiskard/Bibata_Cursor)

## 📦 Icon Theme build
```bash
git clone https://github.com/vinceliuice/Tela-circle-icon-theme ~/tela-circle-icon-theme
sh ~/tela-circle-icon-theme/install.sh -n pawlette-catppuccin-mocha-build dracula
rsync -rL ~/.local/share/icons/pawlette-catppuccin-mocha-build-dracula/ ./icons/
rsync -rL ~/.local/share/icons/pawlette-catppuccin-mocha-build-dracula-dark/ ./icons/

sed -i \
  -e 's/^Name=.*/Name=pawlette-catppuccin-mocha/' \
  -e 's/^Comment=.*/Comment=Tela-circle-dracula icon theme + Bibata-Modern-Classic cursor (hyprcursor support)/' \
  -e 's/^Inherits=.*/Inherits=Papirus-Dark,hicolor/' \
  ./icons/index.theme

gtk-update-icon-cache -f -t ./icons/
gtk4-update-icon-cache -f -t ./icons/
rm -rf ~/tela-circle-icon-theme
rm -rf ~/.local/share/icons/pawlette-catppuccin-mocha-build-dracula
rm -rf ~/.local/share/icons/pawlette-catppuccin-mocha-build-dracula-dark
rm -rf ~/.local/share/icons/pawlette-catppuccin-mocha-build-dracula-light
```