---
title: '방법: 탐색 기록을 뒤로 탐색'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- history [WPF], navigating back
- navigation [WPF], through navigation history (back)
ms.assetid: 9343234b-d864-441d-b8a7-d895cba80a87
ms.openlocfilehash: 86590c2794339ac22cbc8ec5e11224736133e870
ms.sourcegitcommit: 10736f243dd2296212e677e207102c463e5f143e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2019
ms.locfileid: "68817970"
---
# <a name="how-to-navigate-back-through-navigation-history"></a><span data-ttu-id="39e8c-102">방법: 탐색 기록을 뒤로 탐색</span><span class="sxs-lookup"><span data-stu-id="39e8c-102">How to: Navigate Back Through Navigation History</span></span>
<span data-ttu-id="39e8c-103">이 예제에서는 후방 탐색 기록에서 항목으로 이동 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="39e8c-103">This example illustrates how to navigate to entries in back navigation history.</span></span>  
  
## <a name="example"></a><span data-ttu-id="39e8c-104">예제</span><span class="sxs-lookup"><span data-stu-id="39e8c-104">Example</span></span>  
 <span data-ttu-id="39e8c-105">에서 호스트 <xref:System.Windows.Navigation.NavigationWindow> <xref:System.Windows.Controls.Frame> 되는 콘텐츠 (또는 Internet Explorer)에서 실행 되는 코드는 탐색 기록을 통해 다시 탐색할 수 있으며 한 번에 하나의 항목만 탐색할 수 있습니다. <xref:System.Windows.Navigation.NavigationService></span><span class="sxs-lookup"><span data-stu-id="39e8c-105">Code that is running from content that is hosted in a <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame> using <xref:System.Windows.Navigation.NavigationService>, or Internet Explorer can navigate back through navigation history, one entry at a time.</span></span>  
  
 <span data-ttu-id="39e8c-106">한 항목을 뒤로 이동 하려면 먼저 **CanGoBack** 속성을 검사 하 여 후방 탐색 기록에 항목이 있는지 확인 하 고, **GoBack** 메서드를 호출 하 여 한 항목 뒤로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="39e8c-106">Navigating back one entry requires first checking that there are entries in back navigation history, by inspecting the **CanGoBack** property, before navigating back one entry, by calling the **GoBack** method.</span></span> <span data-ttu-id="39e8c-107">이는 다음 예제에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39e8c-107">This is illustrated in the following example:</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 <span data-ttu-id="39e8c-108">**CanGoBack** 및 **GoBack** 은, <xref:System.Windows.Controls.Frame>및 <xref:System.Windows.Navigation.NavigationWindow> <xref:System.Windows.Navigation.NavigationService>에서 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39e8c-108">**CanGoBack** and **GoBack** are implemented by <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, and <xref:System.Windows.Navigation.NavigationService>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="39e8c-109">**GoBack**을 호출 하 고 후방 탐색 기록 <xref:System.InvalidOperationException> 에 항목이 없는 경우이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="39e8c-109">If you call **GoBack**, and there are no entries in back navigation history, an <xref:System.InvalidOperationException> is raised.</span></span>
