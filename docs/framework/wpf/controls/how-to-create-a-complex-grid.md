---
title: 복잡 한 모눈을 만드는 방법
description: 표 형태 컨트롤을 사용 하 여 월별 달력 처럼 보이는 레이아웃을 만드는 방법의 예입니다.
ms.date: 03/30/2017
helpviewer_keywords:
- calendar [WPF], creating
- monthly calendar [WPF], creating
- Grid control [WPF], creating [WPF], complex grid
ms.assetid: 4ce3040a-a156-4364-9596-98ca1eca5550
ms.openlocfilehash: dd17dfeea85e2b404f7a284f93faceec63145b1f
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57355025"
---
# <a name="how-to-create-a-complex-grid"></a><span data-ttu-id="7dde6-103">복잡 한 모눈을 만드는 방법</span><span class="sxs-lookup"><span data-stu-id="7dde6-103">How to create a complex Grid</span></span>

<span data-ttu-id="7dde6-104">사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.Grid> 월별 달력 처럼 보이는 레이아웃을 만들 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="7dde6-104">This example shows how to use a <xref:System.Windows.Controls.Grid> control to create a layout that looks like a monthly calendar.</span></span>

## <a name="example"></a><span data-ttu-id="7dde6-105">예제</span><span class="sxs-lookup"><span data-stu-id="7dde6-105">Example</span></span>

<span data-ttu-id="7dde6-106">다음 예제에서는 8 개 행과 8 개의 열을 사용 하 여 정의 된 <xref:System.Windows.Controls.RowDefinition> 고 <xref:System.Windows.Controls.ColumnDefinition> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="7dde6-106">The following example defines eight rows and eight columns by using the <xref:System.Windows.Controls.RowDefinition> and <xref:System.Windows.Controls.ColumnDefinition> classes.</span></span> <span data-ttu-id="7dde6-107">사용 하 여는 <xref:System.Windows.Controls.Grid.ColumnSpan%2A?displayProperty=nameWithType> 및 <xref:System.Windows.Controls.Grid.RowSpan%2A?displayProperty=nameWithType> 와 함께 연결 된 속성으로 <xref:System.Windows.Shapes.Rectangle> 요소에는 다양 한 열과 행의 배경을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="7dde6-107">It uses the <xref:System.Windows.Controls.Grid.ColumnSpan%2A?displayProperty=nameWithType> and <xref:System.Windows.Controls.Grid.RowSpan%2A?displayProperty=nameWithType> attached properties, together with <xref:System.Windows.Shapes.Rectangle> elements, which fill the backgrounds of various columns and rows.</span></span> <span data-ttu-id="7dde6-108">각 셀에 요소가 둘 이상 있을 수 있으므로이 디자인은 가능한 한 <xref:System.Windows.Controls.Grid>, 원칙 차이점 <xref:System.Windows.Controls.Grid> 및 <xref:System.Windows.Documents.Table>합니다.</span><span class="sxs-lookup"><span data-stu-id="7dde6-108">This design is possible because more than one element can exist in each cell in a <xref:System.Windows.Controls.Grid>, a principle difference between <xref:System.Windows.Controls.Grid> and <xref:System.Windows.Documents.Table>.</span></span>

<span data-ttu-id="7dde6-109">이 예제에서는 세로 그라데이션을 사용 <xref:System.Windows.Shapes.Shape.Fill%2A> 열 및 시각적 표시 및 달력의 가독성을 개선 하는 행입니다.</span><span class="sxs-lookup"><span data-stu-id="7dde6-109">The example uses vertical gradients to <xref:System.Windows.Shapes.Shape.Fill%2A> the columns and rows to improve the visual presentation and readability of the calendar.</span></span> <span data-ttu-id="7dde6-110">스타일 <xref:System.Windows.Controls.TextBlock> 요소는 날짜 및 요일을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7dde6-110">Styled <xref:System.Windows.Controls.TextBlock> elements represent the dates and days of the week.</span></span> <span data-ttu-id="7dde6-111"><xref:System.Windows.Controls.TextBlock> 사용 하 여 해당 셀 내의 요소는 절대적으로 배치를 <xref:System.Windows.FrameworkElement.Margin%2A> 속성 및 응용 프로그램에 대 한 스타일 내에 정의 된 맞춤 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="7dde6-111"><xref:System.Windows.Controls.TextBlock> elements are absolutely positioned within their cells by using the <xref:System.Windows.FrameworkElement.Margin%2A> property and alignment properties that are defined within the style for the application.</span></span>

[!code-xaml[GridComplex#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GridComplex/CS/default.xaml#1)]

<span data-ttu-id="7dde6-112">다음 이미지에는 결과 컨트롤을 사용자 지정할 수 있는 달력을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7dde6-112">The following image shows the resulting control, a customizable calendar:</span></span>

![결과 컨트롤의 스크린샷](././media/how-to-create-a-complex-grid/wpf-manual-calendar.png)

## <a name="see-also"></a><span data-ttu-id="7dde6-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="7dde6-114">See also</span></span>

- <xref:System.Windows.Controls.Grid?displayProperty=nameWithType>
- <xref:System.Windows.Documents.TableCell?displayProperty=nameWithType>
- [<span data-ttu-id="7dde6-115">단색 및 그라데이션을 사용한 그리기 개요</span><span class="sxs-lookup"><span data-stu-id="7dde6-115">Painting with Solid Colors and Gradients Overview</span></span>](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="7dde6-116">패널 개요</span><span class="sxs-lookup"><span data-stu-id="7dde6-116">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="7dde6-117">테이블 개요</span><span class="sxs-lookup"><span data-stu-id="7dde6-117">Table Overview</span></span>](../advanced/table-overview.md)