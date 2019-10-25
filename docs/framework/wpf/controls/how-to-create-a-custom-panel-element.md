---
title: '방법: 사용자 지정 패널 요소 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Panel control [WPF]
- custom Panel elements [WPF]
ms.assetid: e0df4f1e-8c07-4e86-89a3-e22acfffdc2a
ms.openlocfilehash: 31edc75114c5dad613e5b65e7d8b051e2c3713af
ms.sourcegitcommit: 9bd1c09128e012b6e34bdcbdf3576379f58f3137
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2019
ms.locfileid: "72799137"
---
# <a name="how-to-create-a-custom-panel-element"></a><span data-ttu-id="254de-102">방법: 사용자 지정 패널 요소 만들기</span><span class="sxs-lookup"><span data-stu-id="254de-102">How to: Create a Custom Panel Element</span></span>
## <a name="example"></a><span data-ttu-id="254de-103">예제</span><span class="sxs-lookup"><span data-stu-id="254de-103">Example</span></span>  
 <span data-ttu-id="254de-104">이 예제에서는 <xref:System.Windows.Controls.Panel> 요소의 기본 레이아웃 동작을 재정의 하 고 <xref:System.Windows.Controls.Panel>에서 파생 된 사용자 지정 레이아웃 요소를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="254de-104">This example shows how to override the default layout behavior of the <xref:System.Windows.Controls.Panel> element and create custom layout elements that are derived from <xref:System.Windows.Controls.Panel>.</span></span>  
  
 <span data-ttu-id="254de-105">이 예제에서는 두 개의 하드 코딩 된 x 및 y 좌표에 따라 자식 요소를 배치 하는 `PlotPanel`라는 간단한 사용자 지정 <xref:System.Windows.Controls.Panel> 요소를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="254de-105">The example defines a simple custom <xref:System.Windows.Controls.Panel> element called `PlotPanel`, which positions child elements according to two hard-coded x- and y-coordinates.</span></span> <span data-ttu-id="254de-106">이 예제에서는 `x` 및 `y` 모두 `50`로 설정 됩니다. 따라서 모든 자식 요소가 x 축과 y 축의 해당 위치에 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="254de-106">In this example, `x` and `y` are both set to `50`; therefore, all child elements are positioned at that location on the x and y axes.</span></span>  
  
 <span data-ttu-id="254de-107">사용자 지정 <xref:System.Windows.Controls.Panel> 동작을 구현 하기 위해이 예제에서는 <xref:System.Windows.FrameworkElement.MeasureOverride%2A> 및 <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="254de-107">To implement custom <xref:System.Windows.Controls.Panel> behaviors, the example uses the <xref:System.Windows.FrameworkElement.MeasureOverride%2A> and <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> methods.</span></span> <span data-ttu-id="254de-108">각 메서드는 자식 요소를 배치 하 고 렌더링 하는 데 필요한 <xref:System.Windows.Size> 데이터를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="254de-108">Each method returns the <xref:System.Windows.Size> data that is necessary to position and render child elements.</span></span>  
  
 [!code-cpp[PlotPanel#1](~/samples/snippets/cpp/VS_Snippets_Wpf/PlotPanel/CPP/PlotPanel.cpp#1)]
 [!code-csharp[PlotPanel#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PlotPanel/CSharp/PlotPanel.cs#1)]
 [!code-vb[PlotPanel#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PlotPanel/VisualBasic/PlotPanel.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="254de-109">참조</span><span class="sxs-lookup"><span data-stu-id="254de-109">See also</span></span>

- <xref:System.Windows.Controls.Panel>
- [<span data-ttu-id="254de-110">패널 개요</span><span class="sxs-lookup"><span data-stu-id="254de-110">Panels Overview</span></span>](panels-overview.md)
