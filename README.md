# 🗄️ Trabajo Práctico – Gestión de Datos (UTN)

## 🎯 Objetivo

Diseñar e implementar una base de datos relacional normalizada a partir de una tabla desnormalizada, incluyendo procesos de migración de datos y la construcción de un modelo dimensional orientado al análisis de Business Intelligence.

---

## ⚙️ Cómo ejecutar el proyecto

1. Crear la base de datos **GDIC2025** en SQL Server (con parámetros por defecto).
2. Ejecutar el archivo `EjecutarScriptTablaMaestra.bat` para generar y poblar la Master Table.
3. Ejecutar el script de creación de tablas del modelo transaccional.
4. Ejecutar el script de migración de datos desde la Master Table.
5. Ejecutar el script correspondiente al modelo de Business Intelligence.
   
   > Opcional: se incluye un script unificado en `/mejoras` para ejecutar el sistema completo con las mejoras incorporadas.

---

## 📁 Estructura del repositorio

* `/docs` → Enunciado y archivos provistos por la cátedra
* `/der` → Diagrama Entidad-Relación y decisiones de diseño
* `/transaccional` → Scripts de creación y migración de datos
* `/bi` → Modelo dimensional y scripts asociados
* `/mejoras` → Implementaciones y mejoras desarrolladas individualmente (post-entrega)

---

## 📌 Introducción

En la materia Gestión de Datos de tercer año en la UTN, existe un Trabajo Práctico grupal que se debe aprobar y entregar en tiempo y forma para poder regularizar o promocionar la materia. En este repositorio se encuentra el trabajo desarrollado y entregado en conjunto con mis compañeros, junto con modificaciones adicionales realizadas de forma individual posteriormente a su aprobación.

El objetivo del trabajo fue abordar un proceso completo de diseño e implementación de una base de datos, que decidí dividir en cinco secciones. En total, el trabajo constaba de tres entregas:

* **Primera entrega:** construcción del Diagrama Entidad-Relación (DER).
* **Segunda entrega:** desarrollo del modelo transaccional, incluyendo scripts de creación de objetos y migración de datos desde la Master Table.
* **Tercera entrega:** diseño e implementación de un modelo dimensional orientado a Business Intelligence, con su correspondiente DER y procesos de carga.

Además, se elaboró un documento complementario que detalla las decisiones de diseño adoptadas y las estrategias implementadas.

> **ACLARACIÓN:** Existen múltiples formas de resolver el problema planteado en el enunciado. En este repositorio se presenta la solución desarrollada por nuestro grupo, tanto para el diseño del DER como para los procesos de migración y modelado.

---

## 1. Requisitos y archivos provistos

Para el desarrollo del trabajo se utilizó **Microsoft SQL Server 2022**, junto con **SQL Server Management Studio (SSMS)**. Tanto la versión Express como la versión completa son válidas como entorno de trabajo.

Se debía crear una base de datos llamada **GDIC2025**, utilizando la configuración por defecto.

La cátedra proporcionó los siguientes archivos:

* `gd_esquema.Schema.sql`: genera el esquema `gd_esquema` dentro de la base de datos y lo asigna al usuario `gd`. Puede ejecutarse desde el SSMS, aunque no lo recomiendo.

* `gd_esquema.Maestra.Table.sql`: crea y carga la tabla principal del trabajo (Master Table). Debido a su tamaño, **no puede ejecutarse directamente desde el SSMS**.

* `EjecutarScriptTablaMaestra.bat`: archivo batch que ejecuta los scripts anteriores mediante `sqlcmd`. Este proceso tiene una duración aproximada de 40 minutos.

Una vez finalizado este proceso, se debía crear un esquema propio dentro de la base de datos (siguiendo las pautas indicadas por la cátedra). Es fundamental que todos los objetos creados (tablas, vistas, stored procedures, triggers, etc.) pertenezcan a dicho esquema.

---

## 2. Diagrama Entidad-Relación

A partir de la Master Table (generada mediante el script provisto), se realizó un análisis de sus columnas con el objetivo de construir un modelo relacional adecuado. Dado que esta tabla se encuentra **desnormalizada**, el objetivo principal fue aplicar las Formas Normales (idealmente hasta **3FN**) para obtener un esquema consistente y libre de redundancias. Sin embargo, en ciertos casos se permitieron excepciones justificadas por motivos de performance.

---

## 3. Modelo transaccional y migración de datos

Una vez definido el DER, se procedió a implementar el modelo en SQL Server mediante scripts de creación de tablas y relaciones. Además, se desarrollaron los procesos de migración de datos desde la Master Table hacia el nuevo modelo normalizado. De forma opcional, se podían incorporar objetos adicionales como **triggers** y **stored procedures** para enriquecer la lógica del sistema y mejorar la integridad de los datos.

---

## 4. Modelo de Business Intelligence (BI)

En la última etapa del trabajo, se diseñó un modelo dimensional orientado al análisis de datos.

Este proceso incluyó:

* Definición de un nuevo DER basado en dimensiones y hechos
* Implementación del modelo en SQL Server
* Migración de datos desde el modelo transaccional
* Creación de vistas para cumplir con los requerimientos analíticos

Este modelo se debía implementar dentro de la misma base de datos y esquema que el modelo transaccional.

La comprensión del modelo dimensional puede resultar desafiante inicialmente; recomiendo encarecidamente estudiar y analizar bien la lógica de los modelos dimensionales. Una vez comprendido esto, la implementación no presenta demasiada complejidad.

---

## 5. Aporte individual

Las siguientes implementaciones fueron desarrolladas de manera individual, posteriormente a la entrega y aprobación del trabajo práctico:

- Nuevos triggers
- Stored procedures adicionales
- Mejoras en la integridad de los datos
- Optimizaciones en procesos de carga

Estas modificaciones tienen como objetivo extender y mejorar la solución original desarrollada en equipo.

---

## 🙌 Créditos

Trabajo realizado en conjunto con:

* Nicolás
* Facundo
* Araceli
