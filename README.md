# Solucionar error de collation desconocida en MariaDB en Linux

Si te encuentras con el error "unknown collation utf8mb4_0900_ai_ci" en una base de datos MariaDB en Linux, puedes seguir estos pasos para corregirlo en tu archivo SQL.

## Utilizando sed

1. Ejecuta los siguientes comandos en tu terminal:

    ```bash
    sed -i 's/utf8mb4_0900_ai_ci/utf8_general_ci/g' TU_ARCHIVO_SQL.sql
    sed -i 's/CHARSET=utf8mb4/CHARSET=utf8/g' TU_ARCHIVO_SQL.sql
    ```

    Asegúrate de reemplazar "TU_ARCHIVO_SQL.sql" con el nombre real de tu archivo SQL.

    Si encuentras un error similar a "sed: 1: "TU_ARCHIVO_SQL.sql": invalid command code Y", puedes probar con la siguiente alternativa:

2. Abre tu archivo en el editor vi:

    ```bash
    sudo vi TU_ARCHIVO_SQL.sql
    ```

3. Dentro del editor vi, presiona `Esc` y luego ingresa los siguientes comandos:

    ```bash
    :%s/utf8mb4_0900_ai_ci/utf8_general_ci/g
    :%s/CHARSET=utf8mb4/CHARSET=utf8/g
    ```

    4. Guarda los cambios presionando `Esc`, escribiendo `:wq`, y presionando `Enter`.

**Nota Adicional para Compatibilidad Más Moderna:**

Si estás utilizando una versión reciente de MariaDB, considera la posibilidad de cambiar a una collación más moderna para un mejor soporte y compatibilidad:

- Puedes utilizar `utf8mb4_unicode_520_ci` para seguir las reglas de Unicode versión 5.2, o `uca1400_as_ci` si tu versión de MariaDB es más reciente.

Estas instrucciones te ayudarán a actualizar la collation y el conjunto de caracteres en tu archivo SQL para resolver el problema mencionado y asegurar una compatibilidad más moderna.

