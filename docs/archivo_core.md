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

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__unidad__ </span> 

(type: _str_, default = '0')

Variable que guarda el valor de la unidad de servicio seleccionada por usuario para generar revisiones específicas en Panel.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__anexo1__ </span>

(type: _pandas.DataFrame_, default = pandas.DataFrame())

Variable que guarda la estructura del DataFrame con la información completa del Anexo 1.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__anexo1_name__</span>

(type: _str_, default = 'No cargado')

Variable que guarda el nombre del archivo Excel que contiene la información del Anexo 1 Nuevo.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__anexo3__</span>

(type: _pandas.DataFrame_, default = pandas.DataFrame())

Variable que guarda la estructura del DataFrame con la información completa del Anexo 3 Nuevo.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__anexo3_name__</span>

(type: _str_, default = 'No cargado')

Variable que guarda el nombre del archivo Excel que contiene la información del Anexo 3 Nuevo.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__anexo3b__</span>

(type: _pandas.DataFrame_, default = pandas.DataFrame())

Variable que guarda la estructura del DataFrame con la información completa del Anexo 3 Vigente.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__anexo3b_name__</span>

(type: _str_, default = 'No cargado')

Variable que guarda el nombre del archivo Excel que contiene la información del Anexo 3 Vigente.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__anexo4__</span>

(type: _pandas.DataFrame_, default = pandas.DataFrame())

Variable que guarda la estructura del DataFrame con la información completa del Anexo 4 Nuevo.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__anexo4_name__</span>

(type: _str_, default = 'No cargado')

Variable que guarda el nombre del archivo Excel que contiene la información del Anexo 4 Nuevo.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__anexo4_solocomerc__</span>

(type: _pandas.DataFrame_, default = pandas.DataFrame())

Variable que guarda la estructura del DataFrame con la información de salidas comerciales (C01) del Anexo 4 Nuevo.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__anexo4_capac__</span>

(type: _pandas.DataFrame_, default = pandas.DataFrame())

Variable que guarda la estructura del DataFrame con la información de capacidades de buses del Anexo 4 Nuevo.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__anexo4b__</span>

(type: _pandas.DataFrame_, default = pandas.DataFrame())

Variable que guarda la estructura del DataFrame con la información completa del Anexo 4 Vigente.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__anexo4b_name__</span>

(type: _str_, default = 'No cargado')

Variable que guarda el nombre del archivo Excel que contiene la información del Anexo 4 Vigente.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__anexo4b_solocomerc__</span>

(type: _pandas.DataFrame_, default = pandas.DataFrame())

Variable que guarda la estructura del DataFrame con la información de salidas comerciales (C01) del Anexo 4 Vigente.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__anexo4b_capac__</span>

(type: _pandas.DataFrame_, default = pandas.DataFrame())

Variable que guarda la estructura del DataFrame con la información de capacidades de buses del Anexo 4 Vigente.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__consolidado__</span>

(type: _pandas.DataFrame_, default = pandas.DataFrame())

Variable que guarda la estructura del DataFrame con la información del Consolidado de Salidas.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__consolidado_name__</span>

(type: _str_, default = 'No cargado')

Variable que guarda el nombre del archivo Excel que contiene la información del Consolidado de Salidas.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__consolidado_frec__</span>

(type: _pandas.DataFrame_, default = pandas.DataFrame())

Variable que guarda la estructura del DataFrame con información de frecuencias, calculadas desde el Consolidado de Salidas.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__consolidado_par__</span>

(type: _pandas.DataFrame_, default = pandas.DataFrame())

Variable que guarda la estructura del DataFrame con la información del Registro Consolidado de Paradas.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__consolidado_par_name__</span>

(type: _str_, default = 'No cargado')

Variable que guarda el nombre del archivo Excel que contiene la información del Registro Consolidado de Paradas.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__base_cons__</span>

(type: _pandas.DataFrame_, default = pandas.DataFrame())

Variable que guarda la estructura del DataFrame con la información base de Servicios-Sentido en el orden preestablecido histórico de los Consolidados.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__base_cons_name__</span>

(type: _str_, default = 'No cargado')

Variable que guarda el nombre del archivo Excel que contiene la información base de Servicios-Sentido en el orden preestablecido histórico de los Consolidados.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__periodos__</span>

(type: _pandas.DataFrame_, default = Información de Periodos*)

