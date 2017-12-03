---
title: "_EFN_GetManagedExcepStack (Función)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: _EFN_GetManagedExcepStack
api_location: mscordbi.dll
api_type: COM
f1_keywords: _EFN_GetManagedExcepStack
helpviewer_keywords: _EFN_GetManagedExcepStack function [.NET Framework debugging]
ms.assetid: 21ceed9e-62b2-4024-b027-6d095109955a
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9dabcf1d39bea44a3bd90824082a082ae9650b54
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="efngetmanagedexcepstack-function"></a><span data-ttu-id="b77a9-102">_EFN_GetManagedExcepStack (Función)</span><span class="sxs-lookup"><span data-stu-id="b77a9-102">_EFN_GetManagedExcepStack Function</span></span>
<span data-ttu-id="b77a9-103">Dada una dirección de objeto de excepción administrado, devuelve una versión de cadena del seguimiento de pila que contiene.</span><span class="sxs-lookup"><span data-stu-id="b77a9-103">Given a managed exception object address, returns a string version of the stack trace contained inside.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b77a9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b77a9-104">Syntax</span></span>  
  
```  
HRESULT _EFN_GetManagedExcepStack(  
    [in]  PDEBUG_CLIENT Client,  
    [in]  ULONG64       StackObjAddr,  
    [out] __out_ecount(cbString) PSTR szStackString,  
    [out] ULONG         cbString  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b77a9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b77a9-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="b77a9-106">[in] El cliente que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="b77a9-106">[in] The client being debugged.</span></span>  
  
 `StackObjAddr`  
 <span data-ttu-id="b77a9-107">[in] Un puntero de objeto administrado, derivado de <xref:System.Exception>.</span><span class="sxs-lookup"><span data-stu-id="b77a9-107">[in] A managed object pointer, derived from <xref:System.Exception>.</span></span>  
  
 <span data-ttu-id="b77a9-108">szStackString</span><span class="sxs-lookup"><span data-stu-id="b77a9-108">szStackString</span></span>  
 <span data-ttu-id="b77a9-109">[out] La cadena devuelta.</span><span class="sxs-lookup"><span data-stu-id="b77a9-109">[out] The returned string.</span></span>  
  
 `cbString`  
 <span data-ttu-id="b77a9-110">[out] El número de caracteres disponibles en el búfer de cadena.</span><span class="sxs-lookup"><span data-stu-id="b77a9-110">[out] The number of characters available in the string buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b77a9-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b77a9-111">Remarks</span></span>  
 <span data-ttu-id="b77a9-112">Si no hay código administrado en el subproceso actualmente en contexto, la función devuelve HRESULT SOS_E_NOMANAGEDCODE con un valor 0xa0 y el código de error de 0 x 1000.</span><span class="sxs-lookup"><span data-stu-id="b77a9-112">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b77a9-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b77a9-113">Requirements</span></span>  
 <span data-ttu-id="b77a9-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b77a9-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b77a9-115">**Encabezado:** SOS_Stacktrace.h</span><span class="sxs-lookup"><span data-stu-id="b77a9-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="b77a9-116">**Versión de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b77a9-116">**.NET Framework Version:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b77a9-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="b77a9-117">See Also</span></span>  
 [<span data-ttu-id="b77a9-118">Funciones estáticas globales para la depuración</span><span class="sxs-lookup"><span data-stu-id="b77a9-118">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)