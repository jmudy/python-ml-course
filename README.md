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

Al importar `ggplot` salta un error que se ha solucionado siguiendo los pasos del siguiente [link](https://github.com/yhat/ggpy/issues/662#issuecomment-484138308).

Hay que hacer varios cambios en ficheros internos de la librería:

`ggplot/utils.py`

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

`ggplot/stats/smoothers.py`

hacer lo mismo y además comentar:

`from pandas.lib import Timestamp`
