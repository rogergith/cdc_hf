
# CDC HF: 

> *REPORT SELL, CREATE CUSTOMER AND MIGRATION SQL*


## PASO 1: Desplegar las siguientes ramas

 - **CoreServicesHF**
   - `merge_user_hf_to_ky_and_reportSeller_and_CreateCustomer`
 - **scr-admin**
   - `feat_reportAgent`
## PASO 2: Ejecutar los siguientes script
 - `operatorSellerUpdated.sql`
 - `MigrationOperatorEmailAndSeller.sql`

# CDC KY
## PASO 1: Desplegar las siguientes ramas

- **CoreServicesKY**
  - `merge_ky_online_produccion`
- **Evento KY Online Context** *`/kiyosaki-miami-online`*
  - `kiyosaki_online`
- **Admin KY Miami México Context** *`/kiyosaki-admin`*
  - `feat/scanQR_uncheck_role_miami_mexico`

## PASO 2: Ejecutar los siguientes script

 - `scrip-cdc-kiyosaki-online-new.sql` 
   - (En este script hay una sentencia que se debe ejecutar solo en la BD HF)





```sql
UPDATE public.fund_lang SET description='ÚLTIMA OPORTUNIDAD DE APRENDER DIRECTAMENTE DE ROBERT KIYOSAKI CÓMO GENERAR INGRESOS PASIVOS Y ASEGURAR TU LIBERTAD FINANCIERA DE POR VIDA' WHERE fund_id=658 AND lang_id=1;

UPDATE public.fund_lang SET description='ÚLTIMA OPORTUNIDAD DE APRENDER DIRECTAMENTE DE ROBERT KIYOSAKI CÓMO GENERAR INGRESOS PASIVOS Y ASEGURAR TU LIBERTAD FINANCIERA DE POR VIDA' WHERE fund_id=658 AND lang_id=2;

INSERT INTO public.application_parameter (application_id, "name", value, description)

VALUES(627, 'CHECK_CAPTCHA', 'false', 'controla la visibilidad del captcha');

INSERT INTO public.application_parameter (application_id, "name", value, description)

VALUES(628, 'CHECK_CAPTCHA', 'false', 'controla la visibilidad del captcha');

INSERT INTO public.system_property (id, "name", value, description) VALUES(30, 'url_core', 'https://coredev.harvestful.org/CoreServicesHF/rest/api/request', 'URL CORE HF');

--EJECUTAR EN LA BD HF

INSERT INTO public."method" (id, "name", description, implementor_class, method_type_id, module_id, created_at)

VALUES(279, 'findUserWithPasswordMethodImpl', '', 'com.us.weavx.core.services.impl.FindUserWithPasswordMethodImpl', 2, 3, '2024-09-10 01:13:06.176');
```
