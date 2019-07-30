---
title: 클래스의 do 바인딩
description: 개체가 생성 될 때 또는 F# 형식이 처음 사용 될 때 동작을 수행 하는 클래스 정의에서 ' do ' 바인딩을 사용 하는 방법에 대해 알아봅니다.
ms.date: 05/16/2016
ms.openlocfilehash: ced4f1bb17d9e23bf51cc79b5a275cc334cca013
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627582"
---
# <a name="do-bindings-in-classes"></a><span data-ttu-id="6c2dc-103">클래스의 do 바인딩</span><span class="sxs-lookup"><span data-stu-id="6c2dc-103">do Bindings in Classes</span></span>

<span data-ttu-id="6c2dc-104">클래스 정의의 `do` 바인딩은개체가생성될때동작을수행하고,형식을처음사용할때정적바인딩에대해`do` 를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c2dc-104">A `do` binding in a class definition performs actions when the object is constructed or, for a static `do` binding, when the type is first used.</span></span>

## <a name="syntax"></a><span data-ttu-id="6c2dc-105">구문</span><span class="sxs-lookup"><span data-stu-id="6c2dc-105">Syntax</span></span>

```fsharp
[static] do expression
```

## <a name="remarks"></a><span data-ttu-id="6c2dc-106">설명</span><span class="sxs-lookup"><span data-stu-id="6c2dc-106">Remarks</span></span>

<span data-ttu-id="6c2dc-107">바인딩은 또는 이후에 `let` 바인딩과 함께 표시 되지만 클래스 정의의 멤버 정의 앞에 표시 됩니다. `do`</span><span class="sxs-lookup"><span data-stu-id="6c2dc-107">A `do` binding appears together with or after `let` bindings but before member definitions in a class definition.</span></span> <span data-ttu-id="6c2dc-108">키워드는 `do` 모듈 수준에서 바인딩에 `do` 대해 선택 사항 이지만 클래스 정의의 `do` 바인딩에는 선택 사항이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="6c2dc-108">Although the `do` keyword is optional for `do` bindings at the module level, it is not optional for `do` bindings in a class definition.</span></span>

<span data-ttu-id="6c2dc-109">지정 된 형식의 모든 개체를 `do` 생성 하는 경우 비정적 바인딩과 비정적 `let` 바인딩은 클래스 정의에 표시 되는 순서 대로 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c2dc-109">For the construction of every object of any given type, non-static `do` bindings and non-static `let` bindings are executed in the order in which they appear in the class definition.</span></span> <span data-ttu-id="6c2dc-110">하나의 `do` 형식에서 여러 바인딩이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c2dc-110">Multiple `do` bindings can occur in one type.</span></span> <span data-ttu-id="6c2dc-111">비정적 바인딩과 비정적 `do` 바인딩은 기본 생성자의 본문이 됩니다. `let`</span><span class="sxs-lookup"><span data-stu-id="6c2dc-111">The non-static `let` bindings and the non-static `do` bindings become the body of the primary constructor.</span></span> <span data-ttu-id="6c2dc-112">비정적 `do` 바인딩 섹션의 코드는 기본 생성자 매개 변수와 `let` 바인딩 섹션에 정의 된 모든 값 또는 함수를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c2dc-112">The code in the non-static `do` bindings section can reference the primary constructor parameters and any values or functions that are defined in the `let` bindings section.</span></span>

<span data-ttu-id="6c2dc-113">클래스가 클래스 제목의 `do` `as` 키워드에 의해 정의 된 자체 식별자를 포함 하는 동안에는 비정적 바인딩이 클래스의 멤버에 액세스할 수 있습니다 .이 경우 해당 멤버의 모든 사용은 클래스의 자체 식별자로 한정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c2dc-113">Non-static `do` bindings can access members of the class as long as the class has a self identifier that is defined by an `as` keyword in the class heading, and as long as all uses of those members are qualified with the self identifier for the class.</span></span>

