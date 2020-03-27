---
title: '방법: 사용자 지정 팝업 위치 지정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Popup control [WPF], specifying custom position
ms.assetid: 28c24f39-d3aa-4ee2-b950-384b4a5dab92
ms.openlocfilehash: ea8d73c51dd018608b95104f00bf341ff434225c
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344958"
---
# <a name="how-to-specify-a-custom-popup-position"></a>방법: 사용자 지정 팝업 위치 지정
이 예제에서는 <xref:System.Windows.Controls.Primitives.Popup> <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 속성이 로 설정될 때 컨트롤에 <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>대한 사용자 지정 위치를 지정하는 방법을 보여 주며 있습니다.  
  
## <a name="example"></a>예제  
 속성이 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 설정되면 <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>대리자의 <xref:System.Windows.Controls.Primitives.Popup> 정의된 인스턴스를 <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> 호출합니다. 이 대리자는 대상 영역의 왼쪽 상단 모서리와 의 왼쪽 상단 모서리를 기준으로 <xref:System.Windows.Controls.Primitives.Popup>가능한 점 집합을 반환합니다. 배치는 <xref:System.Windows.Controls.Primitives.Popup> 최상의 가시성을 제공하는 지점에서 발생합니다.  
  
 다음 예제에서는 속성을 로 설정하여 <xref:System.Windows.Controls.Primitives.Popup> a의 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 위치를 <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>정의하는 방법을 보여 주며 있습니다. 또한 를 배치하기 위해 <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> 대리자를 만들고 할당하는 <xref:System.Windows.Controls.Primitives.Popup>방법도 보여 주며.  콜백 대리자는 <xref:System.Windows.Controls.Primitives.CustomPopupPlacement> 두 개의 개체를 반환합니다.  <xref:System.Windows.Controls.Primitives.Popup> 첫 번째 위치에서 화면 가장자리에 의해 숨김이 있으면 두 번째 위치에 <xref:System.Windows.Controls.Primitives.Popup> 배치됩니다.  
  
 [!code-xaml[PopupCustomPlacement#CustomPlacement](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml#customplacement)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateInstance](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegateinstance)]
 [!code-vb[PopupCustomPlacement#DelegateInstance](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegateinstance)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegatedefinition)]
 [!code-vb[PopupCustomPlacement#DelegateDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegatedefinition)]  
  
 전체 샘플은 [팝업 배치 샘플을](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS)참조하십시오.  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Controls.Primitives.Popup>
- [Popup 개요](popup-overview.md)
- [방법 항목](popup-how-to-topics.md)
