---
title: TableLayoutPanel 컨트롤
ms.date: 03/30/2017
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms]
- layout [Windows Forms]
- controls [Windows Forms], sizing
- sizing [Windows Forms], automatic
- layout [Windows Forms], TableLayoutPanel control
- automatic sizing
ms.assetid: f55175c6-424e-4782-a86e-3f79c1550235
ms.openlocfilehash: 12b40d4ce47770b3ffe9bfdebca74eca4afd3dd1
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735513"
---
# <a name="tablelayoutpanel-control-windows-forms"></a><span data-ttu-id="4679a-102">TableLayoutPanel 컨트롤(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="4679a-102">TableLayoutPanel Control (Windows Forms)</span></span>
<span data-ttu-id="4679a-103"><xref:System.Windows.Forms.TableLayoutPanel> 컨트롤은 표 형태의 내용을 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="4679a-103">The <xref:System.Windows.Forms.TableLayoutPanel> control arranges its contents in a grid.</span></span> <span data-ttu-id="4679a-104">레이아웃이 디자인 타임과 런타임에 모두 수행되므로 애플리케이션 환경이 변경되면 동적으로 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4679a-104">Because the layout is performed both at design time and run time, it can change dynamically as the application environment changes.</span></span> <span data-ttu-id="4679a-105">따라서 패널의 컨트롤이 비례적으로 크기를 조정할 수 있으므로 지역화로 인한 부모 컨트롤 크기 조정이나 텍스트 길이 변경과 같은 변경 내용에 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4679a-105">This gives the controls in the panel the ability to proportionally resize, so it can respond to changes such as the parent control resizing or text length changing due to localization.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4679a-106">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="4679a-106">In This Section</span></span>  
 [<span data-ttu-id="4679a-107">TableLayoutPanel 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="4679a-107">TableLayoutPanel Control Overview</span></span>](tablelayoutpanel-control-overview.md)  
 <span data-ttu-id="4679a-108">행과 열이 있는 레이아웃을 만들 수 있게 해주는 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤의 일반적인 개념을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="4679a-108">Introduces the general concepts of the <xref:System.Windows.Forms.TableLayoutPanel> control, which allows you to create a layout with rows and columns.</span></span>  
  
 [<span data-ttu-id="4679a-109">TableLayoutPanel 컨트롤에 대한 모범 사례</span><span class="sxs-lookup"><span data-stu-id="4679a-109">Best Practices for the TableLayoutPanel Control</span></span>](best-practices-for-the-tablelayoutpanel-control.md)  
 <span data-ttu-id="4679a-110"><xref:System.Windows.Forms.TableLayoutPanel> 컨트롤의 레이아웃 기능을 최대한 활용할 수 있게 해주는 권장 사항을 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4679a-110">Outlines recommendations to help you get the most out of the layout features of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
 [<span data-ttu-id="4679a-111">TableLayoutPanel 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="4679a-111">AutoSize Behavior in the TableLayoutPanel Control</span></span>](autosize-behavior-in-the-tablelayoutpanel-control.md)  
 <span data-ttu-id="4679a-112"><xref:System.Windows.Forms.TableLayoutPanel> 컨트롤이 자동 크기 조정 동작을 지원하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4679a-112">Explains the ways in which the <xref:System.Windows.Forms.TableLayoutPanel> control supports automatic sizing behavior.</span></span>  
  
 [<span data-ttu-id="4679a-113">방법: TableLayoutPanel 컨트롤의 자식 컨트롤 고정 및 도킹</span><span class="sxs-lookup"><span data-stu-id="4679a-113">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 <span data-ttu-id="4679a-114"><xref:System.Windows.Forms.TableLayoutPanel> 컨트롤에서 자식 컨트롤을 고정 및 도킹하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4679a-114">Shows how to anchor and dock child controls in a <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
 [<span data-ttu-id="4679a-115">방법: 지역화에 적합한 Windows Forms 레이아웃 디자인</span><span class="sxs-lookup"><span data-stu-id="4679a-115">How to: Design a Windows Forms Layout that Responds Well to Localization</span></span>](how-to-design-a-windows-forms-layout-that-responds-well-to-localization.md)  
 <span data-ttu-id="4679a-116"><xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 사용하여 지역화에 효과적으로 대응하는 폼을 빌드하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4679a-116">Demonstrates using a <xref:System.Windows.Forms.TableLayoutPanel> control to build a form that responds well to localization.</span></span>  
  
 [<span data-ttu-id="4679a-117">방법: 데이터를 입력할 수 있는 크기 조정 가능한 Windows Form 만들기</span><span class="sxs-lookup"><span data-stu-id="4679a-117">How to: Create a Resizable Windows Form for Data Entry</span></span>](how-to-create-a-resizable-windows-form-for-data-entry.md)  
 <span data-ttu-id="4679a-118"><xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 사용하여 크기 조정에 효과적으로 대응하는 폼을 빌드하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4679a-118">Demonstrates using a <xref:System.Windows.Forms.TableLayoutPanel> control to build a form that responds well to resizing.</span></span>  
  
1. [<span data-ttu-id="4679a-119">방법: TableLayoutPanel 컨트롤의 컨트롤 맞춤 및 늘이기</span><span class="sxs-lookup"><span data-stu-id="4679a-119">How to: Align and Stretch a Control in a TableLayoutPanel Control</span></span>](how-to-align-and-stretch-a-control-in-a-tablelayoutpanel-control.md)  
  
2. [<span data-ttu-id="4679a-120">방법: TableLayoutPanel 컨트롤에서 행과 열 확장</span><span class="sxs-lookup"><span data-stu-id="4679a-120">How to: Span Rows and Columns in a TableLayoutPanel Control</span></span>](how-to-span-rows-and-columns-in-a-tablelayoutpanel-control.md)  
  
3. [<span data-ttu-id="4679a-121">방법: TableLayoutPanel 컨트롤에서 열과 행 편집</span><span class="sxs-lookup"><span data-stu-id="4679a-121">How to: Edit Columns and Rows in a TableLayoutPanel Control</span></span>](how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control.md)  
  
4. [<span data-ttu-id="4679a-122">연습: TableLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="4679a-122">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  
  
## <a name="reference"></a><span data-ttu-id="4679a-123">참조</span><span class="sxs-lookup"><span data-stu-id="4679a-123">Reference</span></span>  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 <span data-ttu-id="4679a-124"><xref:System.Windows.Forms.TableLayoutPanel> 컨트롤에 대한 참조 설명서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4679a-124">Provides reference documentation for the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
 <xref:System.Windows.Forms.TableLayoutSettings>  
 <span data-ttu-id="4679a-125"><xref:System.Windows.Forms.TableLayoutSettings> 형식에 대한 참조 설명서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4679a-125">Provides reference documentation for the <xref:System.Windows.Forms.TableLayoutSettings> type.</span></span>  
  
 <xref:System.Windows.Forms.FlowLayoutPanel>  
 <span data-ttu-id="4679a-126"><xref:System.Windows.Forms.FlowLayoutPanel> 컨트롤에 대한 참조 설명서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4679a-126">Provides reference documentation for the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="4679a-127">관련 섹션</span><span class="sxs-lookup"><span data-stu-id="4679a-127">Related Sections</span></span>  
 [<span data-ttu-id="4679a-128">지역화</span><span class="sxs-lookup"><span data-stu-id="4679a-128">Localization</span></span>](../../../standard/globalization-localization/localization.md)  
 <span data-ttu-id="4679a-129">지역화와 관련된 항목의 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4679a-129">Provides an overview of topics relating to localization.</span></span>  
  
 <span data-ttu-id="4679a-130">또한 [응용 프로그램 지역화](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/z68135h5(v=vs.120))를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4679a-130">Also see [Localizing Applications](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/z68135h5(v=vs.120)).</span></span>
