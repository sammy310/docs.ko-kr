---
title: 액세스 제어
description: 형식, 메서드 및 함수 등 프로그래밍 요소에 대 한 액세스를 제어 하는 방법을 알아봅니다는 F# 프로그래밍 언어입니다.
ms.date: 05/16/2016
ms.openlocfilehash: 8db178b26f3beb6ce95bff84ccad9ac9e8c40ce7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772738"
---
# <a name="access-control"></a><span data-ttu-id="715e9-103">액세스 제어</span><span class="sxs-lookup"><span data-stu-id="715e9-103">Access Control</span></span>

<span data-ttu-id="715e9-104">*액세스 제어* 선언 형식, 메서드 및 함수 같은 특정 프로그램 요소를 사용할 수 있는 클라이언트를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="715e9-104">*Access control* refers to declaring which clients can use certain program elements, such as types, methods, and functions.</span></span>

## <a name="basics-of-access-control"></a><span data-ttu-id="715e9-105">Access Control의 기본 사항</span><span class="sxs-lookup"><span data-stu-id="715e9-105">Basics of Access Control</span></span>

<span data-ttu-id="715e9-106">F#, 액세스 제어 지정자 `public`, `internal`, 및 `private` 모듈, 형식, 메서드, 값 정의 함수, 속성 및 명시적 필드에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="715e9-106">In F#, the access control specifiers `public`, `internal`, and `private` can be applied to modules, types, methods, value definitions, functions, properties, and explicit fields.</span></span>

- <span data-ttu-id="715e9-107">`public` 엔터티의 모든 호출자가 액세스할 수 있는지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="715e9-107">`public` indicates that the entity can be accessed by all callers.</span></span>

- <span data-ttu-id="715e9-108">`internal` 엔터티는 동일한 어셈블리 에서만에서 액세스할 수 있는지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="715e9-108">`internal` indicates that the entity can be accessed only from the same assembly.</span></span>

- <span data-ttu-id="715e9-109">`private` 엔터티 바깥쪽 형식이 나 모듈 에서만 액세스할 수 있는지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="715e9-109">`private` indicates that the entity can be accessed only from the enclosing type or module.</span></span>

> [!NOTE]
> <span data-ttu-id="715e9-110">액세스 지정자 `protected` 에서 사용 되지 않습니다 F#이지만 지 원하는 언어로 작성 된 형식을 사용 하는 경우 적합 `protected` 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="715e9-110">The access specifier `protected` is not used in F#, although it is acceptable if you are using types authored in languages that do support `protected` access.</span></span> <span data-ttu-id="715e9-111">따라서 보호 된 메서드를 재정의 하는 경우 메서드 계속 클래스 및 해당 하위 항목 내 에서만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="715e9-111">Therefore, if you override a protected method, your method remains accessible only within the class and its descendents.</span></span>

<span data-ttu-id="715e9-112">지정자는 때를 제외 하 고 엔터티 이름 앞에 옵니다 일반적으로 `mutable` 또는 `inline` 지정자만 사용 하는 액세스 제어 지정자 뒤에 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="715e9-112">In general, the specifier is put in front of the name of the entity, except when a `mutable` or `inline` specifier is used, which appear after the access control specifier.</span></span>

<span data-ttu-id="715e9-113">응용 프로그램이 사용 되는 액세스 지정 자가 없는 경우 기본값은 `public`를 제외 하 고 `let` 항상는 바인딩 형식에서 `private` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="715e9-113">If no access specifier is used, the default is `public`, except for `let` bindings in a type, which are always `private` to the type.</span></span>

<span data-ttu-id="715e9-114">서명에서 F# 에 대 한 액세스를 제어 하기 위한 다른 메커니즘을 제공 F# 요소를 프로그래밍 합니다.</span><span class="sxs-lookup"><span data-stu-id="715e9-114">Signatures in F# provide another mechanism for controlling access to F# program elements.</span></span> <span data-ttu-id="715e9-115">서명은 액세스 제어에 대 한 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="715e9-115">Signatures are not required for access control.</span></span> <span data-ttu-id="715e9-116">자세한 내용은 [시그니처](signatures.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="715e9-116">For more information, see [Signatures](signatures.md).</span></span>

## <a name="rules-for-access-control"></a><span data-ttu-id="715e9-117">Access Control에 대 한 규칙</span><span class="sxs-lookup"><span data-stu-id="715e9-117">Rules for Access Control</span></span>

