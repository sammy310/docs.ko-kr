---
title: '방법: 바인딩 유효성 검사 구현'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- validation of binding [WPF]
- data binding [WPF], validation of binding
- binding [WPF], validation of
ms.assetid: eb98b33d-9866-49ae-b981-bc5ff20d607a
ms.openlocfilehash: 7a1a8df78a785066992472c7de37f958ae3467f1
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/25/2019
ms.locfileid: "72920163"
---
# <a name="how-to-implement-binding-validation"></a>방법: 바인딩 유효성 검사 구현

이 예제에서는 <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> 및 스타일 트리거를 사용 하 여 사용자 지정 유효성 검사 규칙에 따라 잘못 된 값이 입력 될 때 사용자에 게 알리는 시각적 피드백을 제공 하는 방법을 보여 줍니다.

## <a name="example"></a>예제

다음 예제에서 <xref:System.Windows.Controls.TextBox> 텍스트 콘텐츠는 `ods`이라는 바인딩 소스 개체의 `Age` 속성 (int 형식)에 바인딩됩니다. 바인딩이 `AgeRangeRule`이라는 유효성 검사 규칙을 사용하도록 설정되어 있으므로 숫자가 아닌 문자 또는 21보다 작거나 130보다 큰 값을 입력하면 빨간색 느낌표가 텍스트 상자 옆에 나타나고 텍스트 상자 위로 마우스를 이동하면 오류 메시지가 포함된 도구 설명이 나타납니다.

[!code-xaml[BindValidation#2](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#2)]

다음 예제에서는 <xref:System.Windows.Controls.ValidationRule>에서 상속 되 고 <xref:System.Windows.Controls.ValidationRule.Validate%2A> 메서드를 재정의 하는 `AgeRangeRule`의 구현을 보여 줍니다. 값에 대해 `Int32.Parse` 메서드를 호출 하 여 잘못 된 문자를 포함 하지 않는지 확인 합니다. <xref:System.Windows.Controls.ValidationRule.Validate%2A> 메서드는 구문 분석 중에 예외가 catch 되는지 여부와 사용 기간 값이 하한값과 상한 인지 여부를 기준으로 값이 유효한 지 여부를 나타내는 <xref:System.Windows.Controls.ValidationResult>을 반환 합니다.

[!code-csharp[BindValidation#3](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/AgeRangeRule.cs#3)]
[!code-vb[BindValidation#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BindValidation/VisualBasic/AgeRangeRule.vb#3)]

다음 예제에서는 사용자에 게 유효성 검사 오류를 알리기 위해 빨간색 느낌표를 만드는 사용자 지정 <xref:System.Windows.Controls.ControlTemplate> `validationTemplate`을 보여 줍니다. 컨트롤 템플릿을 사용하여 컨트롤의 모양을 다시 정의합니다.

[!code-xaml[BindValidation#4](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#4)]

다음 예제와 같이 오류 메시지를 표시 하는 <xref:System.Windows.Controls.ToolTip> `textBoxInError`이라는 스타일을 사용 하 여 생성 됩니다. <xref:System.Windows.Controls.Validation.HasError%2A> 값이 `true`되는 경우 트리거는 현재 <xref:System.Windows.Controls.TextBox>의 도구 설명을 첫 번째 유효성 검사 오류로 설정 합니다. <xref:System.Windows.Data.Binding.RelativeSource%2A> 현재 요소를 참조 하는 <xref:System.Windows.Data.RelativeSourceMode.Self>로 설정 됩니다.

[!code-xaml[BindValidation#5](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#5)]

전체 예제는 [바인딩 유효성 검사 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/BindValidation)을 참조 하세요.
  
사용자 지정 <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> 제공 하지 않으면 유효성 검사 오류가 있을 때 사용자에 게 시각적 피드백을 제공 하는 기본 오류 템플릿이 표시 됩니다. 자세한 내용은 [데이터 바인딩 개요](data-binding-overview.md)의 “데이터 유효성 검사”를 참조하세요. 또한 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]은 바인딩 소스 속성을 업데이트하는 동안 throw된 예외를 catch하는 기본 제공 유효성 검사 규칙을 제공합니다. 자세한 내용은 <xref:System.Windows.Controls.ExceptionValidationRule>을 참조하십시오.

## <a name="see-also"></a>참조

- [데이터 바인딩 개요](data-binding-overview.md)
- [방법 항목](data-binding-how-to-topics.md)
