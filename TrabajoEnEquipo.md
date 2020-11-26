# Trabajo Colaborativo con Git

[Regresar](./README.md)

## Creando una organización

* Nos dirigimos a (https://github.com/settings/organizations) y le damos a *new organization*
* Nos aparecera 3 planes (free, team, enterprise). Seleccionaremos free.
* Rellenamos los datos que nos piden y listo
* Una vez creada la organización, crearemos un nuevo repositorio

![Creando Repositorio](./img/organization.PNG)

## Agregando a gente al repositorio

Para eso nos dirigimos al apartado de *People* y lo que tenemos que hacer es invitarlos, podemos gestionar sus permisos tambien.

## Fork a un proyecto de Github

Cuando estemos trabajando en un repositorio colaborativo los recomendable es que el equipo no haga push de forma directa al repositorio, lo que se recomienda es que cada integrante le saque una copia(fork) y cuando tenga una característica desarrollada recién mande una solicitud a los administradores del repositorio.

> **FORK** es una bifurcación, se entiende que de una rama pricipal se generarán nuevas ramas independientes(copias) a esta.

![Fork](./img/fork.png)

## Creando repositorios remotos

El administrador del repositorio principal tendra que decidir la forma de trabajo es deci la distriución de las ramas. Un ejemlo sería tener dos ramas, una `dev` y otra la principal(`master`).

Esta distribución indicará a los integrantes del proyecto que suban todos sus cambios a la rama `dev` y que cuando esten desactualizados del proyecto hagan un pull a esa misma rama. 

Entonces los integrantes en su copia(fork) tendrán que agregar repositorios remotos del proyecto principal y de su proyecto personal. Es decir
```
$ git remote -v
organizacion git@github.com:cuscowebdev/jdpoccorieGit.git
organizacion git@github.com:cuscowebdev/jdpoccorieGit.git
personal(origin) git@github.com:jdpoccorie/jdpoccorieGit.git
personal(origin) git@github.com:jdpoccorie/jdpoccorieGit.git
```

> Es una buena práctica que los integrantes no suban cambios directamente a la rama master del repositorio principal

