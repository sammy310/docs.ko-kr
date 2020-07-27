---
title: UI 자동화 공급자에서 이벤트 발생
description: UI 자동화 공급자에서 이벤트를 발생 시키는 방법을 보여 주는 예제를 참조 하세요. 사용자 지정 단추 컨트롤의 구현에서 UI 자동화 이벤트를 발생 시킵니다.
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, raising events
- raising UI Automation events
ms.assetid: 9fe2f01b-f7d8-49a8-a185-d4472b9976c0
ms.openlocfilehash: 75af4d05172e2417d44f76beab486de5eb3a4ba7
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168114"
---
# <a name="raise-events-from-a-ui-automation-provider"></a><span data-ttu-id="6dc0b-104">UI 자동화 공급자에서 이벤트 발생</span><span class="sxs-lookup"><span data-stu-id="6dc0b-104">Raise Events from a UI Automation Provider</span></span>
> [!NOTE]
> <span data-ttu-id="6dc0b-105">이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6dc0b-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="6dc0b-106">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](/windows/win32/winauto/entry-uiauto-win32)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6dc0b-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="6dc0b-107">이 항목에는 UI 자동화 공급자에서 이벤트를 발생시키는 방법을 보여주는 예제 코드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6dc0b-107">This topic contains example code that shows how to raise an event from a UI Automation provider.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6dc0b-108">예제</span><span class="sxs-lookup"><span data-stu-id="6dc0b-108">Example</span></span>  
 <span data-ttu-id="6dc0b-109">다음 예제에서는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 이벤트가 사용자 지정 단추 컨트롤의 구현에서 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="6dc0b-109">In the following example, a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] event is raised in the implementation of a custom button control.</span></span> <span data-ttu-id="6dc0b-110">이 구현을 통해 UI 자동화 클라이언트 애플리케이션이 단추 클릭을 시뮬레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6dc0b-110">The implementation enables a UI Automation client application to simulate a button click.</span></span>  
  
 <span data-ttu-id="6dc0b-111">불필요한 프로세스를 방지하기 위해, 이 예제에서는 <xref:System.Windows.Automation.Provider.AutomationInteropProvider.ClientsAreListening%2A> 을 검사하여 이벤트 발생 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6dc0b-111">To avoid unnecessary processing, the example checks <xref:System.Windows.Automation.Provider.AutomationInteropProvider.ClientsAreListening%2A> to see whether events should be raised.</span></span>  
  
 [!code-csharp[UIAProvider_snip#150](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAProvider_snip/CSharp/FragmentRoot.cs#150)]  
  
## <a name="see-also"></a><span data-ttu-id="6dc0b-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6dc0b-112">See also</span></span>

- [<span data-ttu-id="6dc0b-113">UI 자동화 공급자 개요</span><span class="sxs-lookup"><span data-stu-id="6dc0b-113">UI Automation Providers Overview</span></span>](ui-automation-providers-overview.md)
