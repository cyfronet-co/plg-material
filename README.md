# **plg-material**
`plg-material` is a custom MkDocs theme for PLGrid infrastructure markdown documentations.

The theme extends the [mkdocs-material](https://github.com/squidfunk/mkdocs-material) theme. It is also configured with [MkDocs static i18n plugin](https://github.com/ultrabug/mkdocs-static-i18n).

# **Instalation guide**
To install **plg-material** just follow the instruction below.

1. Download the project as a ZIP package.
2. Unzip the package in your MkDocs project.
3. Add the following lines to `mkdocs.yml`:
    ```
    theme:
      name: material
      custom_dir: plg-material-main
      palette:
        scheme: plg-material-light

    extra_css:
      - assets/stylesheets/plg-material.css
    ```
    We also recommend changing the unzipped directory name and `custom_dir` value to `plg-material` for the ease of naming.
4. Configure other options in your `mkdocs.yml`. You may find next section useful if you are looking for additional features intruduced in our custom theme.

# **Features**
## Theme features
For the time being, our theme provides styling for the following theme features:
- `navigation.top`
- `navigation.tabs`

## **PLGrid favicon & logo**
To add PLGrid favicon or logo in header in your page you have to define it in your theme:
```
theme:
  favicon: images/favicon.png
  icon:
    logo: logo
```
However, you may skip the `favicon` option since `images/favicon.png` is its default value.

## **Dark & light modes**
In our theme we have defined two custom schemes:
- dark, i.e. `plg-material-dark`
- light, i.e. `plg-material-light`

To use either one in your project you have to define it in your `theme.palette` option, e.g.:
```
theme:
  palette: 
    scheme: plg-material-light
```
However, if you would like to switch between the modes you have to add the following code to your `mkdocs.yml`:
```
theme:
  palette:
    - media: "(prefers-color-scheme: light)" # light mode
      scheme: plg-material-light
      toggle:
        icon: material/weather-night
        name: Switch to dark mode
    - media: "(prefers-color-scheme: dark)" # dark mode
      scheme: plg-material-dark
      toggle:
        icon: material/weather-sunny
        name: Switch to light mode
```

## **PLGrid infrastructure sites**
To add PLGrid infrastucture sites to your footer you have to add `pymdownx.emoji` extension to you markdown extensions and define the directory with the icons:
```
markdown_extensions:
  - pymdownx.emoji:
    emoji_index: !!python/name:materialx.emoji.twemoji
    emoji_generator: !!python/name:materialx.emoji.to_svg
    options:
      custom_icons:
        - plg-material/.icons
```

## **Multi-language copyright**
The [MkDocs static i18n plugin](https://github.com/ultrabug/mkdocs-static-i18n) does not allow to translate the `config.copyright` option. Therefore, you may leave the default copyright value as a fallback and define the translated copyrights in `config.extra`, e.g.:
```
copyright: Default copyright

extra:
  copyright:
    pl: "Polish copyright"
    en: "English copyright"
```

# **Contributing**
Feel free to create an issue if you found a bug or want to request a new feature.

Remember that the issue should be descriptive, that is, provide reproduction scenario and any necessary screenshots.

Such a request will make it easier for us to investigate the problem.

# **License**
**MIT License**

Copyright © 2023, PLGrid Consortium.

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NON-INFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.