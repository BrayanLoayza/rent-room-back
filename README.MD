# Helpi-back
## Installation
- Create a virtualenv
    ```bash
    # linux
    virtualenv venv

    # windows
    py -m venv venv
    ```

- Active virtual env and install dependencies
    ```bash
    # linux
    source venv/bin/activate

    # windows
    venv/Scripts/activate.bat
    ```

- Install dependencies
    ```bash
    # install dependencies
    pip install -r requirements.txt
    ```

- Create keys
    1. If not exist create folder keys
    2. Generate keys
    ```bash
    #run generate keys
    py utils\generate_keys.py
    ```

## Debug
- For debug, run the following command
    ```bash
    python manage.py runserver
    ```

- For more options
    ```bash
    python manage.py runserver --help
    ```

## Some utils command
- For revert migrations 
    ```bash
    #num_migration de la migracion anterior
    #or 'zero' for before 0001
    python manage.py migrate <app_name> <num_migration>
    ```

- For load data 
    ```bash
    #path_file is path of file .json
    python manage.py loaddata "path_file".json
    ```

## Contributing

### Cambios en los modelos
Usar estas reglas cuando se modifica algun archivo models.py. Se deben hacer commmit tanto del models.py y del archivo generado de la migracion.

1. Descargar todos los cambios del repositorio (`git pull`)
2. Hacer las modificaciones necesarias al (o a los ) archivos models.py.
3. Crear el archivo de la migracion
   ```bash 
   #genera un archivo de migracion
   python manage.py makemigrations
   ```
4. Ejecutar la migración en la base de datos local.
   ```bash
   python manage.py migrate
   ```
5. Verificar que los cambios a la base de datos sean correctos.
6. Ejecutar la migración en el servidor de la base de datos.
7. Hacer el commit de los archivos modificados y generados (models.py y los archivos que se generaron dentro de la carpeta migrations).


# Deployment in Heroku
All documentations is in [Heroku](https://devcenter.heroku.com/articles/getting-started-with-python)

- For push to heroku
  ```bash
    #git push <remote> <rama_local>:<rama_main__in_heroku>
    git push heroku heroku:main
    ```


# Solve conflicts with pylance

- [Stackoverflow](https://stackoverflow.com/questions/68486207/import-could-not-be-resolved-could-not-be-resolved-from-source-pylance-in-vs-cod)