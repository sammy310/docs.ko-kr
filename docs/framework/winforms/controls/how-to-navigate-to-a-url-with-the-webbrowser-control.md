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
ms.openlocfilehash: f6cb26ff247bba75cc351d453314bade2d38d9f5
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/28/2020
ms.locfileid: "84144840"
---
# <a name="how-to-navigate-to-a-url-with-the-webbrowser-control"></a><span data-ttu-id="2dd36-102">방법: WebBrowser 컨트롤을 사용하여 URL로 이동</span><span class="sxs-lookup"><span data-stu-id="2dd36-102">How to: Navigate to a URL with the WebBrowser Control</span></span>
<span data-ttu-id="2dd36-103">다음 코드 예제에서는 <xref:System.Windows.Forms.WebBrowser> 컨트롤을 특정 URL로 탐색 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2dd36-103">The following code example demonstrates how to navigate the <xref:System.Windows.Forms.WebBrowser> control to a specific URL.</span></span>

 <span data-ttu-id="2dd36-104">새 문서가 완전히 로드 되는 시기를 확인 하려면 이벤트를 처리 <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dd36-104">To determine when the new document is fully loaded, handle the <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> event.</span></span> <span data-ttu-id="2dd36-105">이 이벤트에 대 한 데모는 [방법: WebBrowser 컨트롤을 사용 하 여 인쇄](how-to-print-with-a-webbrowser-control.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2dd36-105">For a demonstration of this event, see [How to: Print with a WebBrowser Control](how-to-print-with-a-webbrowser-control.md).</span></span>

## <a name="example"></a><span data-ttu-id="2dd36-106">예제</span><span class="sxs-lookup"><span data-stu-id="2dd36-106">Example</span></span>

```vb
Me.webBrowser1.Navigate("https://www.microsoft.com")
```

```csharp
this.webBrowser1.Navigate("https://www.microsoft.com");
```

## <a name="compiling-the-code"></a><span data-ttu-id="2dd36-107">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="2dd36-107">Compiling the Code</span></span>
 <span data-ttu-id="2dd36-108">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2dd36-108">This example requires:</span></span>

- <span data-ttu-id="2dd36-109">`webBrowser1`이라는 <xref:System.Windows.Forms.WebBrowser> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="2dd36-109">A <xref:System.Windows.Forms.WebBrowser> control named `webBrowser1`.</span></span>

- <span data-ttu-id="2dd36-110">`System` 및 `System.Windows.Forms` 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="2dd36-110">References to the `System` and `System.Windows.Forms` assemblies.</span></span>

## <a name="see-also"></a><span data-ttu-id="2dd36-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2dd36-111">See also</span></span>

- <xref:System.Windows.Forms.WebBrowser>
- <xref:System.Windows.Forms.WebBrowser.DocumentCompleted?displayProperty=nameWithType>
- <xref:System.Windows.Forms.WebBrowser.Navigating?displayProperty=nameWithType>
- <xref:System.Windows.Forms.WebBrowser.Navigated?displayProperty=nameWithType>
- [<span data-ttu-id="2dd36-112">WebBrowser 컨트롤</span><span class="sxs-lookup"><span data-stu-id="2dd36-112">WebBrowser Control</span></span>](webbrowser-control-windows-forms.md)
- [<span data-ttu-id="2dd36-113">방법: WebBrowser 컨트롤을 사용하여 인쇄</span><span class="sxs-lookup"><span data-stu-id="2dd36-113">How to: Print with a WebBrowser Control</span></span>](how-to-print-with-a-webbrowser-control.md)
