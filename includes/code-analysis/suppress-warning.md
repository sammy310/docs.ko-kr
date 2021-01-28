---
ms.openlocfilehash: b26e346f7076a57aef8ae7587ab1222b4100a323
ms.sourcegitcommit: 7e42488c2f8f63f6d499b5f8fb1dec5bac9ad254
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2021
ms.locfileid: "98957938"
---
## <a name="suppress-a-warning"></a>경고 표시 안 함

규칙 위반을 억제 하려면 EditorConfig 파일에서 특정 규칙 ID의 심각도 옵션을로 설정 합니다 `none` . 다음은 그 예입니다. 

```ini
[*.{cs,vb}]
dotnet_diagnostic.CA1822.severity = none
```

Visual Studio에서는 코드 분석 규칙에서 경고를 표시 하지 않도록 하는 추가 방법을 제공 합니다. 자세한 내용은 [위반 표시 안 함](/visualstudio/code-quality/use-roslyn-analyzers#suppress-violations)을 참조 하세요.

규칙 심각도에 대 한 자세한 내용은 [규칙 심각도 구성](~/docs/fundamentals/code-analysis/configuration-options.md#severity-level)을 참조 하세요.
