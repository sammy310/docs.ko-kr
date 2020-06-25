---
title: WebBrowser 컨트롤 개요
description: WebBrowser 컨트롤을 사용 하 여 단일 응용 프로그램에서 웹 컨트롤과 Windows Forms 컨트롤을 원활 하 게 결합 하는 방법을 알아봅니다.
ms.date: 03/30/2017
f1_keywords:
- WebBrowser
helpviewer_keywords:
- WebBrowser control [Windows Forms], about
- Web pages [Windows Forms], displaying in applications
ms.assetid: 6e3e1cc2-9c48-4136-9659-e99e4e60b7e9
ms.openlocfilehash: 6a0548bb0f5905d8f848ab13fb82d32b50caa891
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325742"
---
# <a name="webbrowser-control-overview"></a>WebBrowser 컨트롤 개요
<xref:System.Windows.Forms.WebBrowser>컨트롤은 WebBrowser ActiveX 컨트롤에 대 한 관리 되는 래퍼를 제공 합니다. 관리 되는 래퍼를 사용 하면 Windows Forms 클라이언트 응용 프로그램에서 웹 페이지를 표시할 수 있습니다. 이 컨트롤을 사용 하 여 <xref:System.Windows.Forms.WebBrowser> 응용 프로그램에서 Internet Explorer 웹 검색 기능을 복제 하거나 기본 Internet explorer 기능을 사용 하지 않도록 설정 하 고 컨트롤을 간단한 HTML 문서 뷰어로 사용할 수 있습니다. 컨트롤을 사용 하 여 DHTML 기반 사용자 인터페이스 요소를 폼에 추가 하 고 컨트롤에 호스트 되는 사실을 숨길 수도 있습니다 <xref:System.Windows.Forms.WebBrowser> . 이 방법을 사용 하면 단일 응용 프로그램에서 웹 컨트롤을 Windows Forms 컨트롤과 원활 하 게 결합할 수 있습니다.  
  
## <a name="frequently-used-properties-methods-and-events"></a>자주 사용 되는 속성, 메서드 및 이벤트  
 컨트롤에는 <xref:System.Windows.Forms.WebBrowser> Internet Explorer에 있는 컨트롤을 구현 하는 데 사용할 수 있는 여러 속성, 메서드 및 이벤트가 있습니다. 예를 들어, 메서드를 사용 하 여 `Navigate` 주소 표시줄을 구현 하 고,, 및 메서드를 사용 하 여 `GoBack` `GoForward` `Stop` `Refresh` 도구 모음에 탐색 단추를 구현할 수 있습니다. 이벤트를 처리 `Navigated` 하 여 속성 값을 사용 하 여 주소 표시줄을 업데이트 하 `Url` 고 속성 값을 사용 하 여 제목 표시줄을 업데이트할 수 있습니다 `DocumentTitle` .  
  
 응용 프로그램 내에서 고유한 페이지 콘텐츠를 생성 하려는 경우 속성을 설정할 수 있습니다 `DocumentText` . HTML DOM (문서 개체 모델)에 대해 잘 알고 있으면 속성을 통해 현재 웹 페이지의 내용을 조작할 수도 있습니다 `Document` . 이 속성을 사용 하면 파일 간에 이동 하는 대신 메모리에 문서를 저장 하 고 수정할 수 있습니다.  
  
 `Document`속성을 사용 하면 클라이언트 응용 프로그램 코드에서 웹 페이지 스크립팅 코드에 구현 된 메서드를 호출할 수도 있습니다. 스크립팅 코드에서 클라이언트 응용 프로그램 코드에 액세스 하려면 속성을 설정 `ObjectForScripting` 합니다. 사용자가 지정 하는 개체는 스크립트 코드에서 개체로 액세스할 수 있습니다 `window.external` .  
  
