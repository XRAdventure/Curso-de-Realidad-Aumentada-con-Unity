# Curso de Realidad Aumentada con Unity 📱

Durante este curso, crearás una aplicación profesional de Realidad Aumentada llamada **AR Furniture**. Esta aplicación permite al usuario posicionar objetos en su entorno seleccionándolos desde un inventario. Una vez colocados, los objetos pueden ser seleccionados, movidos y rotados. Además, es posible tomar una foto del entorno con los objetos en AR y compartirla en redes sociales.

### Requerimientos

#### Unity

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

#### Visual Studio



## Capitulo uno: ¿Cómo crear una aplicación de Realidad Aumentada?

[![Mira el video en YouTube](https://i9.ytimg.com/vi_webp/TI599JorZ5M/maxresdefault.webp?v=620b6a77&sqp=CND87bUG&rs=AOn4CLB1pWwcgGl9uVFE5opKXLqMapG0UQ)](https://youtu.be/TI599JorZ5M)

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

Para las versiones reciente, este video emplea los elementos Legacy, se pueden usar ambos tipos, pero si se usa TextMeshPro se debe hacer un pequeno cambio mas adelante en el codigo. 

![image](https://github.com/user-attachments/assets/6d299d1a-ad54-4206-96ba-7b7a99ed4660)

*Nota: si usan la misma version del video selecionen la misma tal cual*

Para mejorar el Scroll selecionar Scroll View → En Scroll Rect → Desactivar Veritcal

![image](https://github.com/user-attachments/assets/84f3066c-830b-4a56-87e5-38de5f4691ab)

### DOTween

[Link DOTween (HOTween v2) en Unity Asset Store](https://assetstore.unity.com/packages/tools/animation/dotween-hotween-v2-27676)  

## Capitulo tres: Detección de planos y nube de puntos en Realidad Aumentada

[![Mira el video en YouTube](https://i9.ytimg.com/vi_webp/6bRkKZ9Onk4/maxresdefault.webp?v=61a35fce&sqp=CLid7rUG&rs=AOn4CLAlhsNIZrEDbYcJSKai8VU9JNTOwg)](https://youtu.be/6bRkKZ9Onk4)

En las versiones recientes de ARFoundation se han cambiado algunos nombres: 

- AR Session Origin → XR Origin
El video usa AR Session Origin, si no esta se debe usar XR Origin en su lugar, verificar que este GameObject se encuentre en la posicion (0,0,0)

## Capitulo cuatro: ¿Cómo integrar Modelos 3D en Realidad Aumentada?

[![Mira el video en YouTube](https://i9.ytimg.com/vi/Hjx9o8D1DZg/maxresdefault.jpg?v=61abce96&sqp=CNDH7rUG&rs=AOn4CLChZ7mJTbBelwu8iZqUeTLEHIEiqA)]([https://youtu.be/6bRkKZ9Onk4](https://youtu.be/Hjx9o8D1DZg))

### Que hago si mi modelo 3D no aparece en AR?

1. Verificar la escala del modelo, puede que tu modelo este muy grande o muy pequeno, para ello usar el cubo de Unity como referencia ese cubo tiene 1x1x1 metro
2. Asegurarse que el modelo esta en la posicon (0, 0, 0)
3. Posicionar el pivote en el centro del modelo 3D

- Pivote
   - Modelo 3D

Respetar esta herarquia; crea un empty object (pivote) y has el modelo 3D hijo de es GameObject, luego, recuerda que es el modelo 3D que debes mover para que quede posicionado corectamente respecto al pivote

![image](https://github.com/user-attachments/assets/3b4089f8-8d09-451f-988c-70b402edf402)

### Button Item Prefab

Al definir el prefab del boton es obligatorio seguir este orden de herarquia:

- ButtonItemPrefab
  - ItemName
  - ItemImage
  - ItemDescription

![image](https://github.com/user-attachments/assets/e7d4a52e-f122-49c8-a4e8-d5d8bcb1d771)

### Script ItemButtonManager

Importante! En el capitulos 2 en la UI, les dije que existen dos tipos de UI, TextMeshPro, Legacy, dependiendo de cual hayan elegido, el codigo cambiara. 

- Legacy o la misma del video

El codigo funciona tal cual no necesita cambios

- TextMeshPro

Andir el namespace:

```csharp
using TMPro;
```

Cambiar esta parte de la funcion start queda asi:

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
## Capitulo cinco: ¿Cómo integrar Modelos 3D en Realidad Aumentada?
## Capitulo seis: Rotar y Seleccionar Modelos 3D en Realidad Aumentada
## Capitulo siete: Fotos en Realidad Aumentada
## Capitulo ocho: Actualizar Contenido en Tiempo Real Realidad Aumentada
