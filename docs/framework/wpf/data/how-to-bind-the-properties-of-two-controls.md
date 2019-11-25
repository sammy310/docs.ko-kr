---
title: '방법: 두 컨트롤의 속성 바인딩'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], binding properties of two controls
- binding properties of two controls [WPF]
- controls [WPF], binding properties of
ms.assetid: 06318fac-6afd-4c7d-a277-6d7ef50f47bc
ms.openlocfilehash: d38c473b8c4d3f71f1e3decd4f66be248665c57b
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73974812"
---
# <a name="how-to-bind-the-properties-of-two-controls"></a>방법: 두 컨트롤의 속성 바인딩

이 예제에서는 <xref:System.Windows.Data.Binding.ElementName%2A> 속성을 사용 하 여 인스턴스화된 한 컨트롤의 속성을 다른 컨트롤의 속성에 바인딩하는 방법을 보여 줍니다.

## <a name="example"></a>예제

다음 예제에서는 <xref:System.Windows.Controls.Canvas>의 <xref:System.Windows.Controls.Panel.Background%2A> 속성을 <xref:System.Windows.Controls.ComboBox>의 [Selecteditem. Content](xref:System.Windows.Controls.ContentControl.Content%2A) 속성에 바인딩하는 방법을 보여 줍니다.

[!code-xaml[BindDptoDp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/BindDPtoDP/CS/Window1.xaml#1)]

이 예를 렌더링하면 다음과 같이 표시됩니다.

![녹색 값이 선택 되 고 녹색 사각형이 있는 콤보 상자를 보여 주는 스크린샷](./media/how-to-bind-the-properties-of-two-controls/data-binding-bind-background-canvas.png)

> [!NOTE]
> 바인딩 대상 속성 (이 예제에서는 <xref:System.Windows.Controls.Panel.Background%2A> 속성)은 종속성 속성 이어야 합니다. 자세한 내용은 [데이터 바인딩 개요](../../../desktop-wpf/data/data-binding-overview.md)를 참조하세요.

## <a name="see-also"></a>참조

- [바인딩 소스 지정](how-to-specify-the-binding-source.md)
- [방법 항목](data-binding-how-to-topics.md)
