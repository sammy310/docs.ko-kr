---
title: '방법: TextBox 텍스트가 소스를 업데이트하는 시점 제어'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- source updates [WPF], timing of
- data binding [WPF], timing of source updates
- timing of source updates [WPF]
ms.assetid: ffb7b96a-351d-4c68-81e7-054033781c64
ms.openlocfilehash: 5272a19f69b3caf80fd7d5187c9a6a386cd44621
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59143275"
---
# <a name="how-to-control-when-the-textbox-text-updates-the-source"></a>방법: TextBox 텍스트가 소스를 업데이트하는 시점 제어
이 항목에서는 사용 하는 방법을 설명 합니다 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 바인딩 소스 업데이트의 타이밍을 제어 하는 속성입니다. 항목을 사용 하는 <xref:System.Windows.Controls.TextBox> 예를 들어 제어 합니다.  
  
## <a name="example"></a>예제  
 <xref:System.Windows.Controls.TextBox>.<xref:System.Windows.Controls.TextBox.Text%2A> 속성이 기본값 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 의 값 <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>합니다. 즉, 경우에 응용 프로그램에는 <xref:System.Windows.Controls.TextBox> 데이터 바인딩된을 사용 하 여 <xref:System.Windows.Controls.TextBox>입니다.<xref:System.Windows.Controls.TextBox.Text%2A> 속성를 입력 한 텍스트를 <xref:System.Windows.Controls.TextBox> 될 때까지 소스를 업데이트 하지 않습니다 합니다 <xref:System.Windows.Controls.TextBox> 포커스를 잃을 (예를 들어 클릭 하면에서 <xref:System.Windows.Controls.TextBox>).  
  
 소스를 입력할 때 자동으로 업데이트할 수를 설정 합니다 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 에 대 한 바인딩 <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>합니다. 다음 예제에서는 코드의 강조 표시 된 줄을 표시 하는 합니다 `Text` 모두의 속성을 <xref:System.Windows.Controls.TextBox> 및 <xref:System.Windows.Controls.TextBlock> 같은 소스 속성에 바인딩됩니다. <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 의 속성을 <xref:System.Windows.Controls.TextBox> 로 설정 된 바인딩 <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>.  
  
 [!code-xaml[SimpleBinding#USTHowTo](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=33-39,41-42)]  
  
 결과적으로 <xref:System.Windows.Controls.TextBlock> 사용자가 텍스트 (소스가 변경) 하므로 같은 텍스트가 표시는 <xref:System.Windows.Controls.TextBox>샘플의 다음 스크린샷에 표시 된 대로:  
  
 ![단순 데이터 바인딩 샘플 스크린 샷](./media/databindingsimplebindingsample2.png "DataBindingSimpleBindingSample2")  
  
 대화 상자 또는 사용자가 편집 가능한 폼 및 사용자가 필드 편집을 마치고 "확인"을 클릭할 때까지 소스 업데이트를 지연 하려는 설정할 수 있습니다 하는 경우는 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 값에 대 한 바인딩 <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>다음 예제와 같이:  
  
 [!code-xaml[UpdateSource#2](~/samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml#2)]  
  
 설정한 경우 합니다 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 값을 <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>, 응용 프로그램을 호출 하는 경우에 소스 값을 변경 합니다 <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> 메서드. 다음 예제에서는 호출 하는 방법을 보여 줍니다 <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> 에 대 한 `itemNameTextBox`:  
  
 [!code-csharp[UpdateSource#1](~/samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml.cs#1)]
 [!code-vb[UpdateSource#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UpdateSource/VisualBasic/Window1.xaml.vb#1)]  
  
> [!NOTE]
>  다른 컨트롤의 속성에 대 한 동일한 기법을 사용할 수 있지만 대부분의 다른 속성 기본값 있는 염두에 둡니다 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 의 값 <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>합니다. 자세한 내용은 참조는 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 속성 페이지.  
  
> [!NOTE]
>  합니다 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 속성 소스 업데이트를 사용 하 여 처리 이므로 관련이 <xref:System.Windows.Data.BindingMode.TwoWay> 또는 <xref:System.Windows.Data.BindingMode.OneWayToSource> 바인딩. 에 대 한 <xref:System.Windows.Data.BindingMode.TwoWay> 및 <xref:System.Windows.Data.BindingMode.OneWayToSource> 바인딩 작업에 원본 개체 속성 변경 알림을 제공 합니다. 자세한 내용은 이 항목에 제시된 샘플을 참조하세요. 또한 [속성 변경 알림 구현](how-to-implement-property-change-notification.md)을 참조할 수 있습니다.  
  
## <a name="see-also"></a>참고자료

- [방법 항목](data-binding-how-to-topics.md)
