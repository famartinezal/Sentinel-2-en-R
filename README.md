# Sentinel-2-en-R

# _Fredy Martínez_
# Cargar Multiples Imágenes Sentinel-2 en R
<a href="https://ibb.co/bO4ywU"><img src="https://thumb.ibb.co/bO4ywU/ESPINAL_RGB1.png" alt="ESPINAL_RGB1" border="0"></a>
 <a href="https://ibb.co/jgzOwU"><img src="https://thumb.ibb.co/jgzOwU/ESPINAL_RED1.png" alt="ESPINAL_RED1" border="0"></a>
<a href="https://ibb.co/bO4ywU"><img src="https://thumb.ibb.co/bO4ywU/ESPINAL_RGB1.png" alt="ESPINAL_RGB1" border="0"></a>
 <a href="https://ibb.co/jgzOwU"><img src="https://thumb.ibb.co/jgzOwU/ESPINAL_RED1.png" alt="ESPINAL_RED1" border="0"></a>
## Cargar paquetes

```
if(!require(raster)){install.packages('raster'); library(raster)} else {library(raster)}
if(!require(rgdal)){install.packages('rgdal'); library(rgdal)} else {library(rgdal)}
if(!require(gdalUtils)){install.packages('gdalUtils'); library(gdalUtils)} else {library(gdalUtils)}
```

## Creación de funciones:
### _1. Función que convierte de jp2 a tiff_
```
convierte = function(dir){
    lista= list.files(dir, full.names = T,pattern = "jp2")# Lista los nombres del directorio
    jp2=as.list(lista)# Convierte en una lista
    tif=lapply( jp2,FUN = batch_gdal_translate, dir, outsuffix = ".tif")}
```
### _2. Función que lee tiff_
```
lee_tiff = function(dir){
    listar= list.files(dir, full.names = T,pattern = "tif")# Lista los nombres del directorio
    lista=as.list(listar)# Convierte en una lista
    apila=stack(lista)
    bloque=brick(apila)}
```

<H1 align="center"><FONT FACE="modern" SIZE=5 COLOR="#1E8449  ">Cargar Multiples Imágenes Sentinel-2 en R</FONT></H1>
Syntax highlighted code block

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/famartinezal/Sentinel-2-en-R/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
