---
title: 목록 항목의 UI 자동화 요소 찾기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- list items, finding elements for
- elements, finding for list items
- UI Automation, finding elements for List items
ms.assetid: c326ad2b-2144-4f64-ae4c-d850c74f95c5
ms.openlocfilehash: 2474edf95bf598ba9284b5f6ac36a9e0af1317a1
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "75741759"
---
# <a name="find-a-ui-automation-element-for-a-list-item"></a><span data-ttu-id="1ae0a-102">목록 항목의 UI 자동화 요소 찾기</span><span class="sxs-lookup"><span data-stu-id="1ae0a-102">Find a UI Automation Element for a List Item</span></span>
> [!NOTE]
> <span data-ttu-id="1ae0a-103">이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1ae0a-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="1ae0a-104">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](/windows/win32/winauto/entry-uiauto-win32)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1ae0a-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="1ae0a-105">이 항목에서는 항목의 인덱스를 알고 있을 때 목록 내의 항목에 대 한 <xref:System.Windows.Automation.AutomationElement>를 검색 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1ae0a-105">This topic shows how to retrieve an <xref:System.Windows.Automation.AutomationElement> for an item within a list when the index of the item is known.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1ae0a-106">예</span><span class="sxs-lookup"><span data-stu-id="1ae0a-106">Example</span></span>  
 <span data-ttu-id="1ae0a-107">다음 예에서는 <xref:System.Windows.Automation.TreeWalker>를 사용 하 고 다른 <xref:System.Windows.Automation.AutomationElement.FindAll%2A>를 사용 하 여 목록에서 지정 된 항목을 검색 하는 두 가지 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1ae0a-107">The following example shows two ways of retrieving a specified item from a list, one using <xref:System.Windows.Automation.TreeWalker> and the other using <xref:System.Windows.Automation.AutomationElement.FindAll%2A>.</span></span>  
  
 <span data-ttu-id="1ae0a-108">첫 번째 기술은 Win32 컨트롤에서 속도가 더 빠르지만 WPF (Windows Presentation Foundation) 컨트롤의 경우 더 빠릅니다.</span><span class="sxs-lookup"><span data-stu-id="1ae0a-108">The first technique tends to be faster for Win32 controls, but the second is faster for Windows Presentation Foundation (WPF) controls.</span></span>  
  
 [!code-csharp[UIAClient_snip#184](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#184)]
 [!code-vb[UIAClient_snip#184](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#184)]  
  
## <a name="see-also"></a><span data-ttu-id="1ae0a-109">참조</span><span class="sxs-lookup"><span data-stu-id="1ae0a-109">See also</span></span>

- [<span data-ttu-id="1ae0a-110">UI 자동화 요소 가져오기</span><span class="sxs-lookup"><span data-stu-id="1ae0a-110">Obtaining UI Automation Elements</span></span>](obtaining-ui-automation-elements.md)
