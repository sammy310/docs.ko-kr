---
title: LinkLabel 컨트롤 개요
ms.date: 03/30/2017
f1_keywords:
- LinkLabel
helpviewer_keywords:
- links [Windows Forms], LinkLabel control
- Label control [Windows Forms], about Label control
- LinkLabel control [Windows Forms], about LinkLabel control
ms.assetid: 9e248549-10ca-43a3-bb5e-60f583d369f1
ms.openlocfilehash: 3e8607644c858ae804e384c974b5e81c1786c6a1
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739510"
---
# <a name="linklabel-control-overview-windows-forms"></a><span data-ttu-id="cad1d-102">LinkLabel 컨트롤 개요(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="cad1d-102">LinkLabel Control Overview (Windows Forms)</span></span>
<span data-ttu-id="cad1d-103">Windows 양식 <xref:System.Windows.Forms.LinkLabel> 컨트롤을 사용하면 Windows Forms 응용 프로그램에 웹 스타일 링크를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cad1d-103">The Windows Forms <xref:System.Windows.Forms.LinkLabel> control allows you to add Web-style links to Windows Forms applications.</span></span> <span data-ttu-id="cad1d-104">컨트롤을 <xref:System.Windows.Forms.LinkLabel> 사용할 수 있는 모든 것에 <xref:System.Windows.Forms.Label> 대 한 컨트롤을 사용할 수 있습니다. 텍스트의 일부를 파일, 폴더 또는 웹 페이지에 대한 링크로 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cad1d-104">You can use the <xref:System.Windows.Forms.LinkLabel> control for everything that you can use the <xref:System.Windows.Forms.Label> control for; you can also set part of the text as a link to a file, folder, or Web page.</span></span>  
  
## <a name="what-you-can-do-with-the-linklabel-control"></a><span data-ttu-id="cad1d-105">링크레이블 컨트롤로 수행할 수 있는 일</span><span class="sxs-lookup"><span data-stu-id="cad1d-105">What You Can Do with the LinkLabel Control</span></span>  
 <span data-ttu-id="cad1d-106">컨트롤의 모든 속성, 메서드 및 이벤트 <xref:System.Windows.Forms.Label> 외에도 <xref:System.Windows.Forms.LinkLabel> 컨트롤에는 하이퍼링크 및 링크 색상에 대한 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cad1d-106">In addition to all the properties, methods, and events of the <xref:System.Windows.Forms.Label> control, the <xref:System.Windows.Forms.LinkLabel> control has properties for hyperlinks and link colors.</span></span> <span data-ttu-id="cad1d-107">속성은 <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> 링크를 활성화하는 텍스트의 영역을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="cad1d-107">The <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property sets the area of the text that activates the link.</span></span> <span data-ttu-id="cad1d-108">의 <xref:System.Windows.Forms.LinkLabel.LinkColor%2A> <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>색 <xref:System.Windows.Forms.LinkLabel.ActiveLinkColor%2A> 및 속성은 링크의 색상을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="cad1d-108">The <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>, and <xref:System.Windows.Forms.LinkLabel.ActiveLinkColor%2A> properties set the colors of the link.</span></span> <span data-ttu-id="cad1d-109">이 <xref:System.Windows.Forms.LinkLabel.LinkClicked> 이벤트는 링크 텍스트를 선택할 때 발생하는 일을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="cad1d-109">The <xref:System.Windows.Forms.LinkLabel.LinkClicked> event determines what happens when the link text is selected.</span></span>  
  
 <span data-ttu-id="cad1d-110">컨트롤의 <xref:System.Windows.Forms.LinkLabel> 가장 간단한 용도는 <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> 속성을 사용하여 단일 링크를 표시하는 것이지만 <xref:System.Windows.Forms.LinkLabel.Links%2A> 속성을 사용하여 여러 하이퍼링크를 표시할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cad1d-110">The simplest use of the <xref:System.Windows.Forms.LinkLabel> control is to display a single link using the <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property, but you can also display multiple hyperlinks using the <xref:System.Windows.Forms.LinkLabel.Links%2A> property.</span></span> <span data-ttu-id="cad1d-111">이 <xref:System.Windows.Forms.LinkLabel.Links%2A> 속성을 사용하면 링크 컬렉션에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cad1d-111">The <xref:System.Windows.Forms.LinkLabel.Links%2A> property enables you to access a collection of links.</span></span> <span data-ttu-id="cad1d-112">각 개별 <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> <xref:System.Windows.Forms.LinkLabel.Link> 개체의 속성에 데이터를 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cad1d-112">You can also specify data in the <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> property of each individual <xref:System.Windows.Forms.LinkLabel.Link> object.</span></span> <span data-ttu-id="cad1d-113"><xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> 속성 값은 표시할 파일의 위치 또는 웹 사이트의 주소를 저장하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cad1d-113">The value of the <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> property can be used to store the location of a file to display or the address of a Web site.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cad1d-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cad1d-114">See also</span></span>

- <xref:System.Windows.Forms.LinkLabel>
- [<span data-ttu-id="cad1d-115">Label 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="cad1d-115">Label Control Overview</span></span>](label-control-overview-windows-forms.md)
- [<span data-ttu-id="cad1d-116">방법: Windows Forms LinkLabel 컨트롤을 사용하여 개체 또는 웹 페이지에 연결</span><span class="sxs-lookup"><span data-stu-id="cad1d-116">How to: Link to an Object or Web Page with the Windows Forms LinkLabel Control</span></span>](link-to-an-object-or-web-page-with-wf-linklabel-control.md)
- [<span data-ttu-id="cad1d-117">방법: Windows Forms LinkLabel 컨트롤의 모양 변경</span><span class="sxs-lookup"><span data-stu-id="cad1d-117">How to: Change the Appearance of the Windows Forms LinkLabel Control</span></span>](how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)