Variable que guarda la estructura del DataFrame con información de periodos según tipo día, media hora, duración de cada periodo y otras columnas que auxilian la tarea de distribución de salidas asignadas por periodo.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__periodos_data__</span>

(type: _pandas.DataFrame_, default = Información de Periodos*)

Variable que guarda la estructura del DataFrame con información de periodos según tipo día y media hora. Guarda la estructura original de la tabla anterior, sin las columnas auxiliares del proceso de distribución de salidas asignadas por periodo

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__gradiente__</span>

(type: _pandas.DataFrame_, default = None)

Variable que guarda la estructura del DataFrame con información de tendencias en la asignación de salidas por periodo en el Consolidado. Por ejemplo, si en el siguiente periodo aumentan o disminuyen las salidas. 

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__anexo3_w_inconsist__</span>

(type: _pandas.DataFrame_, default = None)

Variable que guarda la estructura del DataFrame resultante del análisis de consistencia del Anexo 3 Nuevo. 

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__anexo4_w_inconsist__</span>

(type: _pandas.DataFrame_, default = None)

Variable que guarda la estructura del DataFrame resultante del análisis de consistencia del Anexo 4 Nuevo. 

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__validacion_a4_a1__</span>

(type: _pandas.DataFrame_, default = None)

Variable que guarda la estructura del DataFrame resultante de la comparación de horarios de salida (A4) y operación (A1).

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__validacion_a4_a3__</span>

(type: _pandas.DataFrame_, default = None)

Variable que guarda la estructura del DataFrame resultante de la comparación de parámetros de operación definidos en Anexo 3 y Anexo 4.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__validacion_a4_a3_x_mha__</span>

(type: _pandas.DataFrame_, default = None)

Variable que guarda la estructura del DataFrame resultante de la comparación de parámetros de operación definidos en Anexo 3 y Anexo 4, por media hora agrupada según Anexo 3.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__result_comp_a3v_a3n__</span>

(type: _pandas.DataFrame_, default = None)

Variable que guarda la estructura del DataFrame resultante de la comparación de parámetros de operación definidos en Anexo 3 Nuevo y Anexo 3 Vigente.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__validacion_a4_interv_mha_trusted__</span>

(type: _pandas.DataFrame_, default = None)

Variable que guarda la estructura del DataFrame resultante de la validación de intervalos programados de salidas en el Anexo 4, considerando las agrupaciones del Anexo 3.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__anexo1_new__</span>

(type: _pandas.DataFrame_, default = None)

Variable que guarda la estructura del DataFrame con la información formateada del Anexo 1, construido a partir del Anexo 4.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__a3_from_a4_final__</span>

(type: _pandas.DataFrame_, default = None)

Variable que guarda la estructura del DataFrame con la información formateada del Anexo 3, construido a partir del Anexo 4.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__a4_from_a3__</span>

(type: _pandas.DataFrame_, default = None)

Variable que guarda la estructura del DataFrame con la información formateada del Anexo 4, construido a partir del Anexo 3.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__anexo3_ns_w_base__</span>

(type: _pandas.DataFrame_, default = None)

Variable que guarda la estructura del DataFrame con información formateada del Anexo 3, construido a partir del Consolidado de Salidas (distribuidas).

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__perfil_flota__</span>

(type: _pandas.DataFrame_, default = None)

Variable que guarda la estructura del DataFrame con información de cantidad de flota operando por cada media hora en una unidad.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__cons_a3_frec__</span>

(type: _pandas.DataFrame_, default = None)

Variable que guarda la estructura del DataFrame con información de frecuencias consolidada por periodo, para preparar el archivo Consolidado de Parámetros.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__cons_a3_cap__</span>

(type: _pandas.DataFrame_, default = None)

Variable que guarda la estructura del DataFrame con información de capacidades consolidada por periodo, para preparar el archivo Consolidado de Parámetros.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__cons_a3_sal__</span>

(type: _pandas.DataFrame_, default = None)

Variable que guarda la estructura del DataFrame con información de salidas consolidada por periodo, para preparar el archivo Consolidado de Parámetros.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__cons_a3_vel__</span>

(type: _pandas.DataFrame_, default = None)

Variable que guarda la estructura del DataFrame con información de velocidades promedio consolidada por periodo, para preparar el archivo Consolidado de Parámetros.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__cons_a3_dist__</span>

