---
title: TableLayoutPanel 컨트롤 개요
ms.date: 03/30/2017
f1_keywords:
- TableLayoutPanel
helpviewer_keywords:
- controls [Windows Forms], resizing
- resizable controls [Windows Forms]
- Windows Forms controls, proportional resizing
- Windows Forms, proportional resizing of controls
- layout [Windows Forms], TableLayoutPanel control
- TableLayoutPanel control [Windows Forms], about TableLayoutPanel control
ms.assetid: 337661c8-61cb-44ee-93e0-3662bddec327
ms.openlocfilehash: 57a57b9f888f2fc46eddba5b97b9e833a7e9f028
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59134019"
---
# <a name="tablelayoutpanel-control-overview"></a><span data-ttu-id="82c5c-102">TableLayoutPanel 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="82c5c-102">TableLayoutPanel Control Overview</span></span>
<span data-ttu-id="82c5c-103"><xref:System.Windows.Forms.TableLayoutPanel> 컨트롤은 해당 내용을 표에 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="82c5c-103">The <xref:System.Windows.Forms.TableLayoutPanel> control arranges its contents in a grid.</span></span> <span data-ttu-id="82c5c-104">레이아웃이 디자인 타임과 런타임에 모두 수행되므로 애플리케이션 환경이 변경되면 동적으로 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82c5c-104">Because the layout is performed both at design time and run time, it can change dynamically as the application environment changes.</span></span> <span data-ttu-id="82c5c-105">따라서 패널의 컨트롤이 비례적으로 크기를 조정할 수 있으므로 지역화로 인한 부모 컨트롤 크기 조정이나 텍스트 길이 변경과 같은 변경 내용에 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82c5c-105">This gives the controls in the panel the ability to proportionally resize, so they can respond to changes such as the parent control resizing or text length changing due to localization.</span></span>  
  
 <span data-ttu-id="82c5c-106">Windows Forms 컨트롤은 <xref:System.Windows.Forms.TableLayoutPanel>의 다른 인스턴스를 포함하여 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤의 자식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82c5c-106">Any Windows Forms control can be a child of the <xref:System.Windows.Forms.TableLayoutPanel> control, including other instances of <xref:System.Windows.Forms.TableLayoutPanel>.</span></span> <span data-ttu-id="82c5c-107">따라서 런타임에 변경 내용에 맞게 조정되는 정교한 레이아웃을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82c5c-107">This allows you to construct sophisticated layouts that adapt to changes at run time.</span></span>  
  
 <span data-ttu-id="82c5c-108"><xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A>, <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A> 및 <xref:System.Windows.Forms.TableLayoutPanel.GrowStyle%2A> 속성의 값에 따라 새 컨트롤을 추가할 때 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤이 이를 수용하기 위해 확장될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82c5c-108">The <xref:System.Windows.Forms.TableLayoutPanel> control can expand to accommodate new controls when they are added, depending on the value of the <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A>, <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A>, and <xref:System.Windows.Forms.TableLayoutPanel.GrowStyle%2A> properties.</span></span> <span data-ttu-id="82c5c-109"><xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A> 또는 <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A> 속성의 값을 0으로 설정하면 <xref:System.Windows.Forms.TableLayoutPanel>이 해당 방향으로 바인딩되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="82c5c-109">Setting either the <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A> or <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A> property to a value of 0 specifies that the <xref:System.Windows.Forms.TableLayoutPanel> will be unbound in the corresponding direction.</span></span>  
  
 <span data-ttu-id="82c5c-110"><xref:System.Windows.Forms.TableLayoutPanel> 컨트롤이 자식 컨트롤로 가득 찬 후에 확장 방향(가로 또는 세로)을 제어할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82c5c-110">You can also control the direction of expansion (horizontal or vertical) after the <xref:System.Windows.Forms.TableLayoutPanel> control is full of child controls.</span></span> <span data-ttu-id="82c5c-111">기본적으로 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤은 행을 추가하여 아래로 확장됩니다.</span><span class="sxs-lookup"><span data-stu-id="82c5c-111">By default, the <xref:System.Windows.Forms.TableLayoutPanel> control expands downward by adding rows.</span></span>  
  
 <span data-ttu-id="82c5c-112">기본 동작과 다르게 동작하는 행과 열을 원하는 경우 <xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A> 및 <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> 속성을 사용하여 행과 열의 속성을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82c5c-112">If you want rows and columns that behave differently from the default behavior, you can control the properties of rows and columns by using the <xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A> and <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> properties.</span></span> <span data-ttu-id="82c5c-113">행 또는 열의 속성을 개별적으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82c5c-113">You can set the properties of rows or columns individually.</span></span>  
  
 <span data-ttu-id="82c5c-114"><xref:System.Windows.Forms.TableLayoutPanel> 컨트롤은 자식 컨트롤에 `Cell`, `Column`, `Row`, `ColumnSpan` 및 `RowSpan` 속성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="82c5c-114">The <xref:System.Windows.Forms.TableLayoutPanel> control adds the following properties to its child controls: `Cell`, `Column`, `Row`, `ColumnSpan`, and `RowSpan`.</span></span>  
  
 <span data-ttu-id="82c5c-115">자식 컨트롤의 `ColumnSpan` 또는 `RowSpan` 속성을 설정하여 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤에 셀을 병합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82c5c-115">You can merge cells in the <xref:System.Windows.Forms.TableLayoutPanel> control by setting the `ColumnSpan` or `RowSpan` properties on a child control.</span></span>  
  
