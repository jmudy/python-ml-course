# [Curso completo de Machine Learning: Data Science en Python](https://cursos.frogamesformacion.com/courses/machine-learning-python/)

A continuación se describe la instalación de las librerías utilizadas durante el curso. Todos los temas se han desarrollado con notebooks en `JupyterLab 3.4.4`.

## Instalación de la librería rpy2

Para utilizar la librería `rpy2` es necesario instalar (previo a los requerimentos) `R`. Se ha utilizado `R 4.2.1 Patched`, misma versión que en el curso de [Machine Learning: Data Science con RStudio](https://github.com/jmudy/r-course/tree/curso) y que se puede descargar en el siguiente [link](https://cran.r-project.org/bin/windows/base/R-4.2.1patched-win.exe).

## Instalación del entorno virtual en Anaconda

Instalación entorno virtual con Anaconda:

```bash
conda create -n ml-python python=3.7
```

```bash
pip install -r requirements.txt
```

o bien:

```bash
conda env create -f ml-python.yml
```

## Instalación de la librería graphviz

Instalar librería `graphviz` desde Anaconda para que no encuentre problemas en el `PATH` a la hora de dibujar (se ha utilizado la versión `0.16`):

```bash
conda install python-graphviz
```

## Instalación de la librería ggplot

Al importar `ggplot` salta un error que se ha solucionado siguiendo los pasos del siguiente [link](https://github.com/yhat/ggpy/issues/662#issuecomment-484138308).

Hay que hacer varios cambios en ficheros internos de la librería.

`ggplot/utils.py`:

Cambiar

```bash
date_types = (
    pd.tslib.Timestamp,
    pd.DatetimeIndex,
    pd.Period,
    pd.PeriodIndex,
    datetime.datetime,
    datetime.time
)
```

a

```bash
date_types = (
    pd.Timestamp,
    pd.DatetimeIndex,
    pd.Period,
    pd.PeriodIndex,
    datetime.datetime,
    datetime.time
)
```

`ggplot/stats/smoothers.py`:

Hacer lo mismo y además comentar:

`from pandas.lib import Timestamp`
