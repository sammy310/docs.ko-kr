---
title: 클래스의 do 바인딩
description: 사용 하는 방법을 알아봅니다는 F# 개체가 생성 될 때나 형식을 처음 사용할 때 작업을 수행 하는 클래스 정의 바인딩 ' do'.
ms.date: 05/16/2016
ms.openlocfilehash: c924c882974989436d8ea404ebee0a7ef3c54fd3
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641793"
---
# <a name="do-bindings-in-classes"></a><span data-ttu-id="92de4-103">클래스의 do 바인딩</span><span class="sxs-lookup"><span data-stu-id="92de4-103">do Bindings in Classes</span></span>

<span data-ttu-id="92de4-104">A `do` 클래스 정의에서 바인딩 작업을 수행 개체가 생성 될 때 정적 `do` 바인딩는 유형을 처음 사용할 때.</span><span class="sxs-lookup"><span data-stu-id="92de4-104">A `do` binding in a class definition performs actions when the object is constructed or, for a static `do` binding, when the type is first used.</span></span>

## <a name="syntax"></a><span data-ttu-id="92de4-105">구문</span><span class="sxs-lookup"><span data-stu-id="92de4-105">Syntax</span></span>

```fsharp
[static] do expression
```

## <a name="remarks"></a><span data-ttu-id="92de4-106">설명</span><span class="sxs-lookup"><span data-stu-id="92de4-106">Remarks</span></span>

<span data-ttu-id="92de4-107">A `do` 바인딩 표시와 함께 또는 후 `let` 바인딩 클래스 정의의 멤버 정의 하기 전에 합니다.</span><span class="sxs-lookup"><span data-stu-id="92de4-107">A `do` binding appears together with or after `let` bindings but before member definitions in a class definition.</span></span> <span data-ttu-id="92de4-108">하지만 합니다 `do` 키워드는 선택 사항입니다 `do` 바인딩을 대 한 선택적 있지 모듈 수준에서 `do` 클래스 정의에 바인딩.</span><span class="sxs-lookup"><span data-stu-id="92de4-108">Although the `do` keyword is optional for `do` bindings at the module level, it is not optional for `do` bindings in a class definition.</span></span>

<span data-ttu-id="92de4-109">지정 된 형식에 static이 아니고의 모든 개체를 생성할 `do` 바인딩 및 비정적 `let` 바인딩 클래스 정의에 나타나는 순서 대로 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="92de4-109">For the construction of every object of any given type, non-static `do` bindings and non-static `let` bindings are executed in the order in which they appear in the class definition.</span></span> <span data-ttu-id="92de4-110">여러 `do` 바인딩 형식에서 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92de4-110">Multiple `do` bindings can occur in one type.</span></span> <span data-ttu-id="92de4-111">비정적 `let` 바인딩 및 비정적 `do` 바인딩 기본 생성자의 본문이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="92de4-111">The non-static `let` bindings and the non-static `do` bindings become the body of the primary constructor.</span></span> <span data-ttu-id="92de4-112">정적이 지 않은 코드 `do` 기본 생성자 매개 변수를 임의의 값 또는 함수에 정의 된 바인딩 섹션 참조할 수는 `let` 바인딩 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="92de4-112">The code in the non-static `do` bindings section can reference the primary constructor parameters and any values or functions that are defined in the `let` bindings section.</span></span>

<span data-ttu-id="92de4-113">비정적 `do` 클래스에서 정의한 자체 식별자가으로 바인딩 클래스의 멤버를 액세스할 수는 `as` 제목과으로 해당 멤버의 모든 사용은 클래스에 대 한 자체 식별자로 정규화 된 클래스에는 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="92de4-113">Non-static `do` bindings can access members of the class as long as the class has a self identifier that is defined by an `as` keyword in the class heading, and as long as all uses of those members are qualified with the self identifier for the class.</span></span>

