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
# <a name="how-to-bind-to-the-results-of-a-linq-query"></a>방법: LINQ 쿼리 결과에 바인딩

이 예제에서는 LINQ 쿼리를 실행 한 다음 결과에 바인딩하는 방법을 보여 줍니다.

## <a name="example"></a>예제

다음 예에서는 두 개의 목록 상자를 만듭니다. 첫 번째 목록 상자에는 세 개의 목록 항목이 있습니다.

[!code-xaml[LinqExample#UI](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml#ui)]

첫 번째 목록 상자에서 항목을 선택 하면 다음 이벤트 처리기가 호출 됩니다. 이 예제에서 `Tasks`은 `Task` 개체의 컬렉션입니다. `Task` 클래스에는 `Priority`라는 속성이 있습니다. 이 이벤트 처리기는 선택한 우선 순위 값을 가진 `Task` 개체의 컬렉션을 반환 하는 LINQ 쿼리를 실행 한 다음 <xref:System.Windows.FrameworkElement.DataContext%2A>로 설정 합니다.

[!code-csharp[LinqExample#Using](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#using)]
[!code-csharp[LinqExample#Tasks](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#tasks)]
[!code-csharp[LinqExample#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#handler)]

두 번째 목록 상자는 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 값이 `{Binding}`으로 설정 되어 있기 때문에 해당 컬렉션에 바인딩됩니다. 그러면 반환 된 컬렉션 (`myTaskTemplate` <xref:System.Windows.DataTemplate>)을 표시 합니다.

## <a name="see-also"></a>참조

- [XAML의 바인딩에 사용할 수 있는 데이터 만들기](how-to-make-data-available-for-binding-in-xaml.md)
- [선택에 따라 수집 및 표시 정보에 바인딩](how-to-bind-to-a-collection-and-display-information-based-on-selection.md)
- [WPF 버전 4.5의 새로운 기능](../getting-started/whats-new.md)
- [데이터 바인딩 개요](../../../desktop-wpf/data/data-binding-overview.md)
