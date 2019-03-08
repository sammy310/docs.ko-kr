---
title: 클라이언트 쪽 UI 자동화 공급자 만들기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UI Automation, creating client-side provider
- client-side UI Automation provider, creating
ms.assetid: d91edaf2-be28-41ec-a508-af421cb43c3d
ms.openlocfilehash: df6de47f3ed7373f9065ff7035df90ff09d150c9
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/08/2019
ms.locfileid: "57678295"
---
# <a name="create-a-client-side-ui-automation-provider"></a><span data-ttu-id="5d8a4-102">클라이언트 쪽 UI 자동화 공급자 만들기</span><span class="sxs-lookup"><span data-stu-id="5d8a4-102">Create a Client-Side UI Automation Provider</span></span>
> [!NOTE]
>  <span data-ttu-id="5d8a4-103">이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5d8a4-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="5d8a4-104">에 대 한 최신 정보에 대 한 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]를 참조 하세요 [Windows Automation API: UI 자동화](https://go.microsoft.com/fwlink/?LinkID=156746)합니다.</span><span class="sxs-lookup"><span data-stu-id="5d8a4-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="5d8a4-105">이 항목에는 클라이언트 쪽 UI 자동화 공급자를 구현하는 방법을 보여 주는 예제 코드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d8a4-105">This topic contains example code that shows how to implement a client-side UI Automation provider.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d8a4-106">예제</span><span class="sxs-lookup"><span data-stu-id="5d8a4-106">Example</span></span>  
 <span data-ttu-id="5d8a4-107">다음 예제 코드는 콘솔 창에 대해 매우 간단한 클라이언트 쪽 공급자를 구현하는 [!INCLUDE[TLA#tla_dll](../../../includes/tlasharptla-dll-md.md)] 에 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d8a4-107">The following example code can be built into a [!INCLUDE[TLA#tla_dll](../../../includes/tlasharptla-dll-md.md)] that implements a very simple client-side provider for a console window.</span></span> <span data-ttu-id="5d8a4-108">이 코드에는 유용한 기능이 없지만, UI 자동화 클라이언트 애플리케이션에서 등록할 수 있는 공급자 어셈블리를 설정하는 기본 단계를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d8a4-108">The code does not have any useful functionality, but is intended to demonstrate the basic steps in setting up a provider assembly that can be registered by a UI Automation client application.</span></span>  
  
 [!code-csharp[UIAClientSideProvider_snip#101](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClientSideProvider_snip/CSharp/CSProviderProgram.cs#101)]
 [!code-vb[UIAClientSideProvider_snip#101](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClientSideProvider_snip/visualbasic/csproviderprogram.vb#101)]  
  
## <a name="see-also"></a><span data-ttu-id="5d8a4-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="5d8a4-109">See also</span></span>
- [<span data-ttu-id="5d8a4-110">UI 자동화 공급자 개요</span><span class="sxs-lookup"><span data-stu-id="5d8a4-110">UI Automation Providers Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)
- [<span data-ttu-id="5d8a4-111">클라이언트 쪽 공급자 어셈블리 등록</span><span class="sxs-lookup"><span data-stu-id="5d8a4-111">Register a Client-Side Provider Assembly</span></span>](../../../docs/framework/ui-automation/register-a-client-side-provider-assembly.md)
