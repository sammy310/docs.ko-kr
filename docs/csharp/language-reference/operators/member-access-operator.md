---
title: . 연산자 - C# 참조
ms.custom: seodec18
ms.date: 02/25/2019
f1_keywords:
- ._CSharpKeyword
helpviewer_keywords:
- member access operator (.) [C#]
- . operator [C#]
- dot operator (.) [C#]
ms.assetid: a1f54b52-b686-4ae5-a48e-a2a9ebd0eb7b
ms.openlocfilehash: 2661676d53deb874c5e5a90b4443b301730e09df
ms.sourcegitcommit: bd28ff1e312eaba9718c4f7ea272c2d4781a7cac
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/26/2019
ms.locfileid: "56836463"
---
# <a name="-operator-c-reference"></a>. 연산자(C# 참조)

일반적으로 점(`.`)은 멤버 액세스에 사용됩니다.

다음 예제와 같이 `.` 토큰을 사용하여 네임스페이스 또는 형식의 멤버에 액세스합니다.

- [ `using` 지시문](../keywords/using-directive.md)의 다음 예제와 같이 `.`을 사용하여 네임스페이스 내에 중첩된 네임스페이스에 액세스합니다.

  [!code-csharp[nested namespaces](~/samples/snippets/csharp/language-reference/operators/MemberAccessExamples.cs#NestedNamespace)]

- 다음 코드와 같이 `.`을 사용하여 ‘정규화된 이름’을 만들고 네임스페이스 내의 형식에 액세스합니다.

  [!code-csharp[qualified name](~/samples/snippets/csharp/language-reference/operators/MemberAccessExamples.cs#QualifiedName)]

  [`using` 지시문](../keywords/using-directive.md)을 사용하여 정규화된 이름 사용을 선택 사항으로 설정합니다.

- 다음 코드와 같이 `.`을 사용하여 정적 및 비정적 [형식 멤버](../../programming-guide/classes-and-structs/index.md#members)에 액세스합니다.

  [!code-csharp-interactive[type members](~/samples/snippets/csharp/language-reference/operators/MemberAccessExamples.cs#TypeMemberAccess)]

`.`을 사용하여 [확장 메서드](../../programming-guide/classes-and-structs/extension-methods.md)를 호출할 수도 있습니다.

## <a name="operator-overloadability"></a>연산자 오버로드 가능성

`.` 연산자를 오버로드할 수 없습니다.

## <a name="c-language-specification"></a>C# 언어 사양

자세한 내용은 [C# 언어 사양](../language-specification/index.md)의 [멤버 액세스](~/_csharplang/spec/expressions.md#member-access) 섹션을 참조하세요.

## <a name="see-also"></a>참고 항목

- [C# 참조](../index.md)
- [C# 프로그래밍 가이드](../../programming-guide/index.md)
- [C# 연산자](index.md)
- [?. 및 ?[] 연산자](null-conditional-operators.md)