|이름|설명|  
|----------|-----------------|  
|<xref:System.Windows.Forms.WebBrowser.Document%2A> 속성|현재 웹 페이지의 HTML DOM (문서 개체 모델)에 대 한 관리 되는 액세스를 제공 하는 개체를 가져옵니다.|  
|<xref:System.Windows.Forms.WebBrowser.DocumentCompleted> 이벤트|웹 페이지의 로드가 완료 될 때 발생 합니다.|  
|<xref:System.Windows.Forms.WebBrowser.DocumentText%2A> 속성|현재 웹 페이지의 HTML 콘텐츠를 가져오거나 설정 합니다.|  
|<xref:System.Windows.Forms.WebBrowser.DocumentTitle%2A> 속성|현재 웹 페이지의 제목을 가져옵니다.|  
|<xref:System.Windows.Forms.WebBrowser.GoBack%2A> 메서드|기록의 이전 페이지로 이동 합니다.|  
|<xref:System.Windows.Forms.WebBrowser.GoForward%2A> 메서드|기록의 다음 페이지로 이동 합니다.|  
|<xref:System.Windows.Forms.WebBrowser.Navigate%2A> 메서드|지정 된 URL로 이동 합니다.|  
|<xref:System.Windows.Forms.WebBrowser.Navigating> 이벤트|작업을 취소할 수 있도록 탐색이 시작 되기 전에 발생 합니다.|  
|<xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A> 속성|웹 페이지 스크립팅 코드에서 응용 프로그램과 통신 하는 데 사용할 수 있는 개체를 가져오거나 설정 합니다.|  
|<xref:System.Windows.Forms.WebBrowser.Print%2A> 메서드|현재 웹 페이지를 인쇄 합니다.|  
|<xref:System.Windows.Forms.WebBrowser.Refresh%2A> 메서드|현재 웹 페이지를 다시 로드 합니다.|  
|<xref:System.Windows.Forms.WebBrowser.Stop%2A> 메서드|현재 탐색을 중단 하 고 소리 및 애니메이션과 같은 동적 페이지 요소를 중지 합니다.|  
|<xref:System.Windows.Forms.WebBrowser.Url%2A> 속성|현재 웹 페이지의 URL을 가져오거나 설정 합니다. 이 속성을 설정 하면 컨트롤이 새 URL로 이동 합니다.|  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.WebBrowser>
- <xref:System.Windows.Forms.WebBrowserDocumentCompletedEventArgs>
- <xref:System.Windows.Forms.WebBrowserDocumentCompletedEventHandler>
- <xref:System.Windows.Forms.WebBrowserEncryptionLevel>
- <xref:System.Windows.Forms.WebBrowserNavigatedEventArgs>
- <xref:System.Windows.Forms.WebBrowserNavigatedEventHandler>
- <xref:System.Windows.Forms.WebBrowserNavigatingEventArgs>
- <xref:System.Windows.Forms.WebBrowserNavigatingEventHandler>
- <xref:System.Windows.Forms.WebBrowserProgressChangedEventArgs>
- <xref:System.Windows.Forms.WebBrowserReadyState>
- <xref:System.Windows.Forms.WebBrowserRefreshOption>
- [방법: WebBrowser 컨트롤을 사용하여 URL로 이동](how-to-navigate-to-a-url-with-the-webbrowser-control.md)
- [방법: WebBrowser 컨트롤을 사용하여 인쇄](how-to-print-with-a-webbrowser-control.md)
- [방법: Windows Forms 애플리케이션에 웹 브라우저 기능 추가](how-to-add-web-browser-capabilities-to-a-windows-forms-application.md)
- [방법: Windows Forms 애플리케이션에서 HTML 문서 뷰어 만들기](how-to-create-an-html-document-viewer-in-a-windows-forms-application.md)
- [방법: DHTML 코드와 클라이언트 애플리케이션 코드 간의 양방향 통신 구현](implement-two-way-com-between-dhtml-and-client.md)
- [WebBrowser 보안](webbrowser-security.md)
