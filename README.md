# catstagram

> "Catstagram v1.0.0" by IPaHe

## Correr en modo de desarrollo + preguntas y respuestas

``` bash
# Instalar dependencias a través de NPM
npm install

# Correr server de desarrollo en la dirección y puerto localhost:8080
npm run dev

# Generar proyecto listo para produccion con código "minificado"
npm run build

### ¿Qué tecnología/herramientas utilizarías para guardar los favoritos de cada visitante de manera tal que cada browser tenga una lista distinta de favoritos?
LocalStorage ya que tiene soporte para la mayoria de los navegadores modernos y los datos son almacenados directamente en el mismo

### Explica qué tecnologías (AWS, Firebase) podrías utilizar para que un usuario pueda tener una lista de favoritos que pueda llevar a distintas sesiones de navegador
Por simplicidad de uso y bajo costo elegiria Firebase aunque si a futuro se pretende crecer la aplicación a gran escala, AWS ofrece un conjunto de soluciones casi todo en uno y por supuesto son un conjunto de tecnologias mas maduras que el mismo Firebase

### ¿Qué recomendaciones de SEO harías para que tu app sea un éxito en los buscadores?
Optimizar la estructura html a través de meta-etiquetas que proporcionene una mejor visibilidad en los buscadores
Incluir titulos y subtitulos con palabras clave relevantes
Usar URL amigables
Diseño responsive
Mantener siempre un contenido fresco