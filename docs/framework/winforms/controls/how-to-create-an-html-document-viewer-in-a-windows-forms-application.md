---
title: Windows Forms 앱에서 HTML 문서 뷰어 만들기
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WebBrowser control [Windows Forms], creating an HTML document viewer
- document viewers
- Windows Forms, creating document viewers
ms.assetid: 6a6338fe-f7ee-4f5e-9d8f-0465c57e9039
ms.openlocfilehash: 913bc86af034645b4b8cf3d69da4c9def58fc19c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732838"
---
# <a name="how-to-create-an-html-document-viewer-in-a-windows-forms-application"></a>방법: Windows Forms 애플리케이션에서 HTML 문서 뷰어 만들기
인터넷 웹 브라우저의 전체 기능을 제공 하지 않고 <xref:System.Windows.Forms.WebBrowser> 컨트롤을 사용 하 여 HTML 문서를 표시 하 고 인쇄할 수 있습니다. HTML의 서식 지정 기능을 활용 하려고 하지만 신뢰할 수 없는 웹 컨트롤이 나 잠재적으로 악의적인 스크립트 코드를 포함할 수 있는 임의의 웹 페이지를 사용자가 로드 하지 않으려는 경우에 유용 합니다. 예를 들어, HTML 전자 메일 뷰어로 사용 하거나 응용 프로그램에서 HTML 형식의 도움말을 제공 하는 등의 방법으로 <xref:System.Windows.Forms.WebBrowser> 컨트롤의 기능을 제한 하는 것이 좋습니다.  
  
### <a name="to-create-an-html-document-viewer"></a>HTML 문서 뷰어를 만들려면  
  
1. <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A> 속성을 `false`으로 설정 하 여 <xref:System.Windows.Forms.WebBrowser> 컨트롤이 끌어 놓은 파일을 열 수 없도록 합니다.  
  
     [!code-csharp[WebBrowserMisc#20](~/samples/snippets/csharp/VS_Snippets_Winforms/WebBrowserMisc/CS/WebBrowserMisc.cs#20)]
     [!code-vb[WebBrowserMisc#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WebBrowserMisc/vb/WebBrowserMisc.vb#20)]  
  
2. <xref:System.Windows.Forms.WebBrowser.Url%2A> 속성을 표시할 초기 파일의 위치로 설정 합니다.  
  
     [!code-csharp[WebBrowserMisc#21](~/samples/snippets/csharp/VS_Snippets_Winforms/WebBrowserMisc/CS/WebBrowserMisc.cs#21)]
     [!code-vb[WebBrowserMisc#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WebBrowserMisc/vb/WebBrowserMisc.vb#21)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
- `webBrowser1`이라는 <xref:System.Windows.Forms.WebBrowser> 컨트롤  
  
- `System` 및 `System.Windows.Forms` 어셈블리에 대한 참조  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.WebBrowser>
- <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A>
- <xref:System.Windows.Forms.WebBrowser.Url%2A>
- [WebBrowser 컨트롤 개요](webbrowser-control-overview.md)
- [WebBrowser 보안](webbrowser-security.md)
- [방법: WebBrowser 컨트롤을 사용하여 URL 탐색](how-to-navigate-to-a-url-with-the-webbrowser-control.md)
- [방법: WebBrowser 컨트롤을 사용하여 인쇄](how-to-print-with-a-webbrowser-control.md)
