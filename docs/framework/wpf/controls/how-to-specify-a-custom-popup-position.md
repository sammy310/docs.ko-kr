---
title: '방법: 사용자 지정 팝업 위치 지정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Popup control [WPF], specifying custom position
ms.assetid: 28c24f39-d3aa-4ee2-b950-384b4a5dab92
ms.openlocfilehash: dc516f0eb1cfcbac6662497eb4019041eefec2a9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59200586"
---
# <a name="how-to-specify-a-custom-popup-position"></a><span data-ttu-id="a7a35-102">방법: 사용자 지정 팝업 위치 지정</span><span class="sxs-lookup"><span data-stu-id="a7a35-102">How to: Specify a Custom Popup Position</span></span>
<span data-ttu-id="a7a35-103">이 예제에 대 한 사용자 지정 위치를 지정 하는 방법을 보여 줍니다를 <xref:System.Windows.Controls.Primitives.Popup> 시기를 제어 합니다 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 속성이 <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>.</span><span class="sxs-lookup"><span data-stu-id="a7a35-103">This example shows how to specify a custom position for a <xref:System.Windows.Controls.Primitives.Popup> control when the <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> property is set to <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a7a35-104">예제</span><span class="sxs-lookup"><span data-stu-id="a7a35-104">Example</span></span>  
 <span data-ttu-id="a7a35-105">경우는 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 속성이로 설정 되어 <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>, <xref:System.Windows.Controls.Primitives.Popup> 의 정의 된 인스턴스를 호출 합니다 <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> 대리자.</span><span class="sxs-lookup"><span data-stu-id="a7a35-105">When the <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> property is set to <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>, the <xref:System.Windows.Controls.Primitives.Popup> calls a defined instance of the <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegate.</span></span> <span data-ttu-id="a7a35-106">대상 영역의 왼쪽된 위 모퉁이와 왼쪽된 위 모퉁이 있는 가능한 점의 집합을 반환 하는이 대리자는 <xref:System.Windows.Controls.Primitives.Popup>합니다.</span><span class="sxs-lookup"><span data-stu-id="a7a35-106">This delegate returns a set of possible points that are relative to the top left corner of the target area and the top left corner of the <xref:System.Windows.Controls.Primitives.Popup>.</span></span> <span data-ttu-id="a7a35-107"><xref:System.Windows.Controls.Primitives.Popup> 최상의 가시성을 제공 하는 지점에 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7a35-107">The <xref:System.Windows.Controls.Primitives.Popup> placement occurs at the point that provides the best visibility.</span></span>  
  
 <span data-ttu-id="a7a35-108">다음 예제에서는 위치를 정의 하는 방법을 보여 줍니다는 <xref:System.Windows.Controls.Primitives.Popup> 설정 하 여 합니다 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 속성을 <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>입니다.</span><span class="sxs-lookup"><span data-stu-id="a7a35-108">The following example shows how to define the position of a <xref:System.Windows.Controls.Primitives.Popup> by setting the <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> property to <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>.</span></span> <span data-ttu-id="a7a35-109">또한 만들고 할당 하는 방법을 보여 줍니다는 <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> 배치 하기 위해 대리자는 <xref:System.Windows.Controls.Primitives.Popup>합니다.</span><span class="sxs-lookup"><span data-stu-id="a7a35-109">It also shows how to create and assign a <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegate in order to position the <xref:System.Windows.Controls.Primitives.Popup>.</span></span>  <span data-ttu-id="a7a35-110">두 콜백 대리자 반환 <xref:System.Windows.Controls.Primitives.CustomPopupPlacement> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="a7a35-110">The callback delegate returns two <xref:System.Windows.Controls.Primitives.CustomPopupPlacement> objects.</span></span>  <span data-ttu-id="a7a35-111">경우는 <xref:System.Windows.Controls.Primitives.Popup> 화면 가장자리에 첫 번째 위치에 의해 숨겨져는 <xref:System.Windows.Controls.Primitives.Popup> 두 번째 위치에 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7a35-111">If the <xref:System.Windows.Controls.Primitives.Popup> is hidden by a screen edge at the first position, the <xref:System.Windows.Controls.Primitives.Popup> is placed at the second position.</span></span>  
  
 [!code-xaml[PopupCustomPlacement#CustomPlacement](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml#customplacement)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateInstance](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegateinstance)]
 [!code-vb[PopupCustomPlacement#DelegateInstance](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegateinstance)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegatedefinition)]
 [!code-vb[PopupCustomPlacement#DelegateDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegatedefinition)]  
  
 <span data-ttu-id="a7a35-112">전체 샘플을 참조 하세요 [Popup 배치 샘플](https://go.microsoft.com/fwlink/?LinkID=160032)합니다.</span><span class="sxs-lookup"><span data-stu-id="a7a35-112">For the complete sample, see [Popup Placement Sample](https://go.microsoft.com/fwlink/?LinkID=160032).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7a35-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="a7a35-113">See also</span></span>

- <xref:System.Windows.Controls.Primitives.Popup>
- [<span data-ttu-id="a7a35-114">Popup 개요</span><span class="sxs-lookup"><span data-stu-id="a7a35-114">Popup Overview</span></span>](popup-overview.md)
- [<span data-ttu-id="a7a35-115">방법 항목</span><span class="sxs-lookup"><span data-stu-id="a7a35-115">How-to Topics</span></span>](popup-how-to-topics.md)