(type: _pandas.DataFrame_, default = None)

Variable que guarda la estructura del DataFrame con información de distancias totales consolidada por periodo, para preparar el archivo Consolidado de Parámetros.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__cons_a3_dist_int__</span>

(type: _pandas.DataFrame_, default = None)

Variable que guarda la estructura del DataFrame con información de distancias totales consolidada por periodo, para preparar el archivo Consolidado de Parámetros.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__cons_a3_fmax__</span>

(type: _pandas.DataFrame_, default = None)

Variable que guarda la estructura del DataFrame con información de flota máxima consolidada por periodo, para preparar el archivo Consolidado de Parámetros.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__a3_cons_mh__</span>

(type: _pandas.DataFrame_, default = None)

Variable que guarda la estructura del DataFrame con información consolidada de frecuencias por media hora.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__a3_lab_n__</span>

(type: _bool_, default = False)

Variable booleana que identifica si hay días laborales en el Anexo 3 Nuevo.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__a3_sab_n__</span>

(type: _bool_, default = False)

Variable booleana que identifica si hay días sábado en el Anexo 3 Nuevo.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__a3_dom_n__</span>

(type: _bool_, default = False)

Variable booleana que identifica si hay días domingo en el Anexo 3 Nuevo.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__a3_lab_v__</span>

(type: _bool_, default = False)

Variable booleana que identifica si hay días laborales en el Anexo 3 Vigente.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__a3_sab_v__</span>

(type: _bool_, default = False)

Variable booleana que identifica si hay días sábado en el Anexo 3 Vigente.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__a3_dom_v__</span>

(type: _bool_, default = False)

Variable booleana que identifica si hay días domingo en el Anexo 3 Vigente.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__df_km__</span>

(type: _pandas.DataFrame_, default = pandas.DataFrame())

Variable que guarda la estructura del DataFrame con información de kilómetros totales por tipo día.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__cons_interv__</span>

(type: _pandas.DataFrame_, default = pandas.DataFrame())

Variable que guarda la estructura del DataFrame con información de intervalo promedio de salidas por periodo (formato Consolidado).

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__cuenta_ss__</span>

(type: _pandas.DataFrame_, default = None)

Variable que guarda la estructura del DataFrame con información de cantidad de Servicios-Sentido por unidad y por periodo que se agregan por cada categoría de frecuencias.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__perc_ss_nivel_frec__</span>

(type: _pandas.DataFrame_, default = None)

Variable que guarda la estructura del DataFrame con información final de proporciones (porcentaje) de Servicios-Sentido por unidad y por periodo que se agregan por cada categoría de frecuencias.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__revision_biportal__</span>

(type: _pandas.DataFrame_, default = pandas.DataFrame())

Variable que guarda la estructura del DataFrame con información de salidas programadas en Anexo 4 asignadas erróneamente a buses que no pueden operar en servicios que atienden paraderos de puerta izquierda.

---

### Funciones (métodos)

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__reset__</span>

_PanelUS_.**reset**()

Reinicia todos los atributos iniciales del Panel.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__consulta_de_salidas__</span>

_PanelUS_._**consulta_de_salidas**(servicio: _str_, sentido: _str_, periodo: _str_)

Lee el Consolidado de Salidas y retorna el número de salidas efectuadas durante el periodo según el consolidado. Si no encuentra el Servicio-Sentido-Periodo retorna un valor NaN.
        
Parámetros

* `servicio`: Identificador del servicio (Código TS) 
* `sentido`: Identificador del sentido ("Ida", "Ret")
* `periodo`: Identificador del periodo (Abreviatura)

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__consulta_de_gradiente__</span>

_PanelUS_._**consulta_de_gradiente**(servicio: _str_, sentido: _str_, periodo: _str_)

Lee el Consolidado de Salidas y retorna el valor del gradiente en el periodo según el consolidado-gradiente. Si no encuentra el Servicio-Sentido-Periodo retorna un valor NaN.
        
Parámetros

* `servicio`: Identificador del servicio (Código TS) 
* `sentido`: Identificador del sentido ("Ida", "Ret")
* `periodo`: Identificador del periodo (Abreviatura)

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__save_all_anexos__</span>

_PanelUS_._**save_all_anexos**()

