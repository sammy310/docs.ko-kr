---
ms.openlocfilehash: 4fc31f75e8f8cdd50abebd399d9749688e6faa5a
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065178"
---
### <a name="ca2015-do-not-define-finalizers-for-types-derived-from-memorymanagert"></a>CA2015: MemoryManager에서 파생된 형식에 대해 종료자를 정의하지 마세요.\<T>

.NET 코드 분석기 규칙 [CA2015](/visualstudio/code-quality/ca2015)는 .NET 5.0부터 기본적으로 사용됩니다. <xref:System.Buffers.MemoryManager%601>에서 파생된, 종료자를 정의하는 모든 형식에 대해 빌드 경고를 생성합니다.

#### <a name="change-description"></a>변경 내용 설명

.Net 5.0부터 .Net SDK에는 [.NET 소스 코드 분석기](../../../../docs/fundamentals/productivity/code-analysis.md)가 포함됩니다. [CA2015](/visualstudio/code-quality/ca2015)를 포함하여 해당 규칙 중 여러 개가 기본적으로 사용됩니다. 해당 규칙을 위반하는 코드가 프로젝트에 포함되고 프로젝트가 경고를 오류로 처리하도록 구성된 경우 해당 변경으로 인해 빌드의 호환성이 손상될 수 있습니다.

규칙 CA2015는 <xref:System.Buffers.MemoryManager%601>에서 파생된, 종료자를 정의하는 형식에 플래그를 지정합니다. <xref:System.Buffers.MemoryManager%601>에서 파생된 형식에 종료자를 추가하는 것은 버그를 나타낼 가능성이 높습니다. <xref:System.Span%601>에서 확보했을 수 있는 네이티브 리소스가 <xref:System.Span%601>에서 아직 사용 중인데 정리되고 있음을 의미합니다.

#### <a name="version-introduced"></a>도입된 버전

5.0 미리 보기 8

#### <a name="recommended-action"></a>권장 조치

- 종료자 정의를 제거합니다. 자세한 내용은 [CA2015](/visualstudio/code-quality/ca2015)를 참조하세요.

- 코드 분석을 완전히 사용하지 않으려면 프로젝트 파일에서 `EnableNETAnalyzers`를 `false`로 설정합니다. 자세한 내용은 [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers)를 참조하세요.

#### <a name="category"></a>범주

코드 분석

#### <a name="affected-apis"></a>영향을 받는 API

API 분석을 통해 검색할 수 없습니다.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
