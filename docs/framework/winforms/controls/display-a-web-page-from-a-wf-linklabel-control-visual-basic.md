---
title: LinkLabel 컨트롤에서 웹 페이지 표시 (Visual Basic)
ms.date: 03/30/2017
dev_langs:
- vb
f1_keywords:
- LinkLabel1_LinkClicked
helpviewer_keywords:
- examples [Windows Forms], LinkLabel control
- Web pages [Windows Forms], displaying
- linking [Windows Forms], to Web pages from forms
- Windows Forms, linking to Web pages
- LinkLabel control [Windows Forms], examples
ms.assetid: 477a7398-5971-4de3-b24c-f49f32bdb28a
ms.openlocfilehash: 75373d55b7bc5ef11e39d5b9546996cb1c4f6f7c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745918"
---
# <a name="how-to-display-a-web-page-from-a-windows-forms-linklabel-control-visual-basic"></a>방법: Windows Forms LinkLabel 컨트롤에서 웹 페이지 표시(Visual Basic)
이 예제에서는 사용자가 Windows Forms <xref:System.Windows.Forms.LinkLabel> 컨트롤을 클릭할 때 기본 브라우저에 웹 페이지를 표시 합니다.  
  
## <a name="example"></a>예제  
  
```vb  
Private Sub Form1_Load(ByVal sender As System.Object, ByVal e _  
As System.EventArgs) Handles MyBase.Load  
    LinkLabel1.Text = "Click here to get more info."  
    LinkLabel1.Links.Add(6, 4, "www.microsoft.com")  
End Sub  
Private Sub LinkLabel1_LinkClicked(ByVal sender As System.Object, ByVal _  
e As System.Windows.Forms.LinkLabelLinkClickedEventArgs) Handles _  
LinkLabel1.LinkClicked  
    System.Diagnostics.Process.Start(e.Link.LinkData.ToString())  
End Sub  
```  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
- 이름이 `Form1`Windows 폼입니다.  
  
- <xref:System.Windows.Forms.LinkLabel>이라는 `LinkLabel1` 컨트롤  
  
- 활성 인터넷 연결입니다.  
  
## <a name="net-framework-security"></a>.NET Framework 보안  
 <xref:System.Diagnostics.Process.Start%2A> 메서드에 대 한 호출에는 완전 신뢰가 필요 합니다. 자세한 내용은 <xref:System.Security.SecurityException>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.LinkLabel>
- [LinkLabel 컨트롤](linklabel-control-windows-forms.md)
