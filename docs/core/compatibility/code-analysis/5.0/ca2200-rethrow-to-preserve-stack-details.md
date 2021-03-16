---
title: '호환성이 손상되는 변경: CA2200: 스택 정보를 유지하도록 다시 throw하십시오.'
description: 코드 분석 규칙 CA2200 사용으로 발생하는 .NET 5의 호환성이 손상되는 변경에 대해 알아봅니다.
ms.date: 09/03/2020
ms.openlocfilehash: 776a1bcf16c19364017e4652837720080fb7ba72
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102257728"
---
# <a name="warning-ca2200-rethrow-to-preserve-stack-details"></a>경고 CA2200: 스택 정보를 유지하도록 다시 throw하십시오.

.NET 코드 분석기 규칙 [CA2200](/visualstudio/code-quality/ca2200)은 .NET 5.0부터 기본적으로 사용됩니다. 이 규칙은 예외를 다시 throw하는 `catch` 블록에 대해 빌드 경고를 생성하며, 해당 예외는 `throw` 문에서 명시적으로 지정됩니다.

## <a name="change-description"></a>변경 내용 설명

.NET 5부터 .NET SDK에는 [.NET 소스 코드 분석기](../../../../fundamentals/code-analysis/overview.md)가 포함됩니다. [CA2200](/visualstudio/code-quality/ca2200)을 포함하여 해당 규칙 중 여러 개가 기본적으로 사용됩니다. 해당 규칙을 위반하는 코드가 프로젝트에 포함되고 프로젝트가 경고를 오류로 처리하도록 구성된 경우 해당 변경으로 인해 빌드의 호환성이 손상될 수 있습니다.

규칙 CA2200은 예외가 다시 throw되고 `throw` 문에 예외 변수가 지정된 코드를 플래그 지정합니다. 예외가 throw되는 경우 전달되는 정보의 일부는 스택 추적입니다. 스택 추적은 예외를 throw하는 메서드로 시작되고 예외를 catch하는 메서드로 종료되는 메서드 호출 계층 구조의 목록입니다. `throw` 문에 예외를 지정하여 예외가 다시 throw되는 경우 스택 추적은 현재 메서드에서 다시 시작되고 예외를 throw한 원래 메서드와 현재 메서드 간의 메서드 호출 목록이 손실됩니다. 예외에서 원래 스택 추적 정보를 유지하려면 예외를 지정하지 않고 `throw` 문을 사용합니다.

다음 코드 조각은 규칙 CA2200에 대한 경고를 생성하지 않습니다. 그러나 주석 처리된 줄은 위반을 ‘트리거’합니다.

```csharp
catch (ArithmeticException e)
{
    // throw e;
    throw;
}
```

## <a name="version-introduced"></a>도입된 버전

5.0

## <a name="recommended-action"></a>권장 조치

- 예외를 명시적으로 지정하지 않고 예외를 다시 throw합니다. 자세한 내용은 [CA2200](/visualstudio/code-quality/ca2200)을 참조하세요.

- 코드 분석을 완전히 사용하지 않으려면 프로젝트 파일에서 `EnableNETAnalyzers`를 `false`로 설정합니다. 자세한 내용은 [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers)를 참조하세요.

## <a name="affected-apis"></a>영향을 받는 API

API 분석을 통해 검색할 수 없습니다.

<!--

### Affected APIs

Not detectable via API analysis.

### Category

Code analysis

-->
