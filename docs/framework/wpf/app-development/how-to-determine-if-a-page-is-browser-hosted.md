---
title: '방법: 페이지가 브라우저에서 호스트 되는지 확인'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosted pages in browser [WPF]
- pages [WPF], hosted in browser
ms.assetid: 737e0f26-8371-49b4-9579-70879e51e1aa
ms.openlocfilehash: c4cb1065807d16c1d1f5a95c8ac9c9cbe5a0fdab
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424699"
---
# <a name="how-to-determine-if-a-page-is-browser-hosted"></a>방법: 페이지가 브라우저에서 호스트 되는지 확인
이 예제에서는 <xref:System.Windows.Controls.Page> 브라우저에서 호스트 되는지 확인 하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 <xref:System.Windows.Controls.Page>은 호스트를 독립적으로 만들 수 있으며, 따라서 <xref:System.Windows.Controls.Frame>, <xref:System.Windows.Navigation.NavigationWindow>또는 브라우저를 비롯 한 여러 가지 유형의 호스트로 로드할 수 있습니다. 이 문제는 하나 이상의 페이지를 포함 하는 라이브러리 어셈블리와 여러 독립 실행형 및 탐색 가능 (XBAP (XAML 브라우저 응용 프로그램) 호스트 응용 프로그램에서 참조 되는 경우에 발생할 수 있습니다.  
  
 다음 예제에서는 <xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A?displayProperty=nameWithType>를 사용 하 여 <xref:System.Windows.Controls.Page> 브라우저에서 호스트 되는지 확인 하는 방법을 보여 줍니다.  
  
 [!code-csharp[HOWTOBrowserInteropHelperSnippets#IsBrowserHostedCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOBrowserInteropHelperSnippets/CSharp/Page1.xaml.cs#isbrowserhostedcode)]
 [!code-vb[HOWTOBrowserInteropHelperSnippets#IsBrowserHostedCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOBrowserInteropHelperSnippets/visualbasic/page1.xaml.vb#isbrowserhostedcode)]  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Controls.Frame>
- <xref:System.Windows.Controls.Page>
