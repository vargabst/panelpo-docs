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

Si se presenta la tabla, además se presenta un botón para convertir la información en un archivo Excel que se descargue.

Para esta función se ha programado una forma de cambiar todo el menú de filtros, ya que la información puede compararse a nivel de media hora, o bien a nivel de agrupación de medias horas.

---

### <span style="font-size:0.7em;">panel_po_us</span><span style="font-size:1.2em;">.__check_intervalos_a4__</span>

panel_po_us._**check_intervalos_a4**()

Función que gatilla la revisión de consistencia en los intervalos entre salidas programadas del Anexo 4 Nuevo, considerando la agrupación de medias horas que se publica en el Anexo 3 Nuevo.
La función llama al proceso interno (siempre que haya un Anexo 3 Nuevo cargado y un Anexo 4 Nuevo cargado) y luego genera una ventana emergente con dos posibles resultados: un mensaje de que los intervalos cumplen las reglas de programación, o una tabla comparativa con los parámetros que no cumplen. 

También se presentan algunos botones para filtrar la información de la tabla por tipo de día.

Si se presenta la tabla, además se presenta un botón para convertir la información en un archivo Excel que se descargue.

---

### <span style="font-size:0.7em;">panel_po_us</span><span style="font-size:1.2em;">.__save_a1_from_a4__</span>

panel_po_us._**save_a1_from_a4**()

Función que gatilla la generación de archivo Anexo 1 a partir de Tabla Horaria Anexo 4.

La función llama al proceso interno (siempre que haya un Anexo 4 Nuevo cargado) y luego genera una ventana emergente para escoger la dirección donde guardar el archivo.

---

### <span style="font-size:0.7em;">panel_po_us</span><span style="font-size:1.2em;">.__save_a3_from_a4__</span>

panel_po_us._**save_a3_from_a4**()

Función que gatilla la generación de archivo Anexo 3 a partir de Tabla Horaria Anexo 4.

La función llama al proceso interno (siempre que haya un Anexo 4 Nuevo cargado) y luego genera una ventana emergente para escoger la dirección donde guardar el archivo.

---

### <span style="font-size:0.7em;">panel_po_us</span><span style="font-size:1.2em;">.__save_a4_from_a3__</span>

panel_po_us._**save_a4_from_a3**()

Función que gatilla la generación de archivo Tabla Horaria Anexo 4 a partir de un Anexo 3 Nuevo cargado.

La función llama al proceso interno (siempre que haya un Anexo 3 Nuevo cargado) y luego genera una ventana emergente para escoger la dirección donde guardar el archivo.

---

### <span style="font-size:0.7em;">panel_po_us</span><span style="font-size:1.2em;">.__save_a3_ns_w_base__</span>

panel_po_us._**save_a3_ns_w_base**()

Función que gatilla la generación de archivo Anexo 3 a partir de un Consolidado de Salidas y un Anexo 1 (para vigencia de servicios).

La función llama al proceso interno (siempre que haya un Anexo 1 Nuevo cargado y un Consolidado de Salidas cargado) y luego genera una ventana emergente para escoger la dirección donde guardar el archivo.

---

### <span style="font-size:0.7em;">panel_po_us</span><span style="font-size:1.2em;">.__calc_perfil_flota__</span>

panel_po_us._**calc_perfil_flota**()

Función que gatilla la generación de archivo Perfil de Flota a partir de un Anexo 4 Nuevo.

La función llama al proceso interno (siempre que haya un Anexo 4 Nuevo cargado) y luego genera una ventana emergente para escoger la dirección donde guardar el archivo.

---

### <span style="font-size:0.7em;">panel_po_us</span><span style="font-size:1.2em;">.__genera_cons_mh_us__</span>

panel_po_us._**genera_cons_mh_us**()

Función que gatilla la generación de archivo Consolidado Frecuencias MH a partir de un Anexo 3 Nuevo y un archivo Base Consolidado.

La función llama al proceso interno (siempre que haya un Anexo 3 Nuevo cargado y un Base Consolidado cargado) y luego genera una ventana emergente para escoger la dirección donde guardar el archivo.

---

### <span style="font-size:0.7em;">panel_po_us</span><span style="font-size:1.2em;">.__genera_cons_periodo_us__</span>

panel_po_us._**genera_cons_periodo_us**()

Función que gatilla la generación de archivo Consolidado de Parámetros a partir de un Anexo 3 Nuevo y un archivo Base Consolidado.

La función llama al proceso interno (siempre que haya un Anexo 3 Nuevo cargado y un Base Consolidado cargado) y luego genera una ventana emergente para escoger la dirección donde guardar el archivo.

---

### <span style="font-size:0.7em;">panel_po_us</span><span style="font-size:1.2em;">.__save_a3_regroup__</span>

panel_po_us._**save_a3_regroup**()

Función que gatilla la generación de archivo Anexo 3 con agrupación de MH óptima modificada, a partir de un Anexo 3 Nuevo.

La función llama al proceso interno (siempre que haya un Anexo 3 Nuevo cargado) y luego genera una ventana emergente para escoger la dirección donde guardar el archivo.

---

