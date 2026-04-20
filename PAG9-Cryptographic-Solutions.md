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
  - La clave privada nunca se comparte y solo el dueño puede descifrar los datos
    
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
RSA → se utiliza para el cifrado de intercambio de claves, firmas, muy usado, simetrico
ECC → más eficiente, ideal para dispositivos móviles. se basa en la estructura algebraica de las curvas elípticas sobre campos finitos para definir sus claves, su algoritmo es 6 veces más eficaz que RSA, asimetrico
Variantes de ECC:
  - ECDH → intercambio de claves (versión ECC de Diffie-Hellman)
  - ECDHE → igual que ECDH pero usa claves temporales (más seguro)
  - ECDSA → firma digital (verifica identidad)

#### +Caracteristicas

RSA
Criptografía asimétrica
Usa clave pública + clave privada
No cumple lo de “una sola clave”

ECC
También asimétrica
Más eficiente que RSA, pero igual usa dos claves

AES
Simétrica 
Una sola clave 

Diffie-Hellman
No cifra datos directamente
Sirve para intercambiar claves, no para cifrar

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

## Ataques a hashes

Antes de todo hay que tener en cuenta que Las contraseñas no se cifran, se almacenan como hashes para evitar su recuperación en texto plano.

1. Pass-the-Hash → el atacante usa el hash como si fuera la contraseña (no necesita descifrarla). Es decir, es una técnica de hacking que le permite a un atacante autenticarse en un servidor o servicio remoto utilizando el hash subyacente de la contraseña de un usuario en lugar de asociar realmente la contraseña de texto plano con la que normalmente tiene que iniciar sesión. Es realmente difícil de defender porque hay muchos exploits posibles dentro del sistema operativo Windows, así como las aplicaciones que se ejecutan sobre él. Cualquiera de estos puede ser utilizado por un atacante para elevar sus permisos y luego ser capaz de llevar a cabo la recolección de credenciales o recolección de hash que luego puede utilizar en un ataque posterior utilizando la técnica de pasar el hash.

Ejemplo rápido:
Tu contraseña: 123456
Hash guardado: ABC123XYZ

Atacante roba: ABC123XYZ
  - No intenta saber que es 123456
  - Usa ABC123XYZ directamente para entrar

Para evitar el ataque Pass-the-Hash, debe asegurarse de que sólo los sistemas operativos de confianza se les permite conectarse a sus servidores que sus dominios de Windows tienen su confianza configurado correctamente y que todas las estaciones de trabajo van a ser parcheado y actualizado, así como asegurarse
de que su autenticación multifactor se está utilizando correctamente en su red y que todas las cuentas de usuario se han configurado para utilizar el concepto de privilegio de arrendamiento.
    
2. Birthday Attack → busca colisiones (dos inputs con el mismo hash), es decir que ocurre cuando un atacante logra que dos mensajes distintos tengan el mismo hash (colisión).
Se basa en la paradoja del cumpleaños y es más fácil encontrar coincidencias de lo que parece.

Si dos datos tienen el mismo hash:

- Se puede engañar sistemas
- Incluso bypassear autenticación

Por eso hoy en dia es importante utilizar cosas como SHA-256 sobre MD5 porque esto reducirá significativamente la cantidad de colisiones y la efectividad de un ataque de cumpleaños.
Cómo aumentar la seguridad:

1. Key Stretching (estiramiento de claves)
Especial para los Ataques de fuerza bruta. Repite el hashing varias veces y hace más lento el ataque, se somete a un algoritmo para crear una clave más larga y segura que la que se utilizaría normalmente.
Muchos sistemas van a utilizar el estiramiento de claves para aumentar la seguridad que proporcionan, incluyendo sistemas como Wifi Protected Access, Wifi Protected Access 2,
Pretty Good Privacy Decrypt y otros, que todos utilizan el estiramiento de claves para mitigar una debilidad inherente a las claves más cortas.

2. Salting (salazón)
Añade datos aleatorios a la contraseña antes del hash
Evita diccionarios, fuerza bruta y rainbow tables

