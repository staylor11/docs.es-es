---
title: "ICorProfilerCallback::ExceptionSearchFunctionEnter (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ExceptionSearchFunctionEnter
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ExceptionSearchFunctionEnter
helpviewer_keywords:
- ExceptionSearchFunctionEnter method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionSearchFunctionEnter method [.NET Framework profiling]
ms.assetid: bfd54573-b7e6-4bd1-a184-7f08a8b39fae
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3fc6d1708a6a2daea0d0a9dc815bc07736644b49
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackexceptionsearchfunctionenter-method"></a><span data-ttu-id="3549d-102">ICorProfilerCallback::ExceptionSearchFunctionEnter (Método)</span><span class="sxs-lookup"><span data-stu-id="3549d-102">ICorProfilerCallback::ExceptionSearchFunctionEnter Method</span></span>
<span data-ttu-id="3549d-103">Notifica al generador de perfiles que la fase de búsqueda del control de excepciones ha empezado a buscar una función para buscar un controlador para la excepción actual.</span><span class="sxs-lookup"><span data-stu-id="3549d-103">Notifies the profiler that the search phase of exception handling has begun searching a function to find a handler for the current exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3549d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3549d-104">Syntax</span></span>  
  
```  
HRESULT ExceptionSearchFunctionEnter(  
    [in] FunctionID functionId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3549d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3549d-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="3549d-106">[in] El identificador de la función que se ha especificado.</span><span class="sxs-lookup"><span data-stu-id="3549d-106">[in] The ID of the function that has been entered.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3549d-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3549d-107">Requirements</span></span>  
 <span data-ttu-id="3549d-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3549d-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3549d-109">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3549d-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3549d-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3549d-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3549d-111">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3549d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3549d-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="3549d-112">See Also</span></span>  
 [<span data-ttu-id="3549d-113">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3549d-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="3549d-114">ExceptionSearchFunctionLeave (método)</span><span class="sxs-lookup"><span data-stu-id="3549d-114">ExceptionSearchFunctionLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionleave-method.md)