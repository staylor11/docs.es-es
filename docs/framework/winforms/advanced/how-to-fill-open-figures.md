---
title: Procedimiento Rellenar figuras abiertas
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- open figures [Windows Forms], filling
- figures [Windows Forms], filling
ms.assetid: 5a36b0e4-f1f4-46c0-a85a-22ae98491950
ms.openlocfilehash: b4dd37decd86d625a9cdf8a6b4027dfaec0c0ff1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54730755"
---
# <a name="how-to-fill-open-figures"></a>Procedimiento Rellenar figuras abiertas
Puede rellenar una ruta de acceso pasando un <xref:System.Drawing.Drawing2D.GraphicsPath> de objeto para el <xref:System.Drawing.Graphics.FillPath%2A> método. El <xref:System.Drawing.Graphics.FillPath%2A> método rellena la ruta de acceso según el modo de relleno (alternativo o de espirales) establecido para la ruta de acceso. Si la ruta de acceso tiene figuras abiertas, se rellena la ruta de acceso como si se cerraron esas cifras. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] cierra una figura, dibuje una línea recta desde su punto final para el punto de partida.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente crea una ruta de acceso que tiene una figura abierta (un arco) y una figura cerrada (una elipse). El <xref:System.Drawing.Graphics.FillPath%2A> método rellena la ruta de acceso según el modo de relleno predeterminado, que es <xref:System.Drawing.Drawing2D.FillMode.Alternate>.  
  
 La siguiente ilustración muestra el resultado del código de ejemplo. Tenga en cuenta que se rellena la ruta de acceso (según <xref:System.Drawing.Drawing2D.FillMode.Alternate>) como si se cerraron la figura abierta mediante una línea recta desde su punto final para el punto de partida.  
  
 ![Rellenar trayecto abierto](../../../../docs/framework/winforms/advanced/media/fillopenpath.png "FillOpenPath")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Drawing.Drawing2D.GraphicsPath>
- [Trazados de gráficos en GDI+](../../../../docs/framework/winforms/advanced/graphics-paths-in-gdi.md)