Guarda todos los archivos cargados en el Panel, en formato encriptado, para permitir su recarga al reiniciar el programa.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__load_all_anexos__</span>

_PanelUS_._**load_all_anexos**(files_in_memory: _list_)

Carga todos los archivos guardados en la memoria del Panel.
        
Parámetros

* `files_in_memory`: Lista con los nombres de los archivos guardados en la memoria del panel. 

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__clear_all_anexos__</span>

_PanelUS_._**clear_all_anexos**(path_: _str_)

Borra todos los archivos guardados en la memoria del Panel.
        
Parámetros

* `path_`: Nombre de la dirección de la carpeta de memoria. 

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__load_A1__</span>

_PanelUS_._**load_A1**()

Proceso que carga un archivo Excel Anexo 1 Nuevo.

El proceso es llamado por una función de la interfaz, y permite la interacción en los casos que no se seleccione ningún archivo, así también gatilla variables booleanas para alertar cuando el archivo tiene fórmulas u hojas ocultas. También está diseñado para renombrar las columnas, y así no tener conflictos por alteraciones o typos en los archivos originales.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__load_A3__</span>

_PanelUS_._**load_A3**()

Proceso que carga un archivo Excel Anexo 3 Nuevo.

El proceso es llamado por una función de la interfaz, y permite la interacción en los casos que no se seleccione ningún archivo, así también gatilla variables booleanas para alertar cuando el archivo tiene fórmulas u hojas ocultas. También está diseñado para renombrar las columnas, y así no tener conflictos por alteraciones o typos en los archivos originales.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__load_A4__</span>

_PanelUS_._**load_A4**()

Proceso que carga un archivo Excel Anexo 4 Nuevo.

El proceso es llamado por una función de la interfaz, y permite la interacción en los casos que no se seleccione ningún archivo, así también gatilla variables booleanas para alertar cuando el archivo tiene fórmulas, hojas ocultas o las marcas temporales sin el formato adecuado. También está diseñado para renombrar las columnas, y así no tener conflictos por alteraciones o typos en los archivos originales. Desde el Anexo 4 se obtienen la programación completa de salidas, la programación de salidas comerciales, y las capacidades de buses programados.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__load_A1b__</span>

_PanelUS_._**load_A1b**()

Proceso que carga un archivo Excel Anexo 1 Vigente.

El proceso es llamado por una función de la interfaz, y permite la interacción en los casos que no se seleccione ningún archivo, así también gatilla variables booleanas para alertar cuando el archivo tiene fórmulas u hojas ocultas. También está diseñado para renombrar las columnas, y así no tener conflictos por alteraciones o typos en los archivos originales.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__load_A3b__</span>

_PanelUS_._**load_A3b**()

Proceso que carga un archivo Excel Anexo 3 Vigente.

El proceso es llamado por una función de la interfaz, y permite la interacción en los casos que no se seleccione ningún archivo, así también gatilla variables booleanas para alertar cuando el archivo tiene fórmulas u hojas ocultas. También está diseñado para renombrar las columnas, y así no tener conflictos por alteraciones o typos en los archivos originales.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__load_A4b__</span>

_PanelUS_._**load_A4b**()

Proceso que carga un archivo Excel Anexo 4 Vigente.

El proceso es llamado por una función de la interfaz, y permite la interacción en los casos que no se seleccione ningún archivo, así también gatilla variables booleanas para alertar cuando el archivo tiene fórmulas u hojas ocultas. También está diseñado para renombrar las columnas, y así no tener conflictos por alteraciones o typos en los archivos originales. Desde el Anexo 4 se obtienen la programación completa de salidas, la programación de salidas comerciales, y las capacidades de buses programados.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__load_cons__</span>

_PanelUS_._**load_cons**()

Proceso que carga un archivo Consolidado de Salidas.

El proceso es llamado por una función de la interfaz, y permite la interacción en los casos que no se seleccione ningún archivo, así también gatilla variables booleanas para alertar cuando el archivo tiene fórmulas u hojas ocultas. También está diseñado para renombrar las columnas, y así no tener conflictos por alteraciones o typos en los archivos originales.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__consolidado_loader__</span>

_PanelUS_._**consolidado_loader**()

Procesamiento del archivo Consolidado de Salidas, para generar estructuras de datos auxiliares para la distribución de salidas por media hora y el consolidado de frecuencias.

