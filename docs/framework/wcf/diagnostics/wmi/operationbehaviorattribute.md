---
title: OperationBehaviorAttribute
ms.date: 03/30/2017
ms.assetid: 8c9b0755-9e83-411f-bdcb-61a586022797
ms.openlocfilehash: d0bf59e6064748a045f761777a2f8f3e88f1cb5a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54504332"
---
# <a name="operationbehaviorattribute"></a>OperationBehaviorAttribute
OperationBehaviorAttribute  
  
## <a name="syntax"></a>Sintaxis  
  
```csharp
class OperationBehaviorAttribute : Behavior  
{  
  boolean AutoDisposeParameters;  
  string Impersonation;  
  string ReleaseInstanceMode;  
  boolean TransactionAutoComplete;  
  boolean TransactionScopeRequired;  
};  
```  
  
## <a name="methods"></a>Métodos  
 La clase OperationBehaviorAttribute no define ningún método.  
  
## <a name="properties"></a>Propiedades  
 La clase OperationBehaviorAttribute tiene las propiedades siguientes:  
  
### <a name="autodisposeparameters"></a>AutoDisposeParameters  
 Tipo de datos: booleano  
  
 Tipo de acceso: De sólo lectura  
  
 El estado de la característica de eliminación automática para parámetros.  
  
### <a name="impersonation"></a>Suplantación  
 Tipo de datos: cadena  
  
 Tipo de acceso: De sólo lectura  
  
 Indica el nivel de suplantación del llamador que la operación admite.  
  
### <a name="releaseinstancemode"></a>ReleaseInstanceMode  
 Tipo de datos: cadena  
  
 Tipo de acceso: De sólo lectura  
  
 Indica cuándo durante el curso de una invocación de la operación debe reciclarse el objeto.  
  
### <a name="transactionautocomplete"></a>TransactionAutoComplete  
 Tipo de datos: booleano  
  
 Tipo de acceso: De sólo lectura  
  
 Indica si confirmar automáticamente la transacción actual si no se produce ninguna excepción no controlada.  
  
### <a name="transactionscoperequired"></a>TransactionScopeRequired  
 Tipo de datos: booleano  
  
 Tipo de acceso: De sólo lectura  
  
 Indica si la operación requiere una transacción.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|  
  
## <a name="see-also"></a>Vea también
- <xref:System.ServiceModel.OperationBehaviorAttribute>
