---
title: <list> - Guía de programación de C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- list
- <list>
helpviewer_keywords:
- list C# XML tag
- listheader C# XML tag
- <listheader> C# XML tag
- item C# XML tag
- <item> C# XML tag
- <list> C# XML tag
ms.assetid: c9620b1b-c2e6-43f1-ab88-8ab47308ffec
ms.openlocfilehash: 0df6653171aa0366f555c39e4644f13b2b7384f9
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "72523428"
---
# <a name="list-c-programming-guide"></a>\<list> (Guía de programación de C#)
## <a name="syntax"></a>Sintaxis  
  
```xml  
<list type="bullet" | "number" | "table">  
    <listheader>  
        <term>term</term>  
        <description>description</description>  
    </listheader>  
    <item>  
        <term>term</term>  
        <description>description</description>  
    </item>  
</list>  
```  
  
## <a name="parameters"></a>Parámetros  
 `term`  
 Término que se define en `description`.  
  
 `description`  
 Elemento de una lista numerada o con viñetas, o definición de un `term`.  
  
## <a name="remarks"></a>Comentarios  
 El bloque \<listheader> se usa para definir la fila de encabezado de una tabla o de una lista de definiciones. Cuando se define una tabla, solo es necesario suministrar una entrada para un término en el encabezado.  
  
 Cada elemento de la lista se especifica con un bloque \<item>. Cuando se crea una lista de definiciones, se deberán especificar tanto `term` como `description`. En cambio, para una tabla, lista con viñetas o lista numerada, solo es necesario suministrar una entrada para `description`.  
  
 Una lista o una tabla pueden tener tantos bloques \<item> como sean necesarios.  
  
 Compile con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación de un archivo.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csProgGuideDocComments#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#6)]  
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Etiquetas recomendadas para los comentarios de documentación](./recommended-tags-for-documentation-comments.md)
