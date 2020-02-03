---
title: SaveFileDialog 구성 요소 개요
ms.date: 03/30/2017
f1_keywords:
- SaveFileDialog
helpviewer_keywords:
- Save File dialog box [Windows Forms], displaying
- SaveFileDialog component [Windows Forms], about SaveFileDialog
ms.assetid: be7a625f-46fd-4d06-9985-b613dcbf9bd2
ms.openlocfilehash: 7609c29b7e932ecee7dc8a289617094bd8d480e2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743105"
---
# <a name="savefiledialog-component-overview-windows-forms"></a><span data-ttu-id="88d04-102">SaveFileDialog 구성 요소 개요(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="88d04-102">SaveFileDialog Component Overview (Windows Forms)</span></span>

<span data-ttu-id="88d04-103">Windows Forms <xref:System.Windows.Forms.SaveFileDialog> 구성 요소는 미리 구성된 대화 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="88d04-103">The Windows Forms <xref:System.Windows.Forms.SaveFileDialog> component is a pre-configured dialog box.</span></span> <span data-ttu-id="88d04-104">Windows에서 사용 하는 표준 **파일 저장** 대화 상자와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="88d04-104">It is the same as the standard **Save File** dialog box used by Windows.</span></span> <span data-ttu-id="88d04-105"><xref:System.Windows.Forms.CommonDialog> 클래스에서 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="88d04-105">It inherits from the <xref:System.Windows.Forms.CommonDialog> class.</span></span>

## <a name="working-with-the-savefiledialog-component"></a><span data-ttu-id="88d04-106">SaveFileDialog 구성 요소 작업</span><span class="sxs-lookup"><span data-stu-id="88d04-106">Working with the SaveFileDialog Component</span></span>

<span data-ttu-id="88d04-107">사용자가 직접 대화 상자를 구성 하는 대신 사용자가 파일을 저장할 수 있도록 하는 간단한 솔루션으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="88d04-107">Use it as a simple solution for enabling users to save files instead of configuring your own dialog box.</span></span> <span data-ttu-id="88d04-108">표준 Windows 대화 상자를 사용할 경우 사용자가 직접 만든 응용 프로그램의 기본 기능은 사용자에 게 친숙 합니다.</span><span class="sxs-lookup"><span data-stu-id="88d04-108">By relying on standard Windows dialog boxes, the basic functionality of applications you create is immediately familiar to users.</span></span> <span data-ttu-id="88d04-109">그러나 <xref:System.Windows.Forms.SaveFileDialog> 구성 요소를 사용 하는 경우 고유한 파일 저장 논리를 작성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88d04-109">Be aware, however, that when using the <xref:System.Windows.Forms.SaveFileDialog> component, you must write your own file-saving logic.</span></span>

<span data-ttu-id="88d04-110"><xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 메서드를 사용 하 여 런타임에 대화 상자를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88d04-110">You can use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box at run time.</span></span> <span data-ttu-id="88d04-111"><xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> 메서드를 사용 하 여 읽기/쓰기 모드로 파일을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88d04-111">You can open a file in read/write mode using the <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> method.</span></span>

<span data-ttu-id="88d04-112">폼에 추가 되 면 <xref:System.Windows.Forms.SaveFileDialog> 구성 요소가 Visual Studio의 Windows Forms 디자이너 아래쪽에 있는 트레이에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="88d04-112">When it is added to a form, the <xref:System.Windows.Forms.SaveFileDialog> component appears in the tray at the bottom of the Windows Forms Designer in Visual Studio.</span></span>

## <a name="see-also"></a><span data-ttu-id="88d04-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="88d04-113">See also</span></span>

- <xref:System.Windows.Forms.SaveFileDialog>
- [<span data-ttu-id="88d04-114">SaveFileDialog 구성 요소</span><span class="sxs-lookup"><span data-stu-id="88d04-114">SaveFileDialog Component</span></span>](savefiledialog-component-windows-forms.md)
