---
title: '방법: 시각적 개체의 기하 도형 적중 테스트'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [WPF], on visual objects comprising Geometry objects [WPF]
- visual objects [WPF], hit tests on
- Geometry objects [WPF], visual objects comprising
ms.assetid: 8bf2643f-d7f9-4cb4-9ea6-5b893c23200d
ms.openlocfilehash: 87b626e575d889447ef061d1ed62ef28efe5dfeb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947344"
---
# <a name="how-to-hit-test-geometry-in-a-visual"></a><span data-ttu-id="126f6-102">방법: 시각적 개체의 기하 도형 적중 테스트</span><span class="sxs-lookup"><span data-stu-id="126f6-102">How to: Hit Test Geometry in a Visual</span></span>
<span data-ttu-id="126f6-103">하나 이상의 구성 된 시각적 개체에 대해 적중된 테스트를 수행 하는 방법을 보여 주는이 예제 <xref:System.Windows.Media.Geometry> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="126f6-103">This example shows how to perform a hit test on a visual object that is composed of one or more <xref:System.Windows.Media.Geometry> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="126f6-104">예제</span><span class="sxs-lookup"><span data-stu-id="126f6-104">Example</span></span>  
 <span data-ttu-id="126f6-105">다음 예제에서는 검색 하는 방법을 보여 줍니다 합니다 <xref:System.Windows.Media.DrawingGroup> 를 사용 하는 시각적 개체에서의 <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="126f6-105">The following example shows how to retrieve the <xref:System.Windows.Media.DrawingGroup> from a visual object that uses the <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> method.</span></span> <span data-ttu-id="126f6-106">적중 횟수 테스트에서 각 그림의 렌더링 된 콘텐츠에 대해 수행한 후의 <xref:System.Windows.Media.DrawingGroup> 적중 된 기 하 도형을 확인 하려면.</span><span class="sxs-lookup"><span data-stu-id="126f6-106">A hit test is then performed on the rendered content of each drawing in the <xref:System.Windows.Media.DrawingGroup> to determine which geometry was hit.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="126f6-107">대부분의 경우에 사용 된 <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> 점을 시각적 개체의 렌더링된 된 콘텐츠 중 하나를 교차 하는지 여부를 결정 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="126f6-107">In most cases, you would use the <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> method to determine whether a point intersects any of the rendered content of a visual.</span></span>  
  
 [!code-csharp[VisualsOverview#VisualsOverviewSnippet4](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml.cs#visualsoverviewsnippet4)]
 [!code-vb[VisualsOverview#VisualsOverviewSnippet4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsOverview/visualbasic/window1.xaml.vb#visualsoverviewsnippet4)]  
  
 <span data-ttu-id="126f6-108">합니다 <xref:System.Windows.Media.Geometry.FillContains%2A> 메서드는 지정 된 사용 하 여 적중 테스트를 할 수 있는 오버 로드 된 메서드입니다 <xref:System.Windows.Point> 또는 <xref:System.Windows.Media.Geometry>합니다.</span><span class="sxs-lookup"><span data-stu-id="126f6-108">The <xref:System.Windows.Media.Geometry.FillContains%2A> method is an overloaded method that allows you to hit test by using a specified <xref:System.Windows.Point> or <xref:System.Windows.Media.Geometry>.</span></span> <span data-ttu-id="126f6-109">기하 도형에 스트로크를 적용할 경우 스트로크가 채우기 경계 밖으로 확장될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="126f6-109">If a geometry is stroked, the stroke can extend outside the fill bounds.</span></span> <span data-ttu-id="126f6-110">호출 하려는 경우에 <xref:System.Windows.Media.Geometry.StrokeContains%2A> 외에 <xref:System.Windows.Media.Geometry.FillContains%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="126f6-110">In which case, you may want to call <xref:System.Windows.Media.Geometry.StrokeContains%2A> in addition to <xref:System.Windows.Media.Geometry.FillContains%2A>.</span></span>  
  
 <span data-ttu-id="126f6-111">제공할 수도 있습니다는 <xref:System.Windows.Media.ToleranceType> 3 차원 곡선의 목적에 사용 되는 합니다.</span><span class="sxs-lookup"><span data-stu-id="126f6-111">You can also provide a <xref:System.Windows.Media.ToleranceType> that is used for the purposes of Bezier flattening.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="126f6-112">이 샘플에서는 기하 도형에 적용될 수 있는 변환 또는 클리핑을 고려하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="126f6-112">This sample does not take into account any transforms or clipping that may be applied to the geometry.</span></span> <span data-ttu-id="126f6-113">또한 이 샘플은 직접 연결된 그림이 없으므로 스타일이 적용된 컨트롤에서 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="126f6-113">In addition, this sample will not work with a styled control, since it does not have any drawings directly associated with it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="126f6-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="126f6-114">See also</span></span>

- [<span data-ttu-id="126f6-115">시각적 계층에서 적중 테스트</span><span class="sxs-lookup"><span data-stu-id="126f6-115">Hit Testing in the Visual Layer</span></span>](hit-testing-in-the-visual-layer.md)
- [<span data-ttu-id="126f6-116">기하 도형을 매개 변수로 사용하여 적중 테스트</span><span class="sxs-lookup"><span data-stu-id="126f6-116">Hit Test Using Geometry as a Parameter</span></span>](how-to-hit-test-using-geometry-as-a-parameter.md)
