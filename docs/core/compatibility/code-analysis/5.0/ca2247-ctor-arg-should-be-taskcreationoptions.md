---
title: '호환성이 손상되는 변경: CA2247: TaskCompletionSource 생성자의 인수는 TaskCreationOptions 값이어야 함'
description: 코드 분석 규칙 CA2247 사용으로 발생하는 .NET 5.0의 호환성이 손상되는 변경에 대해 알아봅니다.
ms.date: 09/03/2020
ms.openlocfilehash: 323fd5a05da4dfeb68ef75d88d5d293ba01c8ade
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759797"
---
# <a name="warning-ca2247-argument-to-taskcompletionsource-constructor-should-be-taskcreationoptions-value"></a>경고 CA2247: TaskCompletionSource 생성자의 인수는 TaskCreationOptions 값이어야 함

.NET 코드 분석기 규칙 [CA2247](/visualstudio/code-quality/ca2247)은 .NET 5.0부터 기본적으로 사용됩니다. <xref:System.Threading.Tasks.TaskContinuationOptions> 형식의 인수를 전달하는 <xref:System.Threading.Tasks.TaskCompletionSource%601> 생성자 호출에 대한 빌드 경고를 생성합니다.

## <a name="change-description"></a>변경 내용 설명

.Net 5.0부터 .Net SDK에는 [.NET 소스 코드 분석기](../../../../fundamentals/code-analysis/overview.md)가 포함됩니다. [CA2247](/visualstudio/code-quality/ca2247)을 포함하여 해당 규칙 중 여러 개가 기본적으로 사용됩니다. 해당 규칙을 위반하는 코드가 프로젝트에 포함되고 프로젝트가 경고를 오류로 처리하도록 구성된 경우 해당 변경으로 인해 빌드의 호환성이 손상될 수 있습니다.

규칙 CA2247은 <xref:System.Threading.Tasks.TaskContinuationOptions> 형식의 인수를 전달하는 <xref:System.Threading.Tasks.TaskCompletionSource%601> 생성자 호출을 찾습니다. <xref:System.Threading.Tasks.TaskCompletionSource%601> 형식에는 <xref:System.Threading.Tasks.TaskCreationOptions> 값을 허용하는 생성자와 <xref:System.Object>를 허용하는 다른 생성자가 있습니다. <xref:System.Threading.Tasks.TaskCreationOptions> 값 대신 <xref:System.Threading.Tasks.TaskContinuationOptions> 값을 실수로 전달하는 경우 <xref:System.Object> 매개 변수를 사용하는 생성자가 런타임에 호출됩니다. 코드가 컴파일되어 실행되지만 의도한 동작이 포함되지 않습니다.

## <a name="version-introduced"></a>도입된 버전

5.0

## <a name="recommended-action"></a>권장 조치

- <xref:System.Threading.Tasks.TaskContinuationOptions> 인수를 해당하는 <xref:System.Threading.Tasks.TaskCreationOptions> 값으로 바꿉니다. 코드의 버그를 대부분 강조 표시하므로 이 경고를 해제하지 않습니다. 자세한 내용은 [CA2247](/visualstudio/code-quality/ca2247)을 참조하세요.

- 코드 분석을 완전히 사용하지 않으려면 프로젝트 파일에서 `EnableNETAnalyzers`를 `false`로 설정합니다. 자세한 내용은 [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers)를 참조하세요.

## <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Threading.Tasks.TaskCompletionSource%601.%23ctor(System.Object)>

<!--

### Affected APIs

- ``M:System.Threading.Tasks.TaskCompletionSource`1.#ctor(System.Object)``

### Category

Code analysis

-->
