---
title: UI 자동화를 사용하여 텍스트 특성 가져오기
description: UI 자동화를 사용 하 여 텍스트 특성을 가져오는 방법에 대해 알아봅니다. 텍스트 범위에서 텍스트 특성을 가져오는 코드 예제를 참조 하세요.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- getting, text attributes
- UI Automation, getting text attributes
- text attributes, getting
ms.assetid: fdefc6c3-b836-4cfe-8dec-1484bfdc5551
ms.openlocfilehash: b48f773e27088ba4b33ad01b299d77a0992a9159
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168006"
---
# <a name="obtain-text-attributes-using-ui-automation"></a><span data-ttu-id="3af71-104">UI 자동화를 사용하여 텍스트 특성 가져오기</span><span class="sxs-lookup"><span data-stu-id="3af71-104">Obtain Text Attributes Using UI Automation</span></span>
> [!NOTE]
> <span data-ttu-id="3af71-105">이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3af71-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="3af71-106">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](/windows/win32/winauto/entry-uiauto-win32)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3af71-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="3af71-107">이 항목에서는 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 을 사용하여 텍스트 범위에서 텍스트 특성을 가져오는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="3af71-107">This topic shows how to use [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] to obtain text attributes from a text range.</span></span> <span data-ttu-id="3af71-108">텍스트 범위는 문서 내에서 캐럿의 현재 위치(또는 중복 제거 선택 항목), 연속적인 텍스트 선택 항목, 분리형 텍스트 선택 항목의 컬렉션 또는 문서의 전체 텍스트 내용에 해당될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3af71-108">A text range can correspond to the current location of the caret (or degenerate selection) within a document, a contiguous selection of text, a collection of disjoint text selections, or the entire textual content of a document.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3af71-109">예제</span><span class="sxs-lookup"><span data-stu-id="3af71-109">Example</span></span>  
 <span data-ttu-id="3af71-110">다음 코드 예제는 텍스트 범위에서 <xref:System.Windows.Automation.TextPattern.FontNameAttribute> 를 가져오는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3af71-110">The following code example demonstrates how to obtain the <xref:System.Windows.Automation.TextPattern.FontNameAttribute> from a text range.</span></span>  
  
 [!code-csharp[UIATextPattern_snip#StartTarget](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATextPattern_snip/CSharp/SearchWindow.cs#starttarget)]
 [!code-vb[UIATextPattern_snip#StartTarget](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATextPattern_snip/VisualBasic/SearchWindow.vb#starttarget)]  
[!code-csharp[UIATextPattern_snip#GetTextElement](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATextPattern_snip/CSharp/SearchWindow.cs#gettextelement)]
[!code-vb[UIATextPattern_snip#GetTextElement](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATextPattern_snip/VisualBasic/SearchWindow.vb#gettextelement)]  
[!code-csharp[UIATextPattern_snip#FontName](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATextPattern_snip/CSharp/SearchWindow.cs#fontname)]
[!code-vb[UIATextPattern_snip#FontName](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATextPattern_snip/VisualBasic/SearchWindow.vb#fontname)]  
  
 <span data-ttu-id="3af71-111"><xref:System.Windows.Automation.TextPattern> 컨트롤 패턴은 <xref:System.Windows.Automation.Text.TextPatternRange> 클래스와 함께 기본 텍스트 특성, 속성 및 메서드를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="3af71-111">The <xref:System.Windows.Automation.TextPattern> control pattern, in tandem with the <xref:System.Windows.Automation.Text.TextPatternRange> class, supports basic text attributes, properties, and methods.</span></span> <span data-ttu-id="3af71-112"><xref:System.Windows.Automation.TextPattern> 또는 <xref:System.Windows.Automation.Text.TextPatternRange> 에서 지원되지 않는 컨트롤 관련 기능의 경우 <xref:System.Windows.Automation.AutomationElement>클래스는 UI 자동화 클라이언트가 해당되는 기본 개체 모델에 액세스할 수 있는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3af71-112">For control-specific functionality that is not supported by <xref:System.Windows.Automation.TextPattern> or <xref:System.Windows.Automation.Text.TextPatternRange> the <xref:System.Windows.Automation.AutomationElement>, class provides methods for a UI Automation client to access the corresponding native object model.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3af71-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3af71-113">See also</span></span>

- [<span data-ttu-id="3af71-114">UI 자동화 TextPattern 개요</span><span class="sxs-lookup"><span data-stu-id="3af71-114">UI Automation TextPattern Overview</span></span>](ui-automation-textpattern-overview.md)
- [<span data-ttu-id="3af71-115">UI 자동화를 사용하여 텍스트 상자에 콘텐츠 추가</span><span class="sxs-lookup"><span data-stu-id="3af71-115">Add Content to a Text Box Using UI Automation</span></span>](add-content-to-a-text-box-using-ui-automation.md)
- [<span data-ttu-id="3af71-116">UI 자동화를 사용하여 텍스트 찾기 및 강조</span><span class="sxs-lookup"><span data-stu-id="3af71-116">Find and Highlight Text Using UI Automation</span></span>](find-and-highlight-text-using-ui-automation.md)
- [<span data-ttu-id="3af71-117">UI 자동화 컨트롤 패턴 개요</span><span class="sxs-lookup"><span data-stu-id="3af71-117">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="3af71-118">클라이언트용 UI 자동화 컨트롤 패턴</span><span class="sxs-lookup"><span data-stu-id="3af71-118">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="3af71-119">UI 자동화를 사용하여 혼합 텍스트 특성 정보 가져오기</span><span class="sxs-lookup"><span data-stu-id="3af71-119">Obtain Mixed Text Attribute Details Using UI Automation</span></span>](obtain-mixed-text-attribute-details-using-ui-automation.md)
