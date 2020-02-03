---
title: PrintDialog 구성 요소 개요
ms.date: 03/30/2017
f1_keywords:
- PrintDialog
helpviewer_keywords:
- Print dialog box [Windows Forms], displaying
- PrintDialog component [Windows Forms], about PrintDialog component
ms.assetid: 8327b8ac-1017-4b5e-a88b-fea9dd56999c
ms.openlocfilehash: 0ed7f7a1f9770f71b75ae744a056b6943335c852
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728673"
---
# <a name="printdialog-component-overview-windows-forms"></a><span data-ttu-id="f9f59-102">PrintDialog 구성 요소 개요(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="f9f59-102">PrintDialog Component Overview (Windows Forms)</span></span>

<span data-ttu-id="f9f59-103">Windows Forms [PrintDialog](printdialog-component-windows-forms.md) 구성 요소는 프린터를 선택 하 고, 인쇄할 페이지를 선택 하 고, Windows 기반 응용 프로그램에서 다른 인쇄 관련 설정을 결정 하는 데 사용 되는 미리 구성 된 대화 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="f9f59-103">The Windows Forms [PrintDialog](printdialog-component-windows-forms.md) component is a pre-configured dialog box used to select a printer, choose the pages to print, and determine other print-related settings in Windows-based applications.</span></span> <span data-ttu-id="f9f59-104">고유한 대화 상자를 구성하는 대신 이 대화 상자를 프린터 및 인쇄 관련 설정 선택을 위한 간단한 솔루션으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f9f59-104">Use it as a simple solution for printer and print-related settings selection in lieu of configuring your own dialog box.</span></span> <span data-ttu-id="f9f59-105">사용자가 문서를 모두 인쇄 하거나 선택한 페이지 범위를 인쇄 하거나 선택 항목을 인쇄할 수 있도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9f59-105">You can enable users to print many parts of their documents: print all, print a selected page range, or print a selection.</span></span> <span data-ttu-id="f9f59-106">표준 Windows 대화 상자를 사용하여 기본 기능이 사용자에게 익숙한 애플리케이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f9f59-106">By relying on standard Windows dialog boxes, you create applications whose basic functionality is immediately familiar to users.</span></span> <span data-ttu-id="f9f59-107"><xref:System.Windows.Forms.PrintDialog> 구성 요소는 <xref:System.Windows.Forms.CommonDialog> 클래스에서 상속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9f59-107">The <xref:System.Windows.Forms.PrintDialog> component inherits from the <xref:System.Windows.Forms.CommonDialog> class.</span></span>

## <a name="working-with-the-component"></a><span data-ttu-id="f9f59-108">구성 요소 작업</span><span class="sxs-lookup"><span data-stu-id="f9f59-108">Working with the Component</span></span>

<span data-ttu-id="f9f59-109">런타임에 대화 상자를 표시 하려면 <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9f59-109">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box at run time.</span></span> <span data-ttu-id="f9f59-110">이 구성 요소에는 단일 인쇄 작업 (<xref:System.Drawing.Printing.PrintDocument> 클래스) 또는 개별 프린터의 설정 (<xref:System.Drawing.Printing.PrinterSettings> 클래스)과 관련 된 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9f59-110">This component has properties that relate to either a single print job (<xref:System.Drawing.Printing.PrintDocument> class) or the settings of an individual printer (<xref:System.Drawing.Printing.PrinterSettings> class).</span></span> <span data-ttu-id="f9f59-111">그 중 하나는 여러 프린터에서 공유 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9f59-111">Either of these, in turn, may be shared by multiple printers.</span></span>

<span data-ttu-id="f9f59-112">폼에 추가 되 면 <xref:System.Windows.Forms.PrintDialog> 구성 요소가 Visual Studio의 Windows Forms 디자이너 아래쪽에 있는 트레이에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9f59-112">When it is added to a form, the <xref:System.Windows.Forms.PrintDialog> component appears in the tray at the bottom of the Windows Forms Designer in Visual Studio.</span></span>

## <a name="see-also"></a><span data-ttu-id="f9f59-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f9f59-113">See also</span></span>

- <xref:System.Windows.Forms.PrintDialog>
- [<span data-ttu-id="f9f59-114">PrintDialog 구성 요소</span><span class="sxs-lookup"><span data-stu-id="f9f59-114">PrintDialog Component</span></span>](printdialog-component-windows-forms.md)