<span data-ttu-id="92de4-114">때문에 `let` 멤버는 예상 대로 작동 하도록 하는 데 필요한 경우가 되는 클래스를 개인 필드를 초기화 하는 바인딩을 `do` 바인딩 후 일반적으로 배치 됩니다 `let` 바인딩이 있으므로 해당 코드는 `do` 바인딩 수 완전히 초기화 된 개체를 사용 하 여 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="92de4-114">Because `let` bindings initialize the private fields of a class, which is often necessary to guarantee that members behave as expected, `do` bindings are usually put after `let` bindings so that code in the `do` binding can execute with a fully initialized object.</span></span> <span data-ttu-id="92de4-115">코드를 초기화가 완료 되기 전에 구성원을 사용 하려고 InvalidOperationException이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="92de4-115">If your code attempts to use a member before the initialization is complete, an InvalidOperationException is raised.</span></span>

<span data-ttu-id="92de4-116">정적 `do` 바인딩 정적 멤버를 참조할 수 또는 필드 바깥쪽의 클래스 하지만 하지 인스턴스 멤버 또는 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="92de4-116">Static `do` bindings can reference static members or fields of the enclosing class but not instance members or fields.</span></span> <span data-ttu-id="92de4-117">정적 `do` 바인딩 클래스를 처음 사용 하기 전에 실행 되는 클래스의 정적 이니셜라이저의 일부가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="92de4-117">Static `do` bindings become part of the static initializer for the class, which is guaranteed to execute before the class is first used.</span></span>

<span data-ttu-id="92de4-118">에 대 한 특성은 무시 됩니다 `do` 바인딩 형식에서입니다.</span><span class="sxs-lookup"><span data-stu-id="92de4-118">Attributes are ignored for `do` bindings in types.</span></span> <span data-ttu-id="92de4-119">특성에서 실행 되는 코드에 대 한 필수 인지를 `do` 바인딩을 적용 해야 기본 생성자입니다.</span><span class="sxs-lookup"><span data-stu-id="92de4-119">If an attribute is required for code that executes in a `do` binding, it must be applied to the primary constructor.</span></span>

<span data-ttu-id="92de4-120">다음 코드를 클래스에 정적 `do` 바인딩 및 static이 아니고 `do` 바인딩.</span><span class="sxs-lookup"><span data-stu-id="92de4-120">In the following code, a class has a static `do` binding and a non-static `do` binding.</span></span> <span data-ttu-id="92de4-121">두 매개 변수가 있는 생성자를 포함 하는 개체 `a` 하 고 `b`, 및 두 개의 private 필드에 정의 됩니다는 `let` 클래스에 대 한 바인딩을 합니다.</span><span class="sxs-lookup"><span data-stu-id="92de4-121">The object has a constructor that has two parameters, `a` and `b`, and two private fields are defined in the `let` bindings for the class.</span></span> <span data-ttu-id="92de4-122">두 가지 속성이 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="92de4-122">Two properties are also defined.</span></span> <span data-ttu-id="92de4-123">비정적의 범위 내에 이러한 모든 기능은 `do` 바인딩 섹션에는 해당 값을 모든 출력 줄에서 볼 수 있듯이 합니다.</span><span class="sxs-lookup"><span data-stu-id="92de4-123">All of these are in scope in the non-static `do` bindings section, as is illustrated by the line that prints all those values.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3101.fs)]

<span data-ttu-id="92de4-124">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="92de4-124">The output is as follows.</span></span>

```console
Initializing MyType.
Initializing object 1 2 2 4 8 16
```

## <a name="see-also"></a><span data-ttu-id="92de4-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="92de4-125">See also</span></span>

- [<span data-ttu-id="92de4-126">멤버</span><span class="sxs-lookup"><span data-stu-id="92de4-126">Members</span></span>](index.md)
- [<span data-ttu-id="92de4-127">클래스</span><span class="sxs-lookup"><span data-stu-id="92de4-127">Classes</span></span>](../classes.md)
- [<span data-ttu-id="92de4-128">생성자</span><span class="sxs-lookup"><span data-stu-id="92de4-128">Constructors</span></span>](constructors.md)
- [<span data-ttu-id="92de4-129">클래스의 `let` 바인딩</span><span class="sxs-lookup"><span data-stu-id="92de4-129">`let` Bindings in Classes</span></span>](let-bindings-in-classes.md)
- [<span data-ttu-id="92de4-130">`do` Bindings</span><span class="sxs-lookup"><span data-stu-id="92de4-130">`do` Bindings</span></span>](../functions/do-Bindings.md)
