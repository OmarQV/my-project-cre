# Mi Proyecto Chainlink CRE (Chainlink Runtime Environment)

Bienvenido al espacio de trabajo principal de tu proyecto local para [Chainlink Runtime Environment (CRE)](https://docs.chain.link/cre).
Este directorio raíz contiene tus flujos de trabajo (*workflows*) y configuraciones de entorno global, permitiendo desarrollar y simular aplicaciones off-chain respaldadas por los oráculos de Chainlink.

---

## 📁 Estructura del Workspace

Actualmente este espacio de trabajo contiene los siguientes elementos principales:

* **`/hellow_world_TS`**: Un flujo de trabajo de ejemplo que demuestra el caso de uso más básico en CRE: un *Cron Job* automatizado en TypeScript. Muestra cómo usar capacidades (Capabilities), configurar los tiempos de ejecución y manejar eventos repetitivos descentralizados de forma segura. Contiene su propio archivo [README.md](hellow_world_TS/README.md) con detalles y diagramas arquitectónicos avanzados.
* **`project.yaml`**: Archivo principal usado por el entorno de Chainlink CRE (CLI) para la configuración general de este espacio de proyecto.
* **`secrets.yaml`**: (Opcional/General). Aquí se pueden almacenar referencias de secretos a compartir entre varios flujos de trabajo si la topología incluye un orquestador o entorno local multi-workflow.
* **`.env`** (debes crearlo): Contiene las variables de entorno principales, como `CRE_ETH_PRIVATE_KEY` para simulaciones de despliegues.

---

## 🛠 Entorno de Desarrollo

Para trabajar con Chainlink CRE en tu máquina local (Windows o Unix) desde este espacio de trabajo:

1. **Instalar Dependencias Globales:**
   * Tener [Bun](https://bun.sh/) instalado para la gestión de paquetes e intérprete JS/TS ultrarrápido.
   * [Chainlink CLI (`cre`)](https://docs.chain.link/cre/getting-started/cli-installation) instalado globalmente.

2. **Configurar Llaves y Entorno:**
   Crea un archivo llamado `.env` en este directorio raíz (donde se encuentra el `project.yaml`) y configura una llave privada para la simulación de red:
   ```env
   # Llave privada de simulación ficticia para pruebas locales aisladas sin On-chain
   CRE_ETH_PRIVATE_KEY=0000000000000000000000000000000000000000000000000000000000000001
   ```

3. **Ejecutar Simulaciones desde la Raíz:**
   El flujo natural de desarrollo en CRE exige que las simulaciones se ejecuten **desde la raíz del Workspace**, referenciando el `workflow.yaml` individual de cada carpeta. Por ejemplo, para hacer correr el Hello World:

   ```bash
   cre workflow simulate hellow_world_TS/workflow.yaml --target=staging-settings
   ```

---

## 🚀 Próximos Pasos

Una vez familiarizado con la ejecución básica del Workflow en `/hellow_world_TS`, puedes crear tus propios workflows a medida generándolos de cero.
Usa la interfaz interactiva o corre:

```bash
cre init
```

Para ver la documentación oficial de Chainlink, visita [docs.chain.link/cre](https://docs.chain.link/cre).
