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
ms.openlocfilehash: a5a0e7a8e7effac7c51f4dee92d30de56d60d90c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57369342"
---
# <a name="how-to-navigate-to-a-page"></a>방법: 페이지로 이동
이 예제는 페이지를 탐색할 수 있습니다에서 여러 가지 방법으로 <xref:System.Windows.Navigation.NavigationWindow>합니다.  
  
## <a name="example"></a>예제  
 있기를 <xref:System.Windows.Navigation.NavigationWindow> 다음 중 하나를 사용 하는 페이지로 이동 합니다.  
  
-   <xref:System.Windows.Navigation.NavigationWindow.Source%2A> 속성  
  
-   <xref:System.Windows.Navigation.NavigationWindow.Navigate%2A> 메서드  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateToPageCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/MainWindow.xaml.cs#navigatetopagecode)]
 [!code-vb[HOWTONavigationSnippets#NavigateToPageCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/mainwindow.xaml.vb#navigatetopagecode)]  
  
> [!NOTE]
>  [!INCLUDE[TLA#tla_uri#initcap#plural](../../../../includes/tlasharptla-urisharpinitcapsharpplural-md.md)] 상대 또는 절대 수 있습니다. 자세한 내용은 [WPF의 Pack URI](pack-uris-in-wpf.md)를 참조하세요.  
  
## <a name="see-also"></a>참고자료
- <xref:System.Windows.Controls.Frame>
- <xref:System.Windows.Controls.Page>
- <xref:System.Windows.Navigation.NavigationService>