1.  [<span data-ttu-id="82c5c-116">방법: TableLayoutPanel 컨트롤에서 컨트롤 맞춤 및 늘이기</span><span class="sxs-lookup"><span data-stu-id="82c5c-116">How to: Align and Stretch a Control in a TableLayoutPanel Control</span></span>](how-to-align-and-stretch-a-control-in-a-tablelayoutpanel-control.md)  
  
2.  [<span data-ttu-id="82c5c-117">방법: TableLayoutPanel 컨트롤에서 행 및 열 확장</span><span class="sxs-lookup"><span data-stu-id="82c5c-117">How to: Span Rows and Columns in a TableLayoutPanel Control</span></span>](how-to-span-rows-and-columns-in-a-tablelayoutpanel-control.md)  
  
3.  [<span data-ttu-id="82c5c-118">방법: TableLayoutPanel 컨트롤에서 열 및 행 편집</span><span class="sxs-lookup"><span data-stu-id="82c5c-118">How to: Edit Columns and Rows in a TableLayoutPanel Control</span></span>](how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control.md)  
  
4.  [<span data-ttu-id="82c5c-119">연습: TableLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="82c5c-119">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  
  
## <a name="see-also"></a><span data-ttu-id="82c5c-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="82c5c-120">See also</span></span>

- <xref:System.Windows.Forms.FlowLayoutPanel>
- <xref:System.Windows.Forms.TableLayoutSettings>
- [<span data-ttu-id="82c5c-121">방법: 지역화에 효과적으로 대응하는 Windows Forms 레이아웃 디자인</span><span class="sxs-lookup"><span data-stu-id="82c5c-121">How to: Design a Windows Forms Layout that Responds Well to Localization</span></span>](how-to-design-a-windows-forms-layout-that-responds-well-to-localization.md)
- [<span data-ttu-id="82c5c-122">방법: 데이터 입력에 맞게 크기 조정 가능한 Windows Form 만들기</span><span class="sxs-lookup"><span data-stu-id="82c5c-122">How to: Create a Resizable Windows Form for Data Entry</span></span>](how-to-create-a-resizable-windows-form-for-data-entry.md)
- [<span data-ttu-id="82c5c-123">TableLayoutPanel 컨트롤에 대한 모범 사례</span><span class="sxs-lookup"><span data-stu-id="82c5c-123">Best Practices for the TableLayoutPanel Control</span></span>](best-practices-for-the-tablelayoutpanel-control.md)
