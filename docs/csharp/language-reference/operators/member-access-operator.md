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
# <a name="-operator-c-reference"></a><span data-ttu-id="c7bb5-103">.</span><span class="sxs-lookup"><span data-stu-id="c7bb5-103">.</span></span> <span data-ttu-id="c7bb5-104">연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="c7bb5-104">operator (C# Reference)</span></span>

<span data-ttu-id="c7bb5-105">일반적으로 점(`.`)은 멤버 액세스에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7bb5-105">The dot, `.`, is typically used for member access.</span></span>

<span data-ttu-id="c7bb5-106">다음 예제와 같이 `.` 토큰을 사용하여 네임스페이스 또는 형식의 멤버에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="c7bb5-106">You use the `.` token to access a member of a namespace or a type, as the following examples demonstrate:</span></span>

- <span data-ttu-id="c7bb5-107">[ `using` 지시문](../keywords/using-directive.md)의 다음 예제와 같이 `.`을 사용하여 네임스페이스 내에 중첩된 네임스페이스에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="c7bb5-107">Use `.` to access a nested namespace within a namespace, as the following example of a [`using` directive](../keywords/using-directive.md) shows:</span></span>

  [!code-csharp[nested namespaces](~/samples/snippets/csharp/language-reference/operators/MemberAccessExamples.cs#NestedNamespace)]

- <span data-ttu-id="c7bb5-108">다음 코드와 같이 `.`을 사용하여 ‘정규화된 이름’을 만들고 네임스페이스 내의 형식에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="c7bb5-108">Use `.` to form a *qualified name* to access a type within a namespace, as the following code shows:</span></span>

  [!code-csharp[qualified name](~/samples/snippets/csharp/language-reference/operators/MemberAccessExamples.cs#QualifiedName)]

  <span data-ttu-id="c7bb5-109">[`using` 지시문](../keywords/using-directive.md)을 사용하여 정규화된 이름 사용을 선택 사항으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c7bb5-109">Use the [`using` directive](../keywords/using-directive.md) to make the use of qualified names optional.</span></span>

- <span data-ttu-id="c7bb5-110">다음 코드와 같이 `.`을 사용하여 정적 및 비정적 [형식 멤버](../../programming-guide/classes-and-structs/index.md#members)에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="c7bb5-110">Use `.` to access [type members](../../programming-guide/classes-and-structs/index.md#members), static and non-static, as the following code shows:</span></span>

  [!code-csharp-interactive[type members](~/samples/snippets/csharp/language-reference/operators/MemberAccessExamples.cs#TypeMemberAccess)]

<span data-ttu-id="c7bb5-111">`.`을 사용하여 [확장 메서드](../../programming-guide/classes-and-structs/extension-methods.md)를 호출할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7bb5-111">You can also use `.` to invoke an [extension method](../../programming-guide/classes-and-structs/extension-methods.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="c7bb5-112">연산자 오버로드 가능성</span><span class="sxs-lookup"><span data-stu-id="c7bb5-112">Operator overloadability</span></span>

<span data-ttu-id="c7bb5-113">`.` 연산자를 오버로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c7bb5-113">The operator `.` cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="c7bb5-114">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="c7bb5-114">C# language specification</span></span>

<span data-ttu-id="c7bb5-115">자세한 내용은 [C# 언어 사양](../language-specification/index.md)의 [멤버 액세스](~/_csharplang/spec/expressions.md#member-access) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c7bb5-115">For more information, see the [Member access](~/_csharplang/spec/expressions.md#member-access) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c7bb5-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c7bb5-116">See also</span></span>

- [<span data-ttu-id="c7bb5-117">C# 참조</span><span class="sxs-lookup"><span data-stu-id="c7bb5-117">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="c7bb5-118">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="c7bb5-118">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="c7bb5-119">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="c7bb5-119">C# Operators</span></span>](index.md)
- <span data-ttu-id="c7bb5-120">[?. 및 ?[] 연산자](null-conditional-operators.md)</span><span class="sxs-lookup"><span data-stu-id="c7bb5-120">[?. and ?[] operators](null-conditional-operators.md)</span></span>