---
title: '방법: 읽기 전용 텍스트 상자 만들기'
description: 편집 가능한 Windows Forms 텍스트 상자를 읽기 전용 Windows Forms 입력란으로 변환 하는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [Windows Forms], read-only
- read-only text boxes
- text boxes [Windows Forms], read-only
ms.assetid: 60baa9ab-fa57-44ad-bb7c-61b05aa64296
ms.openlocfilehash: 5baa7c66d5f16560a4ea23861d563b099592957f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619366"
---
# <a name="how-to-create-a-read-only-text-box-windows-forms"></a><span data-ttu-id="86982-103">방법: 읽기 전용 텍스트 상자 만들기(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="86982-103">How to: Create a Read-Only Text Box (Windows Forms)</span></span>

<span data-ttu-id="86982-104">편집 가능한 Windows Forms 텍스트 상자를 읽기 전용 컨트롤로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86982-104">You can transform an editable Windows Forms text box into a read-only control.</span></span> <span data-ttu-id="86982-105">예를 들어 텍스트 상자에는 일반적으로 편집 되지만 응용 프로그램의 상태로 인해 현재는 표시 되지 않는 값이 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86982-105">For example, the text box may display a value that is usually edited but may not be currently, due to the state of the application.</span></span>

## <a name="to-create-a-read-only-text-box"></a><span data-ttu-id="86982-106">읽기 전용 텍스트 상자를 만들려면</span><span class="sxs-lookup"><span data-stu-id="86982-106">To create a read-only text box</span></span>

1. <span data-ttu-id="86982-107"><xref:System.Windows.Forms.TextBox>컨트롤의 <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> 속성을로 설정 `true` 합니다.</span><span class="sxs-lookup"><span data-stu-id="86982-107">Set the <xref:System.Windows.Forms.TextBox> control's <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> property to `true`.</span></span> <span data-ttu-id="86982-108">속성이로 설정 된 `true` 경우 사용자는 변경 내용을 허용 하지 않고 텍스트 상자의 텍스트를 계속 스크롤하고 강조 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86982-108">With the property set to `true`, users can still scroll and highlight text in a text box without allowing changes.</span></span> <span data-ttu-id="86982-109">텍스트 상자에서 **복사** 명령이 작동 하지만 **잘라내기** 및 **붙여넣기** 명령은 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="86982-109">A **Copy** command is functional in a text box, but **Cut** and **Paste** commands are not.</span></span>

    > [!NOTE]
    > <span data-ttu-id="86982-110"><xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A>속성은 런타임에 사용자 상호 작용에만 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="86982-110">The <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> property only affects user interaction at run time.</span></span> <span data-ttu-id="86982-111">런타임에 텍스트 상자의 속성을 변경 하 여 텍스트 상자 콘텐츠를 프로그래밍 방식으로 변경할 수 있습니다 <xref:System.Windows.Forms.TextBox.Text%2A> .</span><span class="sxs-lookup"><span data-stu-id="86982-111">You can still change text box contents programmatically at run time by changing the <xref:System.Windows.Forms.TextBox.Text%2A> property of the text box.</span></span>

## <a name="see-also"></a><span data-ttu-id="86982-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="86982-112">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="86982-113">TextBox 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="86982-113">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="86982-114">방법: Windows Forms TextBox 컨트롤에서 삽입 지점 제어</span><span class="sxs-lookup"><span data-stu-id="86982-114">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="86982-115">방법: Windows Forms TextBox 컨트롤을 사용하여 암호 텍스트 상자 만들기</span><span class="sxs-lookup"><span data-stu-id="86982-115">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="86982-116">방법: 문자열에 인용 부호 넣기</span><span class="sxs-lookup"><span data-stu-id="86982-116">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="86982-117">방법: Windows Forms TextBox 컨트롤에서 텍스트 선택</span><span class="sxs-lookup"><span data-stu-id="86982-117">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="86982-118">방법: Windows Forms TextBox 컨트롤에서 여러 줄 표시</span><span class="sxs-lookup"><span data-stu-id="86982-118">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="86982-119">TextBox 컨트롤</span><span class="sxs-lookup"><span data-stu-id="86982-119">TextBox Control</span></span>](textbox-control-windows-forms.md)
