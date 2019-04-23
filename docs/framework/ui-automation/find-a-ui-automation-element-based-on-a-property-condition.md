---
title: 속성 조건을 기반으로 UI 자동화 요소 찾기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- elements, finding by property conditions
- UI Automation, finding elements by property conditions
ms.assetid: 3acaee5a-6ce8-4c3e-81c8-67e59eb74477
ms.openlocfilehash: a5e775c69a4dd520d8148bfc790cc00428d9d15e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59175515"
---
# <a name="find-a-ui-automation-element-based-on-a-property-condition"></a>속성 조건을 기반으로 UI 자동화 요소 찾기
> [!NOTE]
>  이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다. 에 대 한 최신 정보에 대 한 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]를 참조 하세요 [Windows Automation API: UI 자동화](https://go.microsoft.com/fwlink/?LinkID=156746)합니다.  
  
 이 항목에서는 내에서 요소를 찾는 방법을 보여 주는 예제 코드는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 트리에서 특정 속성 또는 속성에 따라 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 속성 조건 집합은 관심 있는 특정 요소 (또는 요소)를 식별 하는에 지정 된 <xref:System.Windows.Automation.AutomationElement> 트리. 일치 하는 모든 요소에 대 한 검색을 사용 하 여 수행 됩니다 합니다 <xref:System.Windows.Automation.AutomationElement.FindAll%2A> 일련의 통합 하는 메서드 <xref:System.Windows.Automation.AndCondition> 일치 하는 요소 수를 제한 하려면 부울 연산입니다.  
  
> [!NOTE]
>  검색 하는 경우는 <xref:System.Windows.Automation.AutomationElement.RootElement%2A>, 직계 자식 항목만 가져와야 하는 것이 좋습니다. 하위 항목에 대 한 검색을 수백 또는 수천 개의 요소를 스택 오버플로가 발생할 반복 될 수 있습니다. 낮은 수준의 특정 요소를 가져오려고 시도하는 경우, 낮은 수준의 컨테이너 또는 애플리케이션 창에서 검색을 시작해야 합니다.  
  
 [!code-csharp[InvokePatternApp#1100](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1100)]
 [!code-vb[InvokePatternApp#1100](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1100)]  
  
## <a name="see-also"></a>참고자료

- [InvokePattern 및 ExpandCollapsePattern 메뉴 항목 샘플](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771636(v=vs.90))
- [UI 자동화 요소 가져오기](../../../docs/framework/ui-automation/obtaining-ui-automation-elements.md)
- [AutomationID 속성 사용](../../../docs/framework/ui-automation/use-the-automationid-property.md)
