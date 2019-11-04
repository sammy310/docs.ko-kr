---
title: '방법: LINQ 쿼리 결과에 바인딩'
ms.date: 03/30/2017
helpviewer_keywords:
- running a LINQ query [WPF], bind to results
- binding to LINQ query results [WPF]
ms.assetid: ff2844d9-17ed-4ea6-aab1-5111af0bc684
ms.openlocfilehash: d21ac5f366e001ea76d6eda64ed62583248796f6
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73454422"
---
# <a name="how-to-bind-to-the-results-of-a-linq-query"></a><span data-ttu-id="5d64c-102">방법: LINQ 쿼리 결과에 바인딩</span><span class="sxs-lookup"><span data-stu-id="5d64c-102">How to: Bind to the Results of a LINQ Query</span></span>

<span data-ttu-id="5d64c-103">이 예제에서는 LINQ 쿼리를 실행 한 다음 결과에 바인딩하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5d64c-103">This example demonstrates how to run a LINQ query and then bind to the results.</span></span>

## <a name="example"></a><span data-ttu-id="5d64c-104">예제</span><span class="sxs-lookup"><span data-stu-id="5d64c-104">Example</span></span>

<span data-ttu-id="5d64c-105">다음 예에서는 두 개의 목록 상자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5d64c-105">The following example creates two list boxes.</span></span> <span data-ttu-id="5d64c-106">첫 번째 목록 상자에는 세 개의 목록 항목이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d64c-106">The first list box contains three list items.</span></span>

[!code-xaml[LinqExample#UI](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml#ui)]

<span data-ttu-id="5d64c-107">첫 번째 목록 상자에서 항목을 선택 하면 다음 이벤트 처리기가 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d64c-107">Selecting an item from the first list box invokes the following event handler.</span></span> <span data-ttu-id="5d64c-108">이 예제에서 `Tasks`은 `Task` 개체의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="5d64c-108">In this example, `Tasks` is a collection of `Task` objects.</span></span> <span data-ttu-id="5d64c-109">`Task` 클래스에는 `Priority`라는 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d64c-109">The `Task` class has a property named `Priority`.</span></span> <span data-ttu-id="5d64c-110">이 이벤트 처리기는 선택한 우선 순위 값을 가진 `Task` 개체의 컬렉션을 반환 하는 LINQ 쿼리를 실행 한 다음 <xref:System.Windows.FrameworkElement.DataContext%2A>로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d64c-110">This event handler runs a LINQ query that returns the collection of `Task` objects that have the selected priority value, and then sets that as the <xref:System.Windows.FrameworkElement.DataContext%2A>:</span></span>

[!code-csharp[LinqExample#Using](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#using)]
[!code-csharp[LinqExample#Tasks](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#tasks)]
[!code-csharp[LinqExample#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#handler)]

<span data-ttu-id="5d64c-111">두 번째 목록 상자는 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 값이 `{Binding}`으로 설정 되어 있기 때문에 해당 컬렉션에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d64c-111">The second list box binds to that collection because its <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> value is set to `{Binding}`.</span></span> <span data-ttu-id="5d64c-112">그러면 반환 된 컬렉션 (`myTaskTemplate` <xref:System.Windows.DataTemplate>)을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d64c-112">As a result, it displays the returned collection (based on the `myTaskTemplate` <xref:System.Windows.DataTemplate>).</span></span>

## <a name="see-also"></a><span data-ttu-id="5d64c-113">참조</span><span class="sxs-lookup"><span data-stu-id="5d64c-113">See also</span></span>

- [<span data-ttu-id="5d64c-114">XAML의 바인딩에 사용할 수 있는 데이터 만들기</span><span class="sxs-lookup"><span data-stu-id="5d64c-114">Make Data Available for Binding in XAML</span></span>](how-to-make-data-available-for-binding-in-xaml.md)
- [<span data-ttu-id="5d64c-115">선택에 따라 수집 및 표시 정보에 바인딩</span><span class="sxs-lookup"><span data-stu-id="5d64c-115">Bind to a Collection and Display Information Based on Selection</span></span>](how-to-bind-to-a-collection-and-display-information-based-on-selection.md)
- [<span data-ttu-id="5d64c-116">WPF 버전 4.5의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="5d64c-116">What's New in WPF Version 4.5</span></span>](../getting-started/whats-new.md)
- [<span data-ttu-id="5d64c-117">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="5d64c-117">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
