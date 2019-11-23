---
title: Menu 컨트롤 형식에 대한 UI 자동화 지원
ms.date: 03/30/2017
helpviewer_keywords:
- control types, Menu
- UI Automation, Menu control type
- Menu control type
ms.assetid: 016323cb-f800-4938-b77b-2eb25d646090
ms.openlocfilehash: f09438d9941f2abb49cae8f7542efe84f44e81dc
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446749"
---
# <a name="ui-automation-support-for-the-menu-control-type"></a>Menu 컨트롤 형식에 대한 UI 자동화 지원
> [!NOTE]
> 이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](/windows/win32/winauto/entry-uiauto-win32)를 참조하세요.  
  
 이 항목에서는 Menu 컨트롤 형식에 대한 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 지원 정보를 제공합니다. 컨트롤의 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 트리 구조에 대해 설명하고 특정 컨트롤 시나리오에 사용되는 속성 및 컨트롤 패턴을 제공합니다.  
  
 메뉴 컨트롤을 사용하면 명령 및 이벤트 처리기와 연관된 요소를 계층적으로 구성할 수 있습니다. In a typical Microsoft Windows application, a menu bar contains several menu buttons (such as **File**, **Edit**, and **Window**), and each menu button displays a menu. 메뉴 하나에 메뉴 항목 컬렉션(예: **새로 만들기**, **열기**, **닫기**)이 들어 있으며, 클릭하면 확장되어 추가 메뉴 항목이 표시되거나 특정 작업을 수행할 수 있습니다.  
  
 다음 섹션에서는 Menu 컨트롤 형식에 필요한 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 트리 구조, 속성, 컨트롤 패턴, 이벤트를 정의합니다. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 요구 사항은 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]또는 [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)]의 모든 목록 컨트롤에 적용됩니다.  
  
<a name="Required_UI_Automation_Tree_Structure"></a>   
## <a name="required-ui-automation-tree-structure"></a>필요한 UI 자동화 트리 구조  
 다음 표는 메뉴 컨트롤과 관련된 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 트리의 컨트롤 뷰 및 콘텐츠 뷰를 보여주고 각 뷰에 포함될 수 있는 내용에 대해 설명합니다. For more information on the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree, see [UI Automation Tree Overview](ui-automation-tree-overview.md).  
  
|컨트롤 뷰|콘텐츠 뷰|  
|------------------|------------------|  
|메뉴<br /><br /> -   MenuItem (1 or many)|해당 사항 없음(메뉴 컨트롤이 메뉴 항목이 아닌 개체의 부모인 상황에 맞는 메뉴인 경우 제외)<br /><br /> -   MenuItem (1 or many)|  
  
 메뉴 컨트롤은 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 트리의 컨트롤 뷰 및 콘텐츠 뷰에 항상 표시됩니다. Menu 컨트롤 형식은 이 형식의 정보를 참조하는 컨트롤 아래 표시됩니다. UI 자동화 클라이언트는 `MenuOpenedEvent` 를 수신해야 메뉴 컨트롤이 전달하는 정보를 지속적으로 가져올 수 있습니다. 상황에 맞는 메뉴 컨트롤은 특수한 경우입니다. 이 메뉴 컨트롤은 데스크톱의 자식으로 표시됩니다.  
  
<a name="Required_UI_Automation_Properties"></a>   
## <a name="required-ui-automation-properties"></a>필요한 UI 자동화 속성  
 다음 표에서는 값 또는 정의가 Menu 컨트롤 형식과 특별히 관련된 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 속성을 나열하여 보여 줍니다. For more information on [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] properties, see [UI Automation Properties for Clients](ui-automation-properties-for-clients.md).  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 속성|값|노트|  
|------------------------------------------------------------------------------------|-----------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|지원 안 됨|메뉴 컨트롤에서는 Name 속성을 설정할 필요가 없습니다.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|`Null`|일반 메뉴 컨트롤에는 레이블이 필요하지 않습니다.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|메뉴|이 값은 모든 UI 프레임워크에 대해 동일합니다.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|False|메뉴 컨트롤이 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 트리의 콘텐츠 뷰에 포함되지 않습니다.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|True|메뉴 컨트롤이 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 트리의 컨트롤 뷰에 항상 포함됩니다.|  
  
<a name="Required_UI_Automation_Control_Patterns"></a>   
## <a name="required-ui-automation-control-patterns"></a>필요한 UI 자동화 컨트롤 패턴  
 Menu 컨트롤 형식에 필요한 컨트롤 패턴은 없습니다.  
  
<a name="Required_UI_Automation_Events"></a>   
## <a name="required-ui-automation-events"></a>필요한 UI 자동화 이벤트  
 메뉴 컨트롤이 화면에 표시되면 `MenuOpenedEvent` 가 발생해야 합니다. `MenuOpenedEvent` 에 컨트롤의 텍스트가 포함됩니다. 메뉴가 화면에서 사라지면 `MenuClosedEvent` 가 발생해야 합니다.  
  
 다음 표에서는 모든 메뉴 컨트롤에서 지원되는 데 필요한 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 이벤트를 나열하여 보여 줍니다. 이벤트에 대한 자세한 내용은 [UI Automation Events Overview](ui-automation-events-overview.md)를 참조하세요.  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 이벤트|지원/값|노트|  
|---------------------------------------------------------------------------------|--------------------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.MenuOpenedEvent>|필요한 공간|없음|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.MenuClosedEvent>|필요한 공간|없음|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty> 속성 변경 이벤트.|필요한 공간|없음|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty> 속성 변경 이벤트.|필요한 공간|없음|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty> 속성 변경 이벤트.|필요한 공간|없음|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|필요한 공간|없음|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|필요한 공간|없음|  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Automation.ControlType.Menu>
- [UI 자동화 컨트롤 패턴 개요](ui-automation-control-patterns-overview.md)
- [UI 자동화 컨트롤 형식 개요](ui-automation-control-types-overview.md)
- [UI 자동화 개요](ui-automation-overview.md)
