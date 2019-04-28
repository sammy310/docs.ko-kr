---
title: '방법: Panel의 OnRender 메서드 재정의'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- overriding OnRender method
- Panel control, overriding OnRender method
- OnRender method
- controls, Panel, overriding OnRender method
helpviewer_keywords:
- overriding OnRender method of Panel control [WPF]
- OnRender method [WPF], overriding
- Panel control [WPF], overriding OnRender method
ms.assetid: 57397834-a085-4e36-90ab-416fad98f341
ms.openlocfilehash: c4539847368c1a5789e99ec92106d17077ed5943
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61770840"
---
# <a name="how-to-override-the-panel-onrender-method"></a>방법: Panel의 OnRender 메서드 재정의
재정의 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.Panel.OnRender%2A> 메서드의 <xref:System.Windows.Controls.Panel> 레이아웃 요소를 사용자 지정 그래픽 효과 추가 하려면.  
  
## <a name="example"></a>예제  
 사용 된 <xref:System.Windows.Controls.Panel.OnRender%2A> 그래픽 효과 렌더링된 panel 요소를 추가 하기 위해 메서드. 예를 들어, 사용자 지정 테두리 또는 배경 효과 추가 하려면이 메서드를 사용할 수 있습니다. <xref:System.Windows.Media.DrawingContext> 개체는 도형, 텍스트, 이미지 또는 비디오를 그리기 위한 메서드를 제공 하는 인수로 전달 됩니다. 결과적으로,이 메서드는 패널 개체의 사용자 지정에 유용 합니다.  
  
 [!code-csharp[LightWeightCustomPanel#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LightWeightCustomPanel/CSharp/OffsetPanel.cs#1)]
 [!code-vb[LightWeightCustomPanel#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/LightWeightCustomPanel/visualbasic/offsetpanel.vb#1)]  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Controls.Panel>
- [패널 개요](panels-overview.md)
- [사용자 지정 방사형 패널 샘플](https://go.microsoft.com/fwlink/?LinkID=159982)
- [방법 항목](panel-how-to-topics.md)
