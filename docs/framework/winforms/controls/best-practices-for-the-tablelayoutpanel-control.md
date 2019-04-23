---
title: TableLayoutPanel 컨트롤에 대한 모범 사례
ms.date: 03/30/2017
helpviewer_keywords:
- layout [Windows Forms]
- TableLayoutPanel control [Windows Forms], best practices
- forms [Windows Forms], best practices
- AutoSize property [Windows Forms], tableLayoutPanel control
- controls [Windows Forms], sizing
- TableLayoutPanel control [Windows Forms], AutoSize behavior
- layout [Windows Forms], AutoSize
- layout [Windows Forms], best practices
- best practices [Windows Forms], tableLayoutPanel control
- sizing [Windows Forms], automatic
- automatic sizing
ms.assetid: b6706efb-d7a4-45ec-8cf4-08fa993e3afb
ms.openlocfilehash: 57abf3527af146f1ce918bcabbc6a5a34bfb9b34
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59773833"
---
# <a name="best-practices-for-the-tablelayoutpanel-control"></a><span data-ttu-id="418ad-102">TableLayoutPanel 컨트롤에 대한 모범 사례</span><span class="sxs-lookup"><span data-stu-id="418ad-102">Best Practices for the TableLayoutPanel Control</span></span>
<span data-ttu-id="418ad-103"><xref:System.Windows.Forms.TableLayoutPanel> 컨트롤에 Windows Forms에서 사용 하기 전에 신중 하 게 고려해 야 하는 강력한 레이아웃 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="418ad-103">The <xref:System.Windows.Forms.TableLayoutPanel> control provides powerful layout features that you should consider carefully before using on your Windows Forms.</span></span>  
  
## <a name="recommendations"></a><span data-ttu-id="418ad-104">권장 사항</span><span class="sxs-lookup"><span data-stu-id="418ad-104">Recommendations</span></span>  
 <span data-ttu-id="418ad-105">다음 권장 사항을 사용 하도록 도와 <xref:System.Windows.Forms.TableLayoutPanel> 해당 최대한 활용 하는 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="418ad-105">The following recommendations will help you use the <xref:System.Windows.Forms.TableLayoutPanel> control to its best advantage.</span></span>  
  
### <a name="targeted-use"></a><span data-ttu-id="418ad-106">대상된 사용</span><span class="sxs-lookup"><span data-stu-id="418ad-106">Targeted Use</span></span>  
 <span data-ttu-id="418ad-107">사용 된 <xref:System.Windows.Forms.TableLayoutPanel> 꼭 필요할 때만 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="418ad-107">Use the <xref:System.Windows.Forms.TableLayoutPanel> control sparingly.</span></span> <span data-ttu-id="418ad-108">크기 조정 가능한 레이아웃을 필요로 하는 모든 상황에서 하지 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="418ad-108">You should not use it in all situations that require a resizable layout.</span></span> <span data-ttu-id="418ad-109">다음 목록에서는 가장 많이 사용 하 여에서 향상 된 레이아웃을 <xref:System.Windows.Forms.TableLayoutPanel> 제어:</span><span class="sxs-lookup"><span data-stu-id="418ad-109">The following list describes layouts that benefit most from the use of the <xref:System.Windows.Forms.TableLayoutPanel> control:</span></span>  
  
-   <span data-ttu-id="418ad-110">서로 크기를 비례적으로 크기를 조정 하는 폼의 여러 부분이 있는 레이아웃입니다.</span><span class="sxs-lookup"><span data-stu-id="418ad-110">Layouts in which there are multiple parts of the form that resize proportionally to each other.</span></span>  
  
-   <span data-ttu-id="418ad-111">레이아웃을 수정 또는 추가 되거나 삭제 된 사용자 지정 가능한 필드가 있는 데이터 항목 형식과 같은 런타임에 동적으로 생성 될 기본 설정을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="418ad-111">Layouts that will be modified or generated dynamically at run time, such as data entry forms that have user-customizable fields added or subtracted based on preferences.</span></span>  
  
-   <span data-ttu-id="418ad-112">전체 고정 크기로 유지 되어야 하는 레이아웃을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="418ad-112">Layouts that should remain at an overall fixed size.</span></span> <span data-ttu-id="418ad-113">예를 들어 800 x 600, 보다 작게 유지 해야 하는 대화 상자가 있을 수 있지만 지역화 된 문자열을 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="418ad-113">For example, you may have a dialog box that should remain smaller than 800 x 600, but you need to support localized strings.</span></span>  
  
 <span data-ttu-id="418ad-114">다음 목록에서는 레이아웃을 사용 하 여에서 매우 유용 하지 않습니다는 <xref:System.Windows.Forms.TableLayoutPanel> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="418ad-114">The following list describes layouts that do not benefit greatly from using the <xref:System.Windows.Forms.TableLayoutPanel> control:</span></span>  
  
-   <span data-ttu-id="418ad-115">간단한 데이터 입력 폼 단일 열을 사용 하 여 레이블 및 텍스트 입력 영역의 단일 열입니다.</span><span class="sxs-lookup"><span data-stu-id="418ad-115">Simple data entry forms with a single column of labels and a single column of text-entry areas.</span></span>  
  
