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
# <a name="how-to-display-a-web-page-from-a-windows-forms-linklabel-control-visual-basic"></a><span data-ttu-id="a1956-102">방법: Windows Forms LinkLabel 컨트롤에서 웹 페이지 표시(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a1956-102">How to: Display a Web Page from a Windows Forms LinkLabel Control (Visual Basic)</span></span>
<span data-ttu-id="a1956-103">이 예제에서는 사용자가 Windows Forms <xref:System.Windows.Forms.LinkLabel> 컨트롤을 클릭할 때 기본 브라우저에 웹 페이지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1956-103">This example displays a Web page in the default browser when a user clicks a Windows Forms <xref:System.Windows.Forms.LinkLabel> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a1956-104">예</span><span class="sxs-lookup"><span data-stu-id="a1956-104">Example</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="a1956-105">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="a1956-105">Compiling the Code</span></span>  
 <span data-ttu-id="a1956-106">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a1956-106">This example requires:</span></span>  
  
- <span data-ttu-id="a1956-107">이름이 `Form1`Windows 폼입니다.</span><span class="sxs-lookup"><span data-stu-id="a1956-107">A Windows Form named `Form1`.</span></span>  
  
- <span data-ttu-id="a1956-108">`LinkLabel1`이라는 <xref:System.Windows.Forms.LinkLabel> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="a1956-108">A <xref:System.Windows.Forms.LinkLabel> control named `LinkLabel1`.</span></span>  
  
- <span data-ttu-id="a1956-109">활성 인터넷 연결입니다.</span><span class="sxs-lookup"><span data-stu-id="a1956-109">An active Internet connection.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="a1956-110">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="a1956-110">.NET Framework Security</span></span>  
 <span data-ttu-id="a1956-111"><xref:System.Diagnostics.Process.Start%2A> 메서드에 대 한 호출에는 완전 신뢰가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1956-111">The call to the <xref:System.Diagnostics.Process.Start%2A> method requires full trust.</span></span> <span data-ttu-id="a1956-112">자세한 내용은 <xref:System.Security.SecurityException>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a1956-112">For more information, see <xref:System.Security.SecurityException>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1956-113">참조</span><span class="sxs-lookup"><span data-stu-id="a1956-113">See also</span></span>

- <xref:System.Windows.Forms.LinkLabel>
- [<span data-ttu-id="a1956-114">LinkLabel 컨트롤</span><span class="sxs-lookup"><span data-stu-id="a1956-114">LinkLabel Control</span></span>](linklabel-control-windows-forms.md)
