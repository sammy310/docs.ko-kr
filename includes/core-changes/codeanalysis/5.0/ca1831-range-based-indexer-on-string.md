---
ms.openlocfilehash: 4e937f56f6315ce2abf76dd56989f4d2c4059f22
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065194"
---
### <a name="ca1831-use-asspan-instead-of-range-based-indexers-for-string"></a>CA1831: 문자열에 대해 범위 기반 인덱서 대신 AsSpan 사용

.Net 코드 분석기 규칙 [CA1831](/visualstudio/code-quality/ca1831)은 .NET 5.0부터 기본적으로 사용됩니다. <xref:System.Range> 기반 인덱서가 문자열에서 사용되지만 복사본이 의도되지 않은 코드에 관한 빌드 경고를 생성합니다.

#### <a name="change-description"></a>변경 내용 설명

.Net 5.0부터 .Net SDK에는 [.NET 소스 코드 분석기](../../../../docs/fundamentals/productivity/code-analysis.md)가 포함됩니다. [CA1831](/visualstudio/code-quality/ca1831)을 포함하여 해당 규칙 중 여러 개가 기본적으로 사용됩니다. 해당 규칙을 위반하는 코드가 프로젝트에 포함되고 프로젝트가 경고를 오류로 처리하도록 구성된 경우 해당 변경으로 인해 빌드의 호환성이 손상될 수 있습니다.

규칙 CA1831은 <xref:System.Range> 기반 인덱서가 문자열에서 사용되지만 복사본이 의도되지 않은 인스턴스를 찾습니다. <xref:System.Range> 기반 인덱서가 암시적 캐스트를 생성하기 위해 문자열에서 직접 사용되는 경우에는 요청된 문자열 부분의 불필요한 복사본이 생성됩니다. 예:

```csharp
ReadOnlySpan<char> slice = str[1..3];
```

CA1831은 대신에 문자열의 ‘범위’에서 <xref:System.Range> 기반 인덱서를 사용하도록 제안합니다. 예를 들어:

```csharp
ReadOnlySpan<char> slice = str.AsSpan()[1..3];
```

#### <a name="version-introduced"></a>도입된 버전

5.0 미리 보기 8

#### <a name="recommended-action"></a>권장 조치

- 코드를 수정하고 불필요한 할당을 방지하려면 <xref:System.Range> 기반 인덱서를 사용하기 전에 <xref:System.MemoryExtensions.AsSpan(System.String)> 또는 <xref:System.MemoryExtensions.AsMemory(System.String)>를 호출합니다. 예:

  ```csharp
  ReadOnlySpan<char> slice = str.AsSpan()[1..3];
  ```

- 코드를 변경하지 않으려는 경우 심각도를 `suggestion` 또는 `none`으로 설정하여 규칙을 사용하지 않을 수 있습니다. 자세한 내용은 [코드 분석 규칙 구성](../../../../docs/fundamentals/productivity/configure-code-analysis-rules.md)을 참조하세요.

- 코드 분석을 완전히 사용하지 않으려면 프로젝트 파일에서 `EnableNETAnalyzers`를 `false`로 설정합니다. 자세한 내용은 [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers)를 참조하세요.

#### <a name="category"></a>범주

코드 분석

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Range?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Range`

-->
