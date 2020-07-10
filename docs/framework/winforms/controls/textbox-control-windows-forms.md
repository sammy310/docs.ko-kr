---
title: TextBox 컨트롤
description: 편집 가능한 텍스트에 대 한 사용을 비롯 하 여 읽기 전용으로 설정 하는 Windows Forms TextBox 컨트롤의 다양 한 측면에 대해 알아봅니다.
ms.date: 03/30/2017
helpviewer_keywords:
- text boxes
- TextBox control [Windows Forms]
ms.assetid: e5a06987-8aec-4271-b196-2245ba992d62
ms.openlocfilehash: 026f6d2653e41dabd3db7490660b6ce19846d397
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174447"
---
# <a name="textbox-control-windows-forms"></a><span data-ttu-id="c7c6b-103">TextBox 컨트롤(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="c7c6b-103">TextBox Control (Windows Forms)</span></span>
<span data-ttu-id="c7c6b-104">Windows Forms 텍스트 상자는 사용자의 입력을 가져오거나 텍스트를 표시 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7c6b-104">Windows Forms text boxes are used to get input from the user or to display text.</span></span> <span data-ttu-id="c7c6b-105">`TextBox`컨트롤은 읽기 전용으로 만들 수도 있지만 일반적으로 편집 가능한 텍스트에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7c6b-105">The `TextBox` control is generally used for editable text, although it can also be made read-only.</span></span> <span data-ttu-id="c7c6b-106">텍스트 상자는 여러 줄을 표시 하 고 텍스트를 컨트롤의 크기로 래핑하고 기본 서식 지정을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7c6b-106">Text boxes can display multiple lines, wrap text to the size of the control, and add basic formatting.</span></span> <span data-ttu-id="c7c6b-107">`TextBox`컨트롤은 컨트롤에 표시 되거나 입력 되는 텍스트에 대해 단일 형식을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7c6b-107">The `TextBox` control allows a single format for text displayed or entered in the control.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c7c6b-108">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="c7c6b-108">In This Section</span></span>  
 [<span data-ttu-id="c7c6b-109">TextBox 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="c7c6b-109">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)  
 <span data-ttu-id="c7c6b-110">이 컨트롤의 정의와 주요 기능 및 속성을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c7c6b-110">Explains what this control is and its key features and properties.</span></span>  
  
 [<span data-ttu-id="c7c6b-111">방법: Windows Forms TextBox 컨트롤에서 삽입 지점 제어</span><span class="sxs-lookup"><span data-stu-id="c7c6b-111">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)  
 <span data-ttu-id="c7c6b-112">편집 컨트롤이 먼저 포커스를 얻을 때 삽입 지점이 표시 되는 위치를 지정 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7c6b-112">Gives directions for specifying where the insertion point appears when an edit control first gets the focus.</span></span>  
  
 [<span data-ttu-id="c7c6b-113">방법: Windows Forms TextBox 컨트롤을 사용하여 암호 텍스트 상자 만들기</span><span class="sxs-lookup"><span data-stu-id="c7c6b-113">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)  
 <span data-ttu-id="c7c6b-114">텍스트 상자에 입력 된 내용을 숨기는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7c6b-114">Explains how to conceal what is typed into a text box.</span></span>  
  
 [<span data-ttu-id="c7c6b-115">방법: 읽기 전용 텍스트 상자 만들기</span><span class="sxs-lookup"><span data-stu-id="c7c6b-115">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)  
 <span data-ttu-id="c7c6b-116">텍스트 상자의 내용이 변경 되는 것을 방지 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7c6b-116">Describes how to prevent the contents of a text box from being changed.</span></span>  
  
 [<span data-ttu-id="c7c6b-117">방법: 문자열에 인용 부호 넣기</span><span class="sxs-lookup"><span data-stu-id="c7c6b-117">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)  
 <span data-ttu-id="c7c6b-118">텍스트 상자의 문자열에 따옴표를 추가 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7c6b-118">Explains adding quotation marks to a string in a text box.</span></span>  
  
 [<span data-ttu-id="c7c6b-119">방법: Windows Forms TextBox 컨트롤에서 텍스트 선택</span><span class="sxs-lookup"><span data-stu-id="c7c6b-119">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)  
 <span data-ttu-id="c7c6b-120">텍스트 상자에서 텍스트를 강조 표시 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7c6b-120">Explains how to highlight text in a text box.</span></span>  
  
 [<span data-ttu-id="c7c6b-121">방법: Windows Forms TextBox 컨트롤에서 여러 줄 표시</span><span class="sxs-lookup"><span data-stu-id="c7c6b-121">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)  
 <span data-ttu-id="c7c6b-122">텍스트 상자를 스크롤 가능 하 게 만드는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7c6b-122">Describes how to make a text box scrollable.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="c7c6b-123">참조</span><span class="sxs-lookup"><span data-stu-id="c7c6b-123">Reference</span></span>  
 <span data-ttu-id="c7c6b-124"><xref:System.Windows.Forms.TextBox> 클래스</span><span class="sxs-lookup"><span data-stu-id="c7c6b-124"><xref:System.Windows.Forms.TextBox> class</span></span>  
 <span data-ttu-id="c7c6b-125">이 클래스를 설명하고 모든 해당 멤버의 링크를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="c7c6b-125">Describes this class and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c7c6b-126">관련 단원</span><span class="sxs-lookup"><span data-stu-id="c7c6b-126">Related Sections</span></span>  
 [<span data-ttu-id="c7c6b-127">Windows Forms에 사용할 수 있는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="c7c6b-127">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="c7c6b-128">사용 방법에 대한 정보 링크를 포함하는 Windows Forms 컨트롤의 전체 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c7c6b-128">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>
