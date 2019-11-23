---
title: UI 자동화 공급자에서 이벤트 발생
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, raising events
- raising UI Automation events
ms.assetid: 9fe2f01b-f7d8-49a8-a185-d4472b9976c0
ms.openlocfilehash: 1a940cbb99ac068dad6c366520a544035270da3e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446882"
---
# <a name="raise-events-from-a-ui-automation-provider"></a><span data-ttu-id="1da43-102">UI 자동화 공급자에서 이벤트 발생</span><span class="sxs-lookup"><span data-stu-id="1da43-102">Raise Events from a UI Automation Provider</span></span>
> [!NOTE]
> <span data-ttu-id="1da43-103">이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1da43-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="1da43-104">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](/windows/win32/winauto/entry-uiauto-win32)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1da43-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="1da43-105">이 항목에는 UI 자동화 공급자에서 이벤트를 발생시키는 방법을 보여주는 예제 코드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1da43-105">This topic contains example code that shows how to raise an event from a UI Automation provider.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1da43-106">예제</span><span class="sxs-lookup"><span data-stu-id="1da43-106">Example</span></span>  
 <span data-ttu-id="1da43-107">다음 예제에서는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 이벤트가 사용자 지정 단추 컨트롤의 구현에서 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="1da43-107">In the following example, a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] event is raised in the implementation of a custom button control.</span></span> <span data-ttu-id="1da43-108">이 구현을 통해 UI 자동화 클라이언트 애플리케이션이 단추 클릭을 시뮬레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1da43-108">The implementation enables a UI Automation client application to simulate a button click.</span></span>  
  
 <span data-ttu-id="1da43-109">불필요한 프로세스를 방지하기 위해, 이 예제에서는 <xref:System.Windows.Automation.Provider.AutomationInteropProvider.ClientsAreListening%2A> 을 검사하여 이벤트 발생 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1da43-109">To avoid unnecessary processing, the example checks <xref:System.Windows.Automation.Provider.AutomationInteropProvider.ClientsAreListening%2A> to see whether events should be raised.</span></span>  
  
 [!code-csharp[UIAProvider_snip#150](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAProvider_snip/CSharp/FragmentRoot.cs#150)]  
  
## <a name="see-also"></a><span data-ttu-id="1da43-110">참조</span><span class="sxs-lookup"><span data-stu-id="1da43-110">See also</span></span>

- [<span data-ttu-id="1da43-111">UI 자동화 공급자 개요</span><span class="sxs-lookup"><span data-stu-id="1da43-111">UI Automation Providers Overview</span></span>](ui-automation-providers-overview.md)
