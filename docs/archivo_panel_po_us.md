# Front End (Interfaz)
## Paquetes

* `tkinter` - Generación de interfaces.
* `PIL (pillow)` - Gestión de imágenes.
* `threading` - Capacidad de ejecución de acciones en paralelo.
* `openpyxl` - Tratamiento de archivos Excel.
* `xlsxwriter` - Generador de archivos Excel.
* `tooltip` - Creación y visualización de mensajes 'on-cursor'.
* `pandastable` - Creación y visualización de Pandas DataFrames en tkinter.
* `warnings` - Gestión de mensajes de advertencia.
* `shutil` - Tratamiento de archivos Excel.
* `matplotlib` - Generación de gráficos 2D.
* `core` - Funcionamiento interno de Panel PO.

## Funciones nativas en Archivo 'panel_po_us.py'

### <span style="font-size:0.7em;">panel_po_us</span><span style="font-size:1.2em;">.__pop_up_savior__</span>

panel_po_us._**pop_up_savior**(df: _pandas.DataFrame_, tipo_archivo: _str_)

Función que permite exportar un DataFrame en un archivo Excel, con un nombre particular, unidad revisada, fecha y hora de revisión.

Parámetros:

* `df`: DataFrame de Pandas a exportar
* `tipo_archivo`: Nombre que se le desea otorgar al archivo Excel

---

### <span style="font-size:0.7em;">panel_po_us</span><span style="font-size:1.2em;">.__pop_up_savior_png__</span>

panel_po_us._**pop_up_savior_png**(figure: _matplotlib.Figure_, tipo_archivo: _str_)

Función que permite exportar un gráfico en un archivo PNG, con un nombre particular, unidad revisada, fecha y hora de revisión.

Parámetros:

* `figure`: Figura de Matplotlib a exportar
* `tipo_archivo`: Nombre que se le desea otorgar al archivo

---

### <span style="font-size:0.7em;">panel_po_us</span><span style="font-size:1.2em;">.__filter_df_show__</span>

panel_po_us._**filter_df_show**(table: _pandastable.Table_, df: _pandas.DataFrame_, n_col: _str_)

Función que se utiliza en ventanas emergentes; permite filtrar las tablas, mostrando las filas con problemas según la columna que se utilice para el filtro.

Parámetros:

* `table`: Objeto Table asociado a un DataFrame
* `df`: DataFrame de Pandas
* `n_col`: Nombre de la columna a filtrar

---

### <span style="font-size:0.7em;">panel_po_us</span><span style="font-size:1.2em;">.__filter_df_show_2_tipodia__</span>

panel_po_us._**filter_df_show_2_tipodia**(table: _pandastable.Table_, df: _pandas.DataFrame_, td: _str_)

Función que se utiliza en ventanas emergentes; permite filtrar las tablas por tipo de día.

Parámetros:

* `table`: Objeto Table asociado a un DataFrame
* `df`: DataFrame de Pandas
* `td`: Nombre del tipo de día que se desea filtrar

---

### <span style="font-size:0.7em;">panel_po_us</span><span style="font-size:1.2em;">.__change_df_view__</span>

panel_po_us._**change_df_view**(table: _pandastable.Table_, df: _pandas.DataFrame_, mha: _bool_)

Función que se utiliza en ventanas emergentes de comparación de Anexo 3 y Anexo 4; permite cambiar la vista y botones de la vista para observar según MH o Agrupación de MH.

Parámetros:

* `table`: Objeto Table asociado a un DataFrame
* `df`: DataFrame de Pandas
* `mha`: Variable booleana que permite el cambio de visa en botones de filtro de la ventana emergente

---

### <span style="font-size:0.7em;">panel_po_us</span><span style="font-size:1.2em;">.__check_params_a3__</span>

panel_po_us._**check_params_a3**()

Función que gatilla la revisión de consistencia interna en parámetros del Anexo 3. La función llama al proceso interno (siempre que haya un Anexo 3 Nuevo cargado) y luego genera una ventana emergente con dos posibles resultados: un mensaje de que el archivo es consistente, o una tabla con las filas del Anexo 3 que presentan inconsistencia. 

Si se presenta la tabla, además se presenta un botón para convertir la información en un archivo Excel que se descargue.

---

### <span style="font-size:0.7em;">panel_po_us</span><span style="font-size:1.2em;">.__check_params_a4__</span>

panel_po_us._**check_params_a4**()

Función que gatilla la revisión de consistencia interna en parámetros del Anexo 4. La función llama al proceso interno (siempre que haya un Anexo 4 Nuevo cargado) y luego genera una ventana emergente con dos posibles resultados: un mensaje de que el archivo es consistente, o una tabla con las filas del Anexo 4 que presentan inconsistencia. 

Si se presenta la tabla, además se presenta un botón para convertir la información en un archivo Excel que se descargue.

---

### <span style="font-size:0.7em;">panel_po_us</span><span style="font-size:1.2em;">.__comp_a3v_a3n_panel__</span>

panel_po_us._**comp_a3v_a3n_panel**()

Función que gatilla la revisión comparativa entre parámetros del Anexo 3 Nuevo y el Vigente. La función llama al proceso interno (siempre que haya un Anexo 3 Nuevo cargado y un Anexo 3 Vigente cargado) y luego genera una ventana emergente con dos posibles resultados: un mensaje de que ambos archivos son consistentes, o una tabla comparativa con los parámetros que no coinciden. 

También se presentan algunos botones para filtrar la información de la tabla por tipo de día, o parámetro de comparación.

Si se presenta la tabla, además se presenta un botón para convertir la información en un archivo Excel que se descargue.

---

### <span style="font-size:0.7em;">panel_po_us</span><span style="font-size:1.2em;">.__comp_time_a1_a4__</span>

panel_po_us._**comp_time_a1_a4**()

Función que gatilla la revisión comparativa entre horarios de operación según el Anexo 1 y la programación de primera y última salida del día según Anexo 4. La función llama al proceso interno (siempre que haya un Anexo 1 Nuevo cargado y un Anexo 4 Nuevo cargado) y luego genera una ventana emergente con dos posibles resultados: un mensaje de que ambos archivos son consistentes, o una tabla comparativa con los parámetros que no coinciden. 

También se presentan algunos botones para filtrar la información de la tabla por tipo de día, o parámetro de comparación.

Si se presenta la tabla, además se presenta un botón para convertir la información en un archivo Excel que se descargue.

---

### <span style="font-size:0.7em;">panel_po_us</span><span style="font-size:1.2em;">.__comp_param_a3_a4__</span>

panel_po_us._**comp_param_a3_a4**()

Función que gatilla la revisión comparativa entre parámetros de operación según el Anexo 3 y el Anexo 4. La función llama al proceso interno (siempre que haya un Anexo 1 Nuevo cargado y un Anexo 4 Nuevo cargado) y luego genera una ventana emergente con dos posibles resultados: un mensaje de que ambos archivos son consistentes, o una tabla comparativa con los parámetros que no coinciden. 

También se presentan algunos botones para filtrar la información de la tabla por tipo de día, o parámetro de comparación.

Si se presenta la tabla, además se presenta un botón para convertir la información en un archivo Excel que se descargue