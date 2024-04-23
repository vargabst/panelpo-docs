# Back End (Proceso interno)

## Paquetes
* `pandas` - Procesamiento de datos estructurados.
* `os` - Uso de funciones del sistema operativo.
* `openpyxl` - Tratamiento de archivos Excel.
* `tkinter` - Generación de interfaces.
* `numpy` - Realización de cálculos complejos.
* `datetime` - Uso de fechas y horas.
* `pickle` - Encriptación de archivos (memoria).
* `re` - Uso de lógicas de expresiones regulares.
* `math` - Librería nativa de Python para operaciones complejas.
* `tempfile` - Uso de archivos temporales.

## Funciones nativas en Archivo 'core.py'

### core.InstantesSalidas

_core._**InstantesSalidas**(inicio_periodo:_ datetime_, intervalo:_ int_, nSalidas:_ int_)

Esta función retorna una lista con una cantidad definida de instantes de tiempo en el formato HH:MM:SS iniciando en inicio_periodo, espaciados de acuerdo al intervalo.

Parámetros:


* `inicio_periodo`: Instante en formato HH:MM:SS.
* `intervalo`: Valor de espaciamiento entre instantes (en minutos).
* `nSalidas`: Valor de cantidad de instantes a generar.

---

### core.redondear_al_minuto

_core._**redondear_al_minuto**(td: _timedelta_, min_=1: _int_)

Redondea un timedelta. Por defecto es al minuto.
Se puede indicar como segundo argumento una cantidad decimal de minutos. (ej: 30s -> 0.5)

Parámetros:

* `td`: Valor de tipo _timedelta_.
* `min_`:  Valor de minutos en decimal.

---

### core.int_codigo

_core._**int_codigo**(codigo: _str)_

Convierte un código desde string a int (si es posible).

Parámetros:

* `codigo`: Valor de tipo _str_.

---

### core.new_durac_periodo

_core._**new_durac_periodo**(d2: _datetime_, d1: _datetime)_

Calcula la duración de un periodo de tiempo entre d1 y d2.

Parámetros:

* `d2`: Máximo valor del periodo.
* `d1`: Mínimo valor del periodo.

---

### core.duracion_ok

_core._**duracion_ok**(row: _pandas.Series)_

Analiza una fila de un DataFrame con las columnas 'DURACION' y 'DURACION_MOD'. Si la columna 'DURACION_MOD' es nula o igual a cero, entonces retorna el valor de la columna 'DURACION'; si no, retorna el valor de la columna 'DURACION_MOD'

Parámetros:

* `row`: Fila del DataFrame a analizar.

---

### core.melting_cons

_core._**melting_cons**(cons: _pandas.DataFrame_, version=1: _int)_

Convierte los nombres de las columnas de un Consolidado de Salidas en una sola columna con valores. Si la versión es 1, entonces permite aplicar la función en columnas con abreviaciones en unidad, servicio y sentido. Si la versión es distinta de 1, entonces permite aplicar la función en columnas con los nombres originales.

Parámetros:

* `cons`: DataFrame del archivo Consolidado de Salidas.
* `version`: Valor que define el tipo de `pandas.melt` a utilizar.

---

### core.replace_char

_core._**replace_char**(s: _str_, old_char: _str_, new_char: _int)_

Reemplaza un carácter por otro en un string.

Parámetros:

* `s`: String a alterar.
* `old_char`: Valor del carácter del string que se necesita reemplazar.
* `new_char`: Valor del carácter del string que se desea incorporar.

---

### core.difference_between_dt_times

_core._**difference_between_dt_times**(a: _timestamp_, b: _timestamp_)

Retorna la diferencia (en horas) entre los tiempos a y b.

Parámetros:

* `a`: _Timestamp_ de interés.
* `b`: _Timestamp_ de interés.

---

### core.fileChoose

_core._**fileChoose**()

Llama a la función _askopenfilename_ de la librería _filedialog_. Esta abre una ventana de Windows para obtener el nombre de un archivo. Retorna el nombre del archivo seleccionado.

---

### core.formulaCheck

_core._**formulaCheck**(filename: _str_)

Verifica que el archivo Excel a cargar no tenga fórmulas en alguna de sus celdas.

Parámetros:

* `filename`: Nombre del archivo Excel seleccionado.

---

### core.hiddenSheetsCheck

_core._**hiddenSheetsCheck**(filename: _str_)

Verifica que el archivo Excel a cargar no tenga hojas ocultas.

Parámetros:

* `filename`: Nombre del archivo Excel seleccionado.

---

### core.is_valid_time

_core._**is_valid_time**(value: _any_)

Verifica que el valor sea de tipo _datetime.time_.

Parámetros:

* `value`: Valor a analizar.

---

### core.timeFormatCheck

_core._**timeFormatCheck**(filename: _str_)

