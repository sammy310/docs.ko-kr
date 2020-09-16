---
title: 속성 조건에 따라 UI 자동화 요소 찾기
description: 속성 조건을 기반으로 UI 자동화 요소를 찾습니다. 특정 속성이 나 속성을 기반으로 UI 자동화 트리 내에서 요소를 찾습니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- elements, finding by property conditions
- UI Automation, finding elements by property conditions
ms.assetid: 3acaee5a-6ce8-4c3e-81c8-67e59eb74477
ms.openlocfilehash: 112f38d6bef726f92dbf13da70b88732929175dd
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557686"
---
# <a name="find-a-ui-automation-element-based-on-a-property-condition"></a>속성 조건에 따라 UI 자동화 요소 찾기
> [!NOTE]
> 이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](/windows/win32/winauto/entry-uiauto-win32)를 참조하세요.  
  
 이 항목에는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 특정 속성이 나 속성을 기반으로 트리 내에서 요소를 찾는 방법을 보여 주는 예제 코드가 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 트리에서 관심 있는 특정 요소를 식별 하는 속성 조건의 집합을 지정 합니다 <xref:System.Windows.Automation.AutomationElement> . 일치 하는 <xref:System.Windows.Automation.AutomationElement.FindAll%2A> 요소 수를 제한 하기 위해 일련의 부울 연산을 통합 하는 메서드를 사용 하 여 일치 하는 모든 요소에 대 한 검색을 수행 <xref:System.Windows.Automation.AndCondition> 합니다.  
  
> [!NOTE]
> 에서 검색할 때 <xref:System.Windows.Automation.AutomationElement.RootElement%2A> 직계 자식만 가져오려고 합니다. 하위 항목에 대 한 검색은 수백 또는 수천 개의 요소를 반복 하 여 스택 오버플로가 발생할 수 있습니다. 낮은 수준의 특정 요소를 가져오려고 시도하는 경우, 낮은 수준의 컨테이너 또는 애플리케이션 창에서 검색을 시작해야 합니다.  
  
 [!code-csharp[InvokePatternApp#1100](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1100)]
 [!code-vb[InvokePatternApp#1100](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1100)]  
  
## <a name="see-also"></a>참조

- [InvokePattern 및 ExpandCollapsePattern 메뉴 항목 샘플](/previous-versions/dotnet/netframework-3.5/ms771636(v=vs.90))
- [UI 자동화 요소 가져오기](obtaining-ui-automation-elements.md)
- [AutomationID 속성 사용](use-the-automationid-property.md)
