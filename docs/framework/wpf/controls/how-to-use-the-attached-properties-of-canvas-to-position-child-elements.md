---
title: '방법: Canvas의 연결된 속성을 사용하여 자식 요소 배치'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- attached properties [WPF Designer]
- Canvas control [WPF], attached properties
ms.assetid: 48f1d25d-3820-4107-a4cc-d6c1e5664a44
ms.openlocfilehash: a34bac644bd0fa4c15d76d72d0502b311c49d018
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57365336"
---
# <a name="how-to-use-the-attached-properties-of-canvas-to-position-child-elements"></a>방법: Canvas의 연결된 속성을 사용하여 자식 요소 배치
이 예제는 자식 요소들을 위치시키기 위해 <xref:System.Windows.Controls.Canvas>의 연결 속성을 사용하는 법을 알려줍니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 네 <xref:System.Windows.Controls.Button> 부모의 자식 요소로 요소 <xref:System.Windows.Controls.Canvas>합니다. 각 요소가 표시 되는 <xref:System.Windows.Controls.Canvas.Bottom%2A>, <xref:System.Windows.Controls.Canvas.Left%2A>를 <xref:System.Windows.Controls.Canvas.Right%2A>, 및 <xref:System.Windows.Controls.Canvas.Top%2A>합니다.
각 <xref:System.Windows.Controls.Button> 에서 부모에 상대적인 위치가 <xref:System.Windows.Controls.Canvas> 및 할당된 된 속성 값에 따라 합니다.  
  
 [!code-cpp[CanvasAttachedProperties#1](~/samples/snippets/cpp/VS_Snippets_Wpf/CanvasAttachedProperties/CPP/CanvasAttachedProps.cpp#1)]
 [!code-csharp[CanvasAttachedProperties#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CanvasAttachedProperties/CSharp/CanvasAttachedProps.cs#1)]
 [!code-vb[CanvasAttachedProperties#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasAttachedProperties/VisualBasic/CanvasAttachedProps.vb#1)]  
  
## <a name="see-also"></a>참고자료
- <xref:System.Windows.Controls.Canvas>
- <xref:System.Windows.Controls.Canvas.Bottom%2A>
- <xref:System.Windows.Controls.Canvas.Left%2A>
- <xref:System.Windows.Controls.Canvas.Right%2A>
- <xref:System.Windows.Controls.Canvas.Top%2A>
- <xref:System.Windows.Controls.Button>
- [패널 개요](panels-overview.md)
- [방법 항목](canvas-how-to-topics.md)
- [연결된 속성 개요](../advanced/attached-properties-overview.md)