El proceso es llamado por al interior de load_cons, así también cuando se realiza una carga del consolidado desde la memoria.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__load_conspar__</span>

_PanelUS_._**load_conspar**()

Proceso que carga un archivo Consolidado de Paradas.

El proceso es llamado por una función de la interfaz, y permite la interacción en los casos que no se seleccione ningún archivo, así también gatilla variables booleanas para alertar cuando el archivo tiene fórmulas u hojas ocultas. También está diseñado para renombrar las columnas, y así no tener conflictos por alteraciones o typos en los archivos originales.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__load_base_cons__</span>

_PanelUS_._**load_base_cons**()

Proceso que carga un archivo Base de Consolidado (para obtener el orden de servicios del archivo Consolidado).

El proceso es llamado por una función de la interfaz, y permite la interacción en los casos que no se seleccione ningún archivo, así también gatilla variables booleanas para alertar cuando el archivo tiene fórmulas u hojas ocultas. También está diseñado para renombrar las columnas, y así no tener conflictos por alteraciones o typos en los archivos originales.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__check_param_a3__</span>

_PanelUS_._**check_param_a3**()

Proceso que evalúa la consistencia interna del Anexo 3.

El proceso considera:

* Evaluar si las distancias están truncadas hasta dos decimales

* Evaluar si las velocidades están truncadas hasta dos decimales

* Evaluar si las marcas horarias en la columna MH no tienen segundos

* Evaluar si la unidad de servicio de la columna es equivalente a la seleccionada en el programa

* Evaluar si no existen servicios inyección en el archivo

El proceso guarda en una variable los casos en los que la evaluación falla.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__check_param_a4__</span>

_PanelUS_._**check_param_a4**()

Proceso que evalúa la consistencia interna del Anexo 4.

El proceso considera:

* Evaluar si las marcas horarias en las columnas HORA_INICIO, PERIODO_INICIO, HORA_FIN, PERIODO_FIN y DURACION no tienen segundos

* Evaluar si las distancias están truncadas hasta dos decimales

* Evaluar si no existen datos incompletos (NaN)

* Evaluar si la unidad de servicio de la columna es equivalente a la seleccionada en el programa

El proceso guarda en una variable los casos en los que la evaluación falla.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__compare_a3v_a3n__</span>

_PanelUS_._**compare_a3v_a3n**()

Proceso que compara los parámetros de operación entre el Anexo 3 Vigente y el Anexo 3 Nuevo.

La comparación de parámetros se realiza a nivel de Salidas, Velocidad, Distancia Base, Distancia Integrada, Indicador de Tiempo de Espera y Agrupación de MH.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__compare_a1_a4__</span>

_PanelUS_._**compare_a1_a4**()

Proceso que compara los horarios de operación según el Anexo 1, con las primera y última salidas del Anexo 4, por cada Servicio-Sentido-TipoDía.

Para realizar el proceso se debe obtener las primera y última salida del Anexo 4 (a partir del proceso "genera_a1_from_a4") y realizar la comparación con el Anexo 1.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__genera_a1_from_a4__</span>

_PanelUS_._**genera_a1_from_a4**()

Proceso que genera una estructura como la hoja de Horarios de Operación del Anexo 1, identificando de forma correcta los casos en los que existe más de un tramo de operación (y por tanto más de un horario de inicio y más de un horario de fin). 

Para realizar esto, toma como supuesto que __[no existe una diferencia menor a 3 horas entre el fin de un tramo y el inicio de otro]__, por lo que se centra en la identificación de gaps de tiempo superiores a 3 horas en los tiempos de salida de un tipo día para identificar más de un tramo, o si los inicios y fin se encuentran muy cercanos durante el espacio de la madrugada.

El proceso guarda en una variable los casos en los que los horarios no coinciden.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__compare_a3_a4__</span>

_PanelUS_._**compare_a3_a4**()

Proceso que compara los parámetros de operación según el Anexo 3, con los parámetros que son posibles de estimar a partir de la programación de salidas del Anexo 4, por cada Servicio-Sentido-TipoDía.

Para realizar el proceso se procesa el anexo 4, obteniendo las medidas o parámetros de operación según las características de la programación de salidas, consolidando la información por media hora, de forma de poder comparar directamente la información del Anexo 3.