Verifica que las marcas horarias en el archivo Excel sean de tipo _datetime.time_.

Parámetros:

* `filename`: Nombre del archivo Excel seleccionado.

---

### core.chunker

_core._**chunker**(seq: _list_, size: _int_)

Genera una estructura auxiliar de datos para recorrer una lista seleccionando _size_ elementos.

Parámetros:

* `seq`: La lista de valores a intervenir.
* `size`: Cantidad de elementos a agrupar de la lista.

---

### core.chunker_df

_core._**chunker_df**(seq: _pandas.DataFrame_, size: _int_)

Genera una estructura auxiliar de datos para recorrer un dataframe seleccionando _size_ filas.

Parámetros:

* `seq`: Dataframe a intervenir.
* `size`: Cantidad de filas a agrupar del dataframe.

---

### core.get_second_minimum

_core._**get_second_minimum**(x: _list_)

Entrega el segundo valor mínimo (mayor que el mínimo global)

Parámetros:

* `x`: Lista con elementos ordenables.

---

### core.convertir_horario_dia_siguiente

_core._**convertir_horario_dia_siguiente**(hi: _timestamp_, ht: _timestamp_)

Retorna los horarios _hi_ y _ht_ (usualmente tomados desde las primera y última marca horaria programada como salida) en formato "DD/MM/YYYY HH:MM:SS" para realizar operaciones de comparación en programación de operaciones. Esta función permite convertir el mayor horario al día siguiente para permitir operaciones de comparación consistentes.

Parámetros:

* `hi`: Marca horaria menor.
* `ht`: Marca horaria mayor.

---

### core.arreglar_horarios_inicio_fin

_core._**arreglar_horarios_inicio_fin**(first_exp_time: _timestamp_, second_exp_time: _timestamp_, last_exp_time: _timestamp_)

Retorna los horarios de inicio (menor) y de fin (mayor) (usualmente tomados desde las primera y última marca horaria programada como salida) en formato "DD/MM/YYYY HH:MM:SS" para realizar operaciones de comparación en programación de operaciones. Esta función realiza una estrategia de comparación en la diferencia entre la primera y la segunda marca horaria del día, para estimar correctamente la posición (en días) del horario mayor.

Parámetros:

* `first_exp_time`: Marca horaria menor.
* `second_exp_time`: Marca horaria segunda menor.
* `last_exp_time`: Marca horaria mayor.

---

### core.get_first_and_last_exp

_core._**get_first_and_last_exp**(sub_df: _pandas.DataFrame_)

Esta función recibe un subconjunto de filas de la tabla Anexo 4 cargada en el programa y entrega los tiempos de la primera (menor) y última (mayor) salida programada.

Parámetros:

* `sub_df`: Subconjunto del DataFrame del Anexo 4 cargado.

---

### core.get_limits_tramos

_core._**get_limits_tramos**(sub_df: _pandas.DataFrame_)

Esta función recibe un subconjunto de filas de la tabla Anexo 4 cargada en el programa y retorna un dataframe con  los tiempos de la primera (menor) y última (mayor) salida programada, por cada tramo horario definido en un tipo de día. Esta función se aplica en los casos en los que se sabe que el servicio-sentido-tipodía tiene dos tramos. 

Parámetros:

* `sub_df`: Subconjunto del DataFrame del Anexo 4 cargado.

---

### core.filter_max_values_dict

_core._**filter_max_values_dict**(dict_obj: _dict_)

Esta función recibe un diccionario, el cual tiene valores enteros; y retorna otro diccionario filtrado solo con valores mayores a 3. 

Parámetros:

* `dict_obj`: Diccionario con valores enteros.

---

### core.dt_time_to_hours

_core._**dt_time_to_hours**(time: _datetime.time_)

Esta función recibe una marca horaria y retorna la cantidad de horas de la marca (con decimales)

Parámetros:

* `time`: Marca horaria

---

### core.comp_durac_tolerance

_core._**comp_durac_tolerance**(durac_a3: _datetime.time_, durac_a4: _datetime.time_)

Esta función aplica la regla de tolerancia en la duración de las expediciones según el Anexo 4, dependiente de la duración programada según el Anexo 3. Retorna un booleano y los límites de tolerancia calculados.

Parámetros:

* `durac_a3`: Duración en minutos de las expediciones programadas en el servicio-sentido-tipodía-mediahora.
* `durac_a4`: Duración en minutos de la expedición programada en el servicio-sentido-tipodía.

---

### core.comp_iprog_tolerance

_core._**comp_iprog_tolerance**(iprog: _int_, imin: _int_, imax: _int_)

Esta función aplica la regla de tolerancia en los intervalos de salidas del Anexo 4, de acuerdo con la programación calculada por salidas por media hora según el Anexo 3.

