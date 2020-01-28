---
title: 관리되지 않는 앱
ms.date: 03/30/2017
helpviewer_keywords:
- ActiveX controls [Windows Forms]
- COM interop [Windows Forms], Windows Forms
- COM [Windows Forms]
- Windows Forms, unmanaged
- Windows Forms, interop
ms.assetid: 81bc100c-fa49-4614-85a6-0f7ab59eac8a
ms.openlocfilehash: 17dc20653d1628dfd460a9891e1b0a21c0ebecbd
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746361"
---
# <a name="windows-forms-and-unmanaged-applications"></a><span data-ttu-id="321d2-102">Windows Forms 및 관리되지 않는 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="321d2-102">Windows Forms and Unmanaged Applications</span></span>
<span data-ttu-id="321d2-103">Windows Forms 애플리케이션과 컨트롤은 관리되지 않는 애플리케이션과 상호 운용될 수 있지만 몇 가지 주의할 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="321d2-103">Windows Forms applications and controls can interoperate with unmanaged applications, with some caveats.</span></span> <span data-ttu-id="321d2-104">다음 섹션에서는 Windows Forms 애플리케이션과 컨트롤이 지원하는 시나리오 및 구성과 지원하지 않는 시나리오 및 구성을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="321d2-104">The following sections describe the scenarios and configurations that Windows Forms applications and controls support and those that they do not support.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="321d2-105">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="321d2-105">In This Section</span></span>  
 [<span data-ttu-id="321d2-106">Windows Forms 및 관리되지 않는 애플리케이션 개요</span><span class="sxs-lookup"><span data-stu-id="321d2-106">Windows Forms and Unmanaged Applications Overview</span></span>](windows-forms-and-unmanaged-applications-overview.md)  
 <span data-ttu-id="321d2-107">관리되지 않는 애플리케이션에서 작동하는 Windows Forms 컨트롤을 사용 및 구현하는 방법에 대한 일반적인 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="321d2-107">Offers general information about how to use and implement Windows Forms controls that work with unmanaged applications.</span></span>  
  
 [<span data-ttu-id="321d2-108">방법: ShowDialog 메서드로 Windows Form을 표시하여 COM Interop 지원</span><span class="sxs-lookup"><span data-stu-id="321d2-108">How to: Support COM Interop by Displaying a Windows Form with the ShowDialog Method</span></span>](com-interop-by-displaying-a-windows-form-shadow.md)  
 <span data-ttu-id="321d2-109"><xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> 메서드를 사용하여 관리되지 않는 애플리케이션에서 Windows Form을 실행하는 방법을 보여 주는 코드 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="321d2-109">Provides a code example that shows how to use the <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> method to run a Windows Form in an unmanaged application.</span></span>  
  
 [<span data-ttu-id="321d2-110">How to: Support COM Interop by Displaying Each Windows Form on Its Own Thread</span><span class="sxs-lookup"><span data-stu-id="321d2-110">How to: Support COM Interop by Displaying Each Windows Form on Its Own Thread</span></span>](how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md)  
 <span data-ttu-id="321d2-111">고유한 스레드에서 Windows Form을 실행하는 방법을 보여 주는 코드 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="321d2-111">Provides a code example that shows how to run a Windows Form on its own thread.</span></span>  
  
 <span data-ttu-id="321d2-112">[연습: 각 Windows Form을 별개의 스레드에서 표시하여 COM Interop 지원](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233639(v=vs.100))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="321d2-112">Also see [Walkthrough: Supporting COM Interop by Displaying Each Windows Form on Its Own Thread](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233639(v=vs.100)).</span></span>  
  
## <a name="reference"></a><span data-ttu-id="321d2-113">참조</span><span class="sxs-lookup"><span data-stu-id="321d2-113">Reference</span></span>  
 <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType>  
 <span data-ttu-id="321d2-114">Windows Form에 대한 별도 스레드를 만드는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="321d2-114">Used to create a separate thread for a Windows Form.</span></span>  
  
 <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType>  
 <span data-ttu-id="321d2-115">스레드에 대한 메시지 루프를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="321d2-115">Starts a message loop for a thread.</span></span>  
  
 <xref:System.Windows.Forms.Control.Invoke%2A>  
 <span data-ttu-id="321d2-116">관리되지 않는 애플리케이션에서의 폼 호출을 마샬링합니다.</span><span class="sxs-lookup"><span data-stu-id="321d2-116">Marshals calls from an unmanaged application to a form.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="321d2-117">관련 섹션</span><span class="sxs-lookup"><span data-stu-id="321d2-117">Related Sections</span></span>  
 [<span data-ttu-id="321d2-118">.NET Framework 구성 요소를 COM에 노출</span><span class="sxs-lookup"><span data-stu-id="321d2-118">Exposing .NET Framework Components to COM</span></span>](../../interop/exposing-dotnet-components-to-com.md)  
 <span data-ttu-id="321d2-119">관리되지 않는 애플리케이션에서 .NET Framework 형식을 사용하는 방법에 대한 일반적인 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="321d2-119">Offers general information about how to use .NET Framework types in unmanaged applications.</span></span>
