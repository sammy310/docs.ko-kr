---
title: '방법: 결합된 기하 도형 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- combining geometries [WPF]
- graphics [WPF], combining geometries
- geometries [WPF], combining
ms.assetid: 54c3277c-6b6e-4b25-91be-fda0bbc706b4
ms.openlocfilehash: c5ebe87abd4c2cf70f8fa17f1fcc773293f3ad27
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61910098"
---
# <a name="how-to-create-a-combined-geometry"></a><span data-ttu-id="5d97c-102">방법: 결합된 기하 도형 만들기</span><span class="sxs-lookup"><span data-stu-id="5d97c-102">How to: Create a Combined Geometry</span></span>
<span data-ttu-id="5d97c-103">이 예제에는 기 하 도형을 결합 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5d97c-103">This example shows how to combine geometries.</span></span> <span data-ttu-id="5d97c-104">사용 하 여 두 기 하 도형을 결합 하는 <xref:System.Windows.Media.CombinedGeometry> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="5d97c-104">To combine two geometries, use a <xref:System.Windows.Media.CombinedGeometry> object.</span></span> <span data-ttu-id="5d97c-105">설정 해당 <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> 및 <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> 결합 하 여 설정 하는 두 기 하 도형 사용 하 여 속성을 <xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A> 기 하 도형을 함께 결합할 수는 어떻게 결정을 하는 속성을 `Union`, `Intersect`, `Exclude`, 또는 `Xor`.</span><span class="sxs-lookup"><span data-stu-id="5d97c-105">Set its <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> properties  with the two geometries to combine, and set the <xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A> property, which determines how the geometries will be combined together, to `Union`, `Intersect`, `Exclude`, or `Xor`.</span></span>  
  
 <span data-ttu-id="5d97c-106">복합 기 하 도형을 둘 이상의 기 하 도형에서를 만들려면 사용을 <xref:System.Windows.Media.GeometryGroup>입니다.</span><span class="sxs-lookup"><span data-stu-id="5d97c-106">To create a composite geometry from two or more geometries, use a <xref:System.Windows.Media.GeometryGroup>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d97c-107">예제</span><span class="sxs-lookup"><span data-stu-id="5d97c-107">Example</span></span>  
 <span data-ttu-id="5d97c-108">다음 예제에서는 <xref:System.Windows.Media.CombinedGeometry> 의 기 하 도형 결합 모드를 사용 하 여 정의 `Exclude`합니다.</span><span class="sxs-lookup"><span data-stu-id="5d97c-108">In the following example, a <xref:System.Windows.Media.CombinedGeometry> is defined with a geometry combine mode of `Exclude`.</span></span>  <span data-ttu-id="5d97c-109">둘 다 <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> 하며 <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> 50 여 원 동일한 반지름의 원이지만 중심 오프셋으로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d97c-109">Both <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and the <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> are defined as circles of the same radius, but with centers offset by 50.</span></span>  
  
 [!code-xaml[GeometrySample#21](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#21)]  
  
 <span data-ttu-id="5d97c-110">![결과 Exclude 결합 모드](./media/mil-task-combined-geometry-exclude.PNG "mil_task_combined_geometry_exclude")</span><span class="sxs-lookup"><span data-stu-id="5d97c-110">![Results of the Exclude combine mode](./media/mil-task-combined-geometry-exclude.PNG "mil_task_combined_geometry_exclude")</span></span>  
<span data-ttu-id="5d97c-111">결합 된 기 하 도형 제외</span><span class="sxs-lookup"><span data-stu-id="5d97c-111">Combined Geometry Exclude</span></span>  
  
 <span data-ttu-id="5d97c-112">다음 태그에서를 <xref:System.Windows.Media.CombinedGeometry> 결합 모드를 사용 하 여 정의 `Intersect`합니다.</span><span class="sxs-lookup"><span data-stu-id="5d97c-112">In the following markup, a <xref:System.Windows.Media.CombinedGeometry> is defined with a combine mode of `Intersect`.</span></span>  <span data-ttu-id="5d97c-113">둘 다 <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> 하며 <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> 50 여 원 동일한 반지름의 원이지만 중심 오프셋으로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d97c-113">Both <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and the <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> are defined as circles of the same radius, but with centers offset by 50.</span></span>  
  
 [!code-xaml[GeometrySample#22](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#22)]  
  
 <span data-ttu-id="5d97c-114">![결과 Intersect 결합 모드](./media/mil-task-combined-geometry-intersect.PNG "mil_task_combined_geometry_intersect")</span><span class="sxs-lookup"><span data-stu-id="5d97c-114">![Results of the Intersect combine mode](./media/mil-task-combined-geometry-intersect.PNG "mil_task_combined_geometry_intersect")</span></span>  
<span data-ttu-id="5d97c-115">Intersect 결합 된 기 하 도형</span><span class="sxs-lookup"><span data-stu-id="5d97c-115">Combined Geometry Intersect</span></span>  
  
 <span data-ttu-id="5d97c-116">다음 태그에서를 <xref:System.Windows.Media.CombinedGeometry> 결합 모드를 사용 하 여 정의 `Union`합니다.</span><span class="sxs-lookup"><span data-stu-id="5d97c-116">In the following markup, a <xref:System.Windows.Media.CombinedGeometry> is defined with a combine mode of `Union`.</span></span>  <span data-ttu-id="5d97c-117">둘 다 <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> 하며 <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> 50 여 원 동일한 반지름의 원이지만 중심 오프셋으로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d97c-117">Both <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and the <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> are defined as circles of the same radius, but with centers offset by 50.</span></span>  
  
 [!code-xaml[GeometrySample#23](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#23)]  
  
 <span data-ttu-id="5d97c-118">![Union 결합 모드의 결과](./media/mil-task-combined-geometry-union.PNG "mil_task_combined_geometry_union")</span><span class="sxs-lookup"><span data-stu-id="5d97c-118">![Results of the Union combine mode](./media/mil-task-combined-geometry-union.PNG "mil_task_combined_geometry_union")</span></span>  
<span data-ttu-id="5d97c-119">결합 된 Geometry 합집합</span><span class="sxs-lookup"><span data-stu-id="5d97c-119">Combined Geometry Union</span></span>  
  
 <span data-ttu-id="5d97c-120">다음 태그에서를 <xref:System.Windows.Media.CombinedGeometry> 결합 모드를 사용 하 여 정의 `Xor`합니다.</span><span class="sxs-lookup"><span data-stu-id="5d97c-120">In the following markup, a <xref:System.Windows.Media.CombinedGeometry> is defined with a combine mode of `Xor`.</span></span>  <span data-ttu-id="5d97c-121">둘 다 <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> 하며 <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> 50 여 원 동일한 반지름의 원이지만 중심 오프셋으로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d97c-121">Both <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and the <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> are defined as circles of the same radius, but with centers offset by 50.</span></span>  
  
 [!code-xaml[GeometrySample#24](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#24)]  
  
 <span data-ttu-id="5d97c-122">![Xor 결합 모드의 결과](./media/mil-task-combined-geometry-xor.PNG "mil_task_combined_geometry_union")</span><span class="sxs-lookup"><span data-stu-id="5d97c-122">![Results of the Xor combine mode](./media/mil-task-combined-geometry-xor.PNG "mil_task_combined_geometry_xor")</span></span>  
<span data-ttu-id="5d97c-123">Xor 결합 된 기 하 도형</span><span class="sxs-lookup"><span data-stu-id="5d97c-123">Combined Geometry Xor</span></span>
