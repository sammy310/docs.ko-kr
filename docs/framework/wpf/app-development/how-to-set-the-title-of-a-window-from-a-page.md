---
title: '방법: 페이지에서 창 제목 설정'
ms.date: 03/30/2017
helpviewer_keywords:
- windows [WPF], setting title from a page
- title of window [WPF], setting from a page
- pages [WPF], setting window title from
ms.assetid: fecf0d19-3eb6-4f8c-a44f-ff1b6f2b34b3
ms.openlocfilehash: 55444de6c61107979307b94910ba944e7001cf9e
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57357510"
---
# <a name="how-to-set-the-title-of-a-window-from-a-page"></a><span data-ttu-id="151c7-102">방법: 페이지에서 창 제목 설정</span><span class="sxs-lookup"><span data-stu-id="151c7-102">How to: Set the Title of a Window from a Page</span></span>
<span data-ttu-id="151c7-103">창의 제목을 설정 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.Page> 호스팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="151c7-103">This example shows how to set the title of the window in which a <xref:System.Windows.Controls.Page> is hosted.</span></span>  
  
## <a name="example"></a><span data-ttu-id="151c7-104">예제</span><span class="sxs-lookup"><span data-stu-id="151c7-104">Example</span></span>  
 <span data-ttu-id="151c7-105">페이지를 설정 하 여 호스팅하는 창의 제목을 변경할 수는 <xref:System.Windows.Controls.Page.WindowTitle%2A> 속성을 다음과 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="151c7-105">A page can change the title of the window that is hosting it by setting the <xref:System.Windows.Controls.Page.WindowTitle%2A> property, like so:</span></span>  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowTitleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowTitlePage.xaml#setpagewindowtitlexaml)]  
  
> [!NOTE]
>  <span data-ttu-id="151c7-106">설정 된 <xref:System.Windows.Controls.Page.Title%2A> 페이지의 속성 창 제목의 값을 변경 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="151c7-106">Setting the <xref:System.Windows.Controls.Page.Title%2A> property of a page does not change the value of the window title.</span></span> <span data-ttu-id="151c7-107">대신 <xref:System.Windows.Controls.Page.Title%2A> 탐색 기록에서 페이지 항목의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="151c7-107">Instead, <xref:System.Windows.Controls.Page.Title%2A> specifies the name of a page entry in navigation history.</span></span>