### <span style="font-size:0.7em;">panel_po_us</span><span style="font-size:1.2em;">.__vis_load_a1__</span>

panel_po_us._**vis_load_a1**()

Función que gatilla la carga/lectura de archivo Anexo 1 Nuevo.

La función llama al proceso interno, generando una ventana emergente para escoger el archivo y procesar su información.

---

### <span style="font-size:0.7em;">panel_po_us</span><span style="font-size:1.2em;">.__vis_load_a3__</span>

panel_po_us._**vis_load_a3**()

Función que gatilla la carga/lectura de archivo Anexo 3 Nuevo.

La función llama al proceso interno, generando una ventana emergente para escoger el archivo y procesar su información.

---

### <span style="font-size:0.7em;">panel_po_us</span><span style="font-size:1.2em;">.__vis_load_a4__</span>

panel_po_us._**vis_load_a4**()

Función que gatilla la carga/lectura de archivo Anexo 4 Nuevo.

La función llama al proceso interno, generando una ventana emergente para escoger el archivo y procesar su información.

---

### <span style="font-size:0.7em;">panel_po_us</span><span style="font-size:1.2em;">.__vis_load_a3b__</span>

panel_po_us._**vis_load_a3b**()

Función que gatilla la carga/lectura de archivo Anexo 3 Vigente.

La función llama al proceso interno, generando una ventana emergente para escoger el archivo y procesar su información.

---

### <span style="font-size:0.7em;">panel_po_us</span><span style="font-size:1.2em;">.__vis_load_a4b__</span>

panel_po_us._**vis_load_a4b**()

Función que gatilla la carga/lectura de archivo Anexo 4 Vigente.

La función llama al proceso interno, generando una ventana emergente para escoger el archivo y procesar su información.

---

### <span style="font-size:0.7em;">panel_po_us</span><span style="font-size:1.2em;">.__vis_load_base_cons__</span>

panel_po_us._**vis_load_base_cons**()

Función que gatilla la carga/lectura de archivo Base Consolidado.

La función llama al proceso interno, generando una ventana emergente para escoger el archivo y procesar su información.

---

### <span style="font-size:0.7em;">panel_po_us</span><span style="font-size:1.2em;">.__vis_load_cons__</span>

panel_po_us._**vis_load_cons**()

Función que gatilla la carga/lectura de archivo Consolidado de Salidas.

La función llama al proceso interno, generando una ventana emergente para escoger el archivo y procesar su información.

---

### <span style="font-size:0.7em;">panel_po_us</span><span style="font-size:1.2em;">.__vis_load_conspar__</span>

panel_po_us._**vis_load_conspar**()

Función que gatilla la carga/lectura de archivo Consolidado de Paradas.

La función llama al proceso interno, generando una ventana emergente para escoger el archivo y procesar su información.

---

### <span style="font-size:0.7em;">panel_po_us</span><span style="font-size:1.2em;">.__selection_changed_main__</span>

panel_po_us._**selection_changed_main**(event: _None_)

Función que regula la selección de unidad de servicio para la revisión de archivos. De esta forma, se puede filtrar la información de servicios de la unidad.

---

### <span style="font-size:0.7em;">panel_po_us</span><span style="font-size:1.2em;">.__save_all_anexos__</span>

panel_po_us._**save_all_anexos**()

Función que gatilla el guardado de los archivos cargados en el panel, en el directorio de memoria.

La función llama al proceso interno y al final de su ejecución entrega un mensaje de éxito.

---

### <span style="font-size:0.7em;">panel_po_us</span><span style="font-size:1.2em;">.__reset_button__</span>

panel_po_us._**reset_button**(but: _tkinter.Button_)

Función que devuelve el estado del botón a su formato inicial.

---

### <span style="font-size:0.7em;">panel_po_us</span><span style="font-size:1.2em;">.__button_loading__</span>

panel_po_us._**button_loading**(but: _tkinter.Button_)

Función que cambia el estado del botón al formato definido cuando el botón ha sido accionado y se está realizando el proceso asociado (botón amarillo).

---

### <span style="font-size:0.7em;">panel_po_us</span><span style="font-size:1.2em;">.__button_loaded__</span>

panel_po_us._**button_loaded**(but: _tkinter.Button_)

Función que cambia el estado del botón al formato definido cuando el botón ha sido accionado y el proceso asociado ya ha terminado (botón verde).

---

### <span style="font-size:0.7em;">panel_po_us</span><span style="font-size:1.2em;">.__load_all_anexos__</span>

panel_po_us._**load_all_anexos**()

Función que gatilla la recarga, al panel, de los archivos guardados en el directorio de memoria.

La función llama al proceso interno y al final de su ejecución entrega un mensaje de éxito.

---

### <span style="font-size:0.7em;">panel_po_us</span><span style="font-size:1.2em;">.__clear_all_anexos__</span>

panel_po_us._**clear_all_anexos**()

Función que gatilla la eliminación de los archivos guardados en el directorio de memoria y cargados en el panel.

La función llama al proceso interno y al final de su ejecución entrega un mensaje de éxito.

---

### <span style="font-size:0.7em;">panel_po_us</span><span style="font-size:1.2em;">.__valid_cons_vis__</span>

