---
title: 코드 분석 호환성이 손상되는 변경
description: .NET 소스 코드 분석기의 호환성이 손상되는 변경을 나열합니다.
ms.date: 09/02/2020
ms.openlocfilehash: 3cbe2ecf5d08084db542db0c2da016f1f391452e
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90538927"
---
# <a name="code-analysis-breaking-changes"></a>코드 분석 호환성이 손상되는 변경

이 페이지에는 다음과 같은 주요 변경 사항이 설명되어 있습니다.

| 주요 변경 내용 | 도입된 버전 |
| - | :-: |
| [CA1416: 플랫폼 호환성](#ca1416-platform-compatibility) | 5.0 |
| [CA1417: P/Invoke에 대한 문자열 매개 변수의 OutAttribute](#ca1417-outattribute-on-string-parameter-for-pinvoke) | 5.0 |
| [CA1831: 문자열에 대해 범위 기반 인덱서 대신 AsSpan 사용](#ca1831-use-asspan-instead-of-range-based-indexers-for-string) | 5.0 |
| [CA2013: 값 형식과 함께 ReferenceEquals를 사용하지 마세요.](#ca2013-do-not-use-referenceequals-with-value-types) | 5.0 |
| [CA2014: 루프에 stackalloc를 사용하지 마세요.](#ca2014-do-not-use-stackalloc-in-loops) | 5.0 |
| [CA2015: MemoryManager에서 파생된 형식에 대해 종료자 정의 안 함\<T>](#ca2015-do-not-define-finalizers-for-types-derived-from-memorymanagert) | 5.0 |
| [CA2200: 스택 정보를 유지하도록 다시 throw하십시오.](#ca2200-rethrow-to-preserve-stack-details) | 5.0 |
| [CA2247: TaskCompletionSource 생성자의 인수는 TaskCreationOptions 값이어야 함](#ca2247-argument-to-taskcompletionsource-constructor-should-be-taskcreationoptions-value) | 5.0 |

## <a name="net-50"></a>.NET 5.0

[!INCLUDE [ca1416-platform-compatibility-analyzer](../../../includes/core-changes/codeanalysis/5.0/ca1416-platform-compatibility-analyzer.md)]

***

[!INCLUDE [outattributes-on-pinvoke-string-parameters](../../../includes/core-changes/codeanalysis/5.0/ca1417-outattributes-on-pinvoke-string-parameters.md)]

***

[!INCLUDE [range-based-indexer-on-string](../../../includes/core-changes/codeanalysis/5.0/ca1831-range-based-indexer-on-string.md)]

***

[!INCLUDE [referenceequals-on-value-types](../../../includes/core-changes/codeanalysis/5.0/ca2013-referenceequals-on-value-types.md)]

***

[!INCLUDE [stackalloc-in-loops](../../../includes/core-changes/codeanalysis/5.0/ca2014-stackalloc-in-loops.md)]

***

[!INCLUDE [finalizers-for-memorymanager-types](../../../includes/core-changes/codeanalysis/5.0/ca2015-finalizers-for-memorymanager-types.md)]

***

[!INCLUDE [ca2200-rethrow-to-preserve-stack-details](../../../includes/core-changes/codeanalysis/5.0/ca2200-rethrow-to-preserve-stack-details.md)]

***

[!INCLUDE [ctor-arg-should-be-taskcreationoptions](../../../includes/core-changes/codeanalysis/5.0/ca2247-ctor-arg-should-be-taskcreationoptions.md)]

***
