---
title: PrintDialog 구성 요소를 표시 하는 방법
ms.date: 03/30/2017
helpviewer_keywords:
- Print dialog box [Windows Forms], displaying
- PrintDialog component [Windows Forms], displaying
- printing [Windows Forms], displaying print dialog box
ms.assetid: 745a8db7-0526-4b21-b09d-18e13ed32014
ms.openlocfilehash: 198ae75d407bd1837033a1cc186d84ff972fdc2f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61941572"
---
# <a name="how-to-display-the-printdialog-component"></a><span data-ttu-id="f4877-102">PrintDialog 구성 요소를 표시 하는 방법</span><span class="sxs-lookup"><span data-stu-id="f4877-102">How to display the PrintDialog component</span></span>

<span data-ttu-id="f4877-103"><xref:System.Windows.Forms.PrintDialog> 구성 요소는 쉽게 익힐 수 많은 사용자는 표준 Windows 인쇄 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="f4877-103">The <xref:System.Windows.Forms.PrintDialog> component is the standard Windows print dialog box that many of your users will be familiar with.</span></span> <span data-ttu-id="f4877-104">사용자가 즉시 익숙해 때문에 좋을 것을 사용 하 여 <xref:System.Windows.Forms.PrintDialog> 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="f4877-104">Because your users will be immediately comfortable with it, it would be beneficial for you to use the <xref:System.Windows.Forms.PrintDialog> component.</span></span>

## <a name="to-display-the-printdialog-component"></a><span data-ttu-id="f4877-105">PrintDialog 구성 요소를 표시하려면</span><span class="sxs-lookup"><span data-stu-id="f4877-105">To display the PrintDialog component</span></span>

- <span data-ttu-id="f4877-106">호출 된 <xref:System.Windows.Forms.Form.ShowDialog%2A> 응용 프로그램의 코드 내에서 메서드.</span><span class="sxs-lookup"><span data-stu-id="f4877-106">Call the <xref:System.Windows.Forms.Form.ShowDialog%2A> method from within the code of your application.</span></span>

     <span data-ttu-id="f4877-107">구성 요소가 표시되면 사용자가 이 구성 요소와 상호 작용하여 인쇄 작업의 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f4877-107">Once the component is shown, users will interact with it, setting the properties of the print job.</span></span> <span data-ttu-id="f4877-108">에 저장 된 이러한 합니다 <xref:System.Drawing.Printing.PrinterSettings> 클래스 (및 <xref:System.Drawing.Printing.PageSettings> 클래스를 사용자가 액세스 하는 경우를 [PageSetupDialog 구성 요소](pagesetupdialog-component-windows-forms.md) 를 통해를 <xref:System.Windows.Forms.PrintDialog> 구성 요소) 인쇄 작업에 연결 된.</span><span class="sxs-lookup"><span data-stu-id="f4877-108">These are saved in the  <xref:System.Drawing.Printing.PrinterSettings> class (and the <xref:System.Drawing.Printing.PageSettings> class, if the user accesses the [PageSetupDialog Component](pagesetupdialog-component-windows-forms.md) through the <xref:System.Windows.Forms.PrintDialog> component) associated with that print job.</span></span> <span data-ttu-id="f4877-109">그런 다음 설정한 속성을 호출하여 인쇄 작업의 세부 사항을 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4877-109">You can then make calls to the properties they set to determine the specifics of the print job.</span></span>

## <a name="see-also"></a><span data-ttu-id="f4877-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="f4877-110">See also</span></span>

- [<span data-ttu-id="f4877-111">방법: 표준 Windows Forms 인쇄 작업 만들기</span><span class="sxs-lookup"><span data-stu-id="f4877-111">How to: Create Standard Windows Forms Print Jobs</span></span>](../advanced/how-to-create-standard-windows-forms-print-jobs.md)
- [<span data-ttu-id="f4877-112">방법: 런타임에 PrintDialog에서 사용자 입력 캡처</span><span class="sxs-lookup"><span data-stu-id="f4877-112">How to: Capture User Input from a PrintDialog at Run Time</span></span>](../advanced/how-to-capture-user-input-from-a-printdialog-at-run-time.md)
- [<span data-ttu-id="f4877-113">PrintPreviewDialog 컨트롤</span><span class="sxs-lookup"><span data-stu-id="f4877-113">PrintPreviewDialog Control</span></span>](printpreviewdialog-control-windows-forms.md)
- [<span data-ttu-id="f4877-114">PrintDialog 구성 요소</span><span class="sxs-lookup"><span data-stu-id="f4877-114">PrintDialog Component</span></span>](printdialog-component-windows-forms.md)
- [<span data-ttu-id="f4877-115">Windows Forms 인쇄 지원</span><span class="sxs-lookup"><span data-stu-id="f4877-115">Windows Forms Print Support</span></span>](../advanced/windows-forms-print-support.md)
- [<span data-ttu-id="f4877-116">Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="f4877-116">Windows Forms Controls</span></span>](index.md)