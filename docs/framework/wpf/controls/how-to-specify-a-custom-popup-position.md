---
title: '방법: 사용자 지정 팝업 위치 지정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Popup control [WPF], specifying custom position
ms.assetid: 28c24f39-d3aa-4ee2-b950-384b4a5dab92
ms.openlocfilehash: b48dedc044b418062642af5c5bb40afab78a3c97
ms.sourcegitcommit: 1c1a1f9ec0bd1efb3040d86a79f7ee94e207cca5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/03/2020
ms.locfileid: "80635744"
---
# <a name="how-to-specify-a-custom-popup-position"></a><span data-ttu-id="a7232-102">방법: 사용자 지정 팝업 위치 지정</span><span class="sxs-lookup"><span data-stu-id="a7232-102">How to: Specify a Custom Popup Position</span></span>
<span data-ttu-id="a7232-103">이 예제에서는 <xref:System.Windows.Controls.Primitives.Popup> <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 속성이 로 설정될 때 컨트롤에 <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>대한 사용자 지정 위치를 지정하는 방법을 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7232-103">This example shows how to specify a custom position for a <xref:System.Windows.Controls.Primitives.Popup> control when the <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> property is set to <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a7232-104">예제</span><span class="sxs-lookup"><span data-stu-id="a7232-104">Example</span></span>  
 <span data-ttu-id="a7232-105">속성이 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 설정되면 <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>대리자의 <xref:System.Windows.Controls.Primitives.Popup> 정의된 인스턴스를 <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="a7232-105">When the <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> property is set to <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>, the <xref:System.Windows.Controls.Primitives.Popup> calls a defined instance of the <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegate.</span></span> <span data-ttu-id="a7232-106">이 대리자는 대상 영역의 왼쪽 위 모서리와 <xref:System.Windows.Controls.Primitives.Popup>의 왼쪽 상단 모서리를 기준으로 가능한 점 집합을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a7232-106">This delegate returns a set of possible points that are relative to the top-left corner of the target area and the top-left corner of the <xref:System.Windows.Controls.Primitives.Popup>.</span></span> <span data-ttu-id="a7232-107">배치는 <xref:System.Windows.Controls.Primitives.Popup> 최상의 가시성을 제공하는 지점에서 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="a7232-107">The <xref:System.Windows.Controls.Primitives.Popup> placement occurs at the point that provides the best visibility.</span></span>  
  
 <span data-ttu-id="a7232-108">다음 예제에서는 속성을 로 설정하여 <xref:System.Windows.Controls.Primitives.Popup> a의 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 위치를 <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>정의하는 방법을 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7232-108">The following example shows how to define the position of a <xref:System.Windows.Controls.Primitives.Popup> by setting the <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> property to <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>.</span></span> <span data-ttu-id="a7232-109">또한 를 배치하기 위해 <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> 대리자를 만들고 할당하는 <xref:System.Windows.Controls.Primitives.Popup>방법도 보여 주며.</span><span class="sxs-lookup"><span data-stu-id="a7232-109">It also shows how to create and assign a <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegate in order to position the <xref:System.Windows.Controls.Primitives.Popup>.</span></span>  <span data-ttu-id="a7232-110">콜백 대리자는 <xref:System.Windows.Controls.Primitives.CustomPopupPlacement> 두 개의 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a7232-110">The callback delegate returns two <xref:System.Windows.Controls.Primitives.CustomPopupPlacement> objects.</span></span>  <span data-ttu-id="a7232-111"><xref:System.Windows.Controls.Primitives.Popup> 첫 번째 위치에서 화면 가장자리에 의해 숨김이 있으면 두 번째 위치에 <xref:System.Windows.Controls.Primitives.Popup> 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7232-111">If the <xref:System.Windows.Controls.Primitives.Popup> is hidden by a screen edge at the first position, the <xref:System.Windows.Controls.Primitives.Popup> is placed at the second position.</span></span>  
  
 [!code-xaml[PopupCustomPlacement#CustomPlacement](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml#customplacement)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateInstance](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegateinstance)]
 [!code-vb[PopupCustomPlacement#DelegateInstance](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegateinstance)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegatedefinition)]
 [!code-vb[PopupCustomPlacement#DelegateDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegatedefinition)]  
  
 <span data-ttu-id="a7232-112">전체 샘플은 [팝업 배치 샘플을](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a7232-112">For the complete sample, see [Popup Placement Sample](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7232-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a7232-113">See also</span></span>

- <xref:System.Windows.Controls.Primitives.Popup>
- [<span data-ttu-id="a7232-114">팝업 개요</span><span class="sxs-lookup"><span data-stu-id="a7232-114">Popup overview</span></span>](popup-overview.md)
- [<span data-ttu-id="a7232-115">방법 기사</span><span class="sxs-lookup"><span data-stu-id="a7232-115">How-to articles</span></span>](popup-how-to-topics.md)
