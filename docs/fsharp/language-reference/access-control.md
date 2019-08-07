---
title: 액세스 제어
description: F# 프로그래밍 언어에서 형식, 메서드, 함수 등의 프로그래밍 요소에 대 한 액세스를 제어 하는 방법에 대해 알아봅니다.
ms.date: 05/16/2016
ms.openlocfilehash: 38f8f3fd4114c0428fbe8baca71594cd07740b2c
ms.sourcegitcommit: 10736f243dd2296212e677e207102c463e5f143e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2019
ms.locfileid: "68817863"
---
# <a name="access-control"></a><span data-ttu-id="131d9-103">액세스 제어</span><span class="sxs-lookup"><span data-stu-id="131d9-103">Access Control</span></span>

<span data-ttu-id="131d9-104">*액세스 제어* 는 형식, 메서드 및 함수와 같은 특정 프로그램 요소를 사용할 수 있는 클라이언트를 선언 하는 것을 말합니다.</span><span class="sxs-lookup"><span data-stu-id="131d9-104">*Access control* refers to declaring which clients can use certain program elements, such as types, methods, and functions.</span></span>

## <a name="basics-of-access-control"></a><span data-ttu-id="131d9-105">Access Control의 기본 사항</span><span class="sxs-lookup"><span data-stu-id="131d9-105">Basics of Access Control</span></span>

<span data-ttu-id="131d9-106">에서는 F#액세스 제어 지정자 `public`, `internal`및 `private` 를 모듈, 형식, 메서드, 값 정의, 함수, 속성 및 명시적 필드에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="131d9-106">In F#, the access control specifiers `public`, `internal`, and `private` can be applied to modules, types, methods, value definitions, functions, properties, and explicit fields.</span></span>

- <span data-ttu-id="131d9-107">`public`모든 호출자가 엔터티에 액세스할 수 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="131d9-107">`public` indicates that the entity can be accessed by all callers.</span></span>

- <span data-ttu-id="131d9-108">`internal`동일한 어셈블리 에서만 엔터티를 액세스할 수 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="131d9-108">`internal` indicates that the entity can be accessed only from the same assembly.</span></span>

- <span data-ttu-id="131d9-109">`private`는 바깥쪽 형식 또는 모듈 에서만 엔터티에 액세스할 수 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="131d9-109">`private` indicates that the entity can be accessed only from the enclosing type or module.</span></span>

> [!NOTE]
> <span data-ttu-id="131d9-110">액세스를 지 `protected` `protected` 원하는 언어로 작성 된 F#형식을 사용 하는 경우에는 액세스 지정자를 사용할 수 있지만 액세스 지정자는에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="131d9-110">The access specifier `protected` is not used in F#, although it is acceptable if you are using types authored in languages that do support `protected` access.</span></span> <span data-ttu-id="131d9-111">따라서 protected 메서드를 재정의 하는 경우 메서드는 클래스 및 해당 하위 클래스 내 에서만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="131d9-111">Therefore, if you override a protected method, your method remains accessible only within the class and its descendents.</span></span>

<span data-ttu-id="131d9-112">일반적으로 지정자는 `mutable` 또는 `inline` 지정자를 사용 하는 경우를 제외 하 고는 엔터티 이름 앞에 배치 됩니다 .이는 액세스 제어 지정자 뒤에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="131d9-112">In general, the specifier is put in front of the name of the entity, except when a `mutable` or `inline` specifier is used, which appear after the access control specifier.</span></span>

<span data-ttu-id="131d9-113">액세스 지정자를 사용 하지 않는 경우 기본값 `public`은 형식에 대 한 `let` 바인딩을 제외 하 고 항상 `private` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="131d9-113">If no access specifier is used, the default is `public`, except for `let` bindings in a type, which are always `private` to the type.</span></span>

<span data-ttu-id="131d9-114">의 F# 시그니처는 프로그램 요소에 대 한 액세스 F# 를 제어 하는 또 다른 메커니즘을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="131d9-114">Signatures in F# provide another mechanism for controlling access to F# program elements.</span></span> <span data-ttu-id="131d9-115">액세스 제어에는 서명이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="131d9-115">Signatures are not required for access control.</span></span> <span data-ttu-id="131d9-116">자세한 내용은 [시그니처](signatures.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="131d9-116">For more information, see [Signatures](signatures.md).</span></span>