-   <span data-ttu-id="418ad-116">큰 단일 폼 크기를 조정 하면 사용 가능한 모든 공간을 채워야 하는 영역을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="418ad-116">Forms with a single large display area that should fill all the available space when a resize occurs.</span></span> <span data-ttu-id="418ad-117">이 예제는 단일을 표시 하는 폼 <xref:System.Windows.Forms.PropertyGrid> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="418ad-117">An example of this is a form that displays a single <xref:System.Windows.Forms.PropertyGrid> control.</span></span> <span data-ttu-id="418ad-118">이 경우 아무 폼 크기가 조정 되 면을 확장 해야 하기 때문에 앵커를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="418ad-118">In this case, use anchoring, because nothing else should expand when the form is resized.</span></span>  
  
 <span data-ttu-id="418ad-119">컨트롤에 포함 되도록 해야 신중 하 게 선택는 <xref:System.Windows.Forms.TableLayoutPanel> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="418ad-119">Choose carefully which controls need to be in a <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="418ad-120">공간을 30% 고정을 사용 하 여 늘릴 수 있는 텍스트에 대 한 경우 사용을 고려 합니다 <xref:System.Windows.Forms.Control.Anchor%2A> 속성에만 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="418ad-120">If you have room for your text to grow by 30% using anchoring, consider using the <xref:System.Windows.Forms.Control.Anchor%2A> property only.</span></span> <span data-ttu-id="418ad-121">레이아웃에 필요한 공간을 예측할 수 있습니다, 아니면 사용 하 여 <xref:System.Windows.Forms.Control.Dock%2A> 하 고 <xref:System.Windows.Forms.Control.Anchor%2A> 남은 공간의 세부 정보를 예측 하는 것 보다 쉽습니다 및 <xref:System.Windows.Forms.Control.AutoSize%2A> 동작 합니다.</span><span class="sxs-lookup"><span data-stu-id="418ad-121">If you can estimate the space required by your layout, use of <xref:System.Windows.Forms.Control.Dock%2A> and <xref:System.Windows.Forms.Control.Anchor%2A> is easier than estimating the details of remaining space and <xref:System.Windows.Forms.Control.AutoSize%2A> behavior.</span></span>  
  
 <span data-ttu-id="418ad-122">일반적으로 사용 하 여 레이아웃을 디자인할 때는 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 디자인을 최대한 단순하게 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="418ad-122">In general, when designing your layout with the <xref:System.Windows.Forms.TableLayoutPanel> control, keep the design as simple as possible.</span></span>  
  
### <a name="use-the-document-outline-window"></a><span data-ttu-id="418ad-123">문서 개요 창을 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="418ad-123">Use the Document Outline Window</span></span>  
 <span data-ttu-id="418ad-124">문서 개요 창 레이아웃, 컨트롤의 z 순서와 부모-자식 관계를 조작 하는 데 사용할 수 있는 트리 뷰를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="418ad-124">The Document Outline window gives you a tree view of your layout, which you can use to manipulate the z-order and parent-child relationships of your controls.</span></span> <span data-ttu-id="418ad-125">**보기 메뉴**를 선택 **기타 Windows**을 선택한 후 **문서 개요**합니다.</span><span class="sxs-lookup"><span data-stu-id="418ad-125">From the **View menu**, select **Other Windows**, then select **Document Outline**.</span></span>  
  
### <a name="avoid-nesting"></a><span data-ttu-id="418ad-126">중첩을 하지 마십시오</span><span class="sxs-lookup"><span data-stu-id="418ad-126">Avoid Nesting</span></span>  
 <span data-ttu-id="418ad-127">다른 중첩 하지 마십시오 <xref:System.Windows.Forms.TableLayoutPanel> 내에서 제어를 <xref:System.Windows.Forms.TableLayoutPanel> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="418ad-127">Avoid nesting other <xref:System.Windows.Forms.TableLayoutPanel> controls within a <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="418ad-128">중첩 된 레이아웃을 디버깅 하는 것은 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="418ad-128">Debugging nested layouts can be difficult.</span></span>  
  
### <a name="avoid-visual-inheritance"></a><span data-ttu-id="418ad-129">시각적 상속 방지</span><span class="sxs-lookup"><span data-stu-id="418ad-129">Avoid Visual Inheritance</span></span>  
 <span data-ttu-id="418ad-130"><xref:System.Windows.Forms.TableLayoutPanel> 컨트롤 Windows Forms 디자이너에서 시각적 상속을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="418ad-130">The <xref:System.Windows.Forms.TableLayoutPanel> control does not support visual inheritance in the Windows Forms Designer.</span></span> <span data-ttu-id="418ad-131"><xref:System.Windows.Forms.TableLayoutPanel> 컨트롤 파생된 클래스에서 "잠겨 있음" 디자인 타임에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="418ad-131">A <xref:System.Windows.Forms.TableLayoutPanel> control in a derived class appears as "locked" at design time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="418ad-132">참고자료</span><span class="sxs-lookup"><span data-stu-id="418ad-132">See also</span></span>

- <xref:System.Windows.Forms.TableLayoutPanel>
- <xref:System.Windows.Forms.FlowLayoutPanel>
