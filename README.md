# [Curso completo de Machine Learning: Data Science en Python](https://cursos.frogamesformacion.com/courses/machine-learning-python/)

Curso realizado en `JupyterLab 3.3.2`.

Para utilizar la librería `rpy2` es necesario instalar previamente `R`. La versión que se ha utilizado en este curso es `R 4.2.1 Patched`, misma versión que se utilizó en el curso de [Machine Learning: Data Science con RStudio](https://github.com/jmudy/r-course/tree/curso) y que se puede descargar en el siguiente [link](https://cran.r-project.org/bin/windows/base/R-4.2.1patched-win.exe).

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
