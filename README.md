# 📢 **Actualización y pasos a seguir durante el Curso de Realidad Aumentada con Unity** 📱

Durante este curso, crearás una aplicación profesional de Realidad Aumentada llamada **AR Furniture**. Esta aplicación permite al usuario posicionar objetos en su entorno seleccionándolos desde un inventario. Una vez colocados, los objetos pueden ser seleccionados, movidos y rotados. Además, es posible tomar una foto del entorno con los objetos en AR y compartirla en redes sociales.


https://github.com/user-attachments/assets/9bea7d53-a317-4830-a8d5-589b8944b1e7




## 📖 Capitulos

- [Capitulo 0](#capitulo-cero-requerimientos)
- [Capitulo 1](#capitulo-uno-cómo-crear-una-aplicación-de-realidad-aumentada)
- [Capitulo 2](#capitulo-dos-diseño-de-interfaz-para-realidad-aumentada)
- [Capitulo 3](#capitulo-tres-detección-de-planos-y-nube-de-puntos-en-realidad-aumentada)
- [Capitulo 4](#capitulo-cuatro-cómo-integrar-modelos-3d-en-realidad-aumentada)
- [Capitulo 5](#capitulo-cinco-posicionar-modelos-3d-en-realidad-aumentada)
- [Capitulo 6](#capitulo-seis-rotar-y-seleccionar-modelos-3d-en-realidad-aumentada)
- [Capitulo 7](#capitulo-siete-fotos-en-realidad-aumentada)
- [Capitulo 8](#capitulo-ocho-actualizar-contenido-en-tiempo-real-realidad-aumentada)

## 📞 Contacto

- **🐼 [Discord](https://discord.gg/TBjZuCSmG2)**
- **🐦 [Twitter / X ](https://twitter.com/UnityAdventure)**
- **📷 [Instagram](https://www.instagram.com/unity_adventure)**


## Capitulo cero: Requerimientos

### Unity

Este curso ha sido desarrollado con Unity 2020.3.19f1 LTS, pero es compatible con:

- Unity 2020.3.x
- Unity 2021.3.x
- Unity 2022.3.x

Es importante que la versión de Unity que vayan a usar tenga los módulos de Android instalados. ¿Cómo saber si tienes los módulos de Android?

1. Abre Unity Hub.
2. Ve a **Installs**.
3. Haz clic en el ícono ⚙️ de la versión.
4. Selecciona **Add Modules**.
5. Debes tener instalados:
   - OpenJDK
   - Android SDK & NDK Tools
6. Si no los tienen instalados, simplemente selecciónalos e instalan.

<img src="https://github.com/user-attachments/assets/b051eb56-22d3-4b8a-b5d5-a920e8833d34" alt="Hub" width="750"/>

### Visual Studio

Para este curso, el desarrollo del código se realiza con Visual Studio. Aunque no es obligatorio, se recomienda usarlo para seguir los videos de manera más efectiva. Puedes utilizar:

- Visual Studio Community 2019
- Visual Studio Community 2022

Visual Studio debe estar correctamente instalado y configurado, y debe estar enlazado con Unity. Para hacerlo:

1. Abre el instalador de Visual Studio.
2. Selecciona la versión de Visual Studio y haz clic en **Modify**.
3. Añade **Game Development with Unity**. <br> <img src="https://github.com/user-attachments/assets/76d81690-a588-490d-96d0-ea4ce6a762f8" alt="Hub" width="450"/>
4. En el proyecto de Unity en el que vayas a trabajar, ve a **Edit → Preferences → External Tools → External Script Editor** y selecciona la versión de Visual Studio que vas a usar.
   ![image](https://github.com/user-attachments/assets/8f0bafab-86e0-412e-95fb-d3c8c4c7cf5f)

**¡Ahora sí, estás listo para comenzar el curso! A continuación, encontrarás los capítulos y algunas consideraciones importantes a tener en cuenta.**

## Capitulo uno: ¿Cómo crear una aplicación de Realidad Aumentada?

**⬇️⬇️⬇️ Click en la imagen para ver el video 👇👇👇**

<table>
  <tr>
    <td>
      <a href="https://youtu.be/TI599JorZ5M">
        <img src="https://github.com/user-attachments/assets/c88d1e30-c87e-4d7e-8a14-3d50b1d61d1e" alt="Mira el video en YouTube" width="600"/>
      </a>
    </td>
  </tr>
</table>


### Configuración

1. Deshabilitar Auto Graphics API (si no aparece la opción de eliminar Vulkan).
2. Eliminar Vulkan.
3. Minimum API Level → Android 8.0 'Oreo' (API Level 26).
4. Scripting Backend → IL2CPP.
5. API Compatibility Level → .NET 4.X o .NET Framework.
6. Target Architecture → ARMv7 y ARM64 (si presenta errores, desactivar ARMv7).

![image](https://github.com/user-attachments/assets/eacef1cb-2600-4995-8e5b-c4256b384cf5)

### Versiones

La versión de AR Foundation y ARCore que aparecerá en el Package Manager dependerá de la versión de Unity que estén usando. Elijan la que aparezca.

| Editor Version | AR Foundation Version |
|----------------|-----------------------|
| 2022.3+        | 5.1                   |
| 2021.3+        | 5.1                   |
| 2020.3+        | 4.2                   |

*Notas:*

*1. ARCore XR Plugin es el mismo que Google ARCore XR Plugin.*

*2. En versiones recientes de Unity, ya no aparece el ícono en el script GameManager.*

## Capitulo dos: Diseño de Interfaz para Realidad Aumentada

**⬇️⬇️⬇️ Click en la imagen para ver el video 👇👇👇**
<table>
  <tr>
    <td>
      <a href="https://youtu.be/97d-2bPKhgk">
        <img src="https://github.com/user-attachments/assets/8859a4b6-dcb5-466b-b783-ea1eaad949c9" alt="Mira el video en YouTube" width="600"/>
      </a>
    </td>
  </tr>
</table>

### UI 

En versiones más recientes de Unity, existen dos tipos de elementos de la UI:

TextMeshPro
Legacy
Para las versiones recientes, este video emplea los elementos Legacy. Se pueden usar ambos tipos, pero si se usa TextMeshPro, se debe hacer un pequeño cambio más adelante en el código.

<img src="https://github.com/user-attachments/assets/6d299d1a-ad54-4206-96ba-7b7a99ed4660" alt="Hub" width="600"/>

*Nota: Si usan la misma versión del video, seleccionen la misma tal cual.*

Para mejorar el scroll, seleccionen Scroll View → En Scroll Rect → Desactivar Vertical.

<img src="https://github.com/user-attachments/assets/84f3066c-830b-4a56-87e5-38de5f4691ab" alt="Hub" width="400"/>

### DOTween

[Link DOTween (HOTween v2) en Unity Asset Store](https://assetstore.unity.com/packages/tools/animation/dotween-hotween-v2-27676)  

## Capitulo tres: Detección de planos y nube de puntos en Realidad Aumentada


**⬇️⬇️⬇️ Click en la imagen para ver el video 👇👇👇**
<table>
  <tr>
    <td>
      <a href="https://youtu.be/6bRkKZ9Onk4">
        <img src="https://github.com/user-attachments/assets/83f49b42-fe9f-487f-a81b-4a9980f94585" alt="Mira el video en YouTube" width="600"/>
      </a>
    </td>
  </tr>
</table>

En las versiones recientes de ARFoundation se han cambiado algunos nombres: 

- **AR Session Origin → XR Origin**

El video usa AR Session Origin, si no esta se debe usar XR Origin en su lugar, verificar que este GameObject se encuentre en la posicion (0,0,0)

## Capitulo cuatro: ¿Cómo integrar Modelos 3D en Realidad Aumentada?

**⬇️⬇️⬇️ Click en la imagen para ver el video 👇👇👇**
<table>
  <tr>
    <td>
      <a href="https://www.youtube.com/watch?v=ETeSDb1-Cco">
        <img src="https://github.com/user-attachments/assets/30822169-c949-4a37-8681-e1e02b0d912b" alt="Mira el video en YouTube" width="600"/>
      </a>
    </td>
  </tr>
</table>

### ¿Qué hago si mi modelo 3D no aparece en AR?

1. Verificar la escala del modelo; puede que tu modelo esté muy grande o muy pequeño. Para ello, usa el cubo de Unity como referencia; ese cubo tiene 1x1x1 metro.
2. Asegurarse de que el modelo esté en la posición (0, 0, 0).
3. Posicionar el pivote en el centro del modelo 3D.

- **Pivote**
   - Modelo 3D

Respetar esta jerarquía: crea un *empty object* (pivote) y haz que el modelo 3D sea hijo de este GameObject. Luego, recuerda que es el modelo 3D el que debes mover para que quede posicionado correctamente respecto al pivote.

<img src="https://github.com/user-attachments/assets/3b4089f8-8d09-451f-988c-70b402edf402" alt="Hub" width="600"/>

### Button Item Prefab

Al definir el prefab del botón, es obligatorio seguir este orden de jerarquía:

- ButtonItemPrefab
  - ItemName
  - ItemImage
  - ItemDescription

<img src="https://github.com/user-attachments/assets/e7d4a52e-f122-49c8-a4e8-d5d8bcb1d771" alt="Hub" width="600"/>

### Script ItemButtonManager

¡Importante! En el capítulo 2 sobre la UI, mencioné que existen dos tipos de UI: TextMeshPro y Legacy. Dependiendo de cuál hayan elegido, el código cambiará.

- **Legacy** o la misma del video:

  El código funciona tal cual y no necesita cambios.

- **TextMeshPro**:

  Añadir el namespace:

  ```csharp
  using TMPro;
  ```

  Cambiar esta parte de la función `Start` para que quede así:

  ```csharp
  void Start()
  {
      transform.GetChild(0).GetComponent<TextMeshProUGUI>().text = itemName;
      transform.GetChild(1).GetComponent<RawImage>().texture = itemImage.texture;
      transform.GetChild(2).GetComponent<TextMeshProUGUI>().text = itemDescription;

      var button = GetComponent<Button>();
      button.onClick.AddListener(GameManager.Instance.ARPosition);
      button.onClick.AddListener(Create3DModel);
  }
  ```
## Capitulo cinco: Posicionar Modelos 3D en Realidad Aumentada

**⬇️⬇️⬇️ Click en la imagen para ver el video 👇👇👇**
<table>
  <tr>
    <td>
      <a href="https://youtu.be/Hjx9o8D1DZg">
        <img src="https://github.com/user-attachments/assets/a042e3df-d5ee-48c4-8996-817afccc28c6" alt="Mira el video en YouTube" width="600"/>
      </a>
    </td>
  </tr>
</table>


## Capitulo seis: Rotar y Seleccionar Modelos 3D en Realidad Aumentada

**⬇️⬇️⬇️ Click en la imagen para ver el video 👇👇👇**
<table>
  <tr>
    <td>
      <a href="https://youtu.be/Wh6vGrPHsJ4">
        <img src="https://github.com/user-attachments/assets/6b7d5d36-6494-437c-a234-fa7b7ebfa7ef" alt="Mira el video en YouTube" width="600"/>
      </a>
    </td>
  </tr>
</table>


## Capitulo siete: Fotos en Realidad Aumentada

**⬇️⬇️⬇️ Click en la imagen para ver el video 👇👇👇**
<table>
  <tr>
    <td>
      <a href="https://youtu.be/3TcZXDNBjk0">
        <img src="https://github.com/user-attachments/assets/3a44c847-1687-44d1-bc7a-e46d66c84980" alt="Mira el video en YouTube" width="600"/>
      </a>
    </td>
  </tr>
</table>


## Capitulo ocho: Actualizar Contenido en Tiempo Real Realidad Aumentada

**⬇️⬇️⬇️ Click en la imagen para ver el video 👇👇👇**
<table>
  <tr>
    <td>
      <a href="https://youtu.be/RkbF85LOSiM">
        <img src="https://github.com/user-attachments/assets/8f624f93-9b78-4284-a189-6a9e8c33a96d" alt="Mira el video en YouTube" width="600"/>
      </a>
    </td>
  </tr>
</table>
