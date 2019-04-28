---
title: '방법: 컨트롤에 투명한 배경 적용'
ms.date: 03/30/2017
helpviewer_keywords:
- transparent backgrounds [Windows Forms], custom controls
- custom controls [Windows Forms], transparent background
- transparency [Windows Forms], Windows Forms custom controls
ms.assetid: 32433e63-f4e9-4305-9857-6de3edeb944a
ms.openlocfilehash: 671075973793d7fbf0b70ce77428a0a632305b9c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61941338"
---
# <a name="how-to-give-your-control-a-transparent-background"></a><span data-ttu-id="5ad27-102">방법: 컨트롤에 투명한 배경 적용</span><span class="sxs-lookup"><span data-stu-id="5ad27-102">How to: Give Your Control a Transparent Background</span></span>
<span data-ttu-id="5ad27-103">.NET Framework의 이전 버전에서는 양식 생성자에 먼저 <xref:System.Windows.Forms.Control.SetStyle%2A> 메서드를 설정하지 않으면 컨트롤이 투명 배경색 설정을 지원하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="5ad27-103">In earlier versions of the .NET Framework, controls didn't support setting transparent backcolors without first setting the <xref:System.Windows.Forms.Control.SetStyle%2A> method in the forms's constructor.</span></span> <span data-ttu-id="5ad27-104">현재 프레임워크 버전에서는 대부분의 컨트롤에 대한 배경색을 디자인 타임에 <xref:System.Drawing.Color.Transparent%2A> 속성 **창 또는 양식 생성자의 코드에서** 으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ad27-104">In the current framework version, the backcolor for most controls can be set to <xref:System.Drawing.Color.Transparent%2A> in the **Properties** window at design time, or in code in the form's constructor.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5ad27-105">Windows Forms 컨트롤은 진정한 투명성을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5ad27-105">Windows Forms controls do not support true transparency.</span></span> <span data-ttu-id="5ad27-106">투명한 Windows Forms 컨트롤의 배경은 해당 부모가 색칠합니다.</span><span class="sxs-lookup"><span data-stu-id="5ad27-106">The background of a transparent Windows Forms control is painted by its parent.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5ad27-107"><xref:System.Windows.Controls.Button> 속성이 <xref:System.Windows.Forms.ButtonBase.BackColor%2A> 으로 설정된 경우에도 <xref:System.Drawing.Color.Transparent%2A>컨트롤은 투명한 배경색을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5ad27-107">The <xref:System.Windows.Controls.Button> control doesn't support a transparent backcolor even when the <xref:System.Windows.Forms.ButtonBase.BackColor%2A> property is set to <xref:System.Drawing.Color.Transparent%2A>.</span></span>  
  
### <a name="to-give-your-control-a-transparent-backcolor"></a><span data-ttu-id="5ad27-108">컨트롤에 투명한 배경색을 적용하려면</span><span class="sxs-lookup"><span data-stu-id="5ad27-108">To give your control a transparent backcolor</span></span>  
  
- <span data-ttu-id="5ad27-109">속성 창에서 <xref:System.Windows.Forms.ButtonBase.BackColor%2A> 속성을 선택하고 <xref:System.Drawing.Color.Transparent%2A>으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5ad27-109">In the Properties window, choose the <xref:System.Windows.Forms.ButtonBase.BackColor%2A> property and set it to <xref:System.Drawing.Color.Transparent%2A></span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ad27-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="5ad27-110">See also</span></span>

- <xref:System.Drawing.Color.FromArgb%2A>
- [<span data-ttu-id="5ad27-111">.NET Framework에서 사용자 지정 Windows Forms 컨트롤 개발</span><span class="sxs-lookup"><span data-stu-id="5ad27-111">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)
- [<span data-ttu-id="5ad27-112">관리되는 그래픽 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="5ad27-112">Using Managed Graphics Classes</span></span>](../advanced/using-managed-graphics-classes.md)
- [<span data-ttu-id="5ad27-113">방법: 불투명 및 반투명 선 그리기</span><span class="sxs-lookup"><span data-stu-id="5ad27-113">How to: Draw Opaque and Semitransparent Lines</span></span>](../advanced/how-to-draw-opaque-and-semitransparent-lines.md)
