# EFT — Herramientas DevOps

**Pablo Nicolás Alonso Gallardo Gallardo** · Duoc UC Online · Semana 9

## 🎥 Video de la presentación
👉**https://youtu.be/OV_TFT9ZoLQ**
 
---

## Caso
Municipalidad de La Florida — despliegue del servicio de gestión de usuarios en contenedores con CI/CD.

## Stack
Spring Boot (Java 17) · MySQL en AWS RDS · Jenkins sobre EC2 · Docker · Maven

## Endpoints
Base: `http://<IP>:8081/usuariosBuild`
 
| Método | Ruta | Acción |
|---|---|---|
| GET | `/user` | Listar usuarios |
| POST | `/user` | Crear usuario |
| PUT | `/user/{id}` | Editar usuario |
| DELETE | `/user/{id}` | Eliminar usuario |
 
