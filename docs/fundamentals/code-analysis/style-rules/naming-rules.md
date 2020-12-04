---
title: 코드 스타일 명명 규칙
description: 코드 요소 명명에 대 한 .NET 코드 스타일 규칙에 대해 알아봅니다.
ms.date: 09/25/2020
ms.topic: reference
author: gewarren
ms.author: gewarren
dev_langs:
- CSharp
- VB
f1_keywords:
- IDE1006
- naming rules
helpviewer_keywords:
- IDE1006
- naming code style rules [EditorConfig]
- naming rules
- EditorConfig naming conventions
ms.openlocfilehash: 8ce209e64ee7f9f9028c221daedef8fc6a993ef7
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96594160"
---
# <a name="naming-rules"></a>이름 지정 규칙

명명 규칙은 클래스, 속성, 메서드 등의 .NET 프로그래밍 언어 코드 요소 이름을 지정 하는 것과 관련이 있습니다. 예를 들어 public 멤버를 대문자로 표시해야 하거나 전용 필드를 `_`로 시작해야 하도록 지정할 수 있습니다.

명명 규칙은 다음 세 부분으로 구성 됩니다.

* 적용 되는 기호 그룹입니다.
* 규칙과 연결할 명명 스타일입니다.
* 규칙 적용의 심각도입니다.

EditorConfig 파일에 명명 규칙을 정의 합니다.

## <a name="general-syntax"></a>일반 구문

명명 규칙, 기호 그룹 또는 명명 스타일을 정의 하려면 다음 구문을 사용 하 여 하나 이상의 속성을 설정 합니다.

```ini
<prefix>.<title>.<propertyName> = <propertyValue>
```

각 속성은 한 번만 설정 해야 하지만 일부 설정에서는 쉼표로 구분 된 여러 값을 사용할 수 있습니다.

속성의 순서는 중요하지 않습니다.

### \<prefix>

**\<prefix>** 정의 되는 &mdash; 명명 규칙, 기호 그룹 또는 명명 스타일의 요소 종류를 지정 &mdash; 하 고 다음 중 하나 여야 합니다.

| 속성을 설정 하려면 | 접두사 사용 | 예제 |
| --- | --- | -- |
| 명명 규칙 | `dotnet_naming_rule` | `dotnet_naming_rule.types_should_be_pascal_case.severity = suggestion` |
| 기호 그룹 | `dotnet_naming_symbols` | `dotnet_naming_symbols.interface.applicable_kinds = interface` |
| 명명 스타일 | `dotnet_naming_style` | `dotnet_naming_style.pascal_case.capitalization = pascal_case` |

