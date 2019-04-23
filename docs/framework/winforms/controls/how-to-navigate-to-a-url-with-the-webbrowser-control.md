---
title: '방법: WebBrowser 컨트롤을 사용하여 URL로 이동'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- WebBrowser.Navigate
helpviewer_keywords:
- WebBrowser control [Windows Forms], examples
- URLs [Windows Forms], navigating to
- WebBrowser control [Windows Forms], navigating to URLs
- examples [Windows Forms], WebBrowser control
ms.assetid: b3ec38cb-f509-4d0b-bd79-9f3611259c62
ms.openlocfilehash: a174b6ae60f87e91e6f97e8fa7f8ad3892ef017a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59132940"
---
# <a name="how-to-navigate-to-a-url-with-the-webbrowser-control"></a><span data-ttu-id="50193-102">방법: WebBrowser 컨트롤을 사용하여 URL로 이동</span><span class="sxs-lookup"><span data-stu-id="50193-102">How to: Navigate to a URL with the WebBrowser Control</span></span>
<span data-ttu-id="50193-103">다음 코드 예제를 탐색 하는 방법에 설명 합니다 <xref:System.Windows.Forms.WebBrowser> 특정 URL 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="50193-103">The following code example demonstrates how to navigate the <xref:System.Windows.Forms.WebBrowser> control to a specific URL.</span></span>  
  
 <span data-ttu-id="50193-104">새 문서를 완전히 로드 하는 경우를 확인 하려면 처리는 <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="50193-104">To determine when the new document is fully loaded, handle the <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> event.</span></span> <span data-ttu-id="50193-105">이 이벤트의 데모를 참조 하세요. [방법: WebBrowser 컨트롤을 사용 하 여 인쇄](how-to-print-with-a-webbrowser-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="50193-105">For a demonstration of this event, see [How to: Print with a WebBrowser Control](how-to-print-with-a-webbrowser-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="50193-106">예제</span><span class="sxs-lookup"><span data-stu-id="50193-106">Example</span></span>  
  
```vb  
Me.webBrowser1.Navigate("http://www.microsoft.com")  
```  
  
```csharp  
this.webBrowser1.Navigate("http://www.microsoft.com");  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="50193-107">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="50193-107">Compiling the Code</span></span>  
 <span data-ttu-id="50193-108">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="50193-108">This example requires:</span></span>  
  
-   <span data-ttu-id="50193-109">`webBrowser1`이라는 <xref:System.Windows.Forms.WebBrowser> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="50193-109">A <xref:System.Windows.Forms.WebBrowser> control named `webBrowser1`.</span></span>  
  
-   <span data-ttu-id="50193-110">`System` 및 `System.Windows.Forms` 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="50193-110">References to the `System` and `System.Windows.Forms` assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50193-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="50193-111">See also</span></span>

- <xref:System.Windows.Forms.WebBrowser>
- <xref:System.Windows.Forms.WebBrowser.DocumentCompleted?displayProperty=nameWithType>
- <xref:System.Windows.Forms.WebBrowser.Navigating?displayProperty=nameWithType>
- <xref:System.Windows.Forms.WebBrowser.Navigated?displayProperty=nameWithType>
- [<span data-ttu-id="50193-112">WebBrowser 컨트롤</span><span class="sxs-lookup"><span data-stu-id="50193-112">WebBrowser Control</span></span>](webbrowser-control-windows-forms.md)
- [<span data-ttu-id="50193-113">방법: WebBrowser 컨트롤을 사용 하 여 인쇄</span><span class="sxs-lookup"><span data-stu-id="50193-113">How to: Print with a WebBrowser Control</span></span>](how-to-print-with-a-webbrowser-control.md)
