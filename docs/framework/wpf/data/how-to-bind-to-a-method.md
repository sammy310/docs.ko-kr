---
title: '방법: 메서드 바인딩'
description: 다음 예제에 따라 Windows Presentation Foundation (WPF)에서 개체의 메서드에 바인딩하는 방법을 알아봅니다.
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], binding to methods using ObjectDataProvider
- binding [WPF], to methods
- methods [WPF], binding to
ms.assetid: 5f55e71e-2182-42a0-88d1-700cc1427a7a
ms.openlocfilehash: 9501e6357203c21651e85f1d65059be1d70becf2
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619600"
---
# <a name="how-to-bind-to-a-method"></a>방법: 메서드 바인딩
다음 예제에서는를 사용 하 여 메서드에 바인딩하는 방법을 보여 줍니다 <xref:System.Windows.Data.ObjectDataProvider> .  
  
## <a name="example"></a>예제  
 이 예에서 `TemperatureScale`는 `ConvertTemp` 메서드가 있는 클래스입니다. 이 메서드에서는 두 개의 매개 변수(`double` 중 하나와 `enum` 형식 `TempType)` 중 하나)를 사용하고 지정된 값을 한 온도 눈금에서 다른 눈금으로 변환합니다. 다음 예제에서는 개체를 <xref:System.Windows.Data.ObjectDataProvider> 인스턴스화하는 데 사용 됩니다 `TemperatureScale` . `ConvertTemp` 메서드는 지정된 두 매개 변수를 사용하여 호출합니다.  
  
 [!code-xaml[BindToMethod#WindowResources](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToMethod/CS/Window1.xaml#windowresources)]  
  
 이제 메서드를 리소스로 사용할 수 있으므로, 해당 결과에 바인딩할 수 있습니다. 다음 예제에서의 및의 <xref:System.Windows.Controls.TextBox.Text%2A> 속성은 <xref:System.Windows.Controls.TextBox> <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> <xref:System.Windows.Controls.ComboBox> 메서드의 두 매개 변수에 바인딩됩니다. 그러면 변환될 대상 온도와 변환될 소스 온도 눈금을 지정할 수 있습니다. 는 <xref:System.Windows.Data.Binding.BindsDirectlyToSource%2A> `true` <xref:System.Windows.Data.ObjectDataProvider.MethodParameters%2A> 인스턴스의 속성에 바인딩하고 <xref:System.Windows.Data.ObjectDataProvider> <xref:System.Windows.Data.ObjectDataProvider> (개체)로 래핑된 개체의 속성이 아닌로 설정 됩니다 `TemperatureScale` .  
  
 <xref:System.Windows.Controls.ContentControl.Content%2A> <xref:System.Windows.Controls.Label> 사용자가의 콘텐츠 또는 선택 항목을 수정할 때 마지막으로 업데이트 한의입니다 <xref:System.Windows.Controls.TextBox> <xref:System.Windows.Controls.ComboBox> .  
  
 [!code-xaml[BindToMethod#UI](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToMethod/CS/Window1.xaml#ui)]  
  
 변환기는 `DoubleToString` double을 사용 하 여 <xref:System.Windows.Data.IValueConverter.Convert%2A> 방향의 문자열 (바인딩 소스에서 바인딩 대상까지 <xref:System.Windows.Controls.TextBox.Text%2A> 속성)로 변환 하 고를 `string` `double` 방향으로 변환 합니다 <xref:System.Windows.Data.IValueConverter.ConvertBack%2A> .  
  
 는 `InvalidationCharacterRule` <xref:System.Windows.Controls.ValidationRule> 잘못 된 문자를 확인 하는입니다. 의 빨간색 테두리 인 기본 오류 템플릿은 <xref:System.Windows.Controls.TextBox> 입력 값이 double 값이 아닌 경우 사용자에 게 알리는 것으로 나타납니다.  
  
## <a name="see-also"></a>참고 항목

- [방법 도움말 항목](data-binding-how-to-topics.md)
- [열거형에 바인딩](how-to-bind-to-an-enumeration.md)
