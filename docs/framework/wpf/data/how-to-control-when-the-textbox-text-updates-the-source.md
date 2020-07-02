---
title: '방법: TextBox 텍스트의 소스를 업데이트하는 시점 제어'
description: Windows Presentation Foundation (WPF)에서 System.windows.data.binding.updatesourcetrigger 속성을 사용 하 여 바인딩 소스 업데이트의 타이밍을 제어 합니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- source updates [WPF], timing of
- data binding [WPF], timing of source updates
- timing of source updates [WPF]
ms.assetid: ffb7b96a-351d-4c68-81e7-054033781c64
ms.openlocfilehash: 8f6eb5beb0d14a951f6e6cf6eb81e130f5a3e194
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622785"
---
# <a name="how-to-control-when-the-textbox-text-updates-the-source"></a>방법: TextBox 텍스트의 소스를 업데이트하는 시점 제어
이 항목에서는 속성을 사용 하 여 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 바인딩 소스 업데이트의 타이밍을 제어 하는 방법에 대해 설명 합니다. 이 항목에서는 <xref:System.Windows.Controls.TextBox> 컨트롤을 예제로 사용 합니다.

## <a name="example"></a>예제
 <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType>속성의 기본값은 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus> 입니다. 즉, 응용 프로그램에 데이터 바인딩된 속성을 가진가 있는 경우에 입력 하는 <xref:System.Windows.Controls.TextBox> <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> 텍스트는가 <xref:System.Windows.Controls.TextBox> 포커스를 잃을 때까지 (예 <xref:System.Windows.Controls.TextBox> 를 들어에서 떨어진 곳을 클릭 하는 경우) 소스를 업데이트 하지 않습니다 <xref:System.Windows.Controls.TextBox> .

 입력할 때 원본을 업데이트 하려면 바인딩의를로 설정 합니다 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged> . 다음 예제에서 강조 표시 된 코드 줄은 `Text` 및의 속성이 모두 <xref:System.Windows.Controls.TextBox> <xref:System.Windows.Controls.TextBlock> 동일한 소스 속성에 바인딩되어 있음을 보여 줍니다. <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>바인딩의 속성은 <xref:System.Windows.Controls.TextBox> 로 설정 됩니다 <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged> .

 [!code-xaml[SimpleBinding#USTHowTo](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=33-39,41-42)]

 결과적으로,는 <xref:System.Windows.Controls.TextBlock> <xref:System.Windows.Controls.TextBox> 샘플의 다음 스크린샷에 표시 된 것 처럼 사용자가에 텍스트를 입력할 때 원본 변경 내용으로 인해 동일한 텍스트를 표시 합니다.

 ![간단한 데이터 바인딩을 보여 주는 스크린샷](./media/how-to-control-when-the-textbox-text-updates-the-source/data-binding-simple-binding-sample.png)

 대화 상자 또는 사용자가 편집할 수 있는 폼이 있고 사용자가 필드 편집을 마치고 "확인"을 클릭할 때까지 원본 업데이트를 지연 하려는 경우 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> <xref:System.Windows.Data.UpdateSourceTrigger.Explicit> 다음 예제와 같이 바인딩의 값을로 설정할 수 있습니다.

 [!code-xaml[UpdateSource#2](~/samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml#2)]

 값을로 설정 하면 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> <xref:System.Windows.Data.UpdateSourceTrigger.Explicit> 응용 프로그램에서 메서드를 호출 하는 경우에만 소스 값이 변경 <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> 됩니다. 다음 예제에서는에 대해를 호출 하는 방법을 보여 줍니다 <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> `itemNameTextBox` .

 [!code-csharp[UpdateSource#1](~/samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml.cs#1)]
 [!code-vb[UpdateSource#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UpdateSource/VisualBasic/Window1.xaml.vb#1)]

> [!NOTE]
> 다른 컨트롤의 속성에 동일한 기법을 사용할 수 있지만 대부분의 다른 속성에는 기본값이 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged> 있습니다. 자세한 내용은 속성 페이지를 참조 하세요 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> .

> [!NOTE]
> <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>속성은 원본 업데이트를 처리 하므로 또는 바인딩과만 관련 됩니다 <xref:System.Windows.Data.BindingMode.TwoWay> <xref:System.Windows.Data.BindingMode.OneWayToSource> . <xref:System.Windows.Data.BindingMode.TwoWay>및 <xref:System.Windows.Data.BindingMode.OneWayToSource> 바인딩이 작동 하려면 소스 개체가 속성 변경 알림을 제공 해야 합니다. 자세한 내용은 이 항목에 제시된 샘플을 참조하세요. 또한 [속성 변경 알림 구현](how-to-implement-property-change-notification.md)을 참조할 수 있습니다.

## <a name="see-also"></a>참고 항목

- [방법 도움말 항목](data-binding-how-to-topics.md)