3. Nonce
utilizar un nonce es una forma estratégica de mejorar la seguridad de las contraseñas potencialmente vulnerables. Nonce, que significa número utilizado una vez, es un número único a menudo aleatorio que se va a añadir al proceso
de autenticación basado en contraseña. La función principal de un nonce es garantizar que incluso si el atacante es capaz de obtener tu contraseña o sus correspondientes datos de autenticación, simplemente no pueda reutilizarlos para un acceso no autorizado.
Al añadir este número transitorio a la secuencia de autenticación, los datos hash resultantes cambiarán cada vez y dificultarán considerablemente que un ciberdelincuente se aproveche de las credenciales robadas.
Este enfoque efímero va a añadir una capa adicional de seguridad, especialmente en sistemas vulnerables a ataques de repetición en los que el atacante intenta volver a enviar datos de captura para acceder a ellos sin autorización.

Brute Force Attack (Ataque de fuerza bruta)
Los ataques de fuerza bruta en los que se prueban todas las combinaciones posibles de contraseñas, se convierten en un proceso mucho más lento debido
al proceso de salting.

Rainbown Tables (Tablas Arco iris)
Las tablas arcoíris permiten invertir hashes rápidamente, pero el salting las vuelve impracticables al generar hashes únicos por contraseña
Reduce ataques de fuerza bruta

Si el atacante ya hizo el trabajo antes

En vez de:

calcular hash cada vez ❌

Hace:

busca directamente en la tabla ✔
Ejemplo

Imaginá esto:

Contraseña: 123456, password
Hash : abc123, xyz789

Si roba el hash xyz789
Busca en la tabla → encuentra password

Listo, ya sabe la contraseña

¿Por qué es peligroso?

Porque es MUY rápido

No calcula nada → solo busca

¿Y el salting?

Lo rompe completamente. Sin sal:

password → siempre mismo hash

Con sal:

password + sal1 → hash A
password + sal2 → hash B

Ya no hay una única respuesta en la tabla y la tabla deja de servir

Resumen:

Rainbow Table = “diccionario de hashes ya calculados”
Salting = “hace inútiles esas tablas”

## PKI (Infraestructura de Clave Pública)

PKI es un sistema completo (hardware, software, personas y reglas) que usa criptografía asimétrica para asegurar comunicaciones.
Se usa en cosas cotidianas como HTTPS (el candado del navegador). La infraestructura de clave publica es un protoco de seguridad y HTTPS lo contiene

#### Cómo funciona (ejemplo web (Comunicacion, asignacion de clave ida y vuelta, entre los 2 servidores)):
Tu navegador pide la clave pública del servidor a una Autoridad de Certificación (CA).
Genera una clave secreta (simétrica).
La cifra con la clave pública del servidor y se la envía.
Solo el servidor del oponente la descifra con su clave privada, asignada por el servidor de la web.
Desde ahí, ambos usan cifrado simétrico (ej: AES) para comunicarse rápido y seguro.

#### Qué garantiza:
Confidencialidad → nadie puede leer los datos.
Autenticación → sabés que el servidor es real.
Integridad y seguridad en la comunicación.

#### Componentes clave:
Autoridad de Certificación (CA) → tercero confiable que valida identidades y emite certificados.
Certificados digitales → vinculan identidad + clave pública.
Custodia de claves → guarda claves por si se pierden (aunque tiene riesgos de seguridad).

Idea clave:

PKI es fundamental para garantizar la seguridad de la comunicación y el intercambio de datos que se produce en Internet, y componentes como la custodia de claves van a proporcionarnos capas adicionales de flexibilidad y garantía,
pero también introducen su propio conjunto de retos que debemos gestionar eficazmente para garantizar la seguridad de nuestras redes empresariales.

Criptografía de clave pública → solo cifrar/descifrar.
PKI → todo el sistema que hace posible usar eso de forma segura en la vida real.

Para más información: https://www.ssldragon.com/es/blog/clave-publica-vs-clave-privada/

## Certificados Digitales
Un certificado digital es un documento electrónico que vincula una clave pública con la identidad de una persona, servidor o dispositivo, y está firmado por una entidad de confianza. Sirven para probar identidad + permitir conexión segura

### Puntos clave
Formato: X.509. (formato estándar que usan los certificados para que todos los sistemas (navegadores, servidores, etc.) puedan confiar y entenderlos). Incluye cosas como:

                                                                                                                                                      - Identidad del dueño (nombre, organización)
                                                                                                                                                      - Clave pública
                                                                                                                                                      - Autoridad de certificación (CA)
                                                                                                                                                      - Fecha de validez
                                                                                                                                                      - Firma digital
                                                                                                                                                      - Datos de la autoridad que lo emitió

