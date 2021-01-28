---
title: 코드 스타일 언어 규칙
description: 'C # 및 Visual Basic 언어 구문을 사용 하기 위한 다양 한 코드 스타일 규칙에 대해 알아봅니다.'
ms.date: 09/25/2020
ms.topic: reference
author: gewarren
ms.author: gewarren
dev_langs:
- CSharp
- VB
helpviewer_keywords:
- language code style rules [EditorConfig]
- language rules
- EditorConfig language conventions
ms.openlocfilehash: 2aa2261534363f1da6a2109f092e08d210ebd915
ms.sourcegitcommit: 7e42488c2f8f63f6d499b5f8fb1dec5bac9ad254
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2021
ms.locfileid: "98957977"
---
# <a name="language-rules"></a>언어 규칙

코드 스타일 언어 규칙은 한정자 및 괄호와 같은 .NET 프로그래밍 언어의 다양 한 구문이 사용 되는 방식에 영향을 줍니다. 규칙은 다음과 같은 범주로 분류 됩니다.

- [.Net 스타일 규칙](#net-style-rules): c # 및 Visual Basic 모두에 적용 되는 규칙입니다. 이러한 규칙에 대 한 EditorConfig 옵션 이름은 접두사로 시작 합니다 `dotnet_style_` .
- [C # 스타일 규칙](#c-style-rules): c # 언어에만 적용 되는 규칙입니다. 이러한 규칙에 대 한 EditorConfig 옵션 이름은 접두사로 시작 합니다 `csharp_style_` .
- [Visual Basic 스타일 규칙](#visual-basic-style-rules): Visual Bsic language에만 적용 되는 규칙입니다. 이러한 규칙에 대 한 EditorConfig 옵션 이름은 접두사로 시작 합니다 `visual_basic_style_` .

## <a name="option-format"></a>옵션 형식

언어 규칙에 대 한 옵션은 다음과 같은 형식의 EditorConfig 파일에 지정할 수 있습니다.

`option_name = value` (Visual Studio 2019 버전 16.9 Preview 2 이상)

또는

`option_name = value:severity`

- **값**

  각 언어 규칙에 대해 스타일을 선호 하는지 여부를 정의 하는 값을 지정 합니다. 대부분의 규칙은 `true`(이 스타일 선호) 또는 `false`(이 스타일 선호 안 함) 값을 허용합니다. 다른 규칙은 `when_on_single_line`, `never` 등의 값을 허용합니다.

- **심각도** (Visual Studio 2019 버전 16.9 Preview 2 이상 버전의 경우 선택 사항)

  규칙의 두 번째 부분은 규칙의 [심각도 수준을](../configuration-options.md#severity-level) 지정 합니다. 이러한 방식으로 지정 된 경우 심각도 설정은 Visual Studio와 같은 개발 Ide 내 에서만 적용 됩니다. 빌드 중에는 적용 *되지* 않습니다.

  빌드 시 코드 스타일 규칙을 적용 하려면 분석기에 대 한 규칙 ID 기반 심각도 구성 구문을 대신 사용 하 여 심각도를 설정 합니다. 구문은 `dotnet_diagnostic.<rule ID>.severity = <severity>` 형식을 사용합니다(예: `dotnet_diagnostic.IDE0040.severity = silent`). 자세한 내용은 [심각도 수준](../configuration-options.md#severity-level)을 참조 하세요.

> [!TIP]
>
> Visual Studio 2019 버전 16.3부터, 스타일 위반이 발생한 후에 [빠른 작업](/visualstudio/ide/quick-actions) 전구 메뉴에서 코드 스타일 규칙을 구성할 수 있습니다. 자세한 내용은 [Visual Studio에서 자동으로 코드 스타일 구성](/visualstudio/ide/editorconfig-language-conventions#automatically-configure-code-styles-in-visual-studio)을 참조 하세요.

## <a name="net-style-rules"></a>.NET 스타일 규칙

이 섹션의 스타일 규칙은 C# 및 Visual Basic 모두에 적용됩니다.

- [' this. ' 및 ' Me. ' 한정자](ide0003-ide0009.md)
  - [dotnet_style_qualification_for_field](ide0003-ide0009.md#dotnet_style_qualification_for_field)
  - [dotnet_style_qualification_for_property](ide0003-ide0009.md#dotnet_style_qualification_for_property)
  - [dotnet_style_qualification_for_method](ide0003-ide0009.md#dotnet_style_qualification_for_method)
  - [dotnet_style_qualification_for_event](ide0003-ide0009.md#dotnet_style_qualification_for_event)
- [형식 참조를 위한 프레임워크 형식 이름 대신 언어 키워드](ide0049.md)
  - [dotnet_style_predefined_type_for_locals_parameters_members](ide0049.md#dotnet_style_predefined_type_for_locals_parameters_members)
  - [dotnet_style_predefined_type_for_member_access](ide0049.md#dotnet_style_predefined_type_for_member_access)
- [한정자 기본 설정](modifier-preferences.md#net-modifier-preferences)
  - [dotnet_style_require_accessibility_modifiers](ide0040.md#dotnet_style_require_accessibility_modifiers)
  - [csharp_preferred_modifier_order](ide0036.md#csharp_preferred_modifier_order)
  - [visual_basic_preferred_modifier_order](ide0036.md#visual_basic_preferred_modifier_order)
  - [dotnet_style_readonly_field](ide0044.md#dotnet_style_readonly_field)
- [괄호 기본 설정](ide0047-ide0048.md)
  - [dotnet_style_parentheses_in_arithmetic_binary_operators](ide0047-ide0048.md#dotnet_style_parentheses_in_arithmetic_binary_operators)
  - [dotnet_style_parentheses_in_relational_binary_operators](ide0047-ide0048.md#dotnet_style_parentheses_in_relational_binary_operators)
  - [dotnet_style_parentheses_in_other_binary_operators](ide0047-ide0048.md#dotnet_style_parentheses_in_other_binary_operators)
  - [dotnet_style_parentheses_in_other_operators](ide0047-ide0048.md#dotnet_style_parentheses_in_other_operators)
- [식 수준 기본 설정](expression-level-preferences.md#net-expression-level-preferences)
  - [dotnet_style_object_initializer](ide0017.md#dotnet_style_object_initializer)
  - [dotnet_style_collection_initializer](ide0028.md#dotnet_style_collection_initializer)
  - [dotnet_style_explicit_tuple_names](ide0033.md#dotnet_style_explicit_tuple_names)
  - [dotnet_style_prefer_inferred_tuple_names](ide0037.md#dotnet_style_prefer_inferred_tuple_names)
  - [dotnet_style_prefer_inferred_anonymous_type_member_names](ide0037.md#dotnet_style_prefer_inferred_anonymous_type_member_names)
  - [dotnet_style_prefer_auto_properties](ide0032.md#dotnet_style_prefer_auto_properties)
  - [dotnet_style_prefer_conditional_expression_over_assignment](ide0045.md#dotnet_style_prefer_conditional_expression_over_assignment)
  - [dotnet_style_prefer_conditional_expression_over_return](ide0046.md#dotnet_style_prefer_conditional_expression_over_return)
  - [dotnet_style_prefer_compound_assignment](ide0054-ide0074.md#dotnet_style_prefer_compound_assignment)
  - [dotnet_style_prefer_simplified_interpolation](ide0071.md#dotnet_style_prefer_simplified_interpolation)
  - [dotnet_style_prefer_simplified_boolean_expressions](ide0075.md#dotnet_style_prefer_simplified_boolean_expressions)
  - [Switch 문에 누락 된 사례 추가](ide0010.md) -이 규칙에는 코드 스타일 옵션이 없습니다.
  - [무명 형식을 튜플로 변환](ide0050.md) -이 규칙에는 코드 스타일 옵션이 없습니다.
  - [' 해시 코드 '를 사용](ide0070.md) 합니다 .이 규칙에는 코드 스타일 옵션이 없습니다.
  - [' Typeof '를 ' nameof '로 변환](ide0082.md) -이 규칙에는 코드 스타일 옵션이 없습니다.
- [Null 검사 기본 설정](null-checking-preferences.md#net-null-checking-preferences)
  - [dotnet_style_coalesce_expression](ide0029-ide0030.md#dotnet_style_coalesce_expression)
  - [dotnet_style_null_propagation](ide0031.md#dotnet_style_null_propagation)
  - [dotnet_style_prefer_is_null_check_over_reference_equality_method](ide0041.md#dotnet_style_prefer_is_null_check_over_reference_equality_method)
- [파일 헤더 기본 설정](ide0073.md)
  - [file_header_template](ide0073.md#file_header_template)

## <a name="c-style-rules"></a>C # 스타일 규칙

이 섹션의 스타일 규칙은 c # 언어에만 적용 됩니다.

- [' var ' 기본 설정](ide0007-ide0008.md)
  - [csharp_style_var_for_built_in_types](ide0007-ide0008.md#csharp_style_var_for_built_in_types)
  - [csharp_style_var_when_type_is_apparent](ide0007-ide0008.md#csharp_style_var_when_type_is_apparent)
  - [csharp_style_var_elsewhere](ide0007-ide0008.md#csharp_style_var_elsewhere)
- [식 본문 멤버](expression-bodied-members.md)
  - [csharp_style_expression_bodied_methods](ide0022.md#csharp_style_expression_bodied_methods)
  - [csharp_style_expression_bodied_constructors](ide0021.md#csharp_style_expression_bodied_constructors)
  - [csharp_style_expression_bodied_operators](ide0023-ide0024.md#csharp_style_expression_bodied_operators)
  - [csharp_style_expression_bodied_properties](ide0025.md#csharp_style_expression_bodied_properties)
  - [csharp_style_expression_bodied_indexers](ide0026.md#csharp_style_expression_bodied_indexers)
  - [csharp_style_expression_bodied_accessors](ide0027.md#csharp_style_expression_bodied_accessors)
  - [csharp_style_expression_bodied_lambdas](ide0053.md#csharp_style_expression_bodied_lambdas)
  - [csharp_style_expression_bodied_local_functions](ide0061.md#csharp_style_expression_bodied_local_functions)
- [패턴 일치 기본 설정](pattern-matching-preferences.md)
  - [csharp_style_pattern_matching_over_is_with_cast_check](ide0020-ide0038.md#csharp_style_pattern_matching_over_is_with_cast_check)
  - [csharp_style_pattern_matching_over_as_with_null_check](ide0019.md#csharp_style_pattern_matching_over_as_with_null_check)
  - [csharp_style_prefer_switch_expression](ide0066.md#csharp_style_prefer_switch_expression)
  - [csharp_style_prefer_pattern_matching](ide0078.md#csharp_style_prefer_pattern_matching)
  - [csharp_style_prefer_not_pattern](ide0083.md#csharp_style_prefer_not_pattern)
- [식 수준 기본 설정](expression-level-preferences.md#c-expression-level-preferences)
  - [csharp_style_inlined_variable_declaration](ide0018.md#csharp_style_inlined_variable_declaration)
  - [csharp_prefer_simple_default_expression](ide0034.md#csharp_prefer_simple_default_expression)
  - [csharp_style_pattern_local_over_anonymous_function](ide0039.md#csharp_style_pattern_local_over_anonymous_function)
  - [csharp_style_deconstructed_variable_declaration](ide0042.md#csharp_style_deconstructed_variable_declaration)
  - [csharp_style_prefer_index_operator](ide0056.md#csharp_style_prefer_index_operator)
  - [csharp_style_prefer_range_operator](ide0057.md#csharp_style_prefer_range_operator)
  - [csharp_style_implicit_object_creation_when_type_is_apparent](ide0090.md#csharp_style_implicit_object_creation_when_type_is_apparent)
  - [스위치 식에 누락 된 사례 추가](ide0072.md) -이 규칙에는 코드 스타일 옵션이 없습니다.
- ["Null" 검사 기본 설정](null-checking-preferences.md#c-null-checking-preferences)
  - [csharp_style_throw_expression](ide0016.md#csharp_style_throw_expression)
  - [csharp_style_conditional_delegate_call](ide1005.md#csharp_style_conditional_delegate_call)
- [코드 블록 기본 설정](code-block-preferences.md)
  - [csharp_prefer_braces](ide0011.md#csharp_prefer_braces)
  - [csharp_prefer_simple_using_statement](ide0063.md#csharp_prefer_simple_using_statement)
- [' using ' 지시문 기본 설정](ide0065.md)
  - [csharp_using_directive_placement](ide0065.md#csharp_using_directive_placement)
- [한정자 기본 설정](modifier-preferences.md#c-modifier-preferences)
  - [csharp_prefer_static_local_function](ide0062.md#csharp_prefer_static_local_function)
  - [구조체 필드를 쓰기 가능 하 게 설정](ide0064.md) -이 규칙에는 코드 스타일 옵션이 없습니다.

## <a name="visual-basic-style-rules"></a>Visual Basic 스타일 규칙

이 섹션의 스타일 규칙은 Visual Basic 언어에만 적용 됩니다.

- [패턴 일치 기본 설정](pattern-matching-preferences.md)
  - [visual_basic_style_prefer_isnot_expression](ide0084.md#visual_basic_style_prefer_isnot_expression)

## <a name="see-also"></a>참고 항목

- [불필요한 코드 규칙](unnecessary-code-rules.md)
- [서식 지정 규칙](formatting-rules.md)
- [이름 지정 규칙](naming-rules.md)
- [.NET 코드 스타일 규칙 참조](index.md)
