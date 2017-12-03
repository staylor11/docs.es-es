---
title: "IHostTaskManager::ReverseEnterRuntime (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager.ReverseEnterRuntime
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager::ReverseEnterRuntime
helpviewer_keywords:
- IHostTaskManager::ReverseEnterRuntime method [.NET Framework hosting]
- ReverseEnterRuntime method [.NET Framework hosting]
ms.assetid: b1e26bff-d3ea-436e-9867-29720df999f4
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1c8d84cbd02527a026206d6fa172a9d3f40683fb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ihosttaskmanagerreverseenterruntime-method"></a><span data-ttu-id="6a41e-102">IHostTaskManager::ReverseEnterRuntime (Método)</span><span class="sxs-lookup"><span data-stu-id="6a41e-102">IHostTaskManager::ReverseEnterRuntime Method</span></span>
<span data-ttu-id="6a41e-103">Notifica al host que se está realizando una llamada en common language runtime (CLR) de código no administrado.</span><span class="sxs-lookup"><span data-stu-id="6a41e-103">Notifies the host that a call is being made into the common language runtime (CLR) from unmanaged code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a41e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6a41e-104">Syntax</span></span>  
  
```  
HRESULT ReverseEnterRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="6a41e-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="6a41e-105">Return Value</span></span>  
  
|<span data-ttu-id="6a41e-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6a41e-106">HRESULT</span></span>|<span data-ttu-id="6a41e-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="6a41e-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6a41e-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="6a41e-108">S_OK</span></span>|<span data-ttu-id="6a41e-109">`ReverseEnterRuntime`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="6a41e-109">`ReverseEnterRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="6a41e-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6a41e-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6a41e-111">El CLR no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="6a41e-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6a41e-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6a41e-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6a41e-113">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="6a41e-113">The call timed out.</span></span>|  
|<span data-ttu-id="6a41e-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6a41e-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6a41e-115">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="6a41e-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6a41e-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6a41e-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6a41e-117">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="6a41e-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6a41e-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6a41e-118">E_FAIL</span></span>|<span data-ttu-id="6a41e-119">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="6a41e-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6a41e-120">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="6a41e-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6a41e-121">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="6a41e-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="6a41e-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="6a41e-122">E_OUTOFMEMORY</span></span>|<span data-ttu-id="6a41e-123">No hay suficiente memoria disponible para completar la asignación de recurso solicitado.</span><span class="sxs-lookup"><span data-stu-id="6a41e-123">Not enough memory is available to complete the requested resource allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6a41e-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6a41e-124">Remarks</span></span>  
 <span data-ttu-id="6a41e-125">Si se realiza la llamada a CLR de una secuencia que se ha originado en código administrado, cada llamada a `ReverseEnterRuntime` corresponde a una llamada a [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md).</span><span class="sxs-lookup"><span data-stu-id="6a41e-125">If the call into the CLR is made from a sequence that originated in managed code, each call to `ReverseEnterRuntime` corresponds to a call to [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6a41e-126">Llamadas pueden originarse en código no administrado sin estar anidadas.</span><span class="sxs-lookup"><span data-stu-id="6a41e-126">Calls can originate from unmanaged code without being nested.</span></span> <span data-ttu-id="6a41e-127">En este caso, no hay ninguna llamada a [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), o `ReverseLeaveRuntime`y el número de llamadas a `ReverseEnterRuntime` no es igual al número de llamadas a `ReverseLeaveRuntime`.</span><span class="sxs-lookup"><span data-stu-id="6a41e-127">In this case, there is no call to [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), or `ReverseLeaveRuntime`, and the number of calls to `ReverseEnterRuntime` does not equal the number of calls to `ReverseLeaveRuntime`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a41e-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6a41e-128">Requirements</span></span>  
 <span data-ttu-id="6a41e-129">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6a41e-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a41e-130">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6a41e-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6a41e-131">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6a41e-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6a41e-132">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a41e-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a41e-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="6a41e-133">See Also</span></span>  
 [<span data-ttu-id="6a41e-134">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6a41e-134">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="6a41e-135">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6a41e-135">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="6a41e-136">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6a41e-136">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="6a41e-137">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6a41e-137">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)