### Tipos importantes
Certificado comodín (Wildcard):
Garantiza: seguridad para todos los subdominios y sirve para ahorrar y simplificar gestión
Ejemplo:
protege www.ejemplo.com, api.ejemplo.com, etc.

#### Certificado SAN (multi-dominio)
Garantiza: seguridad para varios dominios distintos. Sirve para: empresas con muchos dominios
Ejemplo:
google.com + youtube.com

#### Certificado de Una cara vs Dos caras:
Una cara: solo el servidor se identifica
Dos caras: servidor y cliente se autentican (más seguro)

#### Certificado Autofirmado:
Lo firma el propio servidor → menos confiable (sin tercero), es decir, firma la misma entidad cuya identidad está certificando, en lugar de una autoridad de certificación de confianza o un tercero.
Por lo general, se utilizarán en entornos de prueba, sistemas cerrados y sistemas de no producción en los que ya se ha establecido la confianza.

Pero cada vez que acceda a un sitio que utilice uno de estos certificados autofirmados, aparecerá una advertencia en su navegador, especialmente si lo utiliza en un sitio web público, ya que carece del respaldo de un tercero
de confianza.

#### Certificado De terceros sería:
Emitido por una Autoridad de Certificación (CA) → confiable

#### Raiz de la Confianza (muy importante)
Todo funciona con unao como una Cadena de Confianza (Root Trust), se confia desde abajo hasta arriba, ej: si lo pensamos como arbol genealogico, supongamos que era amigo de su abuelo y confiaba en el, y tuvo un hijo y ese hijo tuvo un nieto y seguimos confiando en su familia, asi lo debemos pensar...
El abuelo en este ejemplo es la autoridad de certificación raíz porque es el nivel más alto en este pequeño árbol genealógico particular. El árbol genealógico se va a conocer como nuestra ruta de certificación en el mundo de los certificados digitales.
Si confías en la CA raíz → confías en los certificados que emite

#### CA (Autoridad de Certificación): 
es la tercera parte de confianza que va a emitir estos certificados digitales y, por lo tanto, el certificado también va a contener su nombre, su firma digital, el número de serie de ese certificado, 
la fecha de emisión y caducidad, y la versión de ese certificado. Para obtener un certificado digital para su servidor web,  tiene que comprarlo a una autoridad de certificación o autoridad de registro, 
lo que nos lleva a nuestro séptimo término, la autoridad de registro.

#### RA (Autoridad de Registro): 
Para que se emitan certificados digitales, el usuario tiene que solicitar primero un certificado digital a una autoridad de registro, lo que se conoce como RA.
A continuación, la autoridad de registro solicitará la información de identificación del usuario y remitirá dicha solicitud de certificado a la autoridad de certificación,
que creará el certificado digital para el usuario.
Existen muchas autoridades de certificación raíz, como Verisign, DigiSign y muchas otras, que pueden actuar como terceros de confianza para validar que los certificados se expiden a las personas correctas. En pocas palabras valida identidad antes de emitir.

Así, cuando quiera ir a nuestro servidor web de diontraining. com, tu navegador web se dirige a nuestro tercero de confianza, extrae nuestra clave pública y la utiliza para cifrar una larga serie de números aleatorios que podemos usar como clave secreta compartida. 
Pero ya que lo encriptó usando el diontraining. com, sólo ese servidor será capaz de descifrar tu mensaje, leer esa larga serie aleatoria de números que tu sistema eligió, y luego usarla para crear un túnel de cifrado masivo usando algoritmos de cifrado simétricos como AES con esa clave secreta compartida recién elegida.

#### CSR:
Solicitud de firma para pedir un certificado, Es importante señalar que la clave privada asociada a la solicitud permanece en poder del solicitante y nunca se envía a la autoridad de certificación, ya que así se garantiza la confidencialidad de ese par de claves.
Una vez que la autoridad de certificación valida las credenciales de la entidad y procesa la solicitud de firma de certificado, el certificado resultante se devuelve a la entidad y puede instalarse en todos sus servidores para facilitar las comunicaciones seguras.