panel_po_us._**valid_cons_vis**()

Función que gatilla la generación de una estructura de datos similar al Consolidado de Periodos, pero con información de intervalos promedio entre salidas programadas, a partir de un Consolidado de Salidas y un Anexo 1 Nuevo.

La función llama al proceso interno y al final de su ejecución abre una ventana emergente en la que se visualiza la estructura de datos, con los intervalos mayores a 30 resaltados en rojo.

---

### <span style="font-size:0.7em;">panel_po_us</span><span style="font-size:1.2em;">.__analisis_frecuencias__</span>

panel_po_us._**analisis_frecuencias**()

Función que gatilla la generación de una estructura de datos y un gráfico para el análisis de consistencia en salidas programadas (a través de la frecuencia programada), a partir de un consolidado de salidas o un Anexo 3.

La función llama al proceso interno y al final de su ejecución abre una ventana emergente en la que se visualiza el gráfico y un botón para descargar la estructura de datos en un archivo Excel.

---

### <span style="font-size:0.7em;">panel_po_us</span><span style="font-size:1.2em;">.__revision_biportales_a4__</span>

panel_po_us._**revision_biportales_a4**()

Función que gatilla la revisión de que se asignen buses biportales (en programación de salidas A4) a servicios que operen en paraderos de puerta izquierda. 

La función llama al proceso interno (siempre que haya un Anexo 4 Nuevo cargado y un Consolidado de Paradas cargado) y luego genera una ventana emergente con dos posibles resultados: un mensaje de que el archivo Anexo 4 está correcto, o una tabla con las filas del Anexo 4 que presentan tienen problemas con la asignación de tipo de bus. 

Si se presenta la tabla, además se presenta un botón para convertir la información en un archivo Excel que se descargue.

---

## Variables declaradas

### Colores HEX

Se declaran valores HEX para los colores a utilizar en el panel.

    rojo = '#C00000'
    blanco = '#FFFFFF'
    gris = '#730202'
    clickeado = '#00A15A'
    negro = '#000000'
    loading = '#FFD700'
    azul = '#003399'
    celeste = '#3366CC'
    azul_deep = '#000033'

---

### Declaración objeto Panel

Se declara un objeto de la clase PanelUS() para operar el programa internamente (_backend_).

    panel_core = PanelUS()

---

### Declaración objeto Interfaz

Se declara un objeto de la clase tkinter.Tk() que servirá como la ventana principal de la interfaz (_frontend_).

    mainMenu = tk.Tk()
    mainMenu.title('Panel PO US')
    mainMenu.state("zoomed")
    mainMenu['background'] = blanco

---

### Declaración fuente letra

Se declara la fuente del Panel (Helvetica).

    myFont = font.Font(family='Helvetica')

---

### Declaración de WD y visuales

Se declara la dirección de la carpeta de trabajo (wd) y ubicación de visuales del panel.

    path = os.getcwd()
    path_visuals = path + r"\visuals"
    path_excelfiles = path + r"\Archivos Excel"
    path_memory = path + r"\Memoria"
    path_plantillas = path + r"\plantillas"

---

### Creación de Banner

Se declara el banner de la parte superior.

    change_wd(path_visuals)
    logo_banner = ImageTk.PhotoImage(Image.open("logo2.png").resize((300, 40)))
    banner = tk.Label(mainMenu, image=logo_banner, height=50, bg=rojo)
    banner.pack(fill=tk.X, side="top")

---

### Definición de la Versión

Se declara la versión del Panel.

    version = 'Version 2.3: MARCOPOLO-2'
    version_title = tk.Label(mainMenu, bg=rojo, fg=blanco, bd=4, text=version, 
                             font=('Gill Sans MT', 14, 'bold'))
    version_title.place(relx=0.75, rely=0.018, relheight=0.03, relwidth=0.2)

---

### Definición Título "Carga de Archivos"

Se declara el título de botones de carga de archivos.

    load_title = tk.Label(mainMenu, bg=rojo, fg=blanco, bd=4, text='Carga de Archivos', 
                          font='Helvetica 11 bold')
    load_title.place(relx=0.05, rely=line_1, relheight=0.055, relwidth=0.28)

---

### Definición Botón Carga Anexo 1

Se declara el botón de carga del anexo 1.

    load_a1_button = tk.Button(mainMenu, text="Cargar Anexo 1", 
                               command=lambda: threading.Thread(target=vis_load_a1).start(),
                               bg=gris, fg=blanco)
    load_a1_button.place(relx=0.09, rely=line_1 + 0.065)

---

### Definición Botón Carga Anexo 3

Se declara el botón de carga del anexo 3.

    load_a3_button = tk.Button(mainMenu, text="Cargar Anexo 3",
                               command=lambda: threading.Thread(target=vis_load_a3).start(),
                               bg=gris, fg=blanco)
    load_a3_button.place(relx=0.09, rely=line_1 + 0.101)

---

### Definición Botón Carga Anexo 4

