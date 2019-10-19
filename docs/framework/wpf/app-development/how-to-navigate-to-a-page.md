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
# <a name="how-to-navigate-to-a-page"></a>방법: 페이지로 이동
이 예제에서는 <xref:System.Windows.Navigation.NavigationWindow>에서 페이지를 탐색할 수 있는 여러 가지 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 @No__t_0에서 다음 중 하나를 사용 하 여 페이지로 이동할 수 있습니다.  
  
- <xref:System.Windows.Navigation.NavigationWindow.Source%2A> 속성  
  
- <xref:System.Windows.Navigation.NavigationWindow.Navigate%2A> 메서드  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateToPageCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/MainWindow.xaml.cs#navigatetopagecode)]
 [!code-vb[HOWTONavigationSnippets#NavigateToPageCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/mainwindow.xaml.vb#navigatetopagecode)]  
  
> [!NOTE]
> Uri (Uniform resource identifier)는 상대 또는 절대 경로일 수 있습니다. 자세한 내용은 [WPF의 Pack URI](pack-uris-in-wpf.md)를 참조하세요.  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Controls.Frame>
- <xref:System.Windows.Controls.Page>
- <xref:System.Windows.Navigation.NavigationService>
