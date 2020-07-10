---
title: 컨트롤의 여백 및 안쪽 여백
description: 여백 및 안쪽 여백 속성을 사용 하 여 Windows Form 컨트롤의 여백과 안쪽 여백을 추가 하는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
helpviewer_keywords:
- Padding property [Windows Forms]
- layout [Windows Forms], margins and padding
- Windows Forms, layout
- Margin property [Windows Forms]
ms.assetid: 3781b5a1-3085-4072-bed0-44670c23ffdc
ms.openlocfilehash: 4279f39bb4f89fbda8be472f49c8e60853abcac6
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174486"
---
# <a name="margin-and-padding-in-windows-forms-controls"></a><span data-ttu-id="b5985-103">Windows Forms 컨트롤의 여백 및 안쪽 여백</span><span class="sxs-lookup"><span data-stu-id="b5985-103">Margin and Padding in Windows Forms Controls</span></span>
<span data-ttu-id="b5985-104">폼의 정확한 컨트롤 배치는 많은 애플리케이션에서 우선 순위가 높습니다.</span><span class="sxs-lookup"><span data-stu-id="b5985-104">Precise placement of controls on your form is a high priority for many applications.</span></span> <span data-ttu-id="b5985-105"><xref:System.Windows.Forms?displayProperty=nameWithType> 네임스페이스는 이 목적을 위한 다양한 레이아웃 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b5985-105">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace gives you many layout features to accomplish this.</span></span> <span data-ttu-id="b5985-106">가장 중요한 두 가지 기능은 <xref:System.Windows.Forms.Control.Margin%2A> 및 <xref:System.Windows.Forms.Control.Padding%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="b5985-106">Two of the most important are the <xref:System.Windows.Forms.Control.Margin%2A> and <xref:System.Windows.Forms.Control.Padding%2A> properties.</span></span>  
  
 <span data-ttu-id="b5985-107"><xref:System.Windows.Forms.Control.Margin%2A> 속성은 다른 컨트롤을 컨트롤의 테두리에서 지정된 거리에 유지하는 컨트롤 주위의 공간을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b5985-107">The <xref:System.Windows.Forms.Control.Margin%2A> property defines the space around the control that keeps other controls a specified distance from the control's borders.</span></span>  
  
 <span data-ttu-id="b5985-108"><xref:System.Windows.Forms.Control.Padding%2A> 속성은 컨트롤의 내용(예: <xref:System.Windows.Forms.Control.Text%2A> 속성의 값)을 컨트롤의 테두리에서 지정된 거리에 유지하는 컨트롤 내부의 공간을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b5985-108">The <xref:System.Windows.Forms.Control.Padding%2A> property defines the space in the interior of a control that keeps the control's content (for example, the value of its <xref:System.Windows.Forms.Control.Text%2A> property) a specified distance from the control's borders.</span></span>  
  
 <span data-ttu-id="b5985-109">다음 그림에서는 컨트롤의 <xref:System.Windows.Forms.Control.Padding%2A> 및 <xref:System.Windows.Forms.Control.Margin%2A> 속성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b5985-109">The following illustration shows the <xref:System.Windows.Forms.Control.Padding%2A> and <xref:System.Windows.Forms.Control.Margin%2A> properties on a control.</span></span>  
  
 <span data-ttu-id="b5985-110">![Windows Forms 컨트롤의 여백 및 안쪽 여백](./media/vs-winformpadmargin.gif "VS_WinFormPadMargin")</span><span class="sxs-lookup"><span data-stu-id="b5985-110">![Padding And Margin for Windows Forms Controls](./media/vs-winformpadmargin.gif "VS_WinFormPadMargin")</span></span>  
  
 <span data-ttu-id="b5985-111">Visual Studio에서는 디자인 타임에 이 기능을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="b5985-111">There is design-time support for this feature in Visual Studio.</span></span> <span data-ttu-id="b5985-112">또한 [연습: 안쪽 여백, 여백 및 AutoSize 속성을 사용 하 여 Windows Forms 컨트롤 레이아웃](windows-forms-controls-padding-autosize.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b5985-112">Also see [Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property](windows-forms-controls-padding-autosize.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5985-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b5985-113">See also</span></span>

- <xref:System.Windows.Forms.Control.AutoSize%2A>
- <xref:System.Windows.Forms.Control.Margin%2A>
- <xref:System.Windows.Forms.Control.Padding%2A>
- <xref:System.Windows.Forms.Control.LayoutEngine%2A>
- <xref:System.Windows.Forms.TableLayoutPanel>
- <xref:System.Windows.Forms.FlowLayoutPanel>
