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
ms.openlocfilehash: 76a78debdce14123cc465ac9abf4db906fe0a2df
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69961347"
---
# <a name="how-to-navigate-forward-or-back-through-navigation-history"></a><span data-ttu-id="f63fe-102">방법: 탐색 기록을 앞으로 또는 뒤로 탐색</span><span class="sxs-lookup"><span data-stu-id="f63fe-102">How to: Navigate Forward or Back Through Navigation History</span></span>
<span data-ttu-id="f63fe-103">이 예제에서는 탐색 기록에서 항목으로 앞으로 또는 뒤로 이동 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f63fe-103">This example illustrates how to navigate forward or back to entries in navigation history.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f63fe-104">예제</span><span class="sxs-lookup"><span data-stu-id="f63fe-104">Example</span></span>  
 <span data-ttu-id="f63fe-105">다음 호스트의 콘텐츠에서 실행 되는 코드는 탐색 기록을 앞뒤로 탐색할 수 있으며 한 번에 한 항목만 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f63fe-105">Code that runs from content in the following hosts can navigate forward or back through navigation history, one entry at a time.</span></span>  
  
- <span data-ttu-id="f63fe-106"><xref:System.Windows.Navigation.NavigationWindow>사용 하 여<xref:System.Windows.Navigation.NavigationService></span><span class="sxs-lookup"><span data-stu-id="f63fe-106"><xref:System.Windows.Navigation.NavigationWindow> using <xref:System.Windows.Navigation.NavigationService></span></span>  
  
- <span data-ttu-id="f63fe-107"><xref:System.Windows.Controls.Frame>사용 하 여<xref:System.Windows.Navigation.NavigationService></span><span class="sxs-lookup"><span data-stu-id="f63fe-107"><xref:System.Windows.Controls.Frame> using <xref:System.Windows.Navigation.NavigationService></span></span>  
  
- <span data-ttu-id="f63fe-108">Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="f63fe-108">Internet Explorer</span></span>  
  
 <span data-ttu-id="f63fe-109">한 항목 앞으로 이동 하려면 먼저 **CanGoForward** 속성을 검사 하 여 전방 탐색 기록에 항목이 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f63fe-109">Before you can navigate forward one entry, you must first check that there are entries in forward navigation history by inspecting the **CanGoForward** property.</span></span> <span data-ttu-id="f63fe-110">한 항목 앞으로 이동 하려면 **Goforward** 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="f63fe-110">To navigate forward one entry, you call the **GoForward** method.</span></span> <span data-ttu-id="f63fe-111">이는 다음 예제에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f63fe-111">This is illustrated in the following example:</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateForwardCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigateforwardcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateForwardCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigateforwardcode)]  
  
 <span data-ttu-id="f63fe-112">한 항목 뒤로 이동 하려면 먼저 **CanGoBack** 속성을 검사 하 여 후방 탐색 기록에 항목이 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f63fe-112">Before you can navigate back one entry, you must first check that there are entries in back navigation history by inspecting the **CanGoBack** property.</span></span> <span data-ttu-id="f63fe-113">한 항목 뒤로 이동 하려면 **GoBack** 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="f63fe-113">To navigate back one entry, you call the **GoBack** method.</span></span> <span data-ttu-id="f63fe-114">이는 다음 예제에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f63fe-114">This is illustrated in the following example:</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 <span data-ttu-id="f63fe-115">**CanGoForward**, **goforward**, **CanGoBack**및 **GoBack** 은, <xref:System.Windows.Navigation.NavigationWindow> <xref:System.Windows.Controls.Frame>및 <xref:System.Windows.Navigation.NavigationService>에서 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f63fe-115">**CanGoForward**, **GoForward**, **CanGoBack**, and **GoBack** are implemented by <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, and <xref:System.Windows.Navigation.NavigationService>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f63fe-116">**Goforward**를 호출 하 고 전방 탐색 기록에 항목이 없거나, **GoBack**을 호출 하 고 후방 탐색 <xref:System.InvalidOperationException> 기록에 항목이 없는 경우이 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f63fe-116">If you call **GoForward**, and there are no entries in forward navigation history, or if you call **GoBack**, and there are no entries in back navigation history, an <xref:System.InvalidOperationException> is thrown.</span></span>
