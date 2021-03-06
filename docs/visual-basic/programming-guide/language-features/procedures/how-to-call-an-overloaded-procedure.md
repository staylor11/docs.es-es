---
title: Filtrar Llamar a un procedimiento sobrecargado (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], overloading
- procedures [Visual Basic], calling
- procedures [Visual Basic], multiple versions
- procedure calls [Visual Basic], overloaded
ms.assetid: 3bb331fb-f6bc-406f-9ca0-9609b497014c
ms.openlocfilehash: f13fdae9617fa2af21978979cad6f90a15140a4a
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56970004"
---
# <a name="how-to-call-an-overloaded-procedure-visual-basic"></a>Procedimiento Llamar a un procedimiento sobrecargado (Visual Basic)
La ventaja de sobrecargar un procedimiento es en la flexibilidad de la llamada. El código de llamada puede obtener la información que necesita para pasar al procedimiento y, a continuación, llamar a un único nombre de procedimiento, independientemente de los argumentos está pasando.  
  
### <a name="to-call-a-procedure-that-has-more-than-one-version-defined"></a>Llamar a un procedimiento que tiene más de una versión definida  
  
1.  En el código que realiza la llamada, determine qué datos se deben pasar al procedimiento.  
  
2.  Escribir la llamada al procedimiento de la manera normal, presentación de datos en la lista de argumentos. Asegúrese de que los argumentos coinciden con la lista de parámetros en una de las versiones definidas para el procedimiento.  
  
3.  No es necesario que determinar qué versión del procedimiento para llamar a. Visual Basic pasa el control a la versión que coincida con la lista de argumentos.  
  
     El ejemplo siguiente se llama el `post` procedimiento declarado en [Cómo: Definir varias versiones de un procedimiento](./how-to-define-multiple-versions-of-a-procedure.md). Obtiene la identificación del cliente, se determina si es un `String` o `Integer`y, a continuación, en cualquier caso, llama el mismo procedimiento.  
  
     [!code-vb[VbVbcnProcedures#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#56)]  
  
     [!code-vb[VbVbcnProcedures#57](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#57)]  
  
## <a name="see-also"></a>Vea también
- [Procedimientos](./index.md)
- [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)
- [Sobrecarga de procedimientos](./procedure-overloading.md)
- [Solución de problemas de procedimientos](./troubleshooting-procedures.md)
- [Cómo: Definir varias versiones de un procedimiento](./how-to-define-multiple-versions-of-a-procedure.md)
- [Cómo: Sobrecargar un procedimiento que toma parámetros opcionales](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [Cómo: Sobrecargar un procedimiento que toma un número indefinido de parámetros](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [Consideraciones sobre la sobrecarga de procedimientos](./considerations-in-overloading-procedures.md)
- [Resolución de sobrecargas](./overload-resolution.md)
- [Sobrecargas](../../../../visual-basic/language-reference/modifiers/overloads.md)
