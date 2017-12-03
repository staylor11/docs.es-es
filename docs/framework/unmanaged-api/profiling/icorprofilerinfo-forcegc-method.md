---
title: "ICorProfilerInfo::ForceGC (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.ForceGC
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::ForceGC
helpviewer_keywords:
- ICorProfilerInfo::ForceGC method [.NET Framework profiling]
- ForceGC method [.NET Framework profiling]
ms.assetid: 0da1ef80-d242-4636-87d0-43e0470b342a
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3a3389c6675e992c362e3e0a77dfbc97e142ef8a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfoforcegc-method"></a><span data-ttu-id="015e2-102">ICorProfilerInfo::ForceGC (Método)</span><span class="sxs-lookup"><span data-stu-id="015e2-102">ICorProfilerInfo::ForceGC Method</span></span>
<span data-ttu-id="015e2-103">Fuerza a la recolección se producen dentro de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="015e2-103">Forces garbage collection to occur within the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="015e2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="015e2-104">Syntax</span></span>  
  
```  
HRESULT ForceGC();  
```  
  
## <a name="remarks"></a><span data-ttu-id="015e2-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="015e2-105">Remarks</span></span>  
 <span data-ttu-id="015e2-106">El `ForceGC` método debe llamarse sólo desde un subproceso que nunca se ha ejecutado el código administrado y no tiene las devoluciones de llamada del generador de perfiles en la pila.</span><span class="sxs-lookup"><span data-stu-id="015e2-106">The `ForceGC` method must be called only from a thread that has never run managed code and does not have any profiler callbacks on its stack.</span></span> <span data-ttu-id="015e2-107">La implementación más conveniente consiste en crear un subproceso independiente en el generador de perfiles llama `ForceGC` cuando se señala.</span><span class="sxs-lookup"><span data-stu-id="015e2-107">The most convenient implementation is to create a separate thread within the profiler that calls `ForceGC` when signaled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="015e2-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="015e2-108">Requirements</span></span>  
 <span data-ttu-id="015e2-109">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="015e2-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="015e2-110">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="015e2-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="015e2-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="015e2-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="015e2-112">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="015e2-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="015e2-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="015e2-113">See Also</span></span>  
 [<span data-ttu-id="015e2-114">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="015e2-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)