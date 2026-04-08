# Cryptographic Solutions

La criptografía es la técnica de ocultar información mediante códigos.
Se usa principalmente el cifrado, que convierte datos normales (texto plano) en datos ilegibles (texto cifrado) usando una clave.

Solo quien tiene la clave puede volver a leer la información.

#### Tipos de datos protegidos

En reposo: datos guardados (disco, archivos)
En tránsito: datos que viajan por la red
En uso: datos que se están procesando

#### Cómo funciona

Un algoritmo es la fórmula matemática que cifra/descifra
La clave es lo más importante → da la seguridad real

No importa tanto el algoritmo, sino proteger bien la clave.

#### Seguridad de claves

Claves más largas = más seguras
Ej: 256 bits > 128 bits (mucho más difícil de romper)
Se deben cambiar periódicamente (rotación de claves)

## Cifrado simétrico vs asimétrico

Simétrico: usa una sola clave para cifrar y descifrar.
  - Rápido, pero difícil de compartir la clave de forma segura.
  - No garantiza quién hizo qué (no hay no repudio).
    
Asimétrico: usa dos claves (pública y privada).
  - Más seguro para compartir información, pero más lento.
  - Comparación clave.
  - El cifrado asimétrico usa clave pública y privada para asegurar confidencialidad, autenticación e integridad, y suele combinarse con cifrado simétrico por eficiencia.
    
Simétrico:  rápido (100–1000x más), pero problema de distribución
Asimétrico:  soluciona distribución, pero es más lento

 Por eso se usa un enfoque híbrido:

- Asimétrico para compartir la clave
- Simétrico para cifrar los datos
  
#### Tipos de cifrado

Cifrado de flujo: cifra bit a bit (ideal para streaming)
Cifrado por bloques: cifra en bloques de datos 64, 128, 256 bits en un bloque (más común y seguro)

Ambos se complementan para aprovechar seguridad + velocidad

## Algoritmos de cifrado simétrico

Los algoritmos simétricos usan una sola clave para cifrar y descifrar datos.

#### Principales algoritmos

DES: antiguo, clave débil (56 bits) → ya inseguro
3DES: mejora de DES (usa 3 claves) → más seguro, pero lento
IDEA: clave de 128 bits → más seguro que DES, poco usado
AES: ⭐ el más importante y actual
Claves de 128, 192 o 256 bits
Estándar moderno (muy seguro y usado)
Blowfish: alternativa a DES, poco adoptado
Twofish: versión mejorada, seguro pero no tan popular
RC Cipher Suite (Rivest), creo 6 distintos algoritmos de cifrados y le funcionaron los últimos 3 RC4, RC5 y RC6
RC4: cifrado de flujo (el único de la lista) → usado en SSL/WEP, hoy considerado débil
RC5 / RC6: cifrados de bloque, más avanzados

#### Tipos clave

Bloque: la mayoría (AES, DES, etc.)
Flujo: solo RC4

## Algoritmos asimétricos

Criptografía asimétrica (clave pública)
Usa 2 claves:

- Clave pública (se comparte)
- Clave privada (se mantiene secreta)

#### ¿Para qué sirve?

Confidencialidad:
→ cifras con la clave pública del receptor (solo él lo puede leer)
No repudio / autenticación:
→ cifras (firmas) con tu clave privada (prueba que fuiste vos)
Integridad:
→ se usa hash + firma digital

Para seguridad completa:
✔ Hash (integridad)
✔ Firma con clave privada (no repudio)
✔ Cifrado con clave pública (confidencialidad)

#### Algoritmos importantes

Diffie-Hellman → intercambio de claves y distribuirlas de forma segura (ej: VPN), también es susceptible de ataques en la ruta o de persona en el medio. Se considera un algoritmo asimétrico
RSA → se utiliza para el cifrado de intercambio de claves, firmas, muy usado
ECC → más eficiente, ideal para dispositivos móviles. se basa en la estructura algebraica de las curvas elípticas sobre campos finitos para definir sus claves, su algoritmo es 6 veces más eficaz que RSA
Variantes de ECC:
  - ECDH → intercambio de claves (versión ECC de Diffie-Hellman)
  - ECDHE → igual que ECDH pero usa claves temporales (más seguro)
  - ECDSA → firma digital (verifica identidad)

## Hashing

“El hashing genera una huella única e irreversible para verificar la integridad de los datos”. Es una función unidireccional
Convierte datos en un hash (huella digital), no se puede recuperar el mensaje original y siempre tiene longitud fija

Características clave:
Un pequeño cambio en el mensaje → cambia totalmente el hash
Sirve para verificar integridad
Puede haber colisiones (dos inputs con mismo hash)

Algoritmos importantes:
MD5 → antiguo, inseguro (128 bits)
SHA (SHA-1, SHA-2, SHA-3) → más seguros (recomendados)
RIPEMD → alternativa, menos usado
HMAC → hash + clave (autenticación)

Firma digital (idea clave)... → las firmas digitales son básicamente un resumen hash cifrado que se adjunta a un archivo determinado. Esta firma digital se crea haciendo un hash de un archivo y, a continuación, tomando el resumen del hash resultante y cifrándolo con la clave privada del firmante.
Se hace un hash del mensaje, se cifra con clave privada y se envía junto al mensaje

Sirve para:

- Integridad
- Autenticación
- No repudio
