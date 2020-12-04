---
title: 코드 품질 규칙 구성 옵션
description: 코드 품질 규칙에 대 한 추가 구성 옵션을 지정 하는 방법을 알아봅니다.
ms.date: 09/24/2020
ms.topic: conceptual
no-loc:
- EditorConfig
ms.openlocfilehash: af2984e73c554e8a1e1b32df9460933f86cc41be
ms.sourcegitcommit: 2e4adc490c1d2a705a0592b295d606b10b9f51f1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/25/2020
ms.locfileid: "96592573"
---
# <a name="code-quality-rule-configuration-options"></a>코드 품질 규칙 구성 옵션

*코드 품질* 규칙에는 [심각도를 구성](configuration-options.md#severity-level)하는 것 외에 추가 구성 옵션이 있습니다. 예를 들어 각 코드 품질 분석기는 코드 베이스의 특정 부분에만 적용 되도록 구성할 수 있습니다. [EditorConfig](https://editorconfig.org)규칙 심각도 및 일반 편집기 기본 설정을 지정 하는 동일한 파일에 키-값 쌍을 추가 하 여 이러한 옵션을 지정할 수 있습니다.

## <a name="option-scopes"></a>옵션 범위

모든 규칙, 규칙 범주 (예: 보안 또는 디자인) 또는 특정 규칙에 대해 각 구체화 옵션을 구성할 수 있습니다.

### <a name="all-rules"></a>모든 규칙

*모든* 규칙에 대 한 옵션을 구성 하는 구문은 다음과 같습니다.

|구문|예제|
|-|-|
| dotnet_code_quality. OptionName = OptionValue | `dotnet_code_quality.api_surface = public` |

### <a name="category-of-rules"></a>규칙 범주

규칙 *범주* 에 대 한 옵션을 구성 하는 구문 (예: 이름 지정, 디자인 또는 성능)은 다음과 같습니다.

|구문|예제|
|-|-|
| dotnet_code_quality. RuleCategory OptionName = OptionValue | `dotnet_code_quality.Naming.api_surface = public` |

### <a name="specific-rule"></a>특정 규칙

*특정* 규칙에 대 한 옵션을 구성 하는 구문은 다음과 같습니다.

|구문|예제|
|-|-|
| dotnet_code_quality. RuleId OptionName = OptionValue | `dotnet_code_quality.CA1040.api_surface = public` |

## <a name="options"></a>옵션

이 섹션에서는 사용 가능한 옵션 중 일부를 나열 합니다. 사용 가능한 옵션의 전체 목록을 보려면 [Analyzer 구성](https://github.com/dotnet/roslyn-analyzers/blob/master/docs/Analyzer%20Configuration.md)을 참조 하세요.

### <a name="api_surface"></a>api_surface

| 설명 | 허용 가능한 값 | 기본값 | 구성 가능한 규칙 |
| - | - | - | - |
| 분석할 API 표면의 부분 | `public`<br/>`internal` 또는 `friend`<br/>`private`<br/>`all`<br/><br/>여러 값을 쉼표 (,)로 구분 합니다. | `public` | [CA1000](quality-rules/ca1000.md) [CA1003](quality-rules/ca1003.md) [CA1008](quality-rules/ca1008.md) [CA1010](quality-rules/ca1010.md)<br/>[CA1012](quality-rules/ca1012.md) [CA1024](quality-rules/ca1024.md) [CA1027](quality-rules/ca1027.md) [CA1028](quality-rules/ca1028.md)<br/>[CA1030](quality-rules/ca1030.md) [CA1036](quality-rules/ca1036.md) [CA1040](quality-rules/ca1040.md) [CA1041](quality-rules/ca1041.md)<br/>[CA1043](quality-rules/ca1043.md) [CA1044](quality-rules/ca1044.md) [CA1051](quality-rules/ca1051.md) [CA1052](quality-rules/ca1052.md)<br/>[CA1054](quality-rules/ca1054.md) [CA1055](quality-rules/ca1055.md) [CA1056](quality-rules/ca1056.md) [CA1058](quality-rules/ca1058.md)<br/>[CA1063](quality-rules/ca1063.md) [CA1708](quality-rules/ca1708.md) [CA1710](quality-rules/ca1710.md) [CA1711](quality-rules/ca1711.md)<br/>[CA1714](quality-rules/ca1714.md) [CA1715](quality-rules/ca1715.md) [CA1716](quality-rules/ca1716.md) [CA1717](quality-rules/ca1717.md)<br/>[CA1720](quality-rules/ca1720.md) [CA1721](quality-rules/ca1721.md) [CA1725](quality-rules/ca1725.md) [CA1801](quality-rules/ca1801.md)<br/>[CA1802](quality-rules/ca1802.md) [CA1815](quality-rules/ca1815.md) [CA1819](quality-rules/ca1819.md) [CA2217](quality-rules/ca2217.md)<br/>[CA2225](quality-rules/ca2225.md) [CA2226](quality-rules/ca2226.md) [CA2231](quality-rules/ca2231.md) [CA2234](quality-rules/ca2234.md)<br/>|

### <a name="exclude_async_void_methods"></a>exclude_async_void_methods

| 설명 | 허용 가능한 값 | 기본값 | 구성 가능한 규칙 |
| - | - | - | - |
| 값을 반환 하지 않는 비동기 메서드를 무시할지 여부 | `true`<br/>`false` | `false` | [CA2007](quality-rules/ca2007.md) |

> [!NOTE]
> 이 옵션은 `skip_async_void_methods` 이전 버전에서 이름이 지정 되었습니다.

### <a name="exclude_single_letter_type_parameters"></a>exclude_single_letter_type_parameters

| 설명 | 허용 가능한 값 | 기본값 | 구성 가능한 규칙 |
| - | - | - | - |
| 에서와 같이 단일 문자 [형식 매개 변수](../../csharp/programming-guide/generics/generic-type-parameters.md) 를 규칙에서 제외할지 여부 `S``Collection<S>` | `true`<br/>`false` | `false` | [CA1715](quality-rules/ca1715.md) |

> [!NOTE]
> 이 옵션은 `allow_single_letter_type_parameters` 이전 버전에서 이름이 지정 되었습니다.

### <a name="output_kind"></a>output_kind

| 설명 | 허용 가능한 값 | 기본값 | 구성 가능한 규칙 |
| - | - | - | - |
| 이 어셈블리 유형을 생성 하는 프로젝트의 코드를 분석 해야 함을 지정 합니다. | 열거형의 하나 이상의 필드 <xref:Microsoft.CodeAnalysis.OutputKind><br/><br/>여러 값을 쉼표 (,)로 구분 합니다. | 모든 출력 종류 | [CA2007](quality-rules/ca2007.md) |

### <a name="required_modifiers"></a>required_modifiers

| 설명 | 허용 가능한 값 | 기본값 | 구성 가능한 규칙 |
| - | - | - | - |
| 분석 되어야 하는 Api에 대 한 필수 한정자를 지정 합니다. | 허용 되는 한정자 테이블에서 하나 이상의 값<br/><br/>여러 값을 쉼표 (,)로 구분 합니다. | 각 규칙에 따라 다름 | [CA1802](quality-rules/ca1802.md) |

| 허용 되는 한정자 | 요약 |
| --- | --- |
| `none` | 한정자 요구 사항 없음 |
| `static` 또는 `Shared` | 는 `static` ( `Shared` Visual Basic)로 선언 해야 합니다. |
| `const` | 로 선언 해야 합니다. `const` |
| `readonly` | 로 선언 해야 합니다. `readonly` |
| `abstract` | 로 선언 해야 합니다. `abstract` |
| `virtual` | 로 선언 해야 합니다. `virtual` |
| `override` | 로 선언 해야 합니다. `override` |
| `sealed` | 로 선언 해야 합니다. `sealed` |
| `extern` | 로 선언 해야 합니다. `extern` |
| `async` | 로 선언 해야 합니다. `async` |

### <a name="exclude_extension_method_this_parameter"></a>exclude_extension_method_this_parameter

| 설명 | 허용 가능한 값 | 기본값 | 구성 가능한 규칙 |
| - | - | - | - |
| 확장 메서드의 매개 변수에 대 한 분석을 건너뛸지 여부 `this` | `true`<br/>`false` | `false` | [CA1062](quality-rules/ca1062.md) |

### <a name="null_check_validation_methods"></a>null_check_validation_methods

| 설명 | 허용 가능한 값 | 기본값 | 구성 가능한 규칙 |
| - | - | - | - |
| 메서드에 전달 된 인수가 null이 아닌 유효성을 검사 하는 null 검사 유효성 검사 메서드의 이름 | 허용 되는 메서드 이름 형식 (로 구분 `|` ):<br/> -메서드 이름만 (포함 하는 형식 또는 네임 스페이스에 관계 없이 이름이 인 모든 메서드 포함)<br/> -기호의 [설명서 ID 형식](https://github.com/dotnet/csharplang/blob/master/spec/documentation-comments.md#id-string-format)에 있는 정규화 된 이름 (옵션 접두사 포함) `M:` | 없음 | [CA1062](quality-rules/ca1062.md) |

### <a name="additional_string_formatting_methods"></a>additional_string_formatting_methods

| 설명 | 허용 가능한 값 | 기본값 | 구성 가능한 규칙 |
| - | - | - | - |
| 추가 문자열 형식 지정 메서드의 이름 | 허용 되는 메서드 이름 형식 (로 구분 `|` ):<br/> -메서드 이름만 (포함 하는 형식 또는 네임 스페이스에 관계 없이 이름이 인 모든 메서드 포함)<br/> -기호의 [설명서 ID 형식](/dotnet/csharp/language-reference/language-specification/documentation-comments#id-string-format)에 있는 정규화 된 이름 (옵션 접두사 포함) `M:` | 없음 | [CA2241](quality-rules/ca2241.md) |

### <a name="excluded_type_names_with_derived_types"></a>excluded_type_names_with_derived_types

| 설명 | 허용 가능한 값 | 기본값 | 구성 가능한 규칙 |
| - | - | - | - |
| 형식 이름 (형식 및 모든 파생 형식이 분석에 대해 제외 됨) | 허용 되는 기호 이름 형식 (로 구분 `|` ):<br/> -형식 이름만 (포함 하는 형식 또는 네임 스페이스에 관계 없이 이름이 인 모든 형식 포함).<br/> -기호의 [설명서 ID 형식](/dotnet/csharp/language-reference/language-specification/documentation-comments#id-string-format)에 있는 정규화 된 이름 (옵션 접두사 포함) `T:` | 없음 | [CA1303](quality-rules/ca1303.md) |

### <a name="excluded_symbol_names"></a>excluded_symbol_names

| 설명 | 허용 가능한 값 | 기본값 | 구성 가능한 규칙 |
| - | - | - | - |
| 분석을 위해 제외 된 기호 이름 | 허용 되는 기호 이름 형식 (로 구분 `|` ):<br/> -기호 이름에만 해당 (포함 하는 형식 또는 네임 스페이스에 관계 없이 이름이 인 모든 기호 포함)<br/> -기호의 [설명서 ID 형식](/dotnet/csharp/language-reference/language-specification/documentation-comments#id-string-format)으로 정규화 된 이름입니다. 각 기호 이름에는 `M:` 메서드의 접두사, `T:` 형식의 접두사 및 `N:` 네임 스페이스에 대 한 접두사와 같은 기호 종류 접두사가 필요 합니다.<br/> - `.ctor` 생성자 및 `.cctor` for static 생성자의 경우 | 없음 | [CA1062](quality-rules/ca1062.md) [CA1303](quality-rules/ca1303.md) [CA2000](quality-rules/ca2000.md) [CA2100](quality-rules/ca2100.md) [CA2301](quality-rules/ca2301.md) [CA2302](quality-rules/ca2302.md)<br/>[CA2311](quality-rules/ca2311.md) [CA2312](quality-rules/ca2312.md) [CA2321](quality-rules/ca2321.md) [CA2322](quality-rules/ca2322.md) [CA2327](quality-rules/ca2327.md) [CA2328](quality-rules/ca2328.md)<br/>[CA2329](quality-rules/ca2329.md) [CA2330](quality-rules/ca2330.md) [CA3001](quality-rules/ca3001.md) [CA3002](quality-rules/ca3002.md) [CA3003](quality-rules/ca3003.md) [CA3004](quality-rules/ca3004.md)<br/>[CA3005](quality-rules/ca3005.md) [CA3006](quality-rules/ca3006.md) [CA3007](quality-rules/ca3007.md) [CA3008](quality-rules/ca3008.md) [CA3009](quality-rules/ca3009.md) [CA3010](quality-rules/ca3010.md)<br/>[CA3011](quality-rules/ca3011.md) [CA3012](quality-rules/ca3012.md) [CA5361](quality-rules/ca5361.md) [CA5376 CA5377 CA5378](quality-rules/ca5378.md)<br/>[CA5380](quality-rules/ca5380.md) [CA5381](quality-rules/ca5381.md) CA5382 CA5383 CA5384 CA5387<br/>CA5388 [CA5389](quality-rules/ca5389.md) CA5390 |

### <a name="disallowed_symbol_names"></a>disallowed_symbol_names

| 설명 | 허용 가능한 값 | 기본값 | 구성 가능한 규칙 |
| - | - | - | - |
| 분석 컨텍스트에서 허용 되지 않는 기호의 이름입니다. | 허용 되는 기호 이름 형식 (로 구분 `|` ):<br/> -기호 이름에만 해당 (포함 하는 형식 또는 네임 스페이스에 관계 없이 이름이 인 모든 기호 포함)<br/> -기호의 [설명서 ID 형식](/dotnet/csharp/language-reference/language-specification/documentation-comments#id-string-format)으로 정규화 된 이름입니다. 각 기호 이름에는 `M:` 메서드의 접두사, `T:` 형식의 접두사 및 `N:` 네임 스페이스에 대 한 접두사와 같은 기호 종류 접두사가 필요 합니다.<br/> - `.ctor` 생성자 및 `.cctor` for static 생성자의 경우 | 없음 | [CA1031](quality-rules/ca1031.md) |