Se declara el botón de carga del anexo 4.

    load_a4_button = tk.Button(mainMenu, text="Cargar Anexo 4",
                               command=lambda: threading.Thread(target=vis_load_a4).start(),
                               bg=gris, fg=blanco)
    load_a4_button.place(relx=0.09, rely=line_1 + 0.138)

---

### Definición Botón Carga Anexo 1 Vigente

Se declara el botón de carga del anexo 1 vigente (actualmente desactivado).

    load_a1base_button = tk.Button(mainMenu, text="Cargar Anexo 1 Vigente",
                                   command=lambda: threading.Thread(target=method).start(),
                                   bg=gris, fg=blanco)
    load_a1base_button.place(relx=0.15, rely=line_1 + 0.065)
    load_a1base_button["state"] = "disabled"

---

### Definición Botón Carga Anexo 3 Vigente

Se declara el botón de carga del anexo 3 vigente.

    load_a3base_button = tk.Button(mainMenu, text="Cargar Anexo 3 Vigente",
                                command=lambda: threading.Thread(target=vis_load_a3b).start(),
                                bg=gris, fg=blanco)
    load_a3base_button.place(relx=0.15, rely=line_1 + 0.101)

---

### Definición Botón Carga Anexo 4 Vigente

Se declara el botón de carga del anexo 4 vigente.

    load_a4base_button = tk.Button(mainMenu, text="Cargar Anexo 4 Vigente",
                                command=lambda: threading.Thread(target=vis_load_a4b).start(),
                                bg=gris, fg=blanco)
    load_a4base_button.place(relx=0.15, rely=line_1 + 0.138)

---

### Definición Botón Carga Consolidado de Paradas

Se declara el botón de carga del consolidado de paradas.

    load_consparadas_button = tk.Button(mainMenu, text="Cargar Cons. Paradas",
                                        command=lambda: threading.Thread(target=vis_load_conspar).start(),
                                        bg=gris, fg=blanco)
    load_consparadas_button.place(relx=0.235, rely=line_1 + 0.065)

---

### Definición Botón Carga Consolidado de Salidas

Se declara el botón de carga del consolidado de salidas.

    load_conssalid_button = tk.Button(mainMenu, text="Cargar Cons. Salidas",
                                      command=lambda: threading.Thread(target=vis_load_cons).start(),
                                      bg=gris, fg=blanco)
    load_conssalid_button.place(relx=0.235, rely=line_1 + 0.101)
                                        
---

### Definición Botón Carga Base Consolidado

Se declara el botón de carga del archivo base consolidado.

    load_base_cons_button = tk.Button(mainMenu, text="Cargar Base Cons.",
                                      command=lambda: threading.Thread(target=vis_load_base_cons).start(),
                                      bg=gris, fg=blanco)
    load_base_cons_button.place(relx=0.238, rely=line_1 + 0.138)

---

### Definición Título "Archivos Cargados"

Se declara el título de archivos cargados.

    loaded_files_title = tk.Label(mainMenu, bg=rojo, fg=blanco, bd=4, text='Archivos Cargados',
                              font='Helvetica 11 bold')
    loaded_files_title.place(relx=0.05, rely=0.25, relheight=0.055, relwidth=0.28)

---

### Definición Cuadro Anexo 1 Cargado

Se declara el cuadro de anexo 1 cargado y estado.

    anexo1_title_label = tk.Label(mainMenu, text='Anexo 1 Nuevo:', borderwidth=1.5, relief="solid")
    anexo1_title_label.place(relx=0.05, rely=0.315, relheight=0.04, relwidth=0.075)

    a1_filename = tk.StringVar()
    a1_filename.set('No cargado')
    anexo1_file_label = tk.Label(mainMenu, textvariable=a1_filename, borderwidth=1.5, relief="solid")
    anexo1_file_label.place(relx=0.124, rely=0.315, relheight=0.04, relwidth=0.206)

---

### Definición Cuadro Anexo 3 Cargado

Se declara el cuadro de anexo 3 cargado y estado.

    anexo3_title_label = tk.Label(mainMenu, text='Anexo 3 Nuevo:', borderwidth=1.5, relief="solid")
    anexo3_title_label.place(relx=0.05, rely=0.365, relheight=0.04, relwidth=0.075)
    
    a3_filename = tk.StringVar()
    a3_filename.set('No cargado')
    anexo3_file_label = tk.Label(mainMenu, textvariable=a3_filename, borderwidth=1.5, relief="solid")
    anexo3_file_label.place(relx=0.124, rely=0.365, relheight=0.04, relwidth=0.206)

---

### Definición Cuadro Anexo 4 Cargado

Se declara el cuadro de anexo 4 cargado y estado.

    anexo4_title_label = tk.Label(mainMenu, text='Anexo 4 Nuevo:', borderwidth=1.5, relief="solid")
    anexo4_title_label.place(relx=0.05, rely=0.415, relheight=0.04, relwidth=0.075)

    a4_filename = tk.StringVar()
    a4_filename.set('No cargado')
    anexo4_file_label = tk.Label(mainMenu, textvariable=a4_filename, borderwidth=1.5, relief="solid")
    anexo4_file_label.place(relx=0.124, rely=0.415, relheight=0.04, relwidth=0.206)

