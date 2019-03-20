---
title: '방법: 사전을 사용하여 이벤트 인스턴스 저장 - C# 프로그래밍 가이드'
ms.custom: seodec18
ms.date: 03/11/2019
helpviewer_keywords:
- events [C#], storing instances in a Dictionary
ms.assetid: 9512c64d-5aaf-40cd-b941-ca2a592f0064
ms.openlocfilehash: f8522e499887398402f63c7788bbc6c6c4f57782
ms.sourcegitcommit: 16aefeb2d265e69c0d80967580365fabf0c5d39a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/18/2019
ms.locfileid: "57845278"
---
# <a name="how-to-use-a-dictionary-to-store-event-instances-c-programming-guide"></a>방법: 사전을 사용하여 이벤트 인스턴스 저장(C# 프로그래밍 가이드)

`add` 및 `remove` 사용자 지정 이벤트 접근자는 각 이벤트에 대한 필드를 할당하지 않고, 아래 예제와 같이 <xref:System.Collections.Generic.Dictionary%602> 인스턴스를 통해 이벤트 인스턴스를 저장하여 많은 이벤트를 공개하는 데 사용됩니다. 이 기능은 형식에 많은 이벤트가 있지만 대부분의 이벤트가 구독되지 않을 것으로 예상하는 경우에만 유용합니다.

[!code-csharp[csProgGuideEvents#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#9)]

이 구현은 C# 언어 사양에서 [대리자를 추가 및 제거](~/_csharplang/spec/delegates.md#delegate-invocation)하기 위한 동작을 따릅니다.

[lock](../../language-reference/keywords/lock-statement.md) 문은 이벤트 처리기를 사용하여 사전에 액세스하는 데만 사용됩니다. 교착 상태 또는 잠금 경합을 초래할 수 있으므로 `lock` 문 본문 내에서 이벤트 처리기를 호출하지 않아야 합니다.

## <a name="see-also"></a>참고 항목

- [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)
- [이벤트](../../../csharp/programming-guide/events/index.md)
- [대리자](../../../csharp/programming-guide/delegates/index.md)