&mdash;다음 섹션에 설명 된 대로 각 유형의 정의[명명 규칙](#naming-rule-properties), [기호 그룹](#symbol-group-properties)또는 [명명 스타일](#naming-style-properties) &mdash; 에는 고유한 지원 속성이 있습니다.

### \<title>

**\<title>** 는 여러 속성 설정을 단일 정의로 연결 하는 설명이 포함 된 이름입니다. 예를 들어, 다음 속성은 두 개의 기호 그룹 정의를 생성 하 `interface` 고 `types` 각각에 두 개의 속성을 설정 합니다.

```ini
dotnet_naming_symbols.interface.applicable_kinds = interface
dotnet_naming_symbols.interface.applicable_accessibilities = public, internal, private, protected, protected_internal, private_protected

dotnet_naming_symbols.types.applicable_kinds = class, struct, interface, enum, delegate
dotnet_naming_symbols.types.applicable_accessibilities = public, internal, private, protected, protected_internal, private_protected
```

## <a name="naming-rule-properties"></a>명명 규칙 속성

규칙이 적용 되려면 모든 명명 규칙 속성이 필요 합니다.

| 속성 | Description |
| -- | -- |
| `symbols` | 이 규칙을 적용 해야 하는 기호를 정의 하는 기호 그룹의 제목입니다. |
| `style` | 이 규칙과 연결 되어야 하는 명명 스타일의 제목입니다. |
| `severity` |  명명 규칙을 적용 하는 데 사용 되는 심각도를 설정 합니다. 연결 된 값을 사용 가능한 [심각도 수준](https://docs.microsoft.com/dotnet/fundamentals/code-analysis/configuration-options#severity-level)중 하나로 설정 합니다. <sup>1</sup> |

**참고:**

1. 명명 규칙 내의 심각도 사양은 Visual Studio와 같은 개발 Ide 내 에서만 적용 됩니다. 이 설정은 c # 또는 VB 컴파일러에서 인식 되지 않으므로 빌드하는 동안에는 적용 되지 않습니다. 대신, 빌드에 명명 스타일 규칙을 적용 하려면 [이 섹션](#rule-id-ide1006-naming-rule-violation)에 설명 된 대로 규칙 ID 기반 심각도 구성을 사용 하 여 심각도를 설정 해야 합니다. 자세한 내용은 이 [GitHub 문제](https://github.com/dotnet/roslyn/issues/44201)를 참조하세요.

## <a name="rule-order"></a>규칙 순서

EditorConfig 파일에 명명 규칙을 정의 하는 순서는 중요 하지 않습니다. 명명 규칙은 규칙 자체의 정의에 따라 자동으로 정렬 됩니다. [EditorConfig 언어 서비스 확장](https://marketplace.visualstudio.com/items?itemName=MadsKristensen.EditorConfig)은 EditorConfig 파일을 분석하고, 파일의 규칙 순서가 런타임에 컴파일러에서 사용할 순서와 다른 경우를 보고할 수 있습니다.

> [!NOTE]
>
> Visual Studio 2019 버전 16.2 보다 이전 버전의 Visual Studio를 사용 하는 경우 명명 규칙은 EditorConfig 파일에서 가장 특정에서 최소 전용으로 정렬 되어야 합니다. 적용할 수 있는 첫 번째 규칙은 적용되는 유일한 규칙이 됩니다. 그러나 동일한 이름의 규칙 ‘속성’이 여러 개 있는 경우 가장 최근에 발견된 해당 이름의 속성이 우선 적용됩니다.  자세한 내용은 [파일 계층 구조 및 우선 순위](/visualstudio/ide/create-portable-custom-editor-options#file-hierarchy-and-precedence)를 참조하세요.

## <a name="symbol-group-properties"></a>기호 그룹 속성

기호 그룹에 대해 다음 속성을 설정 하 여 그룹에 포함 되는 기호를 제한할 수 있습니다. 단일 속성 설정에서 여러 값을 지정 하려면 쉼표로 구분 합니다.

| 속성 | Description | 허용되는 값 | 필수 |
| -- | -- | -- | -- |
| `applicable_kinds` | 그룹 1의 기호 종류 <sup>1</sup> | `*`(모든 기호를 지정하려면 이 값을 사용합니다.)<br/>`namespace`<br/>`class`<br/>`struct`<br/>`interface`<br/>`enum`<br/>`property`<br/>`method`<br/>`field`<br/>`event`<br/>`delegate`<br/>`parameter`<br/>`type_parameter`<br/>`local`<br/>`local_function` | 예 |
| `applicable_accessibilities` | 그룹에 있는 기호의 액세스 가능성 수준 | `*`(모든 액세스 가능성 수준을 지정하려면 이 값을 사용합니다.)<br/>`public`<br/>`internal` 또는 `friend`<br/>`private`<br/>`protected`<br/>`protected_internal` 또는 `protected_friend`<br/>`private_protected`<br/>`local` (메서드 내에 정의 된 기호의 경우) | 예 |
| `required_modifiers` | 지정 된 한정자 <sup>2</sup> 를 _모두_ 사용 하는 기호만 일치 | `abstract` 또는 `must_inherit`<br/>`async`<br/>`const`<br/>`readonly`<br/>`static` 또는 `shared` <sup>3</sup> | 아니요 |

**참고:**

1. 튜플 멤버는 현재에서 지원 되지 않습니다 `applicable_kinds` .
2. 기호 그룹은 속성의 _모든_ 한정자와 일치 합니다 `required_modifiers` .  이 속성을 생략 하면 일치에 특정 한정자가 필요 하지 않습니다. 즉, 기호 한정자가 이 규칙의 적용 여부에 영향을 주지 않습니다.
3. 그룹에 `static` 또는 속성이 있는 경우 `shared` `required_modifiers` 그룹은 `const` 암시적 이기 때문에 기호도 포함 합니다 `static` / `Shared` . 그러나 `static` 명명 규칙을 기호에 적용 하지 않으려면 `const` 의 기호 그룹을 사용 하 여 새 명명 규칙을 만들 수 있습니다 `const` .

## <a name="naming-style-properties"></a>이름 지정 스타일 속성

명명 스타일은 규칙을 사용 하 여 적용 하려는 규칙을 정의 합니다. 다음은 그 예입니다. 

* 다음으로 대문자화 `PascalCase`
* 시작 문자 `m_`
* 끝 문자 `_g`
* 단어 구분 `__`

명명 스타일에 대해 다음 속성을 설정할 수 있습니다.

| 속성 | Description | 허용되는 값 | 필수 |
| -- | -- | -- | -- |
| `capitalization` | 기호 내의 단어에 대 한 대/소문자 스타일 | `pascal_case`<br/>`camel_case`<br/>`first_word_upper`<br/>`all_upper`<br/>`all_lower` | 예<sup>1</sup> |
| `required_prefix` | 다음 문자로 시작 해야 합니다. | | 아니요 |
| `required_suffix` | 다음 문자로 끝나야 합니다. | | 아니요 |
| `word_separator` | 기호 내의 단어는이 문자로 구분 해야 합니다. | | 아니요 |

**참고:**

1. 명명 스타일의 일부로 대/소문자 스타일을 지정해야 하고, 그렇지 않으면 명명 스타일이 무시될 수 있습니다.

## <a name="default-naming-styles"></a>기본 명명 스타일

사용자 지정 명명 규칙을 지정 하지 않으면 다음 기본 스타일이 사용 됩니다.

- `public`, `private`, `internal`, `protected` 또는 `protected_internal` 접근성이 있는 클래스, 구조체, 열거형, 속성, 이벤트의 기본 명명 스타일은 파스칼식 대/소문자입니다.

- `public`, `private`, `internal`, `protected` 또는 `protected_internal` 접근성이 있는 인터페이스의 기본 명명 스타일은 필수 접두사 **I** 를 사용하는 파스칼식 대/소문자입니다.

## <a name="example"></a>예제

다음 *.editorconfig* 파일은 공용 속성, 메서드, 필드, 이벤트 및 대리자를 대문자로 시작하도록 지정하는 명명 규칙을 포함하고 있습니다. 이 명명 규칙은 값을 구분하기 위해 쉼표를 사용하여 규칙을 적용하는 여러 종류의 기호를 지정합니다.

```ini
[*.{cs,vb}]

# Defining the 'public_symbols' symbol group
dotnet_naming_symbols.public_symbols.applicable_kinds           = property,method,field,event,delegate
dotnet_naming_symbols.public_symbols.applicable_accessibilities = public
dotnet_naming_symbols.public_symbols.required_modifiers         = readonly

# Defining the `first_word_upper_case_style` naming style
dotnet_naming_style.first_word_upper_case_style.capitalization = first_word_upper

# Defining the `public_members_must_be_capitalized` naming rule, by setting the symbol group to the 'public symbols' symbol group,
dotnet_naming_rule.public_members_must_be_capitalized.symbols   = public_symbols
# setting the naming style to the `first_word_upper_case_style` naming style,
dotnet_naming_rule.public_members_must_be_capitalized.style    = first_word_upper_case_style
# and setting the severity.
dotnet_naming_rule.public_members_must_be_capitalized.severity = suggestion
```

## <a name="rule-id-ide1006-naming-rule-violation"></a><a name="rule-id-ide1006-naming-rule-violation"></a>규칙 ID: "IDE1006" (명명 규칙 위반)

모든 이름 지정 옵션에는 규칙 ID `IDE1006` 와 제목이 있습니다 `Naming rule violation` . 다음 구문을 사용 하 여 EditorConfig 파일에서 전역적으로 명명 위반의 심각도를 구성할 수 있습니다.

```ini
dotnet_diagnostic.IDE1006.severity = <severity value>
```

심각도 값은 `warning` `error` [빌드 시 적용](../overview.md#code-style-analysis)해야 합니다. 가능한 모든 심각도 값은 [심각도 수준](../configuration-options.md#severity-level)을 참조 하세요.

## <a name="see-also"></a>참고 항목

- [언어 규칙](language-rules.md)
- [서식 지정 규칙](formatting-rules.md)
- [Roslyn 명명 규칙](https://github.com/dotnet/roslyn/blob/master/.editorconfig#L63)
- [.NET 코드 스타일 규칙 참조](index.md)
