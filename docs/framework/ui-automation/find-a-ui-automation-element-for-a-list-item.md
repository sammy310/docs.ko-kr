---
title: 목록 항목의 UI 자동화 요소 찾기
description: 항목의 인덱스를 알 수 있는 경우 목록 항목의 UI 자동화 요소를 찾는 방법을 보여 주는 예제를 참조 하세요.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- list items, finding elements for
- elements, finding for list items
- UI Automation, finding elements for List items
ms.assetid: c326ad2b-2144-4f64-ae4c-d850c74f95c5
ms.openlocfilehash: ec6464bc0ec504fd34ed113c9bed1a54a7d4eaec
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168413"
---
# <a name="find-a-ui-automation-element-for-a-list-item"></a><span data-ttu-id="014a2-103">목록 항목의 UI 자동화 요소 찾기</span><span class="sxs-lookup"><span data-stu-id="014a2-103">Find a UI Automation Element for a List Item</span></span>
> [!NOTE]
> <span data-ttu-id="014a2-104">이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="014a2-104">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="014a2-105">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](/windows/win32/winauto/entry-uiauto-win32)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="014a2-105">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="014a2-106">이 항목에서는 <xref:System.Windows.Automation.AutomationElement> 항목의 인덱스를 알고 있을 때 목록 내의 항목에 대 한를 검색 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="014a2-106">This topic shows how to retrieve an <xref:System.Windows.Automation.AutomationElement> for an item within a list when the index of the item is known.</span></span>  
  
## <a name="example"></a><span data-ttu-id="014a2-107">예제</span><span class="sxs-lookup"><span data-stu-id="014a2-107">Example</span></span>  
 <span data-ttu-id="014a2-108">다음 예제에서는 목록에서 지정 된 항목을 검색 하는 두 가지 방법, 즉를 사용 하는 방법과를 사용 하는 방법을 보여 줍니다 <xref:System.Windows.Automation.TreeWalker> <xref:System.Windows.Automation.AutomationElement.FindAll%2A> .</span><span class="sxs-lookup"><span data-stu-id="014a2-108">The following example shows two ways of retrieving a specified item from a list, one using <xref:System.Windows.Automation.TreeWalker> and the other using <xref:System.Windows.Automation.AutomationElement.FindAll%2A>.</span></span>  
  
 <span data-ttu-id="014a2-109">첫 번째 기술은 Win32 컨트롤에서 속도가 더 빠르지만 WPF (Windows Presentation Foundation) 컨트롤의 경우 더 빠릅니다.</span><span class="sxs-lookup"><span data-stu-id="014a2-109">The first technique tends to be faster for Win32 controls, but the second is faster for Windows Presentation Foundation (WPF) controls.</span></span>  
  
 [!code-csharp[UIAClient_snip#184](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#184)]
 [!code-vb[UIAClient_snip#184](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#184)]  
  
## <a name="see-also"></a><span data-ttu-id="014a2-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="014a2-110">See also</span></span>

- [<span data-ttu-id="014a2-111">UI 자동화 요소 가져오기</span><span class="sxs-lookup"><span data-stu-id="014a2-111">Obtaining UI Automation Elements</span></span>](obtaining-ui-automation-elements.md)