<span data-ttu-id="715e9-118">액세스 제어는 다음 규칙이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="715e9-118">Access control is subject to the following rules:</span></span>

- <span data-ttu-id="715e9-119">상속 선언 (즉, 사용 `inherit` 클래스에 대 한 기본 클래스를 지정 하), (즉를 지정 하는 클래스 인터페이스를 구현 하는) 선언, 인터페이스 및 추상 멤버는 항상 바깥쪽 형식으로 동일한 수준의 액세스 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="715e9-119">Inheritance declarations (that is, the use of `inherit` to specify a base class for a class), interface declarations (that is, specifying that a class implements an interface), and abstract members always have the same accessibility as the enclosing type.</span></span> <span data-ttu-id="715e9-120">따라서 이러한 구문에 대해 액세스 제어 지정자를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="715e9-120">Therefore, an access control specifier cannot be used on these constructs.</span></span>

- <span data-ttu-id="715e9-121">구별된 된 공용 구조체의 개별 사례에 대 한 내게 필요한 옵션 자체 구별 된 공용 구조체의 액세스 가능성에 의해 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="715e9-121">Accessibility for individual cases in a discriminated union is determined by the accessibility of the discriminated union itself.</span></span> <span data-ttu-id="715e9-122">즉, 공용 구조체 케이스는 공용 구조체 자체 보다 액세스 하기 더 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="715e9-122">That is, a particular union case is no less accessible than the union itself.</span></span>

- <span data-ttu-id="715e9-123">내게 필요한 옵션 없습니다 레코드 형식의 각 필드에 대 한 레코드 자체의 액세스 가능성에 의해 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="715e9-123">Accessibility for individual fields of a record type cannot is determined by the accessibility of the record itself.</span></span> <span data-ttu-id="715e9-124">즉, 특정 레코드 레이블은입니다는 레코드 자체 보다 액세스 하기 더 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="715e9-124">That is, a particular record label is no less accessible than the record itself.</span></span>

## <a name="example"></a><span data-ttu-id="715e9-125">예제</span><span class="sxs-lookup"><span data-stu-id="715e9-125">Example</span></span>

<span data-ttu-id="715e9-126">다음 코드를 액세스 제어 지정자의 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="715e9-126">The following code illustrates the use of access control specifiers.</span></span> <span data-ttu-id="715e9-127">프로젝트에서 두 개의 파일이 `Module1.fs` 고 `Module2.fs`입니다.</span><span class="sxs-lookup"><span data-stu-id="715e9-127">There are two files in the project, `Module1.fs` and `Module2.fs`.</span></span> <span data-ttu-id="715e9-128">각 파일은 암시적으로 모듈.</span><span class="sxs-lookup"><span data-stu-id="715e9-128">Each file is implicitly a module.</span></span> <span data-ttu-id="715e9-129">따라서 두 모듈은 `Module1` 고 `Module2`입니다.</span><span class="sxs-lookup"><span data-stu-id="715e9-129">Therefore, there are two modules, `Module1` and `Module2`.</span></span> <span data-ttu-id="715e9-130">개인 유형 및 내부 형식에 정의 된 `Module1`합니다.</span><span class="sxs-lookup"><span data-stu-id="715e9-130">A private type and an internal type are defined in `Module1`.</span></span> <span data-ttu-id="715e9-131">전용 형식에서 액세스할 수 없습니다 `Module2`, 내부 형식 수입니다.</span><span class="sxs-lookup"><span data-stu-id="715e9-131">The private type cannot be accessed from `Module2`, but the internal type can.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/access-control/snippet1.fs)]

<span data-ttu-id="715e9-132">다음 코드에서 만든 형식의 액세스 가능성을 테스트 `Module1.fs`합니다.</span><span class="sxs-lookup"><span data-stu-id="715e9-132">The following code tests the accessibility of the types created in `Module1.fs`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/access-control/snippet2.fs)]

## <a name="see-also"></a><span data-ttu-id="715e9-133">참고자료</span><span class="sxs-lookup"><span data-stu-id="715e9-133">See also</span></span>

- [<span data-ttu-id="715e9-134">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="715e9-134">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="715e9-135">서명</span><span class="sxs-lookup"><span data-stu-id="715e9-135">Signatures</span></span>](signatures.md)