<span data-ttu-id="6c2dc-114">바인딩이 `let` 클래스의 전용 필드를 초기화 하기 때문에 멤버가 `do` 정상적으로 작동 하도록 보장 하기 위해 일반적으로 바인딩이 바인딩 후 `let` 에 `do` 배치 되므로 바인딩의 코드를 사용할 수 있습니다. 완전히 초기화 된 개체를 사용 하 여를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c2dc-114">Because `let` bindings initialize the private fields of a class, which is often necessary to guarantee that members behave as expected, `do` bindings are usually put after `let` bindings so that code in the `do` binding can execute with a fully initialized object.</span></span> <span data-ttu-id="6c2dc-115">초기화가 완료 되기 전에 코드에서 멤버를 사용 하려고 하면 InvalidOperationException이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c2dc-115">If your code attempts to use a member before the initialization is complete, an InvalidOperationException is raised.</span></span>

<span data-ttu-id="6c2dc-116">정적 `do` 바인딩은 바깥쪽 클래스의 정적 멤버 또는 필드를 참조할 수 있지만 인스턴스 멤버나 필드는 참조할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6c2dc-116">Static `do` bindings can reference static members or fields of the enclosing class but not instance members or fields.</span></span> <span data-ttu-id="6c2dc-117">정적 `do` 바인딩은 클래스에 대 한 정적 이니셜라이저의 일부가 되므로 클래스를 처음 사용 하기 전에 실행이 보장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c2dc-117">Static `do` bindings become part of the static initializer for the class, which is guaranteed to execute before the class is first used.</span></span>

<span data-ttu-id="6c2dc-118">특성은 형식의 바인딩에 `do` 대해 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c2dc-118">Attributes are ignored for `do` bindings in types.</span></span> <span data-ttu-id="6c2dc-119">`do` 바인딩에서 실행 되는 코드에 특성이 필요한 경우 기본 생성자에 적용 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c2dc-119">If an attribute is required for code that executes in a `do` binding, it must be applied to the primary constructor.</span></span>

<span data-ttu-id="6c2dc-120">다음 코드에서 클래스에는 정적 `do` 바인딩과 `do` 비정적 바인딩이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c2dc-120">In the following code, a class has a static `do` binding and a non-static `do` binding.</span></span> <span data-ttu-id="6c2dc-121">개체에는 두 개의 매개 변수 `a` 및 `b`가 있고 클래스의 `let` 바인딩에 두 개의 전용 필드가 정의 되어 있는 생성자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c2dc-121">The object has a constructor that has two parameters, `a` and `b`, and two private fields are defined in the `let` bindings for the class.</span></span> <span data-ttu-id="6c2dc-122">두 속성도 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c2dc-122">Two properties are also defined.</span></span> <span data-ttu-id="6c2dc-123">이러한 모든 값을 출력 하는 줄에서 볼 수 `do` 있듯이 이러한 모든 값은 비정적 바인딩 섹션의 범위 내에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c2dc-123">All of these are in scope in the non-static `do` bindings section, as is illustrated by the line that prints all those values.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3101.fs)]

<span data-ttu-id="6c2dc-124">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6c2dc-124">The output is as follows.</span></span>

```console
Initializing MyType.
Initializing object 1 2 2 4 8 16
```

## <a name="see-also"></a><span data-ttu-id="6c2dc-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="6c2dc-125">See also</span></span>

- [<span data-ttu-id="6c2dc-126">멤버</span><span class="sxs-lookup"><span data-stu-id="6c2dc-126">Members</span></span>](index.md)
- [<span data-ttu-id="6c2dc-127">클래스</span><span class="sxs-lookup"><span data-stu-id="6c2dc-127">Classes</span></span>](../classes.md)
- [<span data-ttu-id="6c2dc-128">생성자</span><span class="sxs-lookup"><span data-stu-id="6c2dc-128">Constructors</span></span>](constructors.md)
- [<span data-ttu-id="6c2dc-129">클래스의 `let` 바인딩</span><span class="sxs-lookup"><span data-stu-id="6c2dc-129">`let` Bindings in Classes</span></span>](let-bindings-in-classes.md)
- [<span data-ttu-id="6c2dc-130">`do`바인딩하</span><span class="sxs-lookup"><span data-stu-id="6c2dc-130">`do` Bindings</span></span>](../functions/do-Bindings.md)
