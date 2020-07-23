---
title: '방법: 인쇄 대화 상자 호출'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- invoking print dialogs [WPF]
- print dialogs [WPF], invoking
ms.assetid: e3a2c84c-74fe-45a4-8501-5813f9dbfed2
ms.openlocfilehash: 75a4160366766efbd19d6e8ae26fbec102e7f95b
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/22/2020
ms.locfileid: "86924502"
---
# <a name="how-to-invoke-a-print-dialog"></a><span data-ttu-id="dd419-102">방법: 인쇄 대화 상자 호출</span><span class="sxs-lookup"><span data-stu-id="dd419-102">How to: Invoke a Print Dialog</span></span>
<span data-ttu-id="dd419-103">응용 프로그램에서 인쇄 하는 기능을 제공 하기 위해 단순히 개체를 만들고 열 수 있습니다 <xref:System.Windows.Controls.PrintDialog> .</span><span class="sxs-lookup"><span data-stu-id="dd419-103">To provide the ability to print from you application, you can simply create and open a <xref:System.Windows.Controls.PrintDialog> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dd419-104">예제</span><span class="sxs-lookup"><span data-stu-id="dd419-104">Example</span></span>  
 <span data-ttu-id="dd419-105"><xref:System.Windows.Controls.PrintDialog>컨트롤은 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] , 구성 및 XPS 작업 제출을 위한 단일 진입점을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd419-105">The <xref:System.Windows.Controls.PrintDialog> control provides a single entry point for [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], configuration, and XPS job submission.</span></span> <span data-ttu-id="dd419-106">컨트롤은 사용 하기 쉬우며 태그 또는 코드를 사용 하 여 인스턴스화할 수 있습니다 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dd419-106">The control is easy to use and can be instantiated by using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] markup or code.</span></span> <span data-ttu-id="dd419-107">다음 예제에서는 코드에서 컨트롤을 인스턴스화하고 여는 방법과 인쇄 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dd419-107">The following example demonstrates how to instantiate and open the control in code and how to print from it.</span></span> <span data-ttu-id="dd419-108">또한 대화 상자에서 사용자에 게 특정 페이지 범위를 설정 하는 옵션을 제공 하도록 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dd419-108">It also shows how to ensure that the dialog will give the user the option of setting a specific range of pages.</span></span> <span data-ttu-id="dd419-109">예제 코드는 C: 드라이브의 루트에 FixedDocumentSequence 파일이 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd419-109">The example code assumes that there is a file FixedDocumentSequence.xps in the root of the C: drive.</span></span>  
  
 [!code-csharp[printdialog#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintDialog/CSharp/Window1.xaml.cs#1)]
 [!code-vb[printdialog#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintDialog/visualbasic/window1.xaml.vb#1)]  
  
 <span data-ttu-id="dd419-110">대화 상자가 열리면 사용자는 컴퓨터에 설치 된 프린터에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd419-110">Once the dialog is open, users will be able to select from the printers installed on their computer.</span></span> <span data-ttu-id="dd419-111">또한 인쇄 대신 XPS (XML Paper Specification) 파일을 만들 수 있도록 [MICROSOFT Xps Document Writer](/windows/win32/printdocs/microsoft-xps-document-writer) 를 선택 하는 옵션도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd419-111">They will also have the option of selecting the [Microsoft XPS Document Writer](/windows/win32/printdocs/microsoft-xps-document-writer) to create an XML Paper Specification (XPS) file instead of printing.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dd419-112"><xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType>이 항목에서 설명 하는 WPF의 컨트롤은 <xref:System.Windows.Forms.PrintDialog?displayProperty=nameWithType> Windows Forms 구성 요소와 혼동 해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd419-112">The <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType> control of WPF, which is discussed in this topic, should not be confused with the <xref:System.Windows.Forms.PrintDialog?displayProperty=nameWithType> component of Windows Forms.</span></span>  
  
 <span data-ttu-id="dd419-113">엄격 하 게 말하면 <xref:System.Windows.Controls.PrintDialog.PrintDocument%2A> 대화 상자를 열지 않고 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd419-113">Strictly speaking, you can use the <xref:System.Windows.Controls.PrintDialog.PrintDocument%2A> method without ever opening the dialog.</span></span> <span data-ttu-id="dd419-114">따라서 컨트롤을 보이지 않는 인쇄 구성 요소로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd419-114">In that sense, the control can be used as an unseen printing component.</span></span> <span data-ttu-id="dd419-115">그러나 성능상의 이유로 <xref:System.Printing.PrintQueue.AddJob%2A> 메서드 또는의 여러 및 메서드 중 하나를 사용 하는 것이 좋습니다 <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> <xref:System.Windows.Xps.XpsDocumentWriter> .</span><span class="sxs-lookup"><span data-stu-id="dd419-115">But for performance reasons, it would be better to use either the <xref:System.Printing.PrintQueue.AddJob%2A> method or one of the many <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> and <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> methods of the <xref:System.Windows.Xps.XpsDocumentWriter>.</span></span> <span data-ttu-id="dd419-116">이에 대 한 자세한 내용은 [프로그래밍 방식으로 XPS 파일 인쇄](how-to-programmatically-print-xps-files.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dd419-116">For more about this, see [Programmatically Print XPS Files](how-to-programmatically-print-xps-files.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd419-117">추가 정보</span><span class="sxs-lookup"><span data-stu-id="dd419-117">See also</span></span>

- <xref:System.Windows.Controls.PrintDialog>
- [<span data-ttu-id="dd419-118">WPF의 문서</span><span class="sxs-lookup"><span data-stu-id="dd419-118">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="dd419-119">인쇄 개요</span><span class="sxs-lookup"><span data-stu-id="dd419-119">Printing Overview</span></span>](printing-overview.md)
- [<span data-ttu-id="dd419-120">Microsoft XPS Document Writer</span><span class="sxs-lookup"><span data-stu-id="dd419-120">Microsoft XPS Document Writer</span></span>](/windows/win32/printdocs/microsoft-xps-document-writer)
