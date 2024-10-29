# CDC a PRODUCCIÓN

## PASO 1: Desplegar las siguientes ramas

- **CoreServicesHF**
  - `merge_user_hf_to_ky_and_reportSeller_and_CreateCustomer`
- **scr-admin**
  - `feat_reportAgent`
- **CoreServicesKY**
  - `merge_ky_online_produccion`
- **Evento KY Online Context** 
  - `/kiyosaki-miami-online`
  - `kiyosaki_online`
- **Admin KY Miami México**
  - `feat/scanQR_uncheck_role_miami_mexico`

## PASO 2: Aplicar scripts adjuntados en esta card

**SE DEBE APLICAR LOS SIGUIENTES SCRIPTS EN EL SIGUIENTE ORDEN:**

1. `operatorSellerUpdated.sql`
2. `MigrationOperatorEmailAndSeller.sql`
3. `scrip-cdc-kiyosaki-online-new.sql` 
   - (En este script hay una sentencia que se debe ejecutar solo en la BD HF)
