---
title: PrintDocument 구성 요소 개요(Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- PrintDocument
helpviewer_keywords:
- PrintDocument component [Windows Forms], about PrintDocument component
- printing [Windows Forms], PrintDocument component
ms.assetid: b59b4b60-dce5-42ca-8421-3a54a2f7bab0
ms.openlocfilehash: a3f08aa4bd5b63769cef35dbea2209d5d83261be
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59198636"
---
# <a name="printdocument-component-overview-windows-forms"></a><span data-ttu-id="bbb9e-102">PrintDocument 구성 요소 개요(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="bbb9e-102">PrintDocument Component Overview (Windows Forms)</span></span>
<span data-ttu-id="bbb9e-103">Windows Forms [PrintDocument](printdocument-component-windows-forms.md) 구성 요소는 인쇄 대상 및 Windows 기반 애플리케이션 내에서 문서를 인쇄하는 기능을 설명하는 속성을 설정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbb9e-103">The Windows Forms [PrintDocument](printdocument-component-windows-forms.md) component is used to set the properties that describe what to print and the ability to print the document within Windows-based applications.</span></span> <span data-ttu-id="bbb9e-104">모든 문서 인쇄 측면의 제어에 포함되도록 [PrintDialog](printdialog-component-windows-forms.md) 구성 요소와 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbb9e-104">It can be used in conjunction with the [PrintDialog](printdialog-component-windows-forms.md) component to be in control of all aspects of document printing.</span></span>  
  
## <a name="working-with-the-printdocument-component"></a><span data-ttu-id="bbb9e-105">PrintDocument 구성 요소 작업</span><span class="sxs-lookup"><span data-stu-id="bbb9e-105">Working with the PrintDocument Component</span></span>  
 <span data-ttu-id="bbb9e-106">두 가지 관련 된 주요 시나리오는 <xref:System.Drawing.Printing.PrintDocument> 구성 요소는:</span><span class="sxs-lookup"><span data-stu-id="bbb9e-106">Two of the main scenarios that involve the <xref:System.Drawing.Printing.PrintDocument> component are:</span></span>  
  
-   <span data-ttu-id="bbb9e-107">개별 텍스트 파일 인쇄 등의 간단한 인쇄 작업.</span><span class="sxs-lookup"><span data-stu-id="bbb9e-107">Simple print jobs, such as printing an individual text file.</span></span> <span data-ttu-id="bbb9e-108">이러한 경우에 추가 합니다 <xref:System.Drawing.Printing.PrintDocument> 구성 요소를 Windows 폼에 추가한 다음에 파일을 인쇄 하는 프로그래밍 논리는 <xref:System.Drawing.Printing.PrintDocument.PrintPage> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="bbb9e-108">In such a case you would add the <xref:System.Drawing.Printing.PrintDocument> component to a Windows Form, then add programming logic that prints a file in the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler.</span></span> <span data-ttu-id="bbb9e-109">프로그래밍 논리 끝나야 합니다 <xref:System.Drawing.Printing.PrintDocument.Print%2A> 문서를 인쇄 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="bbb9e-109">The programming logic should culminate with the <xref:System.Drawing.Printing.PrintDocument.Print%2A> method to print the document.</span></span> <span data-ttu-id="bbb9e-110">이 메서드는 전송를 <xref:System.Drawing.Graphics> 에 포함 된 개체를 <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> 의 속성을 <xref:System.Drawing.Printing.PrintPageEventArgs> 프린터 클래스.</span><span class="sxs-lookup"><span data-stu-id="bbb9e-110">This method sends a <xref:System.Drawing.Graphics> object, contained in the <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> property of the <xref:System.Drawing.Printing.PrintPageEventArgs> class, to the printer.</span></span> <span data-ttu-id="bbb9e-111">사용 하 여 텍스트 문서를 인쇄 하는 방법을 보여 주는 예는 <xref:System.Drawing.Printing.PrintDocument> 구성 요소 참조 [방법: Windows Forms에서 다중 페이지 텍스트 파일 인쇄](../advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bbb9e-111">For an example that shows how to print a text document using the <xref:System.Drawing.Printing.PrintDocument> component, see [How to: Print a Multi-Page Text File in Windows Forms](../advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md).</span></span>  
  
-   <span data-ttu-id="bbb9e-112">작성한 인쇄 논리를 다시 사용하려는 상황과 같은 좀 더 복잡한 인쇄 작업.</span><span class="sxs-lookup"><span data-stu-id="bbb9e-112">More complex print jobs, such as a situation where you will want to reuse printing logic you have written.</span></span> <span data-ttu-id="bbb9e-113">이러한 경우 새 구성 요소에서 파생 된다는 합니다 <xref:System.Drawing.Printing.PrintDocument> 구성 요소 및 재정의 (참조 [재정의](~/docs/visual-basic/language-reference/modifiers/overrides.md) Visual basic 또는 [재정의](~/docs/csharp/language-reference/keywords/override.md) 에 대 한 C#)를 <xref:System.Drawing.Printing.PrintDocument.PrintPage> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="bbb9e-113">In such a case you would derive a new component from the <xref:System.Drawing.Printing.PrintDocument> component and override (see [Overrides](~/docs/visual-basic/language-reference/modifiers/overrides.md) for Visual Basic or [override](~/docs/csharp/language-reference/keywords/override.md) for C#) the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span>  
  
 <span data-ttu-id="bbb9e-114">폼에 추가 될 때를 <xref:System.Drawing.Printing.PrintDocument> 구성 요소가 Windows Forms 디자이너 아래쪽에 있는 트레이에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="bbb9e-114">When it is added to a form, the <xref:System.Drawing.Printing.PrintDocument> component appears in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbb9e-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="bbb9e-115">See also</span></span>

- <xref:System.Drawing.Graphics>
- <xref:System.Drawing.Printing.PrintDocument>
- [<span data-ttu-id="bbb9e-116">Windows Forms 인쇄 지원</span><span class="sxs-lookup"><span data-stu-id="bbb9e-116">Windows Forms Print Support</span></span>](../advanced/windows-forms-print-support.md)
- [<span data-ttu-id="bbb9e-117">PrintDocument 구성 요소</span><span class="sxs-lookup"><span data-stu-id="bbb9e-117">PrintDocument Component</span></span>](printdocument-component-windows-forms.md)
