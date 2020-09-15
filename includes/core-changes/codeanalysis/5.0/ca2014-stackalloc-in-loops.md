---
ms.openlocfilehash: a51160a8ab5a4b437e51db31def577f8d8f50182
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065181"
---
### <a name="ca2014-do-not-use-stackalloc-in-loops"></a>CA2014: 루프에 stackalloc를 사용하지 마세요.

.NET 코드 분석기 규칙 [CA2014](/visualstudio/code-quality/ca2014)는 .NET 5.0부터 기본적으로 사용됩니다. [stackalloc](../../../../docs/csharp/language-reference/operators/stackalloc.md) 식이 루프 내에서 사용되는 모든 C# 코드에 대해 빌드 경고를 생성합니다.

#### <a name="change-description"></a>변경 내용 설명

.Net 5.0부터 .Net SDK에는 [.NET 소스 코드 분석기](../../../../docs/fundamentals/productivity/code-analysis.md)가 포함됩니다. [CA2014](/visualstudio/code-quality/ca2014)를 포함하여 해당 규칙 중 여러 개가 기본적으로 사용됩니다. 해당 규칙을 위반하는 코드가 프로젝트에 포함되고 프로젝트가 경고를 오류로 처리하도록 구성된 경우 해당 변경으로 인해 빌드의 호환성이 손상될 수 있습니다.

규칙 CA2014는 [stackalloc 식](../../../../docs/csharp/language-reference/operators/stackalloc.md)이 루프 내에서 사용되는 C# 코드를 찾습니다. [stackalloc](../../../../docs/csharp/language-reference/operators/stackalloc.md)는 현재 스택 프레임에서 메모리를 할당합니다. 현재 메서드 호출이 반환될 때까지 메모리가 해제되지 않아 스택 오버플로가 발생할 수 있습니다. 스택 오버플로 예외를 catch할 수 없기 때문에 스택 오버플로가 발생할 경우 앱이 종료됩니다.

#### <a name="version-introduced"></a>도입된 버전

5.0 미리 보기 8

#### <a name="recommended-action"></a>권장 조치

- 루프 내에서 [stackalloc](../../../../docs/csharp/language-reference/operators/stackalloc.md)를 사용하지 않습니다. 루프 외부에서 메모리 블록을 할당하고 루프 내부에서 재사용합니다. 자세한 내용은 [CA2014](/visualstudio/code-quality/ca2014)를 참조하세요.

- 코드 분석을 완전히 사용하지 않으려면 프로젝트 파일에서 `EnableNETAnalyzers`를 `false`로 설정합니다. 자세한 내용은 [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers)를 참조하세요.

#### <a name="category"></a>범주

코드 분석

#### <a name="affected-apis"></a>영향을 받는 API

API 분석을 통해 검색할 수 없습니다.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
