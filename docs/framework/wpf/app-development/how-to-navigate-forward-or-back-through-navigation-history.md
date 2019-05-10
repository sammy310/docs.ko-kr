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
ms.openlocfilehash: 00a41fcf85583ec0d081a2fa099f3a77cfcd2900
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64625361"
---
# <a name="how-to-navigate-forward-or-back-through-navigation-history"></a>방법: 탐색 기록을 앞으로 또는 뒤로 탐색
이 예제에서는 앞으로 또는 뒤로 탐색 기록에 항목을 탐색 하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 콘텐츠에서 다음 호스트에서 실행 되는 코드 탐색 기록에서 한 번에 하나의 항목을 통해 앞뒤로 이동 수 있습니다.  
  
- <xref:System.Windows.Navigation.NavigationWindow> 사용 하 여 <xref:System.Windows.Navigation.NavigationService>  
  
- <xref:System.Windows.Controls.Frame> 사용 하 여 <xref:System.Windows.Navigation.NavigationService>  
  
- [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)]  
  
 한 항목 앞으로 탐색할 수 있습니다, 전에 먼저 체크 해야 검사 하 여 전방 탐색 기록에 항목이 있는지 합니다 **CanGoForward** 속성입니다. 한 항목 앞으로 탐색 하려면 호출을 **GoForward** 메서드. 이 다음 예제에 나와 있습니다.  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateForwardCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigateforwardcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateForwardCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigateforwardcode)]  
  
 탐색 하려면 하나의 항목을 다시, 검사 하 여 후방 탐색 기록에 항목이 있는지를 먼저 확인 해야 합니다 **CanGoBack** 속성입니다. 한 항목 뒤로 탐색 하려면 호출을 **GoBack** 메서드. 이 다음 예제에 나와 있습니다.  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 **CanGoForward**, **GoForward**를 **CanGoBack**, 및 **GoBack** 하 여 구현 됩니다 <xref:System.Windows.Navigation.NavigationWindow>를 <xref:System.Windows.Controls.Frame>, 및 <xref:System.Windows.Navigation.NavigationService>합니다.  
  
> [!NOTE]
>  호출 하는 경우 **GoForward**, 전방 탐색 기록에 항목이 없음 및 호출 하는 경우 또는 **GoBack**, 후방 탐색 기록에 항목이 없음 및는 <xref:System.InvalidOperationException> throw 됩니다.
