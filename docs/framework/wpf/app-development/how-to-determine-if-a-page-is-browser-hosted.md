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
# <a name="how-to-determine-if-a-page-is-browser-hosted"></a><span data-ttu-id="303cc-102">방법: 페이지가 브라우저에서 호스트 되는지 확인</span><span class="sxs-lookup"><span data-stu-id="303cc-102">How to: Determine If a Page is Browser Hosted</span></span>
<span data-ttu-id="303cc-103">이 예제에서는 <xref:System.Windows.Controls.Page> 브라우저에서 호스트 되는지 확인 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="303cc-103">This example demonstrates how to determine if a <xref:System.Windows.Controls.Page> is hosted in a browser.</span></span>  
  
## <a name="example"></a><span data-ttu-id="303cc-104">예제</span><span class="sxs-lookup"><span data-stu-id="303cc-104">Example</span></span>  
 <span data-ttu-id="303cc-105"><xref:System.Windows.Controls.Page>은 호스트를 독립적으로 만들 수 있으며, 따라서 <xref:System.Windows.Controls.Frame>, <xref:System.Windows.Navigation.NavigationWindow>또는 브라우저를 비롯 한 여러 가지 유형의 호스트로 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="303cc-105">A <xref:System.Windows.Controls.Page> can be host agnostic and, consequently, can be loaded into several different types of hosts, including a <xref:System.Windows.Controls.Frame>, a <xref:System.Windows.Navigation.NavigationWindow>, or a browser.</span></span> <span data-ttu-id="303cc-106">이 문제는 하나 이상의 페이지를 포함 하는 라이브러리 어셈블리와 여러 독립 실행형 및 탐색 가능 (XBAP (XAML 브라우저 응용 프로그램) 호스트 응용 프로그램에서 참조 되는 경우에 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="303cc-106">This can happen when you have a library assembly that contains one or more pages, and which is referenced by multiple standalone and browsable (XAML browser application (XBAP)) host applications.</span></span>  
  
 <span data-ttu-id="303cc-107">다음 예제에서는 <xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A?displayProperty=nameWithType>를 사용 하 여 <xref:System.Windows.Controls.Page> 브라우저에서 호스트 되는지 확인 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="303cc-107">The following example demonstrates how to use <xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A?displayProperty=nameWithType> to determine if a <xref:System.Windows.Controls.Page> is hosted in a browser.</span></span>  
  
 [!code-csharp[HOWTOBrowserInteropHelperSnippets#IsBrowserHostedCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOBrowserInteropHelperSnippets/CSharp/Page1.xaml.cs#isbrowserhostedcode)]
 [!code-vb[HOWTOBrowserInteropHelperSnippets#IsBrowserHostedCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOBrowserInteropHelperSnippets/visualbasic/page1.xaml.vb#isbrowserhostedcode)]  
  
## <a name="see-also"></a><span data-ttu-id="303cc-108">참조</span><span class="sxs-lookup"><span data-stu-id="303cc-108">See also</span></span>

- <xref:System.Windows.Controls.Frame>
- <xref:System.Windows.Controls.Page>
