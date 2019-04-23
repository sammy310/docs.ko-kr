---
title: 관리되는 HTML 문서 개체 모델의 노출되지 않은 멤버에 액세스
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- unexposed members
- managed HTML DOM [Windows Forms], accessing unexposed members
ms.assetid: 762295bd-2355-4aa7-b43c-5bff997a33e6
ms.openlocfilehash: 20341a44eb8a43a9d130e0b76d23b513738c6782
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59129508"
---
# <a name="accessing-unexposed-members-on-the-managed-html-document-object-model"></a>관리되는 HTML 문서 개체 모델의 노출되지 않은 멤버에 액세스
호출 하는 클래스를 포함 하는 관리 되는 HTML 문서 개체 모델 (DOM) <xref:System.Windows.Forms.HtmlElement> 속성, 메서드 및 모든 HTML 요소에 공통 되는 이벤트를 노출 하는 합니다. 그러나 경우에 따라 해야 관리 되는 인터페이스를 직접 노출 하지 않는 멤버에 액세스 합니다. 이 항목에서는 두 가지 방법으로 노출 되지 않은 멤버를 포함 하 여 액세스 검사 [!INCLUDE[jsprjscript](../../../../includes/jsprjscript-md.md)] 및 웹 페이지 내에서 정의 하는 VBScript 함수입니다.  
  
## <a name="accessing-unexposed-members-through-managed-interfaces"></a>관리 되는 인터페이스를 통해 노출 되지 않은 멤버에 액세스  
 <xref:System.Windows.Forms.HtmlDocument> 및 <xref:System.Windows.Forms.HtmlElement> 노출 되지 않은 멤버에 액세스할 수 있도록 네 가지 메서드를 제공 합니다. 다음 표에서 형식 및 해당 메서드를 보여 줍니다.  
  
|멤버 형식|메서드|  
|-----------------|-----------------|  
|속성 (<xref:System.Windows.Forms.HtmlElement>)|<xref:System.Windows.Forms.HtmlElement.GetAttribute%2A><br /><br /> <xref:System.Windows.Forms.HtmlElement.SetAttribute%2A>|  
|메서드|<xref:System.Windows.Forms.HtmlElement.InvokeMember%2A>|  
|이벤트 (<xref:System.Windows.Forms.HtmlDocument>)|<xref:System.Windows.Forms.HtmlDocument.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlDocument.DetachEventHandler%2A>|  
|이벤트 (<xref:System.Windows.Forms.HtmlElement>)|<xref:System.Windows.Forms.HtmlElement.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlElement.DetachEventHandler%2A>|  
|이벤트 (<xref:System.Windows.Forms.HtmlWindow>)|<xref:System.Windows.Forms.HtmlWindow.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlWindow.DetachEventHandler%2A>|  
  
 이러한 메서드를 사용 하는 경우 올바른 기본 형식의 요소가 있다고 가정 합니다. 수신 한다고 가정 합니다 `Submit` 의 이벤트를 `FORM` 요소는 HTML 페이지에 몇 가지 사전 처리를 수행할 수 있도록는 `FORM`의 사용자가 서버에 제출 하기 전에 값. 이상적으로 HTML에 대 한 제어를 사용 하는 경우 정의 된 `FORM` 고유한 할 `ID` 특성입니다.  
  
```  
<HTML>  
  
    <HEAD>  
        <TITLE>Form Page</TITLE>  
    </HEAD>  
  
    <BODY>  
        <FORM ID="form1">  
             ... form fields defined here ...  
        </FORM>  
    </BODY>  
  
</HTML>  
```  
  
 이 페이지에 로드 한 후를 <xref:System.Windows.Forms.WebBrowser> 컨트롤을 사용할 수는 <xref:System.Windows.Forms.HtmlDocument.GetElementById%2A> 검색 하는 메서드는 `FORM` 런타임 사용 하 여 `form1` 인수로 합니다.  
  
 [!code-csharp[System.Windows.Forms.HtmlElement#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.HtmlElement/CS/Form1.cs#10)]
 [!code-vb[System.Windows.Forms.HtmlElement#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.HtmlElement/VB/Form1.vb#10)]  
  
## <a name="accessing-unmanaged-interfaces"></a>관리 되지 않는 인터페이스에 액세스  
 또한 각 DOM 클래스에 의해 노출 되는 관리 되지 않는 구성 요소 개체 모델 (COM) 인터페이스를 사용 하 여 관리 되는 HTML DOM에 노출 되지 않은 멤버를 액세스할 수 있습니다. 것이 좋습니다 노출 되지 않은 멤버에 대 한 여러 호출을 수행 해야 할 경우 또는 노출 되지 않은 멤버는 관리 되는 HTML DOM으로 래핑되지 않습니다 다른 관리 되지 않는 인터페이스를 반환 하는 경우  
  
 다음 표에서 모든 관리 되는 HTML DOM을 통해 노출 되는 관리 되지 않는 인터페이스를 표시 합니다. 해당 사용법 및 예를 들어 코드에 대 한 설명은 각 링크를 클릭 합니다.  
  
|형식|관리 되지 않는 인터페이스|  
|----------|-------------------------|  
|<xref:System.Windows.Forms.HtmlDocument>|<xref:System.Windows.Forms.HtmlDocument.DomDocument%2A>|  
|<xref:System.Windows.Forms.HtmlElement>|<xref:System.Windows.Forms.HtmlElement.DomElement%2A>|  
|<xref:System.Windows.Forms.HtmlWindow>|<xref:System.Windows.Forms.HtmlWindow.DomWindow%2A>|  
|<xref:System.Windows.Forms.HtmlHistory>|<xref:System.Windows.Forms.HtmlHistory.DomHistory%2A>|  
  
 COM 인터페이스를 사용 하는 가장 쉬운 방법은 지원 되지 않습니다 하지만 응용 프로그램에서 관리 되지 않는 HTML DOM 라이브러리 (MSHTML.dll)에 대 한 참조를 추가 하는 것입니다. 자세한 내용은 [기술 자료 문서 934368](https://support.microsoft.com/kb/934368)합니다.  
  
## <a name="accessing-script-functions"></a>스크립트 기능에 액세스  
 HTML 페이지와 같은 스크립팅 언어를 사용 하 여 하나 이상의 함수를 정의할 수 [!INCLUDE[jsprjscript](../../../../includes/jsprjscript-md.md)] 또는 VBScript입니다. 이러한 함수 내부에 배치 된 `SCRIPT` 페이지에서 페이지를 DOM에서 주문형으로 또는 이벤트에 대 한 응답으로 실행할 수  
  
 사용 하 여 HTML 페이지에서 정의한 모든 스크립트 함수를 호출할 수는 <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A> 메서드. HTML 요소를 반환 하는 스크립트 메서드를 하는 경우이 반환 결과를 변환 하는 캐스트를 사용할 수 있습니다는 <xref:System.Windows.Forms.HtmlElement>합니다. 세부 정보 및 예제 코드에 대 한 참조 <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A>합니다.  
  
## <a name="see-also"></a>참고자료

- [관리되는 HTML 문서 개체 모델 사용](using-the-managed-html-document-object-model.md)