---

### Definición Cuadro Anexo 3 Vigente Cargado

Se declara el cuadro de anexo 3 vigente cargado y estado.

    anexo3b_title_label = tk.Label(mainMenu, text='Anexo 3 Vigente:', borderwidth=1.5, relief="solid")
    anexo3b_title_label.place(relx=0.05, rely=0.465, relheight=0.04, relwidth=0.075)

    a3b_filename = tk.StringVar()
    a3b_filename.set('No cargado')
    anexo3b_file_label = tk.Label(mainMenu, textvariable=a3b_filename, borderwidth=1.5, relief="solid")
    anexo3b_file_label.place(relx=0.124, rely=0.465, relheight=0.04, relwidth=0.206)

---

### Definición Cuadro Anexo 4 Vigente Cargado

Se declara el cuadro de anexo 4 vigente cargado y estado.

    a4b_title_label = tk.Label(mainMenu, text='Anexo 4 Vigente:', borderwidth=1.5, relief="solid")
    a4b_title_label.place(relx=0.05, rely=0.515, relheight=0.04, relwidth=0.075)

    a4b_filename = tk.StringVar()
    a4b_filename.set('No cargado')
    a4b_file_label = tk.Label(mainMenu, textvariable=a4b_filename, borderwidth=1.5, relief="solid")
    a4b_file_label.place(relx=0.124, rely=0.515, relheight=0.04, relwidth=0.206)

---

### Definición Cuadro Consolidado de Salidas Cargado

Se declara el cuadro de archivo Consolidado de Salidas cargado y estado.

    conssalid_title_label = tk.Label(mainMenu, text='Cons. Salidas:', borderwidth=1.5, relief="solid")
    conssalid_title_label.place(relx=0.05, rely=0.565, relheight=0.04, relwidth=0.075)

    conssalid_filename = tk.StringVar()
    conssalid_filename.set('No cargado')
    conssalid_file_label = tk.Label(mainMenu, textvariable=conssalid_filename, borderwidth=1.5, relief="solid")
    conssalid_file_label.place(relx=0.124, rely=0.565, relheight=0.04, relwidth=0.206)

---

### Definición Cuadro Consolidado de Paradas Cargado

Se declara el cuadro de archivo Consolidado de Paradas cargado y estado.

    conspar_label = tk.Label(mainMenu, text='Cons. Paradas:', borderwidth=1.5, relief="solid")
    conspar_label.place(relx=0.05, rely=0.615, relheight=0.04, relwidth=0.075)
    
    conspar_filename = tk.StringVar()
    conspar_filename.set('No cargado')
    conspar_file_label = tk.Label(mainMenu, textvariable=conspar_filename, borderwidth=1.5, relief="solid")
    conspar_file_label.place(relx=0.124, rely=0.615, relheight=0.04, relwidth=0.206)

---

### Definición Cuadro Base Consolidado Cargado

Se declara el cuadro de archivo Base Consolidado cargado y estado.

    base_cons_label = tk.Label(mainMenu, text='Base Consolidado:', borderwidth=1.5, relief="solid")
    base_cons_label.place(relx=0.05, rely=0.665, relheight=0.04, relwidth=0.075)
    
    base_cons_filename = tk.StringVar()
    base_cons_filename.set('No cargado')
    base_cons_file_label = tk.Label(mainMenu, textvariable=base_cons_filename, borderwidth=1.5, relief="solid")
    base_cons_file_label.place(relx=0.124, rely=0.665, relheight=0.04, relwidth=0.206)

---

### Definición Botones Gestión Archivos 

Se declaran los botones de guardar, cargar y limpiar (eliminar) archivos.

    save_allfiles_button = tk.Button(mainMenu, text="Guardar Anexos",
                                     command=lambda: threading.Thread(target=save_all_anexos).start(),
                                     bg=gris, fg=blanco)
    save_allfiles_button.place(relx=0.075, rely=0.74)

    load_allfiles_button = tk.Button(mainMenu, text="Cargar Anexos",
                                     command=lambda: threading.Thread(target=load_all_anexos).start(),
                                     bg=gris, fg=blanco)
    load_allfiles_button.place(relx=0.17, rely=0.74)

    clear_allfiles_button = tk.Button(mainMenu, text="Limpiar Anexos",
                                      command=lambda: threading.Thread(target=clear_all_anexos).start(),
                                      bg=gris, fg=blanco)
    clear_allfiles_button.place(relx=0.255, rely=0.74)

---

### Definición Sección Selección de Unidad

Se declaran la etiqueta y la lista desplegable para seleccionar unidad de servicio.

    select_unidad_label = tk.Label(mainMenu, text='Selecciona unidad a revisar:', borderwidth=0, relief="solid", bg=blanco,
                                   font='Helvetica 11')
    select_unidad_label.place(relx=0.06, rely=0.785, relheight=0.055, relwidth=0.115)

    unidad_combo = ttk.Combobox(values=["", "8", "9", "10", "11", "12", "13"])
    unidad_combo.bind("<<ComboboxSelected>>", selection_changed_main)
    unidad_combo.place(relx=0.18, rely=0.805)

---

