# FROM indica que la imagen base que se usará para construir la nueva imagen (DockerHub)
FROM python:3.11.5 

#ENV establece una variable de entorno en el contenedor, en este caso se establece la variable PYTHONDONTWRITEBYTECODE en 1 que significa que no se generará archivos .pyc
ENV PYTHONDONTWRITEBYTECODE=1


#ENV se establece la variable PYTHONUNBUFFERED en 1 que significa que la salida de la consola se mostrará inmediatamente.
ENV PYTHONUNBUFFERED=1

#WORKDIR establece el directorio de trabajo en el contenedor, en este caso se establece /app
WORKDIR /app/backend

#COPY copia los archivos de la carpeta local a la carpeta del contenedor, en este caso se copia el archivo requirements.txt a la carpeta /app
COPY requirements.txt /app/backend


#RUN ejecuta un comando en el contenedor, en este caso se ejecuta el comando python -m pip install --upgrade pip para actualizar pip, normalmente se actualiza pip porque la versión que viene por defecto en la imagen base puede estar desactualizada.
RUN python -m pip install --upgrade pip


#RUN ejecuta un comando en el contenedor, en este caso se ejecuta el comando pip install -r requirements.txt para instalar las dependencias del proyecto
RUN python -m pip install -r requirements.txt

#COPY copia los archivos de la carpeta local a la carpeta del contenedor, en este caso se copia el archivo . /app
COPY . /app/backend/

EXPOSE 8000

#CMD ejecuta un comando en el contenedor, en este caso se ejecuta el comando python manage.py runserver
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]