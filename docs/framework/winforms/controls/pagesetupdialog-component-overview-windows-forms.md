---
title: PageSetupDialog 구성 요소 개요
ms.date: 03/30/2017
f1_keywords:
- PageSetupDialog
helpviewer_keywords:
- Page Setup dialog box [Windows Forms], displaying
- PageSetupDialog component
ms.assetid: 791caacb-a5ca-4fca-bad9-1a5721ad697c
ms.openlocfilehash: a891cb8cc77007d7591d41461c94f61c077eb300
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744337"
---
# <a name="pagesetupdialog-component-overview-windows-forms"></a><span data-ttu-id="86bc5-102">PageSetupDialog 구성 요소 개요(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="86bc5-102">PageSetupDialog Component Overview (Windows Forms)</span></span>

<span data-ttu-id="86bc5-103">Windows Forms <xref:System.Windows.Forms.PageSetupDialog> 구성 요소는 Windows 기반 응용 프로그램에서 인쇄를 위한 페이지 세부 정보를 설정 하는 데 사용 되는 미리 구성 된 대화 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="86bc5-103">The Windows Forms <xref:System.Windows.Forms.PageSetupDialog> component is a pre-configured dialog box used to set page details for printing in Windows-based applications.</span></span> <span data-ttu-id="86bc5-104">Windows 기반 응용 프로그램 내에서이 기능을 사용 하 여 사용자가 직접 대화 상자를 구성 하는 대신 페이지 기본 설정을 지정할 수 있는 간단한 솔루션으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="86bc5-104">Use it within your Windows-based application as a simple solution for users to set page preferences in lieu of configuring your own dialog box.</span></span> <span data-ttu-id="86bc5-105">사용자가 테두리 및 여백 조정, 머리글 및 바닥글, 세로 또는 가로 방향을 설정할 수 있도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86bc5-105">You can enable users to set border and margin adjustments, headers and footers, and portrait or landscape orientation.</span></span> <span data-ttu-id="86bc5-106">표준 Windows 대화 상자를 사용하여 기본 기능이 사용자에게 익숙한 애플리케이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="86bc5-106">By relying on standard Windows dialog boxes, you create applications whose basic functionality is immediately familiar to users.</span></span>

## <a name="key-properties-and-methods"></a><span data-ttu-id="86bc5-107">키 속성 및 메서드</span><span class="sxs-lookup"><span data-stu-id="86bc5-107">Key Properties and Methods</span></span>

<span data-ttu-id="86bc5-108">런타임에 대화 상자를 표시 하려면 <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="86bc5-108">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog at run time.</span></span> <span data-ttu-id="86bc5-109">이 구성 요소에는 단일 페이지 (<xref:System.Drawing.Printing.PrintDocument> 클래스) 또는 문서 (<xref:System.Drawing.Printing.PageSettings> 클래스)와 관련 된 속성을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86bc5-109">This component has properties you can set that relate to either a single page (<xref:System.Drawing.Printing.PrintDocument> class) or any document (<xref:System.Drawing.Printing.PageSettings> class).</span></span> <span data-ttu-id="86bc5-110">또한 <xref:System.Windows.Forms.PageSetupDialog> 구성 요소를 사용 하 여 <xref:System.Drawing.Printing.PrinterSettings> 클래스에 저장 된 특정 프린터 설정을 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86bc5-110">Additionally, the <xref:System.Windows.Forms.PageSetupDialog> component can be used to determine specific printer settings, which are stored in the <xref:System.Drawing.Printing.PrinterSettings> class.</span></span>

<span data-ttu-id="86bc5-111">폼에 추가 되 면 <xref:System.Windows.Forms.PageSetupDialog> 구성 요소가 Visual Studio의 Windows Forms 디자이너 아래쪽에 있는 트레이에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86bc5-111">When it is added to a form, the <xref:System.Windows.Forms.PageSetupDialog> component appears in the tray at the bottom of the Windows Forms Designer in Visual Studio.</span></span>

## <a name="see-also"></a><span data-ttu-id="86bc5-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="86bc5-112">See also</span></span>

- <xref:System.Windows.Forms.PageSetupDialog>
- [<span data-ttu-id="86bc5-113">PageSetupDialog 구성 요소</span><span class="sxs-lookup"><span data-stu-id="86bc5-113">PageSetupDialog Component</span></span>](pagesetupdialog-component-windows-forms.md)