### Definición Sección Paso 0 Revisión

Se declaran la etiqueta y los botones para revisiones Paso 0

    paso0_title = tk.Label(mainMenu, bg=rojo, fg=blanco, bd=4, text='Paso 0 (Revisión de Parámetros Faltantes)',
                           wraplength=200, font='Helvetica 11 bold')
    paso0_title.place(relx=labels_line, rely=line_1, relheight=0.055, relwidth=width_label)

    a3_param_check_button = tk.Button(mainMenu, text="Revisar Parámetros Anexo 3",
                                      command=lambda: threading.Thread(target=check_params_a3).start(), wraplength=90,
                                      bg=gris, fg=blanco)
    a3_param_check_button.place(relx=buttons_line, rely=line_1, relwidth=0.05)

    a4_param_check_button = tk.Button(mainMenu, text="Revisar Parámetros Anexo 4",
                                      command=lambda: threading.Thread(target=check_params_a4).start(), wraplength=90,
                                      bg=gris, fg=blanco)
    a4_param_check_button.place(relx=buttons_line + 0.051, rely=line_1, relwidth=0.05)

---

### Definición Sección Paso 1 Revisión

Se declaran la etiqueta y los botones para revisiones Paso 1

    paso1_title = tk.Label(mainMenu, bg=rojo, fg=blanco, bd=4, text='Paso 1 (Comparación Anexo 3 Nuevo y Vigente)',
                           wraplength=200, font='Helvetica 11 bold')
    paso1_title.place(relx=labels_line, rely=line_1 + 0.075, relheight=0.055, relwidth=width_label)

    comp_a3v_a3n_button = tk.Button(mainMenu, text="Compara Anexo 3 Nuevo y Vigente",
                                    command=lambda: threading.Thread(target=comp_a3v_a3n_panel).start(),
                                    wraplength=182, bg=gris, fg=blanco)
    comp_a3v_a3n_button.place(relx=buttons_line, rely=line_1 + 0.082, relwidth=0.1)

---

### Definición Sección Paso 2 Revisión

Se declaran la etiqueta y los botones para revisiones Paso 2.

    paso2_title = tk.Label(mainMenu, bg=rojo, fg=blanco, bd=4, text='Paso 2 (Comparación Horarios y Tabla Horaria)',
                           wraplength=200, font='Helvetica 11 bold')
    paso2_title.place(relx=labels_line, rely=0.22, relheight=0.055, relwidth=width_label)

    comp_a1_a4_button = tk.Button(mainMenu, text="Revisar Consistencia Anexo 1 y Anexo 4",
                                  command=lambda: threading.Thread(target=comp_time_a1_a4).start(),
                                  wraplength=170, bg=gris, fg=blanco)
    comp_a1_a4_button.place(relx=buttons_line, rely=0.23, relwidth=0.1)

---

### Definición Sección Paso 3 Revisión

Se declaran la etiqueta y los botones para revisiones Paso 3.

    paso3_title = tk.Label(mainMenu, bg=rojo, fg=blanco, bd=4,
                        text='Paso 3 (Comparación Parámetros y Tabla Horaria)', wraplength=200,
                        font='Helvetica 11 bold')
    paso3_title.place(relx=labels_line, rely=0.3, relheight=0.055, relwidth=width_label)

    comp_a3_a4_button = tk.Button(mainMenu, text="Revisar Consistencia Anexo 3 y Anexo 4",
                                command=lambda: threading.Thread(target=comp_param_a3_a4).start(), wraplength=170,
                                bg=gris, fg=blanco)
    comp_a3_a4_button.place(relx=buttons_line, rely=0.31, relwidth=0.1)

---

### Definición Sección Paso 4.1 Revisión (DESHABILITADOS)

Se declaran la etiqueta y los botones para revisiones Paso 4.1 (Consistencia Agr MH).

    paso41_title = tk.Label(mainMenu, bg=rojo, fg=blanco, bd=4,
                            text='Paso 4.1 (Revisión de Consistencia de Agrupación MH)', wraplength=200,
                            font='Helvetica 11 bold')
    paso41_title.place(relx=labels_line, rely=0.38, relheight=0.055, relwidth=width_label)

    serr_salid_a3_button = tk.Button(mainMenu, text="Revisar Regularidad Salidas Anexo 3 (sin MHA)",
                                     command=lambda: threading.Thread(target=method).start(),
                                     wraplength=120, bg=gris, fg=blanco)
    serr_salid_a3_button.place(relx=buttons_line, rely=0.38)
    serr_salid_a3_button["state"] = "disabled"

    comp_a3_mha_opt_button = tk.Button(mainMenu, text="Revisar optimalidad de MHA Anexo 3",
                                       command=lambda: threading.Thread(target=method).start(),
                                       wraplength=90, bg=gris, fg=blanco)
    comp_a3_mha_opt_button.place(relx=buttons_line + 0.062, rely=0.38)
    comp_a3_mha_opt_button["state"] = 'disabled'

---

### Definición Sección Paso 4.2 Revisión (en desarrollo)

