---
title: 코드 분석 규칙 구성
description: 분석기 구성 파일에서 코드 분석 규칙을 구성 하는 방법에 대해 알아봅니다.
ms.date: 09/24/2020
ms.topic: conceptual
no-loc:
- EditorConfig
ms.openlocfilehash: af2ebb74786f0ae884ffee4636765cae43fcb23f
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2020
ms.locfileid: "96593143"
---
# <a name="configuration-options-for-code-analysis"></a>코드 분석에 대 한 구성 옵션

코드 분석 규칙에는 다양 한 구성 옵션이 있습니다. 이러한 옵션은 구문을 사용 하 여 [분석기 구성 파일](configuration-files.md) 에서 키-값 쌍으로 지정 됩니다 `<option key> = <option value>` .

가장 일반적으로 구성할 옵션은 규칙의 심각도입니다. [코드 품질 규칙](quality-rules/index.md) 및 [코드 스타일 규칙](style-rules/index.md)을 포함 하 여 모든 분석기 규칙에 대 한 심각도 수준을 구성할 수 있습니다.

규칙 동작을 사용자 지정 하는 추가 옵션을 구성할 수도 있습니다.

- 코드 품질 규칙에는 규칙을 적용 해야 하는 메서드 이름과 같은 동작을 구성 하는 [추가 옵션이](code-quality-rule-options.md) 있습니다.
- 코드 스타일 규칙에는 [사용자 지정 코드 스타일 옵션이](code-style-rule-options.md)있습니다.
- 타사 분석기 규칙은 사용자 지정 키 이름 및 값 형식을 사용 하 여 자체 구성 옵션을 정의할 수 있습니다.

[분석기 구성 파일](configuration-files.md) 에서 특정 규칙의 심각도를 구성 하는 구문은 다음과 같습니다.

```ini
dotnet_diagnostic.<rule ID>.severity = <severity>
```

## <a name="general-options"></a>일반 옵션

이러한 옵션은 전체 코드 분석에 적용 됩니다. 단일 규칙 또는 규칙 집합에만 적용할 수 있습니다.

### <a name="exclude-generated-code"></a>생성 된 코드 제외

`generated_code = true | false` [구성 파일](configuration-files.md)에 항목을 추가 하 여 생성 된 코드로 처리할 추가 파일 및 폴더를 구성할 수 있습니다. .NET 코드 분석기 경고는 디자이너에서 생성 된 파일과 같은 생성 된 코드 파일에는 유용 하지 않습니다. 이러한 파일은 사용자가 편집 하 여 위반을 수정할 수 없습니다. 대부분의 경우 코드 분석기는 생성 된 코드 파일을 건너뛰고 이러한 파일에 대 한 위반을 보고 하지 않습니다.

기본적으로 특정 파일 확장명 또는 자동 생성 파일 헤더를 포함 하는 파일은 생성 된 코드 파일로 처리 됩니다. 예를 들어 또는로 끝나는 파일 이름은 `.designer.cs` `.generated.cs` 생성 된 코드로 간주 됩니다. 이 구성 옵션을 사용 하 여 추가 명명 패턴을 지정할 수 있습니다.

예를 들어 이름이 생성 된 코드로 끝나는 모든 파일을 처리 하려면 `.MyGenerated.cs` 다음 항목을 추가 합니다.

```ini
[*.MyGenerated.cs]
generated_code = true
```

## <a name="rule-specific-options"></a>규칙 관련 옵션

규칙 관련 옵션은 단일 규칙, 규칙 집합 또는 모든 규칙에 적용할 수 있습니다. 규칙 관련 옵션은 다음과 같습니다.

- [규칙 심각도 수준](#severity-level)
- [*코드 품질* 규칙과 관련 한 옵션](code-quality-rule-options.md)

### <a name="severity-level"></a>심각도 수준

다음 표에서는 [코드 품질](quality-rules/index.md) 및 [코드 스타일](style-rules/index.md) 규칙을 포함 하 여 모든 분석기 규칙에 대해 구성할 수 있는 다양 한 규칙 심각도를 보여 줍니다.

| 심각도 | 빌드 시간 동작 |
|-|-|
| `error` | 위반은 빌드 *오류로* 표시 되 고 빌드가 실패 합니다.|
| `warning` | 위반은 빌드 *경고* 로 나타나지만 빌드 실패를 유발 하지 않습니다 (경고를 오류로 처리 하도록 설정 하지 않은 경우). |
| `suggestion` | 위반은 빌드 *메시지로* 표시 되 고 VISUAL Studio IDE에서 제안 사항으로 표시 됩니다. |
| `silent` | 위반은 사용자에 게 표시 되지 않습니다. |
| `none` | 규칙은 전혀 표시되지 않습니다. |
| `default` | 규칙의 기본 심각도가 사용 됩니다. |

> [!TIP]
> Visual Studio의 규칙 심각도 화면에 대 한 자세한 내용은 [심각도 수준](/visualstudio/ide/editorconfig-language-conventions#severity-levels)을 참조 하세요.

#### <a name="scope"></a>범위

단일 규칙에 대 한 규칙 심각도를 설정 하려면 다음 구문을 사용 합니다.

```ini
dotnet_diagnostic.<rule ID>.severity = <severity value>
```

분석기 규칙의 범주에 대 한 기본 규칙 심각도를 설정 하려면 다음 구문을 사용 합니다.

```ini
dotnet_analyzer_diagnostic.category-<rule category>.severity = <severity value>
```

모든 분석기 규칙에 대 한 기본 규칙 심각도를 설정 하려면 다음 구문을 사용 합니다.

```ini
dotnet_analyzer_diagnostic.severity = <severity value>
```

#### <a name="precedence"></a>우선 순위

동일한 규칙 ID에 적용할 수 있는 여러 심각도 구성 항목이 있는 경우 우선 순위는 다음 순서로 선택 됩니다.

- ID 별로 개별 규칙의 항목은 범주에 대 한 항목 보다 우선적으로 적용 됩니다.
- 범주에 대 한 항목은 모든 분석기 규칙의 항목 보다 우선적으로 적용 됩니다.

다음 예를 살펴보십시오. 여기서 [CA1822](/visualstudio/code-quality/ca1822) 에는 "Performance" 범주가 있습니다.

```ini
[*.cs]
dotnet_diagnostic.CA1822.severity = error
dotnet_analyzer_diagnostic.category-performance.severity = warning
dotnet_analyzer_diagnostic.severity = suggestion
```

앞의 예제에서는 세 가지 심각도 항목을 모두 CA1822에 적용할 수 있습니다. 그러나 지정 된 선행 규칙을 사용 하 여 첫 번째 규칙 ID 기반 항목은 다음 항목에 대해 적용 됩니다. 이 예제에서 CA1822은의 유효 심각도를 갖습니다 `error` . "성능" 범주 내의 다른 모든 규칙은의 심각도를 갖습니다 `warning` .

파일 간 우선 순위를 결정 하는 방법에 대 한 자세한 내용은 [구성 파일 문서의 우선 순위 섹션](configuration-files.md#precedence)을 참조 하세요.
