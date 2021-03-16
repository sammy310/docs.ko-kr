---
title: '호환성이 손상되는 변경: CA2013: 값 형식과 함께 ReferenceEquals를 사용하지 마세요.'
description: 코드 분석 규칙 CA2013 사용으로 발생하는 .NET 5의 호환성이 손상되는 변경에 관해 알아봅니다.
ms.date: 09/03/2020
ms.openlocfilehash: fc68d9a3af0d629dc39aba0091d32b1982d6f2c5
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102257767"
---
# <a name="warning-ca2013-do-not-use-referenceequals-with-value-types"></a>경고 CA2013: 값 형식과 함께 ReferenceEquals를 사용하지 마세요.

.NET 코드 분석기 규칙 [CA2013](/visualstudio/code-quality/ca2013)은 .NET 5.0부터 기본적으로 사용됩니다. <xref:System.Object.ReferenceEquals(System.Object,System.Object)>를 사용하여 하나 이상의 값 형식이 같은지 비교하는 코드에 대한 빌드 경고를 생성합니다.

## <a name="change-description"></a>변경 내용 설명

.NET 5부터 .NET SDK에는 [.NET 소스 코드 분석기](../../../../fundamentals/code-analysis/overview.md)가 포함됩니다. [CA2013](/visualstudio/code-quality/ca2013)을 포함하여 해당 규칙 중 여러 개가 기본적으로 사용됩니다. 해당 규칙을 위반하는 코드가 프로젝트에 포함되고 프로젝트가 경고를 오류로 처리하도록 구성된 경우 해당 변경으로 인해 빌드의 호환성이 손상될 수 있습니다.

규칙 CA2013은 <xref:System.Object.ReferenceEquals(System.Object,System.Object)>를 사용하여 하나 이상의 값 형식이 같은지 비교하는 인스턴스를 찾습니다. 이런 방식으로 값 형식이 같은지 비교하면 비교되기 전에 값이 boxing되므로 잘못된 결과가 발생할 수 있습니다. 비교된 값이 동일한 값 형식 인스턴스를 나타내는 경우에도 <xref:System.Object.ReferenceEquals(System.Object,System.Object)>는 `false`를 반환합니다.

## <a name="version-introduced"></a>도입된 버전

5.0

## <a name="recommended-action"></a>권장 조치

- `==` 등의 적절한 같음 연산자를 사용하도록 코드를 변경합니다. 이 경고는 표시하지 않아야 합니다.

- 코드 분석을 완전히 사용하지 않으려면 프로젝트 파일에서 `EnableNETAnalyzers`를 `false`로 설정합니다. 자세한 내용은 [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers)를 참조하세요.

## <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Object.ReferenceEquals(System.Object,System.Object)?displayProperty=fullName>

<!--

### Affected APIs

- `M:System.Object.ReferenceEquals(System.Object,System.Object)`

### Category

Code analysis

-->
