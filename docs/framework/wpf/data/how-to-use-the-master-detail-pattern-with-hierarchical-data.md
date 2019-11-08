---
title: '방법: 계층적 데이터에 마스터-세부 패턴 사용'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: 11429b9e-058d-4084-bfb6-2cf209c8ddf7
ms.openlocfilehash: e4183ddc3868a1568662853b46e05348df129092
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73733475"
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-data"></a>방법: 계층적 데이터에 마스터-세부 패턴 사용
이 예제에서는 마스터-세부 시나리오를 구현 하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 이 예제에서 `LeagueList`은 `Leagues`컬렉션입니다. 각 `League`에는 `Name` 및 `Divisions`컬렉션이 있으며 각 `Division`에는 이름 및 `Teams`컬렉션이 있습니다. 각 `Team`에는 팀 이름이 있습니다.  
  
 [!code-xaml[MasterDetail#HowTo1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto1)]  
[!code-xaml[MasterDetail#HowTo2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto2)]  
  
 예제 스크린샷은 다음과 같습니다. `Divisions` <xref:System.Windows.Controls.ListBox> `Leagues` <xref:System.Windows.Controls.ListBox>에서 선택 항목을 자동으로 추적 하 고 해당 데이터를 표시 합니다. `Teams` <xref:System.Windows.Controls.ListBox>는 다른 두 <xref:System.Windows.Controls.ListBox> 컨트롤의 선택 항목을 추적 합니다.  
  
 ![마스터&#45;세부 시나리오 예를 보여 주는 스크린샷](./media/how-to-use-the-master-detail-pattern-with-hierarchical-data/databinding-master-detail-scenario.png)  
  
 이 예에서는 다음과 같은 두 가지 사항을 확인 해야 합니다.  
  
1. 세 개의 <xref:System.Windows.Controls.ListBox> 컨트롤이 동일한 소스에 바인딩합니다. 바인딩의 <xref:System.Windows.Data.Binding.Path%2A> 속성을 설정 하 여 <xref:System.Windows.Controls.ListBox> 표시할 데이터 수준을 지정 합니다.  
  
2. <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> 속성을 추적 하려는 선택 항목의 <xref:System.Windows.Controls.ListBox> 컨트롤에서 `true`으로 설정 해야 합니다. 이 속성을 설정 하면 선택한 항목이 항상 <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>로 설정 됩니다. 또는 <xref:System.Windows.Controls.ListBox> <xref:System.Windows.Data.CollectionViewSource>에서 데이터를 가져오는 경우 선택 및 통화를 자동으로 동기화 합니다.  
  
 XML 데이터를 사용 하는 경우 기술은 약간 다릅니다. 예제는 [계층적 XML 데이터에 마스터-세부 패턴 사용](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)을 참조 하세요.  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.HierarchicalDataTemplate>
- [선택에 따라 수집 및 표시 정보에 바인딩](how-to-bind-to-a-collection-and-display-information-based-on-selection.md)
- [데이터 바인딩 개요](../../../desktop-wpf/data/data-binding-overview.md)
- [데이터 템플릿 개요](data-templating-overview.md)
- [방법 항목](data-binding-how-to-topics.md)
