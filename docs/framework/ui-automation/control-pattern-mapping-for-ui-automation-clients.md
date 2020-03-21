---
title: UI 자동화 클라이언트에 대한 컨트롤 패턴 매핑
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, for UI Automation clients
- UI Automation, clients, control patterns for
ms.assetid: 8b81645b-8be3-4e26-9c98-4fb0fceca06b
ms.openlocfilehash: 689e649343c93d0670c6870098a09f61097f4fb4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79180237"
---
# <a name="control-pattern-mapping-for-ui-automation-clients"></a>UI 자동화 클라이언트에 대한 컨트롤 패턴 매핑
> [!NOTE]
> 이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](/windows/win32/winauto/entry-uiauto-win32)를 참조하세요.  
  
 이 항목에서는 컨트롤 형식 및 이 형식과 연결된 컨트롤 패턴을 나열하여 보여줍니다.  
  
 다음 표는 컨트롤 패턴을 다음과 같은 범주로 정리하여 보여줍니다.  
  
- 지원됩니다. 컨트롤은 이 컨트롤 패턴을 지원해야 합니다.  
  
- 조건부 지원입니다. 컨트롤은 컨트롤의 상태에 따라 이 컨트롤 패턴을 지원할 수 있습니다.  
  
- 지원되지 않습니다. 컨트롤은 이 컨트롤 패턴을 지원하지 않습니다. 사용자 지정 컨트롤이 이 컨트롤 패턴을 지원할 수 있습니다.  
  
> [!NOTE]
> 일부 컨트롤은 컨트롤 기능에 따라 몇몇 컨트롤 패턴을 조건부로 지원합니다. 예를 들어, 메뉴 항목 컨트롤은 메뉴 컨트롤의 기능에 따라 <xref:System.Windows.Automation.InvokePattern>, <xref:System.Windows.Automation.ExpandCollapsePattern>, <xref:System.Windows.Automation.TogglePattern>또는 <xref:System.Windows.Automation.SelectionItemPattern> 컨트롤 패턴을 조건부로 지원합니다.  
  
<a name="control_mapping_clients"></a>
## <a name="ui-automation-control-patterns-for-clients"></a>클라이언트용 UI 자동화 컨트롤 패턴  
  
|컨트롤 종류|지원됨|조건부 지원|지원되지 않음|  
|------------------|---------------|-------------------------|-------------------|  
|단추|None|Invoke, Toggle, Expand Collapse|None|  
|달력|Grid, Table|Selection, Scroll|값|  
|확인란|설정/해제|None|None|  
|Combo Box|확장 축소|선택, 값|Scroll|  
|데이터 표|표 형태|Scroll, Selection, Table|None|  
|Data Item|Selection Item|Expand Collapse, Grid Item, Scroll Item, Table, Toggle, Value|None|  
|문서|텍스트|Scroll, Value|None|  
|편집|None|Text, Range Value, Value|None|  
|그룹|None|확장 축소|None|  
|헤더|None|변환|None|  
|Header Item|None|Transform, Invoke|None|  
|Hyperlink|호출|값|None|  
|이미지|None|Grid Item, Table Item|Invoke, Selection Item|  
|목록|None|Grid, Multiple View, Scroll, Selection|테이블|  
|List Item|Selection Item|Expand Collapse, Grid Item, Invoke, Scroll Item, Toggle, Value|None|  
|메뉴|None|None|None|  
|메뉴 모음|None|Expand Collapse, Dock, Transform|None|  
|메뉴 항목|None|Expand Collapse, Invoke, Selection Item, Toggle|None|  
|창|None|Dock. Scroll, Transform|시간 범위|  
|Progress Bar|None|Range Value, Value|None|  
|Radio Button|Selection Item|None|설정/해제|  
|Scroll Bar|None|Range Value|Scroll|  
|구분 기호|None|None|None|  
|슬라이더|None|Range Value, Selection, Value|None|  
|Spinner|None|Range Value, Selection, Value|None|  
|분할 단추|Invoke, Expand Collapse|None|None|  
|상태 표시줄|None|표 형태|None|  
|탭|선택|Scroll|None|  
|Tab Item|Selection Item|None|호출|  
|테이블|Grid, Grid Item, Table, Table Item|None|None|  
|텍스트|None|Grid Item, Table Item, Text|값|  
|Thumb|변환|None|None|  
|제목 표시줄|None|None|None|  
|Tool Bar|None|Dock, Expand Collapse, Transform|None|  
|Tool Tip|None|Text, Window|None|  
|트리|None|Scroll, Selection|None|  
|Tree Item|확장 축소|Invoke, Scroll Item, Selection Item, Toggle|None|  
|시간 범위|Transform, Window|도킹|None|  
  
> [!NOTE]
> 컨트롤 형식에 지원되는 컨트롤 패턴이 없지만 조건부로 지원되는 하나 이상의 컨트롤 패턴이 있는 경우, 조건부 컨트롤 패턴 중 하나는 항상 지원됩니다.  
  
## <a name="see-also"></a>참고 항목

- [UI 자동화 개요](ui-automation-overview.md)