Se declaran la etiqueta y los botones para revisiones Paso 4.1 (Regularidad Intervalos).

    paso42_title = tk.Label(mainMenu, bg=rojo, fg=blanco, bd=4,
                            text='Paso 4.2 (Revisión de Regularidad en Intervalos)', wraplength=200,
                            font='Helvetica 11 bold')
    paso42_title.place(relx=labels_line, rely=0.46, relheight=0.067, relwidth=width_label)

    rev_interv_a4_1_button = tk.Button(mainMenu, text="Revisar Diferencias en intervalos Anexo 4 (con MHA)",
                                       command=lambda: threading.Thread(target=check_intervalos_a4).start(),
                                       wraplength=100, bg=gris, fg=blanco)
    rev_interv_a4_1_button.place(relx=buttons_line, rely=0.46)

    rev_interv_a4_2_button = tk.Button(mainMenu, text="Revisar Diferencias en intervalos Anexo 4 (sin MHA)",
                                       command=lambda: threading.Thread(target=method).start(),
                                       wraplength=100, bg=gris, fg=blanco)
    rev_interv_a4_2_button.place(relx=buttons_line + 0.058, rely=0.46)
    rev_interv_a4_2_button["state"] = 'disabled'

---

### Definición Sección Generadores

Se declaran la etiqueta de la sección de Generadores

    extrastep_title = tk.Label(mainMenu, bg=azul, fg=blanco, bd=4, text='Generadores',
                               font='Helvetica 11 bold')
    extrastep_title.place(relx=labels_line, rely=line_1 + 0.49, relheight=0.045, relwidth=0.51)

---

### Definición Sección Generados desde Anexo 4

Se declaran la etiqueta y botones para generar archivos de anexos (1 y 3) desde Anexo 4.

    from_a4_title = tk.Label(mainMenu, bg=celeste, fg=blanco, bd=4, text='Desde Anexo 4',
                             font='Helvetica 10 bold')
    from_a4_title.place(relx=labels_line, rely=line_1 + 0.546, relheight=0.045, relwidth=width_label)

    a1_from_a4_button = tk.Button(mainMenu, text="Genera Anexo 1 desde Anexo 4",
                                  command=lambda: threading.Thread(target=save_a1_from_a4).start(),
                                  wraplength=90, bg=azul_deep, fg=blanco)
    a1_from_a4_button.place(relx=buttons_line, rely=line_1 + 0.546)


    a3_from_a4_button = tk.Button(mainMenu, text="Genera Anexo 3 desde Anexo 4",
                                  command=lambda: threading.Thread(target=save_a3_from_a4).start(),
                                  wraplength=90, bg=azul_deep, fg=blanco)
    a3_from_a4_button.place(relx=buttons_line + 0.0504, rely=line_1 + 0.546)

---

### Definición Sección Generados desde Anexo 3

Se declaran la etiqueta y botones para generar archivos de anexos desde Anexo 3.  

    from_a3_title = tk.Label(mainMenu, bg=celeste, fg=blanco, bd=4, text='Desde Anexo 3',
                             font='Helvetica 10 bold')
    from_a3_title.place(relx=labels_line + 0.28, rely=line_1 + 0.546, relheight=0.045, relwidth=width_label)

    a4_from_a3_button = tk.Button(mainMenu, text="Genera Anexo 4 desde Anexo 3",
                                  command=lambda: threading.Thread(target=save_a4_from_a3).start(),
                                  wraplength=90, bg=azul_deep, fg=blanco)
    a4_from_a3_button.place(relx=buttons_line + 0.28, rely=line_1 + 0.546)

---

### Definición Sección Generados desde Consolidado

Se declaran la etiqueta y botones para generar un Anexo 3 desde A3 Vigente y Consolidado.  

    a3_from_cons_title = tk.Label(mainMenu, bg=celeste, fg=blanco, bd=4, text='Anexo 3 desde Consolidado',
                                  font='Helvetica 10 bold')
    a3_from_cons_title.place(relx=labels_line, rely=line_1 + 0.603, relheight=0.045, relwidth=width_label)

    a3_slds_w_base_button = tk.Button(mainMenu, text="Genera Salidas A3 desde Consolidado con A3 Vigente",
                                      command=lambda: threading.Thread(target=save_a3_ns_w_base).start(),
                                      wraplength=150, bg=azul_deep, fg=blanco)
    a3_slds_w_base_button.place(relx=buttons_line, rely=line_1 + 0.603)

---

### Definición Sección Generación de Perfil de Flota

Se declaran la etiqueta y botones para generar un archivo de Perfil de Flota.

    perfil_flota_title = tk.Label(mainMenu, bg=celeste, fg=blanco, bd=4, text='Cálculo Perfil de Flota',
                                  font='Helvetica 10 bold')
    perfil_flota_title.place(relx=labels_line, rely=line_1 + 0.66, relheight=0.045, relwidth=width_label)

    perfil_flota_button = tk.Button(mainMenu, text="Generar Archivo Perfil Flota",
                                    command=lambda: threading.Thread(target=calc_perfil_flota).start(),
                                    wraplength=200, bg=azul_deep, fg=blanco)
    perfil_flota_button.place(relx=buttons_line, rely=line_1 + 0.667)

