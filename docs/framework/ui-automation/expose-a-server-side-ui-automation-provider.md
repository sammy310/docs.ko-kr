---
title: 서버 쪽 UI 자동화 공급자 노출
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- expose a server-side UI Automation provider
- UI Automation, server-side provider, exposing
- server-side UI Automation provider, exposing
ms.assetid: 55d419c0-2201-4101-90c9-2888df4dbb47
ms.openlocfilehash: 49dcae6ccaf749bae8d8a90af850034bb9bd37fb
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74433612"
---
# <a name="expose-a-server-side-ui-automation-provider"></a><span data-ttu-id="8befd-102">서버 쪽 UI 자동화 공급자 노출</span><span class="sxs-lookup"><span data-stu-id="8befd-102">Expose a Server-side UI Automation Provider</span></span>
> [!NOTE]
> <span data-ttu-id="8befd-103">이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8befd-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="8befd-104">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](/windows/win32/winauto/entry-uiauto-win32)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8befd-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="8befd-105">이 항목에는 <xref:System.Windows.Forms.Control?displayProperty=nameWithType> 창에 호스트되는 서버 쪽 UI 자동화 공급자를 노출하는 방법을 보여주는 예제 코드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8befd-105">This topic contains example code that shows how to expose a server-side UI Automation provider that is hosted in a <xref:System.Windows.Forms.Control?displayProperty=nameWithType> window.</span></span>  
  
 <span data-ttu-id="8befd-106">이 예제에서는 클라이언트 애플리케이션이 창에 대한 정보를 요청할 때 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 핵심 서비스가 보내는 메시지인 WM_GETOBJECT를 트랩하기 위해 창 프로시저를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="8befd-106">The example overrides the window procedure to trap WM_GETOBJECT, which is the message sent by the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] core service when a client application requests information about the window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8befd-107">예제</span><span class="sxs-lookup"><span data-stu-id="8befd-107">Example</span></span>  
 [!code-csharp[UIAFragmentProvider_snip#116](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFragmentProvider_snip/CSharp/ListFragment.cs#116)]
 [!code-vb[UIAFragmentProvider_snip#116](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFragmentProvider_snip/VisualBasic/ListFragment.vb#116)]  
  
## <a name="see-also"></a><span data-ttu-id="8befd-108">참조</span><span class="sxs-lookup"><span data-stu-id="8befd-108">See also</span></span>

- [<span data-ttu-id="8befd-109">UI 자동화 공급자 개요</span><span class="sxs-lookup"><span data-stu-id="8befd-109">UI Automation Providers Overview</span></span>](ui-automation-providers-overview.md)
- [<span data-ttu-id="8befd-110">서버 쪽 UI 자동화 공급자 구현</span><span class="sxs-lookup"><span data-stu-id="8befd-110">Server-Side UI Automation Provider Implementation</span></span>](server-side-ui-automation-provider-implementation.md)
