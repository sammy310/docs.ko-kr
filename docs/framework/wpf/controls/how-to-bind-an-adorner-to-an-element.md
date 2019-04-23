---
title: '방법: 요소에 표시기(Adorner) 바인딩'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UIElements [WPF], binding adorners to
- adorners [WPF], binding to specified UIElements
ms.assetid: b2101611-a0ee-4137-bdb8-9b3673d2e6b9
ms.openlocfilehash: b6909fec466c2b31a7f4156c43b21a0c724f0217
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59307290"
---
# <a name="how-to-bind-an-adorner-to-an-element"></a>방법: 요소에 표시기(Adorner) 바인딩
지정 된 표시기를 프로그래밍 방식으로 바인딩하는 방법을 보여 주는이 예제 <xref:System.Windows.UIElement>합니다.  
  
## <a name="example"></a>예제  
 특정에 표시기를 바인딩할 <xref:System.Windows.UIElement>, 다음이 단계를 수행 합니다.  
  
1. 호출을 `static` 메서드 <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> 가져오려고는 <xref:System.Windows.Documents.AdornerLayer> 개체에 대 한는 <xref:System.Windows.UIElement> 하 합니다. <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> 지정 된 시작 하 여 시각적 트리를 차례로 **UIElement**를 찾으면 첫 번째 표시기 계층을 반환 합니다. (표시기 계층이 없으면 메서드가 null을 반환합니다.)  
  
2. 호출 된 <xref:System.Windows.Documents.AdornerLayer.Add%2A> 대상에 표시기를 바인딩할 메서드 **UIElement**합니다.  
  
 다음 예제에서는 바인딩합니다 (위)에 <xref:System.Windows.Controls.TextBox> 라는 *myTextBox*합니다.  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]  
  
> [!NOTE]
>  [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]를 사용하여 표시기를 다른 요소에 바인딩하는 것은 현재 지원되지 않습니다.  
  
## <a name="see-also"></a>참고자료

- [표시기 개요](adorners-overview.md)
