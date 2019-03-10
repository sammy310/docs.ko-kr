---
title: PageSetupDialog 구성 요소 개요(Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- PageSetupDialog
helpviewer_keywords:
- Page Setup dialog box [Windows Forms], displaying
- PageSetupDialog component
ms.assetid: 791caacb-a5ca-4fca-bad9-1a5721ad697c
ms.openlocfilehash: 702e9a40652e00cc2f93dd52af29a61a50c90ae0
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57715804"
---
# <a name="pagesetupdialog-component-overview-windows-forms"></a><span data-ttu-id="93553-102">PageSetupDialog 구성 요소 개요(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="93553-102">PageSetupDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="93553-103">Windows Forms <xref:System.Windows.Forms.PageSetupDialog> 구성 요소는 Windows 기반 응용 프로그램에서 인쇄를 위한 페이지 세부 정보를 설정 하는 데 사용 되는 미리 구성 된 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="93553-103">The Windows Forms <xref:System.Windows.Forms.PageSetupDialog> component is a pre-configured dialog box used to set page details for printing in Windows-based applications.</span></span> <span data-ttu-id="93553-104">사용 하 여 응용 프로그램 내에서 Windows 기반 간단한 솔루션으로 사용자에 대 한 고유한 대화 상자를 구성 하는 대신 페이지 기본 설정.</span><span class="sxs-lookup"><span data-stu-id="93553-104">Use it within your Windows-based application as a simple solution for users to set page preferences in lieu of configuring your own dialog box.</span></span> <span data-ttu-id="93553-105">테두리 및 여백, 머리글 및 바닥글 및 세로 또는 가로 방향이 설정 하는 사용자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93553-105">You can enable users to set border and margin adjustments, headers and footers, and portrait or landscape orientation.</span></span> <span data-ttu-id="93553-106">표준 Windows 대화 상자를 사용하여 기본 기능이 사용자에게 익숙한 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="93553-106">By relying on standard Windows dialog boxes, you create applications whose basic functionality is immediately familiar to users.</span></span>  
  
## <a name="key-properties-and-methods"></a><span data-ttu-id="93553-107">키 속성 및 메서드</span><span class="sxs-lookup"><span data-stu-id="93553-107">Key Properties and Methods</span></span>  
 <span data-ttu-id="93553-108">사용 된 <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 런타임에 대화 상자를 표시 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="93553-108">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog at run time.</span></span> <span data-ttu-id="93553-109">이 구성 요소는 단일 페이지에 관련 된 속성을 설정할 수 있습니다 (<xref:System.Drawing.Printing.PrintDocument> 클래스) 또는 모든 문서 (<xref:System.Drawing.Printing.PageSettings> 클래스).</span><span class="sxs-lookup"><span data-stu-id="93553-109">This component has properties you can set that relate to either a single page (<xref:System.Drawing.Printing.PrintDocument> class) or any document (<xref:System.Drawing.Printing.PageSettings> class).</span></span> <span data-ttu-id="93553-110">또한 합니다 <xref:System.Windows.Forms.PageSetupDialog> 구성 요소를 사용 하 여에 저장 되는 특정 프린터 설정을 확인할 수 있습니다는 <xref:System.Drawing.Printing.PrinterSettings> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="93553-110">Additionally, the <xref:System.Windows.Forms.PageSetupDialog> component can be used to determine specific printer settings, which are stored in the <xref:System.Drawing.Printing.PrinterSettings> class.</span></span>  
  
 <span data-ttu-id="93553-111">폼에 추가 될 때를 <xref:System.Windows.Forms.PageSetupDialog> 구성 요소가 Windows Forms 디자이너 아래쪽에 있는 트레이에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="93553-111">When it is added to a form, the <xref:System.Windows.Forms.PageSetupDialog> component appears in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93553-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="93553-112">See also</span></span>
- <xref:System.Windows.Forms.PageSetupDialog>
- [<span data-ttu-id="93553-113">PageSetupDialog 구성 요소</span><span class="sxs-lookup"><span data-stu-id="93553-113">PageSetupDialog Component</span></span>](pagesetupdialog-component-windows-forms.md)
