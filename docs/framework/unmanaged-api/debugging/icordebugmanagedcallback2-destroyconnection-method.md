---
title: "ICorDebugManagedCallback2::DestroyConnection (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback2.DestroyConnection
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback2::DestroyConnection
helpviewer_keywords:
- DestroyConnection method [.NET Framework debugging]
- ICorDebugManagedCallback2::DestroyConnection method [.NET Framework debugging]
ms.assetid: cf7940e9-4558-4319-925c-09f6c98c8fcd
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c35c39e5ce2b6478d6945d765403c6e4b63eef89
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmanagedcallback2destroyconnection-method"></a><span data-ttu-id="82667-102">ICorDebugManagedCallback2::DestroyConnection (Método)</span><span class="sxs-lookup"><span data-stu-id="82667-102">ICorDebugManagedCallback2::DestroyConnection Method</span></span>
<span data-ttu-id="82667-103">Notifica al depurador que ha finalizado la conexión especificada.</span><span class="sxs-lookup"><span data-stu-id="82667-103">Notifies the debugger that the specified connection has been terminated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82667-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="82667-104">Syntax</span></span>  
  
```  
HRESULT DestroyConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="82667-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="82667-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="82667-106">[in] Un puntero a un objeto ICorDebugProcess que representa el proceso que contiene la conexión que se ha destruido.</span><span class="sxs-lookup"><span data-stu-id="82667-106">[in] A pointer to an ICorDebugProcess object that represents the process containing the connection that was destroyed.</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="82667-107">[in] El identificador de la conexión que se ha destruido.</span><span class="sxs-lookup"><span data-stu-id="82667-107">[in] The ID of the connection that was destroyed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="82667-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="82667-108">Remarks</span></span>  
 <span data-ttu-id="82667-109">A `DestroyConnection` devolución de llamada se desencadenará cuando un host llama al método [ICLRDebugManager:: EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md) en el [API de hospedaje](../../../../docs/framework/unmanaged-api/hosting/index.md).</span><span class="sxs-lookup"><span data-stu-id="82667-109">A `DestroyConnection` callback will be fired when a host calls [ICLRDebugManager::EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md) in the [Hosting API](../../../../docs/framework/unmanaged-api/hosting/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82667-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="82667-110">Requirements</span></span>  
 <span data-ttu-id="82667-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82667-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82667-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="82667-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="82667-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="82667-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="82667-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82667-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82667-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="82667-115">See Also</span></span>  
 [<span data-ttu-id="82667-116">ICorDebugManagedCallback2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="82667-116">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [<span data-ttu-id="82667-117">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="82667-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)