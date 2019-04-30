---
title: TableLayoutPanel 컨트롤의 AutoSize 동작
ms.date: 03/30/2017
helpviewer_keywords:
- AutoSize property [Windows Forms], tableLayoutPanel control
- controls [Windows Forms], sizing
- localizing forms
- layout [Windows Forms], AutoSize
- sizing [Windows Forms], automatic
- TableLayoutPanel control [Windows Forms], AutoSize behavior
- automatic sizing
- AutoSizeMode property
ms.assetid: 9233e0c3-2fa6-405e-8701-959479b1250e
ms.openlocfilehash: 466edeee5f45ec72ef265ef4855049c7852641b0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61954351"
---
# <a name="autosize-behavior-in-the-tablelayoutpanel-control"></a><span data-ttu-id="cba6c-102">TableLayoutPanel 컨트롤의 AutoSize 동작</span><span class="sxs-lookup"><span data-stu-id="cba6c-102">AutoSize Behavior in the TableLayoutPanel Control</span></span>
## <a name="distinct-autosize-behaviors"></a><span data-ttu-id="cba6c-103">고유 AutoSize 동작</span><span class="sxs-lookup"><span data-stu-id="cba6c-103">Distinct AutoSize Behaviors</span></span>  
 <span data-ttu-id="cba6c-104"><xref:System.Windows.Forms.TableLayoutPanel> 컨트롤은 다음과 같은 방법으로 자동 크기 조정 동작을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="cba6c-104">The <xref:System.Windows.Forms.TableLayoutPanel> control supports automatic sizing behavior in the following ways:</span></span>  
  
- <span data-ttu-id="cba6c-105">통해 여 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성</span><span class="sxs-lookup"><span data-stu-id="cba6c-105">Through the <xref:System.Windows.Forms.Control.AutoSize%2A> property;</span></span>  
  
- <span data-ttu-id="cba6c-106">통해 합니다 <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> 속성에는 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤의 열 및 행 스타일입니다.</span><span class="sxs-lookup"><span data-stu-id="cba6c-106">Through the <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> property on the <xref:System.Windows.Forms.TableLayoutPanel> control’s column and row styles.</span></span>  
  
### <a name="the-autosize-property-with-row-and-column-styles"></a><span data-ttu-id="cba6c-107">행과 열 스타일을 사용 하 여 자동 크기 조정 속성</span><span class="sxs-lookup"><span data-stu-id="cba6c-107">The AutoSize Property with Row and Column Styles</span></span>  
 <span data-ttu-id="cba6c-108">다음 표에서 간의 상호 작용 합니다 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성 및 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤의 열 및 행 스타일입니다.</span><span class="sxs-lookup"><span data-stu-id="cba6c-108">The following table describes the interaction between the <xref:System.Windows.Forms.Control.AutoSize%2A> property and the <xref:System.Windows.Forms.TableLayoutPanel> control’s column and row styles.</span></span>  
  
|<span data-ttu-id="cba6c-109">자동 크기 조정 설정</span><span class="sxs-lookup"><span data-stu-id="cba6c-109">AutoSize setting</span></span>|<span data-ttu-id="cba6c-110">스타일 상호 작용</span><span class="sxs-lookup"><span data-stu-id="cba6c-110">Style interaction</span></span>|  
|----------------------|-----------------------|  
|`false`|<span data-ttu-id="cba6c-111"><xref:System.Windows.Forms.TableLayoutPanel> 컨트롤 왼쪽에서 오른쪽으로 진행 하 고 다음 순서 대로 또는 열 이나 행에 대 한 공간을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="cba6c-111">The <xref:System.Windows.Forms.TableLayoutPanel> control proceeds from left to right, and allocates space for the column or row or in the following order.</span></span><br /><br /> <span data-ttu-id="cba6c-112">1.  경우는 <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> 속성이 <xref:System.Windows.Forms.SizeType.Absolute>, 지정 된 픽셀 수 <xref:System.Windows.Forms.ColumnStyle.Width%2A> 또는 <xref:System.Windows.Forms.RowStyle.Height%2A> 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cba6c-112">1.  If the <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> property is set to <xref:System.Windows.Forms.SizeType.Absolute>, the number of pixels specified by <xref:System.Windows.Forms.ColumnStyle.Width%2A> or <xref:System.Windows.Forms.RowStyle.Height%2A> is allocated.</span></span><br /><span data-ttu-id="cba6c-113">2.  경우는 <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> 속성이 <xref:System.Windows.Forms.SizeType.AutoSize>, 자식 컨트롤에 의해 반환 되는 픽셀 수가 <xref:System.Windows.Forms.Control.GetPreferredSize%2A> 메서드 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cba6c-113">2.  If the <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> property is set to <xref:System.Windows.Forms.SizeType.AutoSize>, the number of pixels returned by the child control’s <xref:System.Windows.Forms.Control.GetPreferredSize%2A> method is allocated.</span></span><br /><span data-ttu-id="cba6c-114">3.  모든 공백 뒤 <xref:System.Windows.Forms.SizeType.Absolute> 하 고 <xref:System.Windows.Forms.SizeType.AutoSize> 열 또는 행 할당 열 또는 행 <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> 로 <xref:System.Windows.Forms.SizeType.Percent> 남은 공간을 비례적으로 할당 하는 데 사용 됩니다</span><span class="sxs-lookup"><span data-stu-id="cba6c-114">3.  After space for all <xref:System.Windows.Forms.SizeType.Absolute> and <xref:System.Windows.Forms.SizeType.AutoSize> columns or rows is allocated, any columns or rows with <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> set to <xref:System.Windows.Forms.SizeType.Percent> are used to proportionally allocate the remaining free space</span></span>|  
|`true`|<span data-ttu-id="cba6c-115">예외를 사용 하 여 이전 상호 작용 비슷합니다는 <xref:System.Windows.Forms.SizeType.Percent> 열 또는 행 자동 크기 조정 aspect를 획득 합니다.</span><span class="sxs-lookup"><span data-stu-id="cba6c-115">Similar to the previous interaction, with the exception that <xref:System.Windows.Forms.SizeType.Percent> columns or rows acquire an automatic sizing aspect.</span></span><br /><br /> <span data-ttu-id="cba6c-116">합니다 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤이 확장 가능한 공간을 만들려면 행 이나 열의 있도록 없는 열 또는 행 <xref:System.Windows.Forms.SizeType.Percent> 스타일 해당 콘텐츠를 자릅니다.</span><span class="sxs-lookup"><span data-stu-id="cba6c-116">The <xref:System.Windows.Forms.TableLayoutPanel> control expands the column or row to create adequate free space, so that no column or row with <xref:System.Windows.Forms.SizeType.Percent> styling clips its contents.</span></span> <span data-ttu-id="cba6c-117">합니다 <xref:System.Windows.Forms.TableLayoutPanel> 비율에 따라 새 공간을 할당 하는 컨트롤을 <xref:System.Windows.Forms.ColumnStyle.Width%2A> 또는 <xref:System.Windows.Forms.RowStyle.Height%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="cba6c-117">The <xref:System.Windows.Forms.TableLayoutPanel> control allocates the new space proportionally according to the <xref:System.Windows.Forms.ColumnStyle.Width%2A> or <xref:System.Windows.Forms.RowStyle.Height%2A> property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cba6c-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="cba6c-118">See also</span></span>

- <xref:System.Windows.Forms.TableLayoutPanel>
- [<span data-ttu-id="cba6c-119">TableLayoutPanel 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="cba6c-119">TableLayoutPanel Control Overview</span></span>](tablelayoutpanel-control-overview.md)
