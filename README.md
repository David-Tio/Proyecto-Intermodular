# Arquitectura Cloud — Inmobiliaria Chamartín

## Descripción
Propuesta de arquitectura cloud para la Inmobiliaria Chamartín basada en Amazon Web Services (AWS). Este documento recoge el proveedor elegido, la arquitectura propuesta, los servicios utilizados y la estimación de costes.

---

## Proveedor elegido: Amazon Web Services (AWS)

Se ha elegido AWS frente a otras alternativas como Microsoft Azure por los siguientes motivos:

- **Escalabilidad inmediata**: AWS permite añadir instancias o servidores a la arquitectura desde el primer momento, sin interrupciones.
- **Alta redundancia**: garantiza que el servicio siga funcionando aunque falle algún componente.
- **Compatibilidad con Windows**: al usar Windows 11 Pro y Windows Server en la empresa, se pueden aprovechar todos los servicios de AWS sin problemas de compatibilidad.
- **Free Tier**: AWS ofrece un año gratuito en los servicios principales, lo que reduce el coste inicial al mínimo.

---

## Arquitectura propuesta

La arquitectura está compuesta por los siguientes elementos:

- Los usuarios de la empresa acceden al sistema a través de **EC2**, el servidor principal en la nube.
- **EC2** se comunica con **RDS** para gestionar la base de datos de clientes e inmuebles.
- Los documentos y fotos se almacenan en **S3**.
- **IAM** controla los permisos de acceso a todos los servicios.
- Todo el tráfico circula dentro de la **VPC**, la red privada de AWS, aunque los usuarios acceden desde fuera de ella.

> El diagrama de arquitectura se encuentra en `/docs/cloud/diagrama_arquitectura.png`

---

## Servicios utilizados

| Servicio | Función |
|----------|---------|
| EC2 | Servidor web de la inmobiliaria |
| RDS | Base de datos de clientes e inmuebles |
| S3 | Almacenamiento de fotos y documentos |
| IAM | Control de accesos y permisos |
| VPC | Red privada virtual |

---

## Estimación de costes

### Primer año (Free Tier)

| Servicio | Especificaciones | Coste/mes |
|----------|-----------------|-----------|
| EC2 | t3.medium · 2 vCPU · 4GB RAM · Windows Server | 0 € |
| RDS | MySQL · db.t3.micro · 20GB almacenamiento | 0 € |
| S3 | 50GB almacenamiento · transferencia estándar | ~2 € |
| IAM | Usuarios, roles y políticas ilimitadas | 0 € |
| VPC | Red privada · subredes · tablas de enrutamiento | 0 € |
| **Total** | | **~2 €/mes** |

### A partir del segundo año

| Servicio | Especificaciones | Coste/mes |
|----------|-----------------|-----------|
| EC2 | t3.medium · 2 vCPU · 4GB RAM · Windows Server | ~30 € |
| RDS | MySQL · db.t3.micro · 20GB almacenamiento | ~15 € |
| S3 | 50GB almacenamiento · transferencia estándar | ~2 € |
| IAM | Usuarios, roles y políticas ilimitadas | 0 € |
| VPC | Red privada · subredes · tablas de enrutamiento | 0 € |
| **Total** | | **~47 €/mes** |

> AWS ofrece un Free Tier durante el primer año que incluye EC2 y RDS de forma gratuita. Una vez finalizado, el coste estimado sería de aproximadamente 47 €/mes.

---

## Archivos del proyecto

- `README.md` → Este documento
- `Diagrama_de_Red_Proyecto_Intermodular_Fundamentos_de_la_Computacion _en_la_nube_David.drawio.png` → Diagrama de arquitectura AWS (draw.io)
- `Presentación_Proyecto_Inter_Modular_Módulo_Profesional_Optativo_David_Tío_Vallejo_SMR1_Caja_Mágica.pptx` → Presentación del módulo (PowerPoint)
- `Presentación_Proyecto_Inter_Modular_Módulo_Profesional_Optativo_David_Tío_Vallejo_SMR1_Caja_Mágica.pdf` → Presentación del módulo (PDF)

---

## Autor

**David Tío** — SMR 1 · Caja Mágica · Modulo Profesional Optativo