---

### Definición Sección Generación de Consolidado

Se declaran la etiqueta y botones para generar archivos de Consolidado.

    cons_us_title = tk.Label(mainMenu, bg=celeste, fg=blanco, bd=4, text='Consolidados US',
                             font='Helvetica 10 bold')
    cons_us_title.place(relx=labels_line, rely=line_1 + 0.718, relheight=0.055, relwidth=width_label)

    cons_per_button = tk.Button(mainMenu, text="Generar Archivo Consolidado por Periodos",
                                command=lambda: threading.Thread(target=genera_cons_periodo_us).start(),
                                wraplength=90, bg=azul_deep, fg=blanco)
    cons_per_button.place(relx=buttons_line, rely=line_1 + 0.718)

    cons_mh_button = tk.Button(mainMenu, text="Generar Archivo Consolidado por MH",
                               command=lambda: threading.Thread(target=genera_cons_mh_us).start(),
                               wraplength=90, bg=azul_deep, fg=blanco)
    cons_mh_button.place(relx=buttons_line + 0.0518, rely=line_1 + 0.718)

---

### Definición Sección Generación de Nueva Agrupación para A3

Se declaran la etiqueta y botones para generar nueva agrupación para el Anexo 3.

    a3_regroup = tk.Label(mainMenu, bg=celeste, fg=blanco, bd=4, text='Anexo 3 Reagrupado',
                          font='Helvetica 10 bold')
    a3_regroup.place(relx=labels_line, rely=line_1 + 0.785, relheight=0.045, relwidth=width_label)

    a3_regroup_button = tk.Button(mainMenu, text="Generar Anexo 3 con Nueva Agrupación MH",
                                  command=lambda: threading.Thread(target=save_a3_regroup).start(),
                                  wraplength=150, bg=azul_deep, fg=blanco)
    a3_regroup_button.place(relx=buttons_line, rely=line_1 + 0.785)

---

### Definición Sección Conteo de Km.

Se declaran la etiqueta y botones para generar ventana con conteo de kilómetros, para Anexos 3.

    cont_km_label = tk.Label(mainMenu, bg=celeste, fg=blanco, bd=4, text='Conteo de KM desde Anexo 3',
                            font='Helvetica 10 bold')
    cont_km_label.place(relx=labels_line, rely=line_1 + 0.845, relheight=0.045, relwidth=width_label)

    contar_km_button = tk.Button(mainMenu, text="Contar KM totales de Anexo 3",
                                command=lambda: threading.Thread(target=contar_km).start(),
                                wraplength=250, bg=azul_deep, fg=blanco)
    contar_km_button.place(relx=buttons_line, rely=line_1 + 0.853)

---

### Definición Sección Consolidado de Intervalos

Se declaran la etiqueta y botones para generar ventana con Análisis de Intervalos entre salidas programadas por periodo.

    cons_interv_label = tk.Label(mainMenu, bg=rojo, fg=blanco, bd=4,
                                text='Revisión preliminar de Intervalos desde Consolidado de Salidas',
                                wraplength=200, font='Helvetica 11 bold')
    cons_interv_label.place(relx=labels_line + 0.28, rely=line_1, relheight=0.065, relwidth=width_label)

    cons_interv_button = tk.Button(mainMenu, text="Validar Consolidado de Salidas",
                                command=lambda: threading.Thread(target=valid_cons_vis).start(),
                                wraplength=90, bg=gris, fg=blanco)
    cons_interv_button.place(relx=labels_line + 0.4, rely=line_1 + 0.006)

---

### Definición Sección Análisis de Frecuencias

Se declaran la etiqueta y botones para generar ventana con Análisis de Frecuencias.

    analys_frec_label = tk.Label(mainMenu, bg=rojo, fg=blanco, bd=4,
                                text='Revisión de Frecuencias',
                                wraplength=200, font='Helvetica 11 bold')
    analys_frec_label.place(relx=labels_line + 0.28, rely=line_1 + 0.076, relheight=0.06, relwidth=width_label)

    analys_frec_button = tk.Button(mainMenu, text="Generar Análisis de Frecuencias",
                                command=lambda: threading.Thread(target=analisis_frecuencias).start(),
                                wraplength=90, bg=gris, fg=blanco)
    analys_frec_button.place(relx=labels_line + 0.4, rely=line_1 + 0.08 + 0.006)

---

### Definición Sección Revisión de Buses Biportales

Se declaran la etiqueta y botones para generar ventana con para Revisión de Buses Biportales.

    biportal_label = tk.Label(mainMenu, bg=rojo, fg=blanco, bd=4,
                            text='Revisión de Buses Biportales',
                            wraplength=200, font='Helvetica 11 bold')
    biportal_label.place(relx=labels_line + 0.28, rely=line_1 + 0.146, relheight=0.06, relwidth=width_label)

    biportal_button = tk.Button(mainMenu, text="Revisar asignación de buses biportales",
                                command=lambda: threading.Thread(target=revision_biportales_a4).start(),
                                wraplength=90, bg=gris, fg=blanco)
    biportal_button.place(relx=labels_line + 0.4, rely=line_1 + 0.149)