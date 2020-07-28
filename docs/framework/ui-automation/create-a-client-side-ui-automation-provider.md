---
title: 클라이언트 쪽 UI 자동화 공급자 만들기
description: 클라이언트 쪽 UI 자동화 공급자를 만드는 방법의 예제를 확인 합니다. 이 예제에서는 콘솔 창에 대 한 간단한 클라이언트 쪽 공급자를 구현 합니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UI Automation, creating client-side provider
- client-side UI Automation provider, creating
ms.assetid: d91edaf2-be28-41ec-a508-af421cb43c3d
ms.openlocfilehash: a25966d0f11e409bd4e53f944fc2528360327039
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168476"
---
# <a name="create-a-client-side-ui-automation-provider"></a><span data-ttu-id="c8e0a-104">클라이언트 쪽 UI 자동화 공급자 만들기</span><span class="sxs-lookup"><span data-stu-id="c8e0a-104">Create a Client-Side UI Automation Provider</span></span>
> [!NOTE]
> <span data-ttu-id="c8e0a-105">이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c8e0a-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="c8e0a-106">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](/windows/win32/winauto/entry-uiauto-win32)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c8e0a-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="c8e0a-107">이 항목에는 클라이언트 쪽 UI 자동화 공급자를 구현하는 방법을 보여 주는 예제 코드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8e0a-107">This topic contains example code that shows how to implement a client-side UI Automation provider.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8e0a-108">예제</span><span class="sxs-lookup"><span data-stu-id="c8e0a-108">Example</span></span>  
 <span data-ttu-id="c8e0a-109">다음 예제 코드는 콘솔 창에 대해 매우 간단한 클라이언트 쪽 공급자를 구현 하는 DLL (동적 연결 라이브러리)로 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8e0a-109">The following example code can be built into a dynamic-link library (DLL) that implements a very simple client-side provider for a console window.</span></span> <span data-ttu-id="c8e0a-110">이 코드에는 유용한 기능이 없지만, UI 자동화 클라이언트 애플리케이션에서 등록할 수 있는 공급자 어셈블리를 설정하는 기본 단계를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8e0a-110">The code does not have any useful functionality, but is intended to demonstrate the basic steps in setting up a provider assembly that can be registered by a UI Automation client application.</span></span>  
  
 [!code-csharp[UIAClientSideProvider_snip#101](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClientSideProvider_snip/CSharp/CSProviderProgram.cs#101)]
 [!code-vb[UIAClientSideProvider_snip#101](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClientSideProvider_snip/visualbasic/csproviderprogram.vb#101)]  
  
## <a name="see-also"></a><span data-ttu-id="c8e0a-111">참조</span><span class="sxs-lookup"><span data-stu-id="c8e0a-111">See also</span></span>

- [<span data-ttu-id="c8e0a-112">UI 자동화 공급자 개요</span><span class="sxs-lookup"><span data-stu-id="c8e0a-112">UI Automation Providers Overview</span></span>](ui-automation-providers-overview.md)
- [<span data-ttu-id="c8e0a-113">클라이언트 쪽 공급자 어셈블리 등록</span><span class="sxs-lookup"><span data-stu-id="c8e0a-113">Register a Client-Side Provider Assembly</span></span>](register-a-client-side-provider-assembly.md)
