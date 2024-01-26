# Solucionar error de collation desconocida en MariaDB en Linux

Si te encuentras con el error "unknown collation utf8mb4_0900_ai_ci" en una base de datos MariaDB en Linux, puedes seguir estos pasos para corregirlo en tu archivo SQL.

## Utilizando sed

1. Ejecuta los siguientes comandos en tu terminal:

    ```bash
    sed -i 's/utf8mb4_0900_ai_ci/utf8_general_ci/g' TU_ARCHIVO_SQL.sql
    sed -i 's/CHARSET=utf8mb4/CHARSET=utf8/g' TU_ARCHIVO_SQL.sql
    ```

    Asegúrate de reemplazar "TU_ARCHIVO_SQL.sql" con el nombre real de tu archivo SQL.

    Ten en cuenta que si encuentras un error similar a "sed: 1: "TU_ARCHIVO_SQL.sql": invalid command code Y", puedes optar por la siguiente alternativa.

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

Estas instrucciones te ayudarán a actualizar la collation y el conjunto de caracteres en tu archivo SQL para resolver el problema mencionado.
