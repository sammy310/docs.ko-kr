---
title: '방법: Windows Forms LinkLabel 컨트롤에서 웹 페이지 표시(Visual Basic)'
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
ms.openlocfilehash: 1be9ff06e749d14b46946e899c6ffb6c3a950d65
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59170029"
---
# <a name="how-to-display-a-web-page-from-a-windows-forms-linklabel-control-visual-basic"></a>방법: Windows Forms LinkLabel 컨트롤에서 웹 페이지 표시(Visual Basic)
이 예제에서는 기본 브라우저에서 웹 페이지는 Windows Forms를 클릭할 때 표시 <xref:System.Windows.Forms.LinkLabel> 제어 합니다.  
  
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
  
-   라는 Windows 폼을 `Form1`입니다.  
  
-   `LinkLabel1`이라는 <xref:System.Windows.Forms.LinkLabel> 컨트롤  
  
-   현재 인터넷에 연결 합니다.  
  
## <a name="net-framework-security"></a>.NET Framework 보안  
 에 대 한 호출을 <xref:System.Diagnostics.Process.Start%2A> 메서드 완전 신뢰가 필요 합니다. 자세한 내용은 <xref:System.Security.SecurityException>을 참조하세요.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.LinkLabel>
- [LinkLabel 컨트롤](linklabel-control-windows-forms.md)