## <a name="rules-for-access-control"></a><span data-ttu-id="131d9-117">Access Control에 대 한 규칙</span><span class="sxs-lookup"><span data-stu-id="131d9-117">Rules for Access Control</span></span>

<span data-ttu-id="131d9-118">액세스 제어에는 다음 규칙이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="131d9-118">Access control is subject to the following rules:</span></span>

- <span data-ttu-id="131d9-119">상속 선언 (즉, 클래스의 기본 클래스 `inherit` 를 지정 하는 데 사용), 인터페이스 선언 (즉, 클래스에서 인터페이스를 구현 하도록 지정) 및 추상 멤버는 항상 바깥쪽 형식과 동일한 접근성을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="131d9-119">Inheritance declarations (that is, the use of `inherit` to specify a base class for a class), interface declarations (that is, specifying that a class implements an interface), and abstract members always have the same accessibility as the enclosing type.</span></span> <span data-ttu-id="131d9-120">따라서 이러한 구문에서는 액세스 제어 지정자를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="131d9-120">Therefore, an access control specifier cannot be used on these constructs.</span></span>

- <span data-ttu-id="131d9-121">구분 된 공용 구조체의 개별 사례에 대 한 접근성은 구별 된 공용 구조체 자체의 접근성에 의해 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="131d9-121">Accessibility for individual cases in a discriminated union is determined by the accessibility of the discriminated union itself.</span></span> <span data-ttu-id="131d9-122">즉, 특정 공용 구조체 케이스는 union 자체 보다 액세스 하기 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="131d9-122">That is, a particular union case is no less accessible than the union itself.</span></span>

- <span data-ttu-id="131d9-123">레코드 형식의 개별 필드에 대 한 액세스 가능성은 레코드 자체의 접근성에 의해 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="131d9-123">Accessibility for individual fields of a record type is determined by the accessibility of the record itself.</span></span> <span data-ttu-id="131d9-124">즉, 특정 레코드 레이블은 레코드 자체 보다 액세스 하기 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="131d9-124">That is, a particular record label is no less accessible than the record itself.</span></span>

## <a name="example"></a><span data-ttu-id="131d9-125">예제</span><span class="sxs-lookup"><span data-stu-id="131d9-125">Example</span></span>

<span data-ttu-id="131d9-126">다음 코드에서는 액세스 제어 지정자를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="131d9-126">The following code illustrates the use of access control specifiers.</span></span> <span data-ttu-id="131d9-127">프로젝트 `Module1.fs` 에는 및 `Module2.fs`라는 두 개의 파일이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="131d9-127">There are two files in the project, `Module1.fs` and `Module2.fs`.</span></span> <span data-ttu-id="131d9-128">각 파일은 암시적으로 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="131d9-128">Each file is implicitly a module.</span></span> <span data-ttu-id="131d9-129">따라서 `Module1` 와`Module2`라는 두 개의 모듈이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="131d9-129">Therefore, there are two modules, `Module1` and `Module2`.</span></span> <span data-ttu-id="131d9-130">전용 형식 및 내부 형식은에 `Module1`정의 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="131d9-130">A private type and an internal type are defined in `Module1`.</span></span> <span data-ttu-id="131d9-131">Private 형식은에서 `Module2`액세스할 수 없지만 내부 형식은 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="131d9-131">The private type cannot be accessed from `Module2`, but the internal type can.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/access-control/snippet1.fs)]

<span data-ttu-id="131d9-132">다음 코드는에서 `Module1.fs`만든 형식의 액세스 가능성을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="131d9-132">The following code tests the accessibility of the types created in `Module1.fs`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/access-control/snippet2.fs)]

## <a name="see-also"></a><span data-ttu-id="131d9-133">참고자료</span><span class="sxs-lookup"><span data-stu-id="131d9-133">See also</span></span>

- [<span data-ttu-id="131d9-134">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="131d9-134">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="131d9-135">서명</span><span class="sxs-lookup"><span data-stu-id="131d9-135">Signatures</span></span>](signatures.md)
