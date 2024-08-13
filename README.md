# Curso de Realidad Aumentada con Unity

Durante este curso crearas una aplicación profesional de Realidad Aumentada llamada AR Furniture, la cual permite al usuario posicionar objetos en su entorno al selecionarlos desde un inventario. Una vez posicionados, pueden ser seleccionados, movidos y rotados, además es posible tomar una foto del ambiente con los objetos en AR y compartirla en redes sociales

### Requerimientos

## Capitulo uno: ¿Cómo crear una aplicación de Realidad Aumentada?

[![Mira el video en YouTube](https://i9.ytimg.com/vi_webp/TI599JorZ5M/maxresdefault.webp?v=620b6a77&sqp=CKTk7LUG&rs=AOn4CLBlqcNwafIEZnnow0CLR4THMVrorg)](https://youtu.be/TI599JorZ5M)

### Configuracion

1. Desabilitar Auto Graphics API (Si no aparece la opcion de eliminar Vulkan)
2. Eliminar Vulkan
3. Minimum API Level → Android 8.0 'Ore' (API Level 26)
4. Scripting Backen → IL2CPP
5. Api Compatibility Level* → NET 4.X o .Net Framework
6. Target Architecture → ARMv7 y ARM64 (Si presenta errores desactivar ARMv7)

![image](https://github.com/user-attachments/assets/eacef1cb-2600-4995-8e5b-c4256b384cf5)

### Versiones

La version de ARFoundation y ARCore que aparecera en Package Manager, dependera de la version de Unity que esten usando, eleguir la que aparezca.

| Editor Version | AR Foundation Version |
|----------------|-----------------------|
| 2022.3+        | 5.1                   |
| 2021.3+        | 5.1                   |
| 2020.3+        | 4.2                   |

*Notas:* 

*1. ARCore XR Plugin es el mismo que Google ARCore XR Plugin*

*2. En recientes versiones de Unity ya no aparece el icono al script GameManager*

## Capitulo dos: Diseño de Interfaz para Realidad Aumentada

[![Mira el video en YouTube](https://i9.ytimg.com/vi/97d-2bPKhgk/maxresdefault.jpg?v=620301fe&sqp=CND87bUG&rs=AOn4CLAQyhi82FN9pZ9qaR6I-O8Aw7zbEQ)](https://youtu.be/97d-2bPKhgk)

### UI 

En versiones mas reciente de Unity, existen dos tipos de elementos de la UI: 

- TextMeshPro
- Legacy

Este video emplea los elementos Legacy, se pueden usar ambos tipos, pero si se usa TextMeshPro se debe hacer un pequeno cambio mas adelante en el codigo. 

![image](https://github.com/user-attachments/assets/6d299d1a-ad54-4206-96ba-7b7a99ed4660)

Para mejorar el Scroll selecionar Scroll View → En Scroll Rect → Desactivar Veritcal

![image](https://github.com/user-attachments/assets/84f3066c-830b-4a56-87e5-38de5f4691ab)

### DOTween

[Link DOTween (HOTween v2) en Unity Asset Store](https://assetstore.unity.com/packages/tools/animation/dotween-hotween-v2-27676)
