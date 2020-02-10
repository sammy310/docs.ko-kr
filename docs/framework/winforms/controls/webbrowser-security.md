---
title: WebBrowser 보안
ms.date: 03/30/2017
helpviewer_keywords:
- WebBrowser control [Windows Forms], security
- security [Windows Forms], WebBrowser control
ms.assetid: 0968846e-48ee-485a-9797-65b5b9a622f8
ms.openlocfilehash: b25cabca050d06dbfe97c563eb56622d1f21be54
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2020
ms.locfileid: "77095257"
---
# <a name="webbrowser-security"></a>WebBrowser 보안
<xref:System.Windows.Forms.WebBrowser> 컨트롤은 완전 신뢰 에서만 작동 하도록 디자인 되었습니다. 컨트롤에 표시 되는 HTML 콘텐츠는 외부 웹 서버에서 가져올 수 있으며 스크립트나 웹 컨트롤 형식의 비관리 코드를 포함할 수 있습니다. 이 경우 <xref:System.Windows.Forms.WebBrowser> 컨트롤을 사용 하는 경우 컨트롤이 Internet Explorer 보다 안전 하지 않지만 관리 되는 <xref:System.Windows.Forms.WebBrowser> 컨트롤은 이러한 비관리 코드가 실행 되는 것을 방지 하지 않습니다.  
  
 기본 ActiveX `WebBrowser` 컨트롤과 관련 된 보안 문제에 대 한 자세한 내용은 [WebBrowser control](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85))을 참조 하세요.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.WebBrowser>
- [WebBrowser 컨트롤 개요](webbrowser-control-overview.md)
- [WebBrowser 컨트롤](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85))
