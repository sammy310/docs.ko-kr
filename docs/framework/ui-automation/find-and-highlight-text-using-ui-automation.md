---
title: UI 자동화를 사용하여 텍스트 찾기 및 강조
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text, highlighting
- finding text
- text, finding
- UI automation, highlighting text
- UI automation, finding text
- highlighting text
ms.assetid: b77693f5-87bb-4b29-a297-05ff882e2044
ms.openlocfilehash: 0e5f856c69fab45a4c92e12746f357320d2e323c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74435744"
---
# <a name="find-and-highlight-text-using-ui-automation"></a><span data-ttu-id="b6db8-102">UI 자동화를 사용하여 텍스트 찾기 및 강조</span><span class="sxs-lookup"><span data-stu-id="b6db8-102">Find and Highlight Text Using UI Automation</span></span>
> [!NOTE]
> <span data-ttu-id="b6db8-103">이 설명서는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 네임스페이스에 정의된 관리되는 <xref:System.Windows.Automation> 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b6db8-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="b6db8-104">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](/windows/win32/winauto/entry-uiauto-win32)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b6db8-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="b6db8-105">이 항목에서는 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]를 사용 하 여 텍스트 컨트롤의 내용 내에서 각 문자열의 발생을 순차적으로 검색 하 고 강조 표시 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b6db8-105">This topic demonstrates how to sequentially search for and highlight each occurrence of a string within the content of a text control using [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)].</span></span>  
  
## <a name="example"></a><span data-ttu-id="b6db8-106">예제</span><span class="sxs-lookup"><span data-stu-id="b6db8-106">Example</span></span>  
 <span data-ttu-id="b6db8-107">다음 예제에서는 텍스트 컨트롤에서 <xref:System.Windows.Automation.TextPattern> 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b6db8-107">The following example obtains a <xref:System.Windows.Automation.TextPattern> object from a text control.</span></span> <span data-ttu-id="b6db8-108">그러면이 <xref:System.Windows.Automation.TextPattern>의 <xref:System.Windows.Automation.TextPattern.DocumentRange%2A> 속성을 사용 하 여 전체 문서의 텍스트 내용을 나타내는 <xref:System.Windows.Automation.Text.TextPatternRange> 개체가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="b6db8-108">A <xref:System.Windows.Automation.Text.TextPatternRange> object, representing the textual content of the entire document, is then created using the <xref:System.Windows.Automation.TextPattern.DocumentRange%2A> property of this <xref:System.Windows.Automation.TextPattern>.</span></span> <span data-ttu-id="b6db8-109">그런 다음 순차적 검색 및 강조 표시 기능을 위해 두 개의 추가 <xref:System.Windows.Automation.Text.TextPatternRange> 개체가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6db8-109">Two additional <xref:System.Windows.Automation.Text.TextPatternRange> objects are then created for the sequential search and highlight functionality.</span></span>  
  
[!code-csharp[FindText#StartApp](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#startapp)]
[!code-vb[FindText#StartApp](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#startapp)]  
[!code-csharp[FindText#FindTextProvider](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#findtextprovider)]
[!code-vb[FindText#FindTextProvider](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#findtextprovider)]  
[!code-csharp[FindText#SearchTarget](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#searchtarget)]
[!code-vb[FindText#SearchTarget](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#searchtarget)]  
  
## <a name="see-also"></a><span data-ttu-id="b6db8-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b6db8-110">See also</span></span>

- [<span data-ttu-id="b6db8-111">UI 자동화를 사용하여 텍스트 찾기 및 강조</span><span class="sxs-lookup"><span data-stu-id="b6db8-111">Find and Highlight Text Using UI Automation</span></span>](find-and-highlight-text-using-ui-automation.md)
