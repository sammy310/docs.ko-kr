---
title: '방법: PriorityBinding 구현'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], PriorityBinding class
ms.assetid: d63b65ab-b3e9-4322-9aa8-1450f8d89532
ms.openlocfilehash: aaf2caff1e2684e08c7eb65125536f1070203d70
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59207567"
---
# <a name="how-to-implement-prioritybinding"></a>방법: PriorityBinding 구현
<xref:System.Windows.Data.PriorityBinding> [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 바인딩 목록을 지정 하 여 작동 합니다. 바인딩 목록은 가장 낮은 우선 순위를 높은 우선 순위에서 정렬 되어 있습니다. 가장 높은 우선 순위 바인딩 값을 반환 하는 경우 성공적으로 처리 될 때 다음 있습니다 되지 목록에 다른 바인딩을 처리 해야 합니다. 우선 순위가 높은 바인딩이 평가할 오래 걸리는 경우 수, 더 높은 우선 순위의 바인딩 값을 성공적으로 반환 될 때까지 다음 우선 순위가 가장 높은 값을 성공적으로 반환 하는 사용 됩니다.  
  
## <a name="example"></a>예제  
 보여 주기 위해 어떻게 <xref:System.Windows.Data.PriorityBinding> 작동 합니다 `AsyncDataSource` 다음 세 가지 속성을 사용 하 여 개체가 생성 되었음을: `FastDP`를 `SlowerDP`, 및 `SlowestDP`합니다.  
  
 get 접근자 `FastDP` 의 값을 반환 합니다 `_fastDP` 데이터 멤버입니다.  
  
 get 접근자 `SlowerDP` 의 값을 반환 하기 전에 3 초간 대기 합니다 `_slowerDP` 데이터 멤버입니다.  
  
 get 접근자 `SlowestDP` 의 값을 반환 하기 전에 5 초간 대기 합니다 `_slowestDP` 데이터 멤버입니다.  
  
> [!NOTE]
>  이 예제는 데모용으로만 제공됩니다. [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] 크기가 커져 느린 필드 집합 보다 속성을 정의 하는 것에 대 한 지침을 권장 합니다. 자세한 내용은 [메서드와 속성 간의 선택](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms229054(v=vs.100))합니다.  
  
 [!code-csharp[PriorityBinding#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml.cs#1)]
 [!code-vb[PriorityBinding#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PriorityBinding/VisualBasic/AsyncDataSource.vb#1)]  
  
 합니다 <xref:System.Windows.Controls.TextBlock.Text%2A> 위의 속성이 바인딩된 `AsyncDS` 사용 하 여 <xref:System.Windows.Data.PriorityBinding>:  
  
 [!code-xaml[PriorityBinding#2](~/samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml#2)]  
  
 바인딩 엔진에서 처리 하는 경우는 <xref:System.Windows.Data.Binding> 개체를 첫 번째를 사용 하 여 시작 <xref:System.Windows.Data.Binding>에 바인딩된는 `SlowestDP` 속성입니다. 때이 <xref:System.Windows.Data.Binding> 는 처리를 반환 하지 않습니다을 성공적으로 대기 하기 5 초간 하므로 다음 때문에 <xref:System.Windows.Data.Binding> 요소가 처리 됩니다. 다음 <xref:System.Windows.Data.Binding> 값 반환 하지는 성공적으로 3 초 동안 대기 하기 때문입니다. 바인딩 엔진은 다음으로 이동 <xref:System.Windows.Data.Binding> 요소에 바인딩되는 `FastDP` 속성입니다. 이 <xref:System.Windows.Data.Binding> 값 "빠른"를 반환 합니다. <xref:System.Windows.Controls.TextBlock> 이제 값 "빠른"를 표시 합니다.  
  
 3 초 경과 후는 `SlowerDP` 속성 "느립니다 Value" 값을 반환 합니다. <xref:System.Windows.Controls.TextBlock> 다음 "느립니다 Value" 값을 표시 합니다.  
  
 5 초 경과 후는 `SlowestDP` 속성 "가장 느린 값" 값을 반환 합니다. 해당 바인딩을 먼저 나열 되므로 가장 높은 우선 순위를 갖습니다. <xref:System.Windows.Controls.TextBlock> 이제 "가장 느린 값" 값을 표시 합니다.  
  
 참조 <xref:System.Windows.Data.PriorityBinding> 바인딩에서 성공적인 반환 값 간주 되는 항목에 대 한 정보에 대 한 합니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Data.Binding.IsAsync%2A?displayProperty=nameWithType>
- [데이터 바인딩 개요](data-binding-overview.md)
- [방법 항목](data-binding-how-to-topics.md)
