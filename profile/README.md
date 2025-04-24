# 🏛️ Normativas y Estándares de la Organización

Este documento establece las **normativas oficiales y de cumplimiento obligatorio** para todos los miembros que trabajen dentro de los repositorios de esta organización. Su objetivo es asegurar la trazabilidad, orden, colaboración y calidad en los desarrollos realizados de los proyectos.

---

## 📂 Estructura de Repositorios

Los repositorios deben organizarse según cliente o propósito específico, usando la siguiente convención:  
odoo-ptc-<nombre_cliente_o_proyecto> (Para repositorios de OdooSH)
ptc-<nombre_cliente_o_proyecto> (Para repositorios de otros desarrollos)

### Ejemplos:
- `odoo-ptc-rroma`
- `odoo-ptc-core`
- `odoo-ptc-tools`
- `ptc-rpcshift`

Cada repositorio debe incluir:
- README.md con información del proyecto
- Chagelog con los cambios aplicados en cada PR
- .gitignore estandar

---

## 👥 2. Equipos y Permisos
  
### Equipos definidos:
| Equipo           | Descripción                                      | Permisos recomendados |
|------------------|--------------------------------------------------|------------------------|
| `Administradores`| Gestión total de la organización y los repos     | Admin                  |
| `Desarrolladores`| Equipo técnico para implementación de código     | Write                  |
| `QA`             | Control de calidad, validación, documentación    | Read / Triage          |

Los permisos se asignan por repositorio, permitiendo que cada equipo colabore sin interferencias innecesarias.

---

## 🔁 3. Flujo de Trabajo Git

### 📌 Ramas Estándar
- `production`: rama de código estable desplegado
- `staging-<fecha-de-creación>`: entorno previo a producción para pruebas QA
- `<tipo>/<num-tarea>`: ramas para nuevas funcionalidades o correcciones

### 🔒 Reglas de Protección (Branch Protection)
Aplicables a `production` y `staging`:
- Revisión obligatoria de al menos 1 miembro del equipo
- No permitir push directo
- Validación de PR con checks automáticos (tests, linting)

---

### 🔗 Conexión con Odoo.sh
- Todos los repos deben estar en esta organización.
- Se conectan como repos externos en Odoo.sh con clave SSH o token PAT con permisos limitados. (Por definir)
- El entorno `production` debe apuntar a la rama `production`.

---

### 🔐 Seguridad Reforzada
- **Autenticación de dos factores (2FA)** obligatoria
- **Secrets** configurados en GitHub para proteger claves y accesos (Por definir)
- Monitoreo activo con el **audit log**

---

## 📝 4. Estándares de Nombres

### 📛 Nombres de Ramas
`<tipo>/<num-tarea>`

Ejemplos:
- `feature/RRM-TSK001`
- `bugfix/WPS-TSK101`
- `hotfix/PTC-TSK450`

Tipos aceptados:

| Tipo       | Uso común                                              |
|------------|--------------------------------------------------------|
| `feature/` | Nuevas funcionalidades                                 |
| `bugfix/`  | Corrección de errores                                  |
| `hotfix/`  | Corrección urgente en `production`                     |
| `chore/`   | Tareas de mantenimiento (linters, CI, docs)            |
| `refactor/`| Reorganización o limpieza sin cambiar lógica funcional |
| `test/`    | Casos de prueba o QA manual                            |


---

## ✅ Reglas de Pull Request y Revisión

1. Todo cambio debe hacerse por PR (Pull Request)
2. Debe incluir:
   - Nombre de la rama
   - Nombre de tareas o ticket
3. Al menos una revisión de otro miembro (`QA` o `Admin`) es obligatoria.
4. No se permite hacer merge propio sin revisión (salvo hotfix urgente aprobado en chat interno)
5. Commits deben seguir los estándares definidos

---

**🔔 IMPORTANTE:** El incumplimiento de estas normativas puede provocar bloqueos en PRs, errores en despliegues o intervención del equipo de administración.

---

