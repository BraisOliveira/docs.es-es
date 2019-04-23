---
title: ISymUnmanagedReader::ReplaceSymbolStore (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.ReplaceSymbolStore
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::ReplaceSymbolStore
helpviewer_keywords:
- ReplaceSymbolStore method [.NET Framework debugging]
- ISymUnmanagedReader::ReplaceSymbolStore method [.NET Framework debugging]
ms.assetid: 43257761-8cb1-4eaf-8fb5-1f3980cb66cd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 34d93c6956ff391e4d8726d8e45265c96947ad4c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59154770"
---
# <a name="isymunmanagedreaderreplacesymbolstore-method"></a><span data-ttu-id="51bb2-102">ISymUnmanagedReader::ReplaceSymbolStore (Método)</span><span class="sxs-lookup"><span data-stu-id="51bb2-102">ISymUnmanagedReader::ReplaceSymbolStore Method</span></span>
<span data-ttu-id="51bb2-103">Reemplaza el almacén de símbolos existente con un almacén de símbolos delta.</span><span class="sxs-lookup"><span data-stu-id="51bb2-103">Replaces the existing symbol store with a delta symbol store.</span></span> <span data-ttu-id="51bb2-104">Este método es similar a la [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) método, salvo que el delta proporcionado actúa como un reemplazo completo en lugar de una actualización.</span><span class="sxs-lookup"><span data-stu-id="51bb2-104">This method is similar to the [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) method, except that the given delta acts as a complete replacement rather than an update.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="51bb2-105">Es necesario especificar solo uno de los `filename` o `pIStream` parámetros, no ambos.</span><span class="sxs-lookup"><span data-stu-id="51bb2-105">You need specify only one of the `filename` or `pIStream` parameters, not both.</span></span> <span data-ttu-id="51bb2-106">Si `filename` se especifica, el almacén de símbolos se actualizará con los símbolos de ese archivo.</span><span class="sxs-lookup"><span data-stu-id="51bb2-106">If `filename` is specified, the symbol store will be updated with the symbols in that file.</span></span> <span data-ttu-id="51bb2-107">Si `pIStream` se especifica, el almacén se actualizará con los datos de la <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span><span class="sxs-lookup"><span data-stu-id="51bb2-107">If `pIStream` is specified, the store will be updated with the data from the <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51bb2-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="51bb2-108">Syntax</span></span>  
  
```  
HRESULT ReplaceSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
## <a name="parameters"></a><span data-ttu-id="51bb2-109">Parámetros</span><span class="sxs-lookup"><span data-stu-id="51bb2-109">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="51bb2-110">[in] El nombre del archivo que contiene el almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="51bb2-110">[in] The name of the file containing the symbol store.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="51bb2-111">[in] La secuencia de archivos que se utiliza como una alternativa a la `filename` parámetro.</span><span class="sxs-lookup"><span data-stu-id="51bb2-111">[in] The file stream, used as an alternative to the `filename` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="51bb2-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="51bb2-112">Return Value</span></span>  
 <span data-ttu-id="51bb2-113">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="51bb2-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51bb2-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="51bb2-114">Requirements</span></span>  
 <span data-ttu-id="51bb2-115">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="51bb2-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51bb2-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="51bb2-116">See also</span></span>

- [<span data-ttu-id="51bb2-117">ISymUnmanagedReader (interfaz)</span><span class="sxs-lookup"><span data-stu-id="51bb2-117">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
