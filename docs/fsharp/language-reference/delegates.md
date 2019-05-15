---
title: 대리자
description: 대리자를 사용 하는 방법에 알아봅니다 F#입니다.
ms.date: 05/16/2016
ms.openlocfilehash: 0596b67530b0399df41dffdf855a07bce2bf4761
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641981"
---
# <a name="delegates"></a><span data-ttu-id="8e3ac-103">대리자</span><span class="sxs-lookup"><span data-stu-id="8e3ac-103">Delegates</span></span>

<span data-ttu-id="8e3ac-104">대리자 개체를 함수 호출을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8e3ac-104">A delegate represents a function call as an object.</span></span> <span data-ttu-id="8e3ac-105">F#, 일반적으로 첫 번째 클래스 값;으로 기능을 나타내는 데 함수 값을 사용 해야 그러나 대리자.NET Framework에서 사용 되 고 예상 하는 Api를 사용 하 여 상호 운용 하는 경우 필요 하므로.</span><span class="sxs-lookup"><span data-stu-id="8e3ac-105">In F#, you ordinarily should use function values to represent functions as first-class values; however, delegates are used in the .NET Framework and so are needed when you interoperate with APIs that expect them.</span></span> <span data-ttu-id="8e3ac-106">이러한도 사용할 수 있습니다 다른.NET Framework 언어에서 사용 하기 위한 라이브러리를 작성할 때.</span><span class="sxs-lookup"><span data-stu-id="8e3ac-106">They may also be used when authoring libraries designed for use from other .NET Framework languages.</span></span>

## <a name="syntax"></a><span data-ttu-id="8e3ac-107">구문</span><span class="sxs-lookup"><span data-stu-id="8e3ac-107">Syntax</span></span>

```fsharp
type delegate-typename = delegate of type1 -> type2
```

## <a name="remarks"></a><span data-ttu-id="8e3ac-108">설명</span><span class="sxs-lookup"><span data-stu-id="8e3ac-108">Remarks</span></span>

<span data-ttu-id="8e3ac-109">이전 구문에서 `type1` 은 인수 형식 또는 형식 및 `type2` 반환 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8e3ac-109">In the previous syntax, `type1` represents the argument type or types and `type2` represents the return type.</span></span> <span data-ttu-id="8e3ac-110">으로 표현 되는 인수 형식을 `type1` 자동 변환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e3ac-110">The argument types that are represented by `type1` are automatically curried.</span></span> <span data-ttu-id="8e3ac-111">튜플 형식을 사용 하 여 대상 함수의 인수 변환 되는 경우이 형식 및 튜플 형식에 이미 있는 인수에 대 한 괄호로 묶인 튜플을 원인 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="8e3ac-111">This suggests that for this type you use a tuple form if the arguments of the target function are curried, and a parenthesized tuple for arguments that are already in the tuple form.</span></span> <span data-ttu-id="8e3ac-112">자동 (currying) 괄호 대상 메서드를 일치 하는 튜플 인수 집합을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e3ac-112">The automatic currying removes a set of parentheses, leaving a tuple argument that matches the target method.</span></span> <span data-ttu-id="8e3ac-113">각각의 경우에서 사용 해야 하는 구문에 대 한 코드 예제를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8e3ac-113">Refer to the code example for the syntax you should use in each case.</span></span>

<span data-ttu-id="8e3ac-114">대리자에 연결할 수 있습니다 F# 함수 값 및 정적 또는 인스턴스 메서드.</span><span class="sxs-lookup"><span data-stu-id="8e3ac-114">Delegates can be attached to F# function values, and static or instance methods.</span></span> <span data-ttu-id="8e3ac-115">F#함수 값 대리자 생성자에 인수로 직접 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e3ac-115">F# function values can be passed directly as arguments to delegate constructors.</span></span> <span data-ttu-id="8e3ac-116">정적 메서드에 대 한 클래스 및 메서드 이름을 사용 하 여 대리자를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e3ac-116">For a static method, you construct the delegate by using the name of the class and the method.</span></span> <span data-ttu-id="8e3ac-117">인스턴스 메서드의 인수로 메서드와 개체 인스턴스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8e3ac-117">For an instance method, you provide the object instance and method in one argument.</span></span> <span data-ttu-id="8e3ac-118">두 경우 모두, 멤버 액세스 연산자 (`.`) 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e3ac-118">In both cases, the member access operator (`.`) is used.</span></span>

<span data-ttu-id="8e3ac-119">`Invoke` 대리자 형식의 메서드로 캡슐화 된 함수를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e3ac-119">The `Invoke` method on the delegate type calls the encapsulated function.</span></span> <span data-ttu-id="8e3ac-120">또한 대리자는 괄호 없이 Invoke 메서드 이름을 참조 하 여 함수 값으로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e3ac-120">Also, delegates can be passed as function values by referencing the Invoke method name without the parentheses.</span></span>

<span data-ttu-id="8e3ac-121">다음 코드에서는 클래스에서 다양 한 메서드를 나타내는 대리자를 만드는 구문을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8e3ac-121">The following code shows the syntax for creating delegates that represent various methods in a class.</span></span> <span data-ttu-id="8e3ac-122">메서드는 정적 메서드 또는 인스턴스 메서드, 인지 및 튜플 형식에서 커리 된 형식 인수가 있는지에 따라 선언 하 고 대리자를 할당 하는 구문은 약간 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="8e3ac-122">Depending on whether the method is a static method or an instance method, and whether it has arguments in the tuple form or the curried form, the syntax for declaring and assigning the delegate is a little different.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4201.fs)]

<span data-ttu-id="8e3ac-123">다음 코드는 일부 대리자를 사용 하 여 작업할 수는 여러 가지 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8e3ac-123">The following code shows some of the different ways you can work with delegates.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4202.fs)]

<span data-ttu-id="8e3ac-124">이전 코드 예제의 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8e3ac-124">The output of the previous code example is as follows.</span></span>

```console
aaaaa
bbbbb
ccccc
[|"aaa"; "bbb"|]
```

## <a name="see-also"></a><span data-ttu-id="8e3ac-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="8e3ac-125">See also</span></span>

- [<span data-ttu-id="8e3ac-126">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="8e3ac-126">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="8e3ac-127">매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="8e3ac-127">Parameters and Arguments</span></span>](parameters-and-arguments.md)
- [<span data-ttu-id="8e3ac-128">이벤트</span><span class="sxs-lookup"><span data-stu-id="8e3ac-128">Events</span></span>](members/events.md)
