---
title: "ISymUnmanagedWriter::DefineGlobalVariable (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.DefineGlobalVariable
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::DefineGlobalVariable
helpviewer_keywords:
- ISymUnmanagedWriter::DefineGlobalVariable method [.NET Framework debugging]
- DefineGlobalVariable method [.NET Framework debugging]
ms.assetid: 843c904a-8176-4d8f-bd47-b4d4c29f4c5c
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 7540dfcefbe7a331a26220a07b2e206c1302ddc8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedwriterdefineglobalvariable-method"></a><span data-ttu-id="9c6f4-102">ISymUnmanagedWriter::DefineGlobalVariable (Método)</span><span class="sxs-lookup"><span data-stu-id="9c6f4-102">ISymUnmanagedWriter::DefineGlobalVariable Method</span></span>
<span data-ttu-id="9c6f4-103">Define una única variable global.</span><span class="sxs-lookup"><span data-stu-id="9c6f4-103">Defines a single global variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c6f4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9c6f4-104">Syntax</span></span>  
  
```  
HRESULT DefineGlobalVariable(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      cSig,  
    [in, size_is(cSig)] unsigned char signature[],  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9c6f4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9c6f4-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="9c6f4-106">[in] Un puntero a un `WCHAR` que define el nombre de variable global.</span><span class="sxs-lookup"><span data-stu-id="9c6f4-106">[in] A pointer to a `WCHAR` that defines the global variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="9c6f4-107">[in] Atributos de la variable globales.</span><span class="sxs-lookup"><span data-stu-id="9c6f4-107">[in] The global variable attributes.</span></span>  
  
 `cSig`  
 <span data-ttu-id="9c6f4-108">[in] A `ULONG32` que indica el tamaño, en caracteres, de la `signature` búfer.</span><span class="sxs-lookup"><span data-stu-id="9c6f4-108">[in] A `ULONG32` that indicates the size, in characters, of the `signature` buffer.</span></span>  
  
 `signature`  
 <span data-ttu-id="9c6f4-109">[in] La firma de variable global.</span><span class="sxs-lookup"><span data-stu-id="9c6f4-109">[in] The global variable signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="9c6f4-110">[in] El tipo de dirección.</span><span class="sxs-lookup"><span data-stu-id="9c6f4-110">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="9c6f4-111">[in] La primera dirección para la especificación de parámetros.</span><span class="sxs-lookup"><span data-stu-id="9c6f4-111">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="9c6f4-112">[in] La segunda dirección para la especificación de parámetros.</span><span class="sxs-lookup"><span data-stu-id="9c6f4-112">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="9c6f4-113">[in] La tercera dirección de la especificación de parámetros.</span><span class="sxs-lookup"><span data-stu-id="9c6f4-113">[in] The third address for the parameter specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9c6f4-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9c6f4-114">Return Value</span></span>  
 <span data-ttu-id="9c6f4-115">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="9c6f4-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c6f4-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9c6f4-116">Requirements</span></span>  
 <span data-ttu-id="9c6f4-117">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="9c6f4-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c6f4-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="9c6f4-118">See Also</span></span>  
 [<span data-ttu-id="9c6f4-119">ISymUnmanagedWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9c6f4-119">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="9c6f4-120">DefineLocalVariable (método)</span><span class="sxs-lookup"><span data-stu-id="9c6f4-120">DefineLocalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definelocalvariable-method.md)  
 [<span data-ttu-id="9c6f4-121">DefineGlobalVariable2 (método)</span><span class="sxs-lookup"><span data-stu-id="9c6f4-121">DefineGlobalVariable2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineglobalvariable2-method.md)