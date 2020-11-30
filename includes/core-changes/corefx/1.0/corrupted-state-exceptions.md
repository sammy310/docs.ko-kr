---
ms.openlocfilehash: 394f2daebad7b6af94bee4d7876796e87fe8ab19
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032068"
---
### <a name="handling-corrupted-state-exceptions-is-not-supported"></a>손상된 상태 예외 처리는 지원되지 않음

.NET Core에서 손상된 프로세스 상태 예외 처리는 지원되지 않습니다.

#### <a name="change-description"></a>변경 내용 설명

이전에는 관리 코드 예외 처리기(예: C#에서 [try-catch](../../../../docs/csharp/language-reference/keywords/try-catch.md) 문을 사용하여)가 손상된 프로세스 상태 예외를 catch하고 처리할 수 있었습니다.

.NET Core 1.0부터는 손상된 프로세스 상태 예외를 관리 코드로 처리할 수 없습니다. 공용 언어 런타임에서는 손상된 프로세스 상태 예외를 관리 코드에 제공하지 않습니다.

#### <a name="version-introduced"></a>도입된 버전

1.0

#### <a name="recommended-action"></a>권장 조치

대신 발생하는 상황을 해결하여 손상된 프로세스 상태 예외를 처리할 필요가 없습니다. 손상된 프로세스 상태 예외를 처리해야 하는 경우 예외 처리기를 C 또는 C++ 코드로 작성합니다.

#### <a name="category"></a>범주

핵심 .NET 라이브러리

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=fullName>
- [legacyCorruptedStateExceptionsPolicy 요소](~/docs/framework/configure-apps/file-schema/runtime/legacycorruptedstateexceptionspolicy-element.md)

<!--

#### Affected APIs

- `T:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute`

-->
