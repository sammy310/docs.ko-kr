---
title: UI 자동화 개요
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, overview
- user interface, see UI
- accessibility, UI automation
ms.assetid: 65847654-9994-4a9e-b36d-2dd5d998770b
ms.openlocfilehash: 06cbc82f3636c4063b445a0ccbe871e0be1dd847
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59134673"
---
# <a name="ui-automation-overview"></a>UI 자동화 개요
> [!NOTE]
>  이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다. 에 대 한 최신 정보에 대 한 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]를 참조 하세요 [Windows Automation API: UI 자동화](https://go.microsoft.com/fwlink/?LinkID=156746)합니다.  
  
 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 에 대 한 새로운 접근성 프레임 워크 [!INCLUDE[TLA#tla_win](../../../includes/tlasharptla-win-md.md)]지 원하는 모든 운영 체제에서 사용할 수 있는, [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)]합니다.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 대부분에 프로그래밍 방식으로 액세스할 [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] 요소와 같은 보조 기술 제품을 사용 하도록 설정, 바탕 화면 판독기에 대 한 정보를 제공 하는 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 최종 사용자에 게 조작 하는 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 이외의 통해 표준 입력 합니다. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 에서는 다음 상호 작용 하는 자동화 된 테스트 스크립트는 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]합니다.  
  
> [!NOTE]
>  [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 통해 다른 사용자가 시작한 프로세스 간의 통신을 사용 하지 않는 합니다 **으로 실행** 명령입니다.  
  
 UI 자동화 클라이언트 애플리케이션이 여러 프레임워크에서 작동되도록 작성할 수 있습니다. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 코어가 다양한 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]항목의 기반이 되는 프레임워크에서 모든 차이점을 마스크합니다. 예를 들어, `Content` 단추의 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 속성, `Caption` 단추의 [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] 속성, HTML 이미지의 `ALT` 속성은 모두 <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name%2A>뷰에서 단일 속성 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 에 매핑됩니다.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 전체 기능을 제공 [!INCLUDE[TLA#tla_longhorn](../../../includes/tlasharptla-longhorn-md.md)], [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)], 및 [!INCLUDE[TLA2#tla_winnetsvrfam](../../../includes/tla2sharptla-winnetsvrfam-md.md)]합니다.  
  
 UI 자동화 공급자는 기본으로 제공되는 브리징 서비스를 통해 [!INCLUDE[TLA#tla_aa](../../../includes/tlasharptla-aa-md.md)] 클라이언트 애플리케이션에 대한 일부 지원을 제공합니다.  
  
<a name="Providers_and_Clients"></a>   
## <a name="providers-and-clients"></a>공급자 및 클라이언트  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 다음 표에 나와 있는 것 처럼 4 개의 주요 구성 요소에 있습니다.  
  
|구성 요소|설명|  
|---------------|-----------------|  
|공급자 [!INCLUDE[TLA#tla_api](../../../includes/tlasharptla-api-md.md)] (UIAutomationProvider.dll 및 UIAutomationTypes.dll)|UI 자동화 공급자가 구현하는 인터페이스 정의 집합으로서, [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 요소에 대한 정보를 제공하고 프로그래밍 방식으로 입력에 응답하는 개체입니다.|  
|클라이언트 API(UIAutomationClient.dll 및 UIAutomationTypes.dll)|UI 자동화 클라이언트 애플리케이션이 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 에 대한 정보를 가져오고 입력을 컨트롤에 보내도록 하는 관리되는 코드의 형식 집합입니다.|  
|UiAutomationCore.dll|공급자와 클라이언트 간의 통신을 처리하는 기본 코드입니다( [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 코어라고도 함).|  
|UIAutomationClientsideProviders.dll|표준 레거시 컨트롤에 대한 UI 자동화 공급자의 집합입니다. ([!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 컨트롤에는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 기본 지원이 있습니다.) 이 지원은 클라이언트 응용 프로그램에서 자동으로 사용할 수 있습니다.|  
  
 소프트웨어 개발자의 관점에서 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]을 두 가지 방법으로 사용할 수 있습니다. 사용자 지정 컨트롤에 대한 지원을 생성하거나(공급자 API 사용) [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 코어를 사용하여 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 요소와 통신하는 애플리케이션을 생성합니다(클라이언트 API 사용). 관점에 따라 다르지만, 설명서의 여러 부분을 참조해야 합니다. 다음 섹션에서 개념에 대해 자세히 알아보고 실용적인 방법에 대한 지식을 얻을 수 있습니다.  
  
|단원|실무|대상 사용자|  
|-------------|--------------------|--------------|  
|[UI 자동화 기본 사항](../../../docs/framework/ui-automation/index.md) (이 섹션)|개념에 대한 광범위한 개요입니다.|모두.|  
|[관리 코드에 대한 UI 자동화 공급자](../../../docs/framework/ui-automation/ui-automation-providers-for-managed-code.md)|공급자 API 사용에 도움을 주는 개념 및 방법에 대한 항목입니다.|컨트롤 개발자입니다.|  
|[관리 코드에 대한 UI 자동화 클라이언트](../../../docs/framework/ui-automation/ui-automation-clients-for-managed-code.md)|클라이언트 API 사용에 도움을 주는 개념 및 방법에 대한 항목입니다.|클라이언트 애플리케이션 개발자.|  
|[UI 자동화 컨트롤 패턴](../../../docs/framework/ui-automation/ui-automation-control-patterns.md)|공급자가 컨트롤 패턴을 구현하는 방법 및 클라이언트에 사용 가능한 기능에 대한 정보입니다.|모두.|  
|[UI 자동화 텍스트 패턴](../../../docs/framework/ui-automation/ui-automation-text-pattern.md)|공급자가 Text 컨트롤 패턴을 구현하는 방법 및 클라이언트에 사용 가능한 기능에 대한 정보입니다.|모두.|  
|[UI 자동화 컨트롤 형식](../../../docs/framework/ui-automation/ui-automation-control-types.md)|다른 컨트롤 형식에서 지원하는 속성 및 컨트롤 패턴에 대한 정보입니다.|모두.|  
  
 다음 표에서는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 네임스페이스, 네임스페이스를 포함하는 DLL, 네임스페이스를 사용하는 대상을 나열하여 보여줍니다.  
  
|네임스페이스|참조되는 DLL|대상 사용자|  
|---------------|---------------------|--------------|  
|<xref:System.Windows.Automation>|UIAutomationClientUIAutomationTypes|UI 자동화 클라이언트 개발자. <xref:System.Windows.Automation.AutomationElement> 개체를 찾고, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 이벤트를 등록하고, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 컨트롤 패턴을 작업하는 데 사용됩니다.|  
|<xref:System.Windows.Automation.Provider>|UIAutomationProviderUIAutomationTypes|[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]가 아닌 프레임워크의 UI 자동화 공급자 개발자.|  
|<xref:System.Windows.Automation.Text>|UIAutomationClientUIAutomationTypes|[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]가 아닌 프레임워크의 UI 자동화 공급자 개발자. TextPattern 컨트롤 패턴을 구현하는 데 사용됩니다.|  
|<xref:System.Windows.Automation.Peers>|PresentationFramework|[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]의 UI 자동화 공급자 개발자.|  
  
<a name="UI_Automation_Model"></a>   
## <a name="ui-automation-model"></a>UI 자동화 모델  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 모든 부분을 노출 합니다 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 클라이언트 응용 프로그램에는 <xref:System.Windows.Automation.AutomationElement>합니다. 요소는 루트 요소로 데스크톱과 함께 트리 구조에 포함됩니다. 클라이언트는 트리의 Raw 보기를 컨트롤 뷰 또는 콘텐츠 뷰로 필터링할 수 있습니다. 애플리케이션은 사용자 지정 뷰를 만들 수도 있습니다.  
  
 <xref:System.Windows.Automation.AutomationElement> 공용 속성을 노출 하는 개체는 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 요소를 나타냅니다. 이러한 속성 중 하나는 인식할 수 있는 단일 엔터티로 기본 모양과 기능을 정의하는 컨트롤 형식입니다(예: 단추 또는 확인란).  
  
 또한 요소는 해당 컨트롤 형식과 관련된 속성을 제공하는 컨트롤 패턴을 노출합니다. 컨트롤 패턴은 클라이언트가 요소에 대한 추가 정보를 수집하고 입력을 제공할 수 있는 메서드를 노출합니다.  
  
> [!NOTE]
>  컨트롤 형식과 컨트롤 패턴 간에 일대일 대응이 없습니다. 단일 컨트롤 패턴은 여러 컨트롤 형식에서 지원될 수 있으며, 단일 컨트롤에는 각각 해당 동작의 다양한 측면을 노출하는 여러 컨트롤 패턴을 지원할 수 있습니다. 예를 들어, 콤보 상자에 둘 이상의 컨트롤 패턴이 있을 수 있으며 그중 하나는 확장 및 축소하는 기능을 나타내며 나머지 하나는 선택 메커니즘을 나타냅니다. 자세한 내용은 [UI Automation Control Types](../../../docs/framework/ui-automation/ui-automation-control-types.md)을 참조하세요.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 또한 이벤트를 통해 클라이언트 응용 프로그램에 대 한 정보를 제공합니다. [!INCLUDE[TLA2#tla_winevents](../../../includes/tla2sharptla-winevents-md.md)]와는 달리, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 이벤트는 브로드캐스트 메커니즘을 기반으로 하지 않습니다. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클라이언트는 특정 이벤트 알림에 대 한 등록 하 고 해당 특정을 요청할 수 있습니다 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 속성 및 컨트롤 패턴 정보를 해당 이벤트 처리기에 전달할 수 있습니다. 또한 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 이벤트에는 이 이벤트를 발생시킨 요소에 대한 참조가 들어 있습니다. 공급자는 모든 클라이언트가 수신 대기하고 있는지 여부에 따라 선택적으로 이벤트를 발생시켜 성능을 향상시킬 수 있습니다.  
  
## <a name="see-also"></a>참고자료

- [UI 자동화 트리 개요](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)
- [UI 자동화 컨트롤 패턴 개요](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)
- [UI 자동화 속성 개요](../../../docs/framework/ui-automation/ui-automation-properties-overview.md)
- [UI 자동화 이벤트 개요](../../../docs/framework/ui-automation/ui-automation-events-overview.md)
- [UI 자동화 보안 개요](../../../docs/framework/ui-automation/ui-automation-security-overview.md)
