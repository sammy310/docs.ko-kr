---
title: '방법: 탐색 기록을 앞으로 또는 뒤로 탐색'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- history [WPF], navigating forward
- navigation [WPF], through navigation history (forward)
ms.assetid: 5939d574-5f53-469e-85f5-1f2b13607caa
ms.openlocfilehash: 4c20ebfab45a24cf34b1476fb94dae6913fb4d99
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947760"
---
# <a name="how-to-navigate-forward-or-back-through-navigation-history"></a><span data-ttu-id="8c69c-102">방법: 탐색 기록을 앞으로 또는 뒤로 탐색</span><span class="sxs-lookup"><span data-stu-id="8c69c-102">How to: Navigate Forward or Back Through Navigation History</span></span>
<span data-ttu-id="8c69c-103">이 예제에서는 앞으로 또는 뒤로 탐색 기록에 항목을 탐색 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8c69c-103">This example illustrates how to navigate forward or back to entries in navigation history.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c69c-104">예제</span><span class="sxs-lookup"><span data-stu-id="8c69c-104">Example</span></span>  
 <span data-ttu-id="8c69c-105">콘텐츠에서 다음 호스트에서 실행 되는 코드 탐색 기록에서 한 번에 하나의 항목을 통해 앞뒤로 이동 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c69c-105">Code that runs from content in the following hosts can navigate forward or back through navigation history, one entry at a time.</span></span>  
  
- <span data-ttu-id="8c69c-106"><xref:System.Windows.Navigation.NavigationWindow> 사용 하 여 <xref:System.Windows.Navigation.NavigationService></span><span class="sxs-lookup"><span data-stu-id="8c69c-106"><xref:System.Windows.Navigation.NavigationWindow> using <xref:System.Windows.Navigation.NavigationService></span></span>  
  
- <span data-ttu-id="8c69c-107"><xref:System.Windows.Controls.Frame> 사용 하 여 <xref:System.Windows.Navigation.NavigationService></span><span class="sxs-lookup"><span data-stu-id="8c69c-107"><xref:System.Windows.Controls.Frame> using <xref:System.Windows.Navigation.NavigationService></span></span>  
  
- [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)]  
  
 <span data-ttu-id="8c69c-108">한 항목 앞으로 탐색할 수 있습니다, 전에 먼저 체크 해야 검사 하 여 전방 탐색 기록에 항목이 있는지 합니다 **CanGoForward** 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="8c69c-108">Before you can navigate forward one entry, you must first check that there are entries in forward navigation history by inspecting the **CanGoForward** property.</span></span> <span data-ttu-id="8c69c-109">한 항목 앞으로 탐색 하려면 호출을 **GoForward** 메서드.</span><span class="sxs-lookup"><span data-stu-id="8c69c-109">To navigate forward one entry, you call the **GoForward** method.</span></span> <span data-ttu-id="8c69c-110">이 다음 예제에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c69c-110">This is illustrated in the following example:</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateForwardCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigateforwardcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateForwardCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigateforwardcode)]  
  
 <span data-ttu-id="8c69c-111">탐색 하려면 하나의 항목을 다시, 검사 하 여 후방 탐색 기록에 항목이 있는지를 먼저 확인 해야 합니다 **CanGoBack** 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="8c69c-111">Before you can navigate back one entry, you must first check that there are entries in back navigation history by inspecting the **CanGoBack** property.</span></span> <span data-ttu-id="8c69c-112">한 항목 뒤로 탐색 하려면 호출을 **GoBack** 메서드.</span><span class="sxs-lookup"><span data-stu-id="8c69c-112">To navigate back one entry, you call the **GoBack** method.</span></span> <span data-ttu-id="8c69c-113">이 다음 예제에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c69c-113">This is illustrated in the following example:</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 <span data-ttu-id="8c69c-114">**CanGoForward**, **GoForward**를 **CanGoBack**, 및 **GoBack** 하 여 구현 됩니다 <xref:System.Windows.Navigation.NavigationWindow>를 <xref:System.Windows.Controls.Frame>, 및 <xref:System.Windows.Navigation.NavigationService>합니다.</span><span class="sxs-lookup"><span data-stu-id="8c69c-114">**CanGoForward**, **GoForward**, **CanGoBack**, and **GoBack** are implemented by <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, and <xref:System.Windows.Navigation.NavigationService>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8c69c-115">호출 하는 경우 **GoForward**, 전방 탐색 기록에 항목이 없음 및 호출 하는 경우 또는 **GoBack**, 후방 탐색 기록에 항목이 없음 및는 <xref:System.InvalidOperationException> throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c69c-115">If you call **GoForward**, and there are no entries in forward navigation history, or if you call **GoBack**, and there are no entries in back navigation history, an <xref:System.InvalidOperationException> is thrown.</span></span>
