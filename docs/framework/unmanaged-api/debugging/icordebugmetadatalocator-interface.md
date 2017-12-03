---
title: ICorDebugMetaDataLocator (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugMetaDataLocator
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugMetaDataLocator
helpviewer_keywords: ICorDebugMetaDataLocator interface [.NET Framework debugging]
ms.assetid: 287f5ecd-863f-4090-a615-077859f0257b
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4611581bd2692d7c2be48adad1db3c495080e776
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmetadatalocator-interface"></a><span data-ttu-id="4386c-102">ICorDebugMetaDataLocator (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4386c-102">ICorDebugMetaDataLocator Interface</span></span>
<span data-ttu-id="4386c-103">Proporciona información de metadatos al depurador.</span><span class="sxs-lookup"><span data-stu-id="4386c-103">Provides metadata information to the debugger.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4386c-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="4386c-104">Methods</span></span>  
  
|<span data-ttu-id="4386c-105">Método</span><span class="sxs-lookup"><span data-stu-id="4386c-105">Method</span></span>|<span data-ttu-id="4386c-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="4386c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4386c-107">GetMetaData (método)</span><span class="sxs-lookup"><span data-stu-id="4386c-107">GetMetaData Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmetadatalocator-getmetadata-method.md)|<span data-ttu-id="4386c-108">Pide al depurador que devuelva la ruta de acceso completa a un módulo cuyos metadatos se necesitan para completar una operación solicitada por el depurador.</span><span class="sxs-lookup"><span data-stu-id="4386c-108">Asks the debugger to return the full path to a module whose metadata is needed to complete an operation the debugger requested.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4386c-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4386c-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4386c-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="4386c-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4386c-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4386c-111">Requirements</span></span>  
 <span data-ttu-id="4386c-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4386c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4386c-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4386c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4386c-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4386c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4386c-115">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4386c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4386c-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="4386c-116">See Also</span></span>  
 [<span data-ttu-id="4386c-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="4386c-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="4386c-118">Depuración</span><span class="sxs-lookup"><span data-stu-id="4386c-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)