#### CRL / OCSP (Revocación de certificados:  
verifican si un certificado fue revocado

#### Seguridad adicional
- OCSP Stapling: acelera la validación
- Pinning: evita certificados falsos
- Custodia de claves: guarda copias seguras de claves privadas
- Recuperación de claves: permite restaurarlas si se pierden

Idea clave final, todo esto existe para garantizar:

- Confianza
- Identidad
- Comunicación segura (HTTPS)

## Ataques Criptográficos

Los ataques criptográficos son técnicas para romper la seguridad del cifrado y acceder o manipular datos protegidos con la intención de comprometer la confidencialidad, integridad y autenticidad de sus datos.
Estos métodos pueden ir desde explotar las debilidades de los algoritmos y protocolos criptográficos hasta aprovechar los fallos en las implementaciones de software o simplemente utilizar técnicas de fuerza bruta para adivinar la clave.

Los principales tipos son:

1. Ataques de degradación (downgrade)
El atacante obliga al sistema a usar versiones antiguas y débiles de cifrado.
Así aprovecha fallas conocidas.
Ejemplo: forzar usar SSL viejo en vez de TLS moderno.
Los ataques a la baja(degradación) ha llevado al desarrollo de contramedidas para ayudar a prevenirlos. Por ejemplo, muchos sistemas han eliminado gradualmente la
compatibilidad con protocolos heredados que se sabe que son realmente inseguros

Problema: los sistemas mantienen compatibilidad con lo viejo.

2. Ataques de colisión
Buscan dos datos diferentes que generen el mismo hash. Por ejemplo, al descargar un archivo de Internet, el sitio web puede proporcionar un valor hash para ese archivo. Una vez que termines de descargar el archivo,
puedes pasarlo por un algoritmo hash y calcular un nuevo resumen hash. Luego lo comparas conel que aparece en la página web. Si coinciden, se supone que el archivo no ha sido manipulado.
Sin embargo, si un atacante puede producir un archivo malicioso con el mismo valor hash explotando una colisión, el usuario podría ser engañado haciéndole creer que tiene un archivo legítimo cuando en
realidad tiene un archivo que tiene el mismo valor hash, lo que significa que está sujeto a una colisión("Esto rompe la confianza en los hashes.")

el "Ataque de Cumpleaños" se refiere a la probabilidad de que dos entradas o archivos distintos, cuando se procesan a través de la misma función hash, produzcan la misma salida, lo que llamamos una colisión.

Ejemplo:
Un archivo falso puede tener el mismo hash que uno real.
Por eso MD5 ya no se usa (es inseguro).

4. Computación cuántica (amenaza futura)
Computadoras cuánticas pueden resolver problemas matemáticos muy rápido.
Podrían romper cifrados actuales como RSA o ECC.

Aún no es una amenaza práctica hoy, pero lo será.

Solución: criptografía post-cuántica.

### Resumen: 

Un ataque de degradación criptográfica se utiliza para forzar a un sistema a utilizar un estándar o protocolo criptográfico más débil o antiguo que el que utiliza actualmente. Se va a utilizar un ataque de colisión para encontrar dos entradas diferentes que produzcan
la misma salida hash utilizando los principios demostrados por la Paradoja del Cumpleaños. La computación cuántica, por su parte, se encuentra hoy más en la fase teórica que en la práctica, y aprovecha los principios de la mecánica cuántica para procesar grandes cantidades de 
información simultáneamente con el fin de permitir romper potencialmente algoritmos de cifrado tradicionales como RSA y ECC en sólo unos segundos mediante la factorización rápida de grandes números primos o la resolución de problemas logarítmicos discretos.


### INFORMACIÓN BREVE-ADICIONAL A TENER EN CUENTA!

#### Steganography
Oculta datos dentro de imágenes, audio, video, etc.
No cambia visiblemente el archivo
Ej: esconder texto en los píxeles de una imagen

#### Tokenization
Reemplaza datos sensibles por “tokens”
Ej: tarjeta → XXXX-XXXX
No oculta datos en imágenes

#### Data Masking
Oculta parcialmente datos (ej: ****1234)
Usado en bases de datos
No sirve para esconder mensajes en archivos

#### Encryption
Convierte datos en ilegibles
Pero se nota que está cifrado
No lo oculta dentro de una imagen
