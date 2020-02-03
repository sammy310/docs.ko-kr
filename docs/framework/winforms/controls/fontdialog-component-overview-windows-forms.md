---
title: FontDialog 구성 요소 개요
ms.date: 03/30/2017
f1_keywords:
- FontDialog
helpviewer_keywords:
- Font dialog box [Windows Forms], Windows Forms
- Font dialog box
- FontDialog component [Windows Forms], about FontDialog component
ms.assetid: daf46e57-1b4b-4b7a-bad0-b50ca7ba75dc
ms.openlocfilehash: 664b756dc068ca283e4f43edbdd0f3266f5d1142
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745696"
---
# <a name="fontdialog-component-overview-windows-forms"></a><span data-ttu-id="a46e5-102">FontDialog 구성 요소 개요(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="a46e5-102">FontDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="a46e5-103">Windows Forms <xref:System.Windows.Forms.FontDialog> 구성 요소는 시스템에 현재 설치 되어 있는 글꼴을 표시 하는 데 사용 되는 표준 Windows **글꼴** 대화 상자 인 미리 구성 된 대화 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="a46e5-103">The Windows Forms <xref:System.Windows.Forms.FontDialog> component is a pre-configured dialog box, which is the standard Windows **Font** dialog box used to expose the fonts that are currently installed on the system.</span></span> <span data-ttu-id="a46e5-104">사용자 고유의 대화 상자를 구성 하는 대신 글꼴 선택을 위한 간단한 솔루션인 Windows 기반 응용 프로그램 내에서이 기능을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a46e5-104">Use it within your Windows-based application as a simple solution for font selection in lieu of configuring your own dialog box.</span></span>  
  
 <span data-ttu-id="a46e5-105">기본적으로 대화 상자에는 글꼴, 글꼴 스타일 및 크기에 대 한 목록 상자가 표시 됩니다. 취소선, 밑줄 등의 효과에 대 한 확인란 스크립트에 대 한 드롭다운 목록 그리고 글꼴이 표시 되는 방법에 대 한 샘플입니다.</span><span class="sxs-lookup"><span data-stu-id="a46e5-105">By default, the dialog box shows list boxes for Font, Font style, and Size; check boxes for effects like Strikeout and Underline; a drop-down list for Script; and a sample of how the font will appear.</span></span> <span data-ttu-id="a46e5-106">스크립트는 지정 된 글꼴에 사용할 수 있는 다른 문자 스크립트 (예: 히브리어 또는 일본어)를 참조 합니다. 글꼴 대화 상자를 표시 하려면 <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="a46e5-106">(Script refers to different character scripts that are available for a given font, for example, Hebrew or Japanese.) To display the font dialog box, call the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="a46e5-107">키 속성</span><span class="sxs-lookup"><span data-stu-id="a46e5-107">Key Properties</span></span>  
 <span data-ttu-id="a46e5-108">구성 요소에는 모양을 구성 하는 다양 한 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a46e5-108">The component has a number of properties that configure its appearance.</span></span> <span data-ttu-id="a46e5-109">대화 상자 선택 항목을 설정 하는 속성은 <xref:System.Windows.Forms.FontDialog.Font%2A> <xref:System.Windows.Forms.FontDialog.Color%2A>됩니다.</span><span class="sxs-lookup"><span data-stu-id="a46e5-109">The properties that set the dialog-box selections are <xref:System.Windows.Forms.FontDialog.Font%2A> and <xref:System.Windows.Forms.FontDialog.Color%2A>.</span></span> <span data-ttu-id="a46e5-110"><xref:System.Windows.Forms.FontDialog.Font%2A> 속성은 글꼴, 스타일, 크기, 스크립트 및 효과를 설정 합니다. 예를 들어 `Arial, 10pt, style=Italic, Strikeout`합니다.</span><span class="sxs-lookup"><span data-stu-id="a46e5-110">The <xref:System.Windows.Forms.FontDialog.Font%2A> property sets the font, style, size, script, and effects; for example, `Arial, 10pt, style=Italic, Strikeout`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a46e5-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a46e5-111">See also</span></span>

- <xref:System.Windows.Forms.FontDialog>
- [<span data-ttu-id="a46e5-112">FontDialog 구성 요소</span><span class="sxs-lookup"><span data-stu-id="a46e5-112">FontDialog Component</span></span>](fontdialog-component-windows-forms.md)
