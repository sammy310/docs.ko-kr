---
title: 대리자
description: 에서 F#대리자를 사용 하는 방법에 대해 알아봅니다.
ms.date: 05/16/2016
ms.openlocfilehash: 65875897d5fc4b2ac66f1dfbe913f29fb74137cd
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630362"
---
# <a name="delegates"></a><span data-ttu-id="9e514-103">대리자</span><span class="sxs-lookup"><span data-stu-id="9e514-103">Delegates</span></span>

<span data-ttu-id="9e514-104">대리자는 함수 호출을 개체로 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9e514-104">A delegate represents a function call as an object.</span></span> <span data-ttu-id="9e514-105">F#에서는 일반적으로 함수 값을 사용 하 여 함수를 첫 번째 클래스 값으로 나타내야 합니다. 그러나 대리자는 .NET Framework에서 사용 되므로이를 필요로 하는 Api와 상호 운용할 때 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e514-105">In F#, you ordinarily should use function values to represent functions as first-class values; however, delegates are used in the .NET Framework and so are needed when you interoperate with APIs that expect them.</span></span> <span data-ttu-id="9e514-106">다른 .NET Framework 언어에서 사용 하도록 디자인 된 라이브러리를 제작할 때에도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e514-106">They may also be used when authoring libraries designed for use from other .NET Framework languages.</span></span>

## <a name="syntax"></a><span data-ttu-id="9e514-107">구문</span><span class="sxs-lookup"><span data-stu-id="9e514-107">Syntax</span></span>

```fsharp
type delegate-typename = delegate of type1 -> type2
```

## <a name="remarks"></a><span data-ttu-id="9e514-108">설명</span><span class="sxs-lookup"><span data-stu-id="9e514-108">Remarks</span></span>

<span data-ttu-id="9e514-109">이전 구문 `type1` 에서은 인수 형식을 `type2` 나타내며 반환 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9e514-109">In the previous syntax, `type1` represents the argument type or types and `type2` represents the return type.</span></span> <span data-ttu-id="9e514-110">로 `type1` 표현 되는 인수 형식은 자동으로 변환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e514-110">The argument types that are represented by `type1` are automatically curried.</span></span> <span data-ttu-id="9e514-111">이는 대상 함수의 인수가 커리 된 경우 튜플 형식을 사용 하 고 이미 튜플 형식에 있는 인수에 대해 괄호로 묶은 튜플을 사용 한다는 것을 제안 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e514-111">This suggests that for this type you use a tuple form if the arguments of the target function are curried, and a parenthesized tuple for arguments that are already in the tuple form.</span></span> <span data-ttu-id="9e514-112">자동 currying는 대상 메서드와 일치 하는 튜플 인수를 그대로 두고 괄호 집합을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e514-112">The automatic currying removes a set of parentheses, leaving a tuple argument that matches the target method.</span></span> <span data-ttu-id="9e514-113">각 사례에서 사용 해야 하는 구문에 대 한 코드 예제를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9e514-113">Refer to the code example for the syntax you should use in each case.</span></span>

<span data-ttu-id="9e514-114">대리자는 F# 함수 값 및 정적 또는 인스턴스 메서드에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e514-114">Delegates can be attached to F# function values, and static or instance methods.</span></span> <span data-ttu-id="9e514-115">F#함수 값은 대리자 생성자에 대 한 인수로 직접 전달 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e514-115">F# function values can be passed directly as arguments to delegate constructors.</span></span> <span data-ttu-id="9e514-116">정적 메서드의 경우 클래스 이름 및 메서드를 사용 하 여 대리자를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e514-116">For a static method, you construct the delegate by using the name of the class and the method.</span></span> <span data-ttu-id="9e514-117">인스턴스 메서드의 경우 하나의 인수에 개체 인스턴스와 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e514-117">For an instance method, you provide the object instance and method in one argument.</span></span> <span data-ttu-id="9e514-118">두 경우 모두 멤버 액세스 연산자 (`.`)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e514-118">In both cases, the member access operator (`.`) is used.</span></span>

<span data-ttu-id="9e514-119">대리자 `Invoke` 형식의 메서드는 캡슐화 된 함수를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e514-119">The `Invoke` method on the delegate type calls the encapsulated function.</span></span> <span data-ttu-id="9e514-120">또한 괄호 없이 Invoke 메서드 이름을 참조 하 여 대리자를 함수 값으로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e514-120">Also, delegates can be passed as function values by referencing the Invoke method name without the parentheses.</span></span>

<span data-ttu-id="9e514-121">다음 코드에서는 클래스의 여러 메서드를 나타내는 대리자를 만드는 구문을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9e514-121">The following code shows the syntax for creating delegates that represent various methods in a class.</span></span> <span data-ttu-id="9e514-122">메서드가 정적 메서드 또는 인스턴스 메서드 인지 여부와 해당 메서드가 튜플 형식 또는 커리 된 형식의 인수를 포함 하는지 여부에 따라 대리자를 선언 하 고 할당 하기 위한 구문이 약간 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="9e514-122">Depending on whether the method is a static method or an instance method, and whether it has arguments in the tuple form or the curried form, the syntax for declaring and assigning the delegate is a little different.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4201.fs)]

<span data-ttu-id="9e514-123">다음 코드에서는 대리자를 사용 하 여 작업할 수 있는 몇 가지 다른 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9e514-123">The following code shows some of the different ways you can work with delegates.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4202.fs)]

<span data-ttu-id="9e514-124">이전 코드 예제의 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9e514-124">The output of the previous code example is as follows.</span></span>

```console
aaaaa
bbbbb
ccccc
[|"aaa"; "bbb"|]
```

## <a name="see-also"></a><span data-ttu-id="9e514-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="9e514-125">See also</span></span>

- [<span data-ttu-id="9e514-126">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="9e514-126">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="9e514-127">매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="9e514-127">Parameters and Arguments</span></span>](parameters-and-arguments.md)
- [<span data-ttu-id="9e514-128">이벤트</span><span class="sxs-lookup"><span data-stu-id="9e514-128">Events</span></span>](./members/events.md)
