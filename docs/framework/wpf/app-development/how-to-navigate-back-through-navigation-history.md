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
ms.openlocfilehash: c489a1593b3d1f22fe1ad6e648d3f8a3f7a6cd44
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947786"
---
# <a name="how-to-navigate-back-through-navigation-history"></a><span data-ttu-id="b9e98-102">방법: 탐색 기록을 뒤로 탐색</span><span class="sxs-lookup"><span data-stu-id="b9e98-102">How to: Navigate Back Through Navigation History</span></span>
<span data-ttu-id="b9e98-103">이 예제에서는 탐색 기록에서 항목을 탐색 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b9e98-103">This example illustrates how to navigate to entries in back navigation history.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9e98-104">예제</span><span class="sxs-lookup"><span data-stu-id="b9e98-104">Example</span></span>  
 <span data-ttu-id="b9e98-105">호스트 되는 내용에서 실행 되는 코드를 <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame> 사용 하 여 <xref:System.Windows.Navigation.NavigationService>, 또는 [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)] 탐색 기록에서 한 번에 하나의 항목을 통해 다시 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9e98-105">Code that is running from content that is hosted in a <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame> using <xref:System.Windows.Navigation.NavigationService>, or [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)] can navigate back through navigation history, one entry at a time.</span></span>  
  
 <span data-ttu-id="b9e98-106">탐색 한 항목이 먼저 검사 하 여 후방 탐색 기록에 항목이 있는지를 확인 해야 합니다 **CanGoBack** 속성을 호출 하 여 하나의 항목을 다시 이동 하기 전에 **GoBack** 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="b9e98-106">Navigating back one entry requires first checking that there are entries in back navigation history, by inspecting the **CanGoBack** property, before navigating back one entry, by calling the **GoBack** method.</span></span> <span data-ttu-id="b9e98-107">이 다음 예제에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9e98-107">This is illustrated in the following example:</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 <span data-ttu-id="b9e98-108">**CanGoBack** 하 고 **GoBack** 하 여 구현 됩니다 <xref:System.Windows.Navigation.NavigationWindow>를 <xref:System.Windows.Controls.Frame>, 및 <xref:System.Windows.Navigation.NavigationService>합니다.</span><span class="sxs-lookup"><span data-stu-id="b9e98-108">**CanGoBack** and **GoBack** are implemented by <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, and <xref:System.Windows.Navigation.NavigationService>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b9e98-109">호출 하는 경우 **GoBack**, 후방 탐색 기록에 항목이 없음 및는 <xref:System.InvalidOperationException> 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9e98-109">If you call **GoBack**, and there are no entries in back navigation history, an <xref:System.InvalidOperationException> is raised.</span></span>