Parámetros:

* `iprog`: Intervalo promedio calculado desde Anexo 3 (tiempo/salidas)
* `imin`: Mínimo intervalo observado en la programación de salidas según Anexo 4.
* `imax`: Máximo intervalo observado en la programación de salidas según Anexo 4.

---

### core.has_more_than_two_decimals

_core._**has_more_than_two_decimals**(value: _float_)

Esta función chequea si un valor tiene más de dos decimales. Retorna True si tiene más de dos decimales, False en caso contrario.

Parámetros:

* `value`: Valor a analizar.

---

### core.has_seconds_greater_than_zero

_core._**has_seconds_greater_than_zero**(time_obj: _datetime.time_)

Esta función chequea si un horario tiene segundos.

Parámetros:

* `time_obj`: Marca horaria a analizar.

---

### core.count_zeroes

_core._**count_zeroes**(list_: _list_)

Esta función cuenta cuántos ceros hay al inicio y al final de una lista. Retorna las cantidades en una tupla.

Parámetros:

* `list_`: Lista con valores enteros.

---

### core.asignacion

_core._**asignacion**(salidas_periodo: _int_, duracion_periodo: _int_, grad: _int_, mhvaciasinicio=0: _int_, mhvaciastermino=0: _int_)

Esta función realiza la distribución de salidas originalmente en un periodo, por cada media hora de operación del servicio-sentido-tipodía.

Parámetros:

* `salidas_periodo`: Cantidad de salidas asociadas al servicio-sentido-periodo.
* `duracion_periodo`: Duracion (en horas) del periodo.
* `grad`: Valor que indica si el próximo periodo aumenta o disminuye salidas.
* `mhvaciasinicio`: Cantidad de medias horas sin salidas al inicio del periodo.
* `mhvaciastermino`: Cantidad de medias horas sin salidas al final del periodo.

---

### core.dt_time_to_dt_dt

_core._**dt_time_to_dt_dt**(time: _any_)

Esta función recibe una marca horaria y la convierte en objeto datetime.datetime.

Parámetros:

* `time`: Marca horaria.

---

### core.all_to_dt_time

_core._**all_to_dt_time**(dt_time: _any_)

Esta función recibe una marca horaria (en cualquier formato) y la convierte en objeto datetime.datetime.

Parámetros:

* `dt_time`: Marca horaria.

---

### core.delete_files_in_folder

_core._**delete_files_in_folder**(folder_path: _str_)

Esta función recibe la dirección de una carpeta en el ordenador, y elimina todos los archivos en su interior.

Parámetros:

* `folder_path`: Dirección de una carpeta particular.

---

### core.periodo_inicio

_core._**periodo_inicio**(hora: _int_, minutos: _int_)

Esta función recibe un valor de horas y un valor de minutos, y retorna un objeto de tipo datetime.time aproximado a la media hora anterior de la marca horaria.

Parámetros:

* `hora`: Valor de horas.
* `minutos`: Valor de minutos.

---

### core.new_periodo_inicio

_core._**new_periodo_inicio**(hora: _int_)

Esta función recibe un valor de horas, y retorna un objeto de tipo datetime.time aproximado a la hora de la marca horaria.

Parámetros:

* `hora`: Valor de horas.

---

### core.aux_salidas

_core._**aux_salidas**(s_ant: _int_, s: _int_, s_sig: _int_)

Esta función recibe tres valores de salidas (para tres MH consecutivas) y retorna valores intermedios en función de ellos.

Parámetros:

* `s_ant`: Cantidad de salidas de la MH anterior.
* `s`: Cantidad de salidas de la MH actual.
* `s_sig`: Cantidad de salidas de la MH siguiente.

---

### core.clasif_an_frec

_core._**clasif_an_frec**(frec: _float_)

Esta función recibe un valor de frecuencias y retorna una clasificación para el análisis de frecuencias.

Parámetros:

* `frec`: Valor real asociado a buses por hora en un periodo.

## Clase PanelUS

### Atributos iniciales

* `PanelUS.unidad`
* `PanelUS.cons_un_chose_gate`
* `PanelUS.unidad`
* `PanelUS.unidad`
* `PanelUS.unidad`
* `PanelUS.unidad`
* `PanelUS.unidad`
* `PanelUS.unidad`
* `PanelUS.unidad`
* `PanelUS.unidad`
* `PanelUS.unidad`
* `PanelUS.unidad`
* `PanelUS.unidad`
* `PanelUS.unidad`
* `PanelUS.unidad`
* `PanelUS.unidad`
* `PanelUS.unidad`
* `PanelUS.unidad`
* `PanelUS.unidad`
* `PanelUS.unidad`
* `PanelUS.unidad`
* `PanelUS.unidad`
* `PanelUS.unidad`
* `PanelUS.unidad`