---
title: '방법: 페이지로 이동'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pages [WPF], navigating to
- navigation [WPF], to page
ms.assetid: 2a556fc0-748b-417f-a58a-0d05a7afb66f
ms.openlocfilehash: 25a0dbbc609c7b6f8f2878d2068e61e492a59c7e
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582533"
---
# <a name="how-to-navigate-to-a-page"></a><span data-ttu-id="1d603-102">방법: 페이지로 이동</span><span class="sxs-lookup"><span data-stu-id="1d603-102">How to: Navigate to a Page</span></span>
<span data-ttu-id="1d603-103">이 예제에서는 <xref:System.Windows.Navigation.NavigationWindow>에서 페이지를 탐색할 수 있는 여러 가지 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1d603-103">This example illustrates several ways in which a page can be navigated to from a <xref:System.Windows.Navigation.NavigationWindow>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1d603-104">예제</span><span class="sxs-lookup"><span data-stu-id="1d603-104">Example</span></span>  
 <span data-ttu-id="1d603-105">@No__t_0에서 다음 중 하나를 사용 하 여 페이지로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d603-105">It is possible for a <xref:System.Windows.Navigation.NavigationWindow> to navigate to a page using one of the following:</span></span>  
  
- <span data-ttu-id="1d603-106"><xref:System.Windows.Navigation.NavigationWindow.Source%2A> 속성</span><span class="sxs-lookup"><span data-stu-id="1d603-106">The <xref:System.Windows.Navigation.NavigationWindow.Source%2A> property.</span></span>  
  
- <span data-ttu-id="1d603-107"><xref:System.Windows.Navigation.NavigationWindow.Navigate%2A> 메서드</span><span class="sxs-lookup"><span data-stu-id="1d603-107">The <xref:System.Windows.Navigation.NavigationWindow.Navigate%2A> method.</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateToPageCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/MainWindow.xaml.cs#navigatetopagecode)]
 [!code-vb[HOWTONavigationSnippets#NavigateToPageCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/mainwindow.xaml.vb#navigatetopagecode)]  
  
> [!NOTE]
> <span data-ttu-id="1d603-108">Uri (Uniform resource identifier)는 상대 또는 절대 경로일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d603-108">Uniform resource identifiers (URIs) can be either relative or absolute.</span></span> <span data-ttu-id="1d603-109">자세한 내용은 [WPF의 Pack URI](pack-uris-in-wpf.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d603-109">For more information, see [Pack URIs in WPF](pack-uris-in-wpf.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d603-110">참조</span><span class="sxs-lookup"><span data-stu-id="1d603-110">See also</span></span>

- <xref:System.Windows.Controls.Frame>
- <xref:System.Windows.Controls.Page>
- <xref:System.Windows.Navigation.NavigationService>
