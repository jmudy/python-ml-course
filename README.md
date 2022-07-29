# [Curso completo de Machine Learning: Data Science en Python](https://cursos.frogamesformacion.com/courses/machine-learning-python/)

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

Al instalar `ggplot` hay que hacer varios cambios en ficheros internos de la librería:

ggplot/utils.py

cambiar:

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

En ggplot/stats/smoothers.py hacer lo mismo y comentar:
`from pandas.lib import Timestamp`