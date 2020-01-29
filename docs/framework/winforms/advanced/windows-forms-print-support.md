---
title: 인쇄 지원
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, printing
- printing [Windows Forms]
- forms [Windows Forms], printing (using designer)
- printing [Windows Forms], Windows Forms, support
- printing [Windows Forms], print support
ms.assetid: a4a2960c-eb70-48e2-b641-cfb222704e46
ms.openlocfilehash: d6e8f60db7afe2f1b04eaae6fe71aa93e5c22cae
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732497"
---
# <a name="windows-forms-print-support"></a><span data-ttu-id="918ed-102">Windows Forms 인쇄 지원</span><span class="sxs-lookup"><span data-stu-id="918ed-102">Windows Forms Print Support</span></span>
<span data-ttu-id="918ed-103">Windows Forms 인쇄는 주로 [PrintDocument component](../controls/printdocument-component-windows-forms.md) 구성 요소를 사용 하 여 사용자가 인쇄할 수 있도록 하 고 [PrintPreviewDialog 컨트롤](../controls/printpreviewdialog-control-windows-forms.md) 컨트롤, [PrintDialog 구성](../controls/printdialog-component-windows-forms.md) 요소 및 [PageSetupDialog](../controls/pagesetupdialog-component-windows-forms.md) 구성 요소 구성 요소를 사용 하 여 Windows 운영 체제에 익숙한 사용자에 게 친숙 한 그래픽 인터페이스를 제공 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="918ed-103">Printing in Windows Forms consists primarily of using the [PrintDocument Component](../controls/printdocument-component-windows-forms.md) component to enable the user to print, and the [PrintPreviewDialog Control](../controls/printpreviewdialog-control-windows-forms.md) control, [PrintDialog Component](../controls/printdialog-component-windows-forms.md) and [PageSetupDialog Component](../controls/pagesetupdialog-component-windows-forms.md) components to provide a familiar graphical interface to users accustomed to the Windows operating system.</span></span>  
  
 <span data-ttu-id="918ed-104">일반적으로 <xref:System.Drawing.Printing.PrintDocument> 구성 요소의 새 인스턴스를 만들고, <xref:System.Drawing.Printing.PrinterSettings> 및 <xref:System.Drawing.Printing.PageSettings> 클래스를 사용 하 여 인쇄할 항목을 설명 하는 속성을 설정 하 고, <xref:System.Drawing.Printing.PrintDocument.Print%2A> 메서드를 호출 하 여 실제로 문서를 인쇄 합니다.</span><span class="sxs-lookup"><span data-stu-id="918ed-104">Typically, you create a new instance of the <xref:System.Drawing.Printing.PrintDocument> component, set the properties that describe what to print using the <xref:System.Drawing.Printing.PrinterSettings> and <xref:System.Drawing.Printing.PageSettings> classes, and call the <xref:System.Drawing.Printing.PrintDocument.Print%2A> method to actually print the document.</span></span>  
  
 <span data-ttu-id="918ed-105">Windows 기반 응용 프로그램에서 인쇄 하는 과정에서 <xref:System.Drawing.Printing.PrintDocument> 구성 요소는 인쇄 중단 대화 상자를 표시 하 여 인쇄가 발생 하 고 인쇄 작업을 취소할 수 있음을 사용자에 게 알립니다.</span><span class="sxs-lookup"><span data-stu-id="918ed-105">During the course of printing from a Windows-based application, the <xref:System.Drawing.Printing.PrintDocument> component will show an abort print dialog box to alert users to the fact that printing is occurring and to allow the print job to be canceled.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="918ed-106">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="918ed-106">In This Section</span></span>  
 [<span data-ttu-id="918ed-107">방법: 표준 Windows Forms 인쇄 작업 만들기</span><span class="sxs-lookup"><span data-stu-id="918ed-107">How to: Create Standard Windows Forms Print Jobs</span></span>](how-to-create-standard-windows-forms-print-jobs.md)  
 <span data-ttu-id="918ed-108"><xref:System.Drawing.Printing.PrintDocument> 구성 요소를 사용 하 여 Windows Form에서 인쇄 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="918ed-108">Explains how to use the <xref:System.Drawing.Printing.PrintDocument> component to print from a Windows Form.</span></span>  
  
 [<span data-ttu-id="918ed-109">방법: 런타임에 PrintDialog에서 사용자 입력 캡처</span><span class="sxs-lookup"><span data-stu-id="918ed-109">How to: Capture User Input from a PrintDialog at Run Time</span></span>](how-to-capture-user-input-from-a-printdialog-at-run-time.md)  
 <span data-ttu-id="918ed-110"><xref:System.Windows.Forms.PrintDialog> 구성 요소를 사용 하 여 프로그래밍 방식으로 선택한 인쇄 옵션을 수정 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="918ed-110">Explains how to modify selected print options programmatically using the <xref:System.Windows.Forms.PrintDialog> component.</span></span>  
  
 [<span data-ttu-id="918ed-111">방법: Windows Forms에서 사용자의 컴퓨터에 연결된 프린터 선택</span><span class="sxs-lookup"><span data-stu-id="918ed-111">How to: Choose the Printers Attached to a User's Computer in Windows Forms</span></span>](how-to-choose-the-printers-attached-to-user-computer-in-windows-forms.md)  
 <span data-ttu-id="918ed-112">런타임에 <xref:System.Windows.Forms.PrintDialog> 구성 요소를 사용 하 여 인쇄 되도록 프린터를 변경 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="918ed-112">Describes changing the printer to print to using the <xref:System.Windows.Forms.PrintDialog> component at run time.</span></span>  
  
 [<span data-ttu-id="918ed-113">방법: Windows Forms의 그래픽 인쇄</span><span class="sxs-lookup"><span data-stu-id="918ed-113">How to: Print Graphics in Windows Forms</span></span>](how-to-print-graphics-in-windows-forms.md)  
 <span data-ttu-id="918ed-114">프린터에 그래픽을 보내는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="918ed-114">Describes sending graphics to the printer.</span></span>  
  
 [<span data-ttu-id="918ed-115">방법: Windows Forms에서 다중 페이지 텍스트 파일 인쇄</span><span class="sxs-lookup"><span data-stu-id="918ed-115">How to: Print a Multi-Page Text File in Windows Forms</span></span>](how-to-print-a-multi-page-text-file-in-windows-forms.md)  
 <span data-ttu-id="918ed-116">프린터에 텍스트를 전송 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="918ed-116">Describes sending text to the printer.</span></span>  
  
 [<span data-ttu-id="918ed-117">방법: Windows Forms 인쇄 작업 완료</span><span class="sxs-lookup"><span data-stu-id="918ed-117">How to: Complete Windows Forms Print Jobs</span></span>](how-to-complete-windows-forms-print-jobs.md)  
 <span data-ttu-id="918ed-118">인쇄 작업이 완료 되었음을 사용자에 게 알리는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="918ed-118">Explains how to alert users to the completion of a print job.</span></span>  
  
 [<span data-ttu-id="918ed-119">방법: Windows Form 인쇄</span><span class="sxs-lookup"><span data-stu-id="918ed-119">How to: Print a Windows Form</span></span>](how-to-print-a-windows-form.md)  
 <span data-ttu-id="918ed-120">현재 폼의 복사본을 인쇄 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="918ed-120">Shows how to print a copy of the current form.</span></span>  
  
 [<span data-ttu-id="918ed-121">방법: Windows Forms에서 인쇄 미리 보기를 사용하여 인쇄</span><span class="sxs-lookup"><span data-stu-id="918ed-121">How to: Print in Windows Forms Using Print Preview</span></span>](how-to-print-in-windows-forms-using-print-preview.md)  
 <span data-ttu-id="918ed-122">문서를 인쇄 하는 데 <xref:System.Windows.Forms.PrintPreviewDialog>를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="918ed-122">Shows how to use a <xref:System.Windows.Forms.PrintPreviewDialog> for printing a document.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="918ed-123">관련 섹션</span><span class="sxs-lookup"><span data-stu-id="918ed-123">Related Sections</span></span>  
 [<span data-ttu-id="918ed-124">PrintDocument 구성 요소</span><span class="sxs-lookup"><span data-stu-id="918ed-124">PrintDocument Component</span></span>](../controls/printdocument-component-windows-forms.md)  
 <span data-ttu-id="918ed-125"><xref:System.Drawing.Printing.PrintDocument> 구성 요소의 사용법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="918ed-125">Explains usage of the <xref:System.Drawing.Printing.PrintDocument> component.</span></span>  
  
 [<span data-ttu-id="918ed-126">PrintDialog 구성 요소</span><span class="sxs-lookup"><span data-stu-id="918ed-126">PrintDialog Component</span></span>](../controls/printdialog-component-windows-forms.md)  
 <span data-ttu-id="918ed-127"><xref:System.Windows.Forms.PrintDialog> 구성 요소의 사용법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="918ed-127">Explains usage of the <xref:System.Windows.Forms.PrintDialog> component.</span></span>  
  
 [<span data-ttu-id="918ed-128">PrintPreviewDialog 컨트롤</span><span class="sxs-lookup"><span data-stu-id="918ed-128">PrintPreviewDialog Control</span></span>](../controls/printpreviewdialog-control-windows-forms.md)  
 <span data-ttu-id="918ed-129"><xref:System.Windows.Forms.PrintPreviewDialog> 컨트롤의 사용법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="918ed-129">Explains usage of the <xref:System.Windows.Forms.PrintPreviewDialog> control.</span></span>  
  
 [<span data-ttu-id="918ed-130">PageSetupDialog Component</span><span class="sxs-lookup"><span data-stu-id="918ed-130">PageSetupDialog Component</span></span>](../controls/pagesetupdialog-component-windows-forms.md)  
 <span data-ttu-id="918ed-131"><xref:System.Windows.Forms.PageSetupDialog> 구성 요소의 사용법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="918ed-131">Explains usage of the <xref:System.Windows.Forms.PageSetupDialog> component.</span></span>  
  
 <xref:System.Drawing.Printing>  
 <span data-ttu-id="918ed-132"><xref:System.Drawing.Printing> 네임 스페이스의 클래스에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="918ed-132">Describes the classes in the <xref:System.Drawing.Printing> namespace.</span></span>
