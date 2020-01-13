---
title: nameof 연산자 - C# 참조
ms.date: 07/12/2019
f1_keywords:
- nameof_CSharpKeyword
- nameof
helpviewer_keywords:
- nameof operator [C#]
ms.assetid: 33601bf3-cc2c-4496-846d-f9679bccf2a7
ms.openlocfilehash: c1d71d52a9222379adc36479715113b181da7133
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712691"
---
# <a name="nameof-operator-c-reference"></a><span data-ttu-id="69e6b-102">nameof 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="69e6b-102">nameof operator (C# reference)</span></span>

<span data-ttu-id="69e6b-103">`nameof` 연산자는 변수, 형식 또는 멤버의 이름을 문자열 상수로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="69e6b-103">The `nameof` operator obtains the name of a variable, type, or member as the string constant:</span></span>

[!code-csharp-interactive[nameof operator](~/samples/csharp/language-reference/operators/NameOfOperator.cs#Examples)]

<span data-ttu-id="69e6b-104">이전 예제와 같이 형식 및 네임스페이스의 경우 생성되는 이름은 일반적으로 [정규화된](~/_csharplang/spec/basic-concepts.md#fully-qualified-names) 이름이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="69e6b-104">As the preceding example shows, in the case of a type and a namespace, the produced name is usually not [fully qualified](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).</span></span>

<span data-ttu-id="69e6b-105">`nameof` 연산자는 컴파일 시간에 평가되며 런타임에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="69e6b-105">The `nameof` operator is evaluated at compile time and has no effect at run time.</span></span>

<span data-ttu-id="69e6b-106">`nameof` 연산자를 사용하여 인수 검사 코드를 더 쉽게 유지 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69e6b-106">You can use the `nameof` operator to make the argument-checking code more maintainable:</span></span>

[!code-csharp[nameof and argument check](~/samples/csharp/language-reference/operators/NameOfOperator.cs#ExceptionMessage)]

<span data-ttu-id="69e6b-107">`nameof` 연산자는 C# 6 이상에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69e6b-107">The `nameof` operator is available in C# 6 and later.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="69e6b-108">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="69e6b-108">C# language specification</span></span>

<span data-ttu-id="69e6b-109">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [Nameof 식](~/_csharplang/spec/expressions.md#nameof-expressions) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="69e6b-109">For more information, see the [Nameof expressions](~/_csharplang/spec/expressions.md#nameof-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="69e6b-110">참조</span><span class="sxs-lookup"><span data-stu-id="69e6b-110">See also</span></span>

- [<span data-ttu-id="69e6b-111">C# 참조</span><span class="sxs-lookup"><span data-stu-id="69e6b-111">C# reference</span></span>](../index.md)
- [<span data-ttu-id="69e6b-112">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="69e6b-112">C# operators</span></span>](index.md)
