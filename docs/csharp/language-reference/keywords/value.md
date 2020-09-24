---
description: value 상황별 키워드 제거 - C# 참조
title: value 상황별 키워드 제거 - C# 참조
ms.date: 07/20/2015
f1_keywords:
- value_CSharpKeyword
helpviewer_keywords:
- value keyword [C#]
ms.assetid: c99d6468-687f-4a46-89b4-a95e1b00bf6d
ms.openlocfilehash: ad2eb6f12d8c295dc5203994d6c570cd2377e3ee
ms.sourcegitcommit: 43ed174f085840ca18a791dc89fe833174da766d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/21/2020
ms.locfileid: "90828918"
---
# <a name="value-c-reference"></a>value(C# 참조)

상황별 키워드 `value`는 [속성](../../programming-guide/classes-and-structs/properties.md) 및 [인덱서](../../programming-guide/indexers/index.md) 선언의 `set` 접근자에 사용됩니다. 메서드의 입력 매개 변수와 비슷합니다. `value` 단어는 클라이언트 코드에서 속성 또는 인덱서에 할당하려는 값을 참조합니다. 다음 예에서 `MyDerivedClass`에는 `Name`이라는 속성이 있습니다. 이 속성은 `value` 매개 변수를 사용하여 지원 필드 `name`에 새 문자열을 할당합니다. 클라이언트 코드의 관점에서 이 작업은 단순한 할당으로 기록됩니다.

[!code-csharp[csrefKeywordsModifiers#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#26)]

자세한 내용은 [속성](../../programming-guide/classes-and-structs/properties.md) 및 [인덱서](../../programming-guide/indexers/index.md) 문서를 참조하세요.

## <a name="c-language-specification"></a>C# 언어 사양

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>참조

- [C# 참조](../index.md)
- [C# 프로그래밍 가이드](../../programming-guide/index.md)
- [C# 키워드](index.md)