El proceso guarda en una variable los casos en los que los parámetros no coinciden.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__check_intervalos_a3_trusted__</span>

_PanelUS_._**check_intervalos_a3_trusted**()

Proceso que evalúa si los intervalos entre salidas programadas según el Anexo 4, cumplen con las restricciones de programación según el intervalo programado del Anexo 3 (tiempo/salidas).

El proceso se genera de acuerdo con la regla señalada en el Manual de Programación US.

El proceso guarda en una variable los casos en los que el intervalo programado en el Anexo 4 no cumple la regla del Manual.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__a3_newslds_w_base__</span>

_PanelUS_._**a3_newslds_w_base**()

Proceso que genera una estructura de datos con información del Anexo 3 a partir de la información de salidas del Consolidado, y los horarios de operación del Anexo 1. El proceso permite generar archivos de parámetros de operación desde el Consolidado, para los fines que se estimen necesarios.

El proceso está basado en una rutina de asignación de salidas por media hora, y además contempla la generación óptima de una columna con las agrupaciones de media hora. Sin embargo, el proceso está diseñado para introducir las modificaciones de salidas y agrupaciones solo en los periodos en los que hubo cambios (de acuerdo con el Consolidado de Salidas).

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__genera_a4_from_a3__</span>

_PanelUS_._**genera_a4_from_a3**()

Proceso que genera una estructura de datos con información del  Anexo 4 (Tabla Horaria Simplificada) a partir de la información de parámetros de operación según el Anexo 3.

El proceso está basado en una rutina de programación de salidas considerando las agrupaciones de MH y los horarios de operación según el Anexo 1.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__genera_a3_from_a4__</span>

_PanelUS_._**genera_a3_from_a4**()

Proceso que genera una estructura de datos con información del Anexo 3 a partir de la información de salidas programadas del Anexo 4.

El proceso consolida por media hora la información programada (similar a lo que se procesa en "compare_a3_a4").

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__genera_cons_frec__</span>

_PanelUS_._**genera_cons_frec**()

Proceso que genera una estructura de datos con información de frecuencias por periodo (similar al Consolidado de Salidas).

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__calc_perfil_flota__</span>

_PanelUS_._**calc_perfil_flota**()

Proceso que genera una estructura de datos con información de flota operativa (cantidad de buses) por media hora en la unidad de servicio.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__cons_periodo_us__</span>

_PanelUS_._**cons_periodo_us**()

Proceso que genera una estructura de datos con información consolidada de parámetros de operación por periodo.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__cons_mh_us__</span>

_PanelUS_._**cons_mh_us**()

Proceso que genera una estructura de datos con información consolidada de frecuencias por media hora.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__reagrupa_a3__</span>

_PanelUS_._**reagrupa_a3**()

Proceso que genera una nueva columna de agrupación de medias horas en el Anexo 3 Nuevo. 

Este proceso se basa en una rutina de agrupación de medias horas con reglas que permitan una distribución suave de las salidas en cada media hora, y evitar una programación inequitativa de salidas.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__conteo_km__</span>

_PanelUS_._**conteo_km**()

Proceso que genera una nueva estructura de datos con el resumen de los kilómetros programados de la unidad, por tipo de día, a partir de cada Anexo 3 (Nuevo y Vigente) comparandolos entre sí.

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__valid_cons_w_intervs__</span>

_PanelUS_._**valid_cons_w_intervs**()

Proceso que genera una nueva estructura de datos con el cálculo de intervalos de salida programada, a partir de las salidas totales por periodo del Consolidado de Salidas.

Esta herramienta permite alertar los casos en que la programación de la salidas tiene tal nivel que puede producir intervalos de salida fuera del estándar (máximo 30 minutos en servicios regulares).

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__generar_bases_analys_frec_cons__</span>

_PanelUS_._**generar_bases_analys_frec_cons**()

Proceso que genera una nueva estructura de datos analizando las frecuencias programadas promedio por periodo y SS, permitiendo su clasificación y revisión. 

---

#### <span style="font-size:0.7em;">PanelUS</span><span style="font-size:1.2em;">.__revisar_a4_buses_biportal__</span>

_PanelUS_._**revisar_a4_buses_biportal**()

Proceso que revisa que las salidas programadas en Anexo 4 en servicios que sirven en paradas de peurta izquierda, cuenten solo con buses de puerta izquierda programados.


