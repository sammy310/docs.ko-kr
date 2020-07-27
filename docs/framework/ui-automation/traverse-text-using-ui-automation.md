---
title: UI 자동화를 사용하여 텍스트 이동
description: Textunit.word 증분에서 Microsoft UI 자동화를 사용 하 여 문서의 텍스트 내용을 트래버스하는 방법의 예제를 참조 하세요.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UI Automation, traversing text
- text, traversing
- traversing text
ms.assetid: 3ddb3b7b-1d6b-4dba-8678-5a68e868aadb
ms.openlocfilehash: 0b4269d043fd6cd0cc5da9825714aab4ead701f9
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168079"
---
# <a name="traverse-text-using-ui-automation"></a><span data-ttu-id="66f00-103">UI 자동화를 사용하여 텍스트 이동</span><span class="sxs-lookup"><span data-stu-id="66f00-103">Traverse Text Using UI Automation</span></span>
> [!NOTE]
> <span data-ttu-id="66f00-104">이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="66f00-104">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="66f00-105">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](/windows/win32/winauto/entry-uiauto-win32)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="66f00-105">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="66f00-106">이 항목에서는 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 을 사용하여 <xref:System.Windows.Automation.Text.TextUnit> 씩 증가시켜 문서의 텍스트 내용을 트래버스하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="66f00-106">This topic shows how to use [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] to traverse the textual content of a document by <xref:System.Windows.Automation.Text.TextUnit> increments.</span></span>  
  
## <a name="example"></a><span data-ttu-id="66f00-107">예제</span><span class="sxs-lookup"><span data-stu-id="66f00-107">Example</span></span>  
 <span data-ttu-id="66f00-108">다음 코드 예제에서는 UI 자동화 텍스트 공급자의 콘텐츠를 트래버스하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="66f00-108">The following code example demonstrates how to traverse the content of a UI Automation text provider.</span></span> <span data-ttu-id="66f00-109">ph x="1" /&gt; 메서드는 <xref:System.Windows.Automation.Text.TextPatternRange>의 <xref:System.Windows.Automation.Text.TextPatternRangeEndpoint.Start> 및 <xref:System.Windows.Automation.Text.TextPatternRangeEndpoint.End> 엔드포인트를 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="66f00-109">The <xref:System.Windows.Automation.Text.TextPatternRange.Move%2A> method moves the <xref:System.Windows.Automation.Text.TextPatternRangeEndpoint.Start> and <xref:System.Windows.Automation.Text.TextPatternRangeEndpoint.End> endpoints of a <xref:System.Windows.Automation.Text.TextPatternRange>.</span></span> <span data-ttu-id="66f00-110">이 텍스트 범위는 일반적으로 텍스트 삽입 지점을 나타내는 중복 제거 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="66f00-110">This text range is typically a degenerate range representing the text insertion point.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="66f00-111">텍스트 기반의 포함된 개체만 텍스트 스트림의 일부로 간주되므로, 이미지 등과 같은 포함된 개체는 `Move` 또는 해당 반환 값에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66f00-111">Since only text-based embedded objects are considered part of the text stream, embedded objects such as images do not affect `Move` or its return value.</span></span>  
  
[!code-csharp[FindText#StartApp](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#startapp)]
[!code-vb[FindText#StartApp](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#startapp)]  
[!code-csharp[FindText#FindTextProvider](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#findtextprovider)]
[!code-vb[FindText#FindTextProvider](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#findtextprovider)]  
[!code-csharp[FindText#Navigate](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#navigate)]
[!code-vb[FindText#Navigate](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#navigate)]  
  
 <span data-ttu-id="66f00-112">제공된 <xref:System.Windows.Automation.Text.TextUnit> 이 컨트롤에서 지원되지 않으면 <xref:System.Windows.Automation.Text.TextUnit> 를 사용하는 모든 메서드는 다음으로 큰 크기의 지원되는 <xref:System.Windows.Automation.Text.TextUnit> 을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="66f00-112">Any method using <xref:System.Windows.Automation.Text.TextUnit> will defer to the next largest <xref:System.Windows.Automation.Text.TextUnit> supported if the given <xref:System.Windows.Automation.Text.TextUnit> is not supported by the control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66f00-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="66f00-113">See also</span></span>

- [<span data-ttu-id="66f00-114">UI 자동화 TextPattern 개요</span><span class="sxs-lookup"><span data-stu-id="66f00-114">UI Automation TextPattern Overview</span></span>](ui-automation-textpattern-overview.md)
- [<span data-ttu-id="66f00-115">UI 자동화를 사용하여 텍스트 상자에 콘텐츠 추가</span><span class="sxs-lookup"><span data-stu-id="66f00-115">Add Content to a Text Box Using UI Automation</span></span>](add-content-to-a-text-box-using-ui-automation.md)
- [<span data-ttu-id="66f00-116">UI 자동화를 사용하여 텍스트 찾기 및 강조</span><span class="sxs-lookup"><span data-stu-id="66f00-116">Find and Highlight Text Using UI Automation</span></span>](find-and-highlight-text-using-ui-automation.md)
- [<span data-ttu-id="66f00-117">UI 자동화 컨트롤 패턴 개요</span><span class="sxs-lookup"><span data-stu-id="66f00-117">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="66f00-118">클라이언트용 UI 자동화 컨트롤 패턴</span><span class="sxs-lookup"><span data-stu-id="66f00-118">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
