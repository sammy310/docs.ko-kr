---
title: Overloads
ms.date: 07/20/2015
f1_keywords:
- vb.Overloads
- Overloads
helpviewer_keywords:
- Overloads keyword [Visual Basic]
- hiding by signature
- Shadows keyword [Visual Basic]
- signature, hiding by
ms.assetid: 0c6820b8-25b2-4664-bc59-5ca93c99c042
ms.openlocfilehash: bd0931cab520f8580c0d7473a44e350752e287bb
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392108"
---
# <a name="overloads-visual-basic"></a><span data-ttu-id="e17fd-102">Overloads(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e17fd-102">Overloads (Visual Basic)</span></span>

<span data-ttu-id="e17fd-103">속성 또는 프로시저에서 하나 이상의 기존 속성 또는 프로시저를 같은 이름으로 다시 선언할 수 있도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e17fd-103">Specifies that a property or procedure redeclares one or more existing properties or procedures with the same name.</span></span>

## <a name="remarks"></a><span data-ttu-id="e17fd-104">설명</span><span class="sxs-lookup"><span data-stu-id="e17fd-104">Remarks</span></span>

<span data-ttu-id="e17fd-105">*오버 로드* 는 동일한 범위에서 지정 된 속성 또는 프로시저 이름에 대 한 정의를 두 개 이상 제공 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="e17fd-105">*Overloading* is the practice of supplying more than one definition for a given property or procedure name in the same scope.</span></span> <span data-ttu-id="e17fd-106">서명이 다른 속성 또는 프로시저를 *서명으로*다시 선언할 하는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e17fd-106">Redeclaring a property or procedure with a different signature is sometimes called *hiding by signature*.</span></span>

## <a name="rules"></a><span data-ttu-id="e17fd-107">규칙</span><span class="sxs-lookup"><span data-stu-id="e17fd-107">Rules</span></span>

- <span data-ttu-id="e17fd-108">**선언 컨텍스트.**</span><span class="sxs-lookup"><span data-stu-id="e17fd-108">**Declaration Context.**</span></span> <span data-ttu-id="e17fd-109">`Overloads`속성 또는 프로시저 선언 문에서만를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e17fd-109">You can use `Overloads` only in a property or procedure declaration statement.</span></span>

- <span data-ttu-id="e17fd-110">**결합된 한정자.**</span><span class="sxs-lookup"><span data-stu-id="e17fd-110">**Combined Modifiers.**</span></span> <span data-ttu-id="e17fd-111">`Overloads`같은 프로시저 선언에서 [그림자](shadows.md) 와 함께 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e17fd-111">You cannot specify `Overloads` together with [Shadows](shadows.md) in the same procedure declaration.</span></span>

- <span data-ttu-id="e17fd-112">**차이 필요.**</span><span class="sxs-lookup"><span data-stu-id="e17fd-112">**Required Differences.**</span></span> <span data-ttu-id="e17fd-113">이 선언의 *시그니처* 는 오버 로드 되는 모든 속성 또는 프로시저의 서명과 달라 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e17fd-113">The *signature* in this declaration must be different from the signature of every property or procedure that it overloads.</span></span> <span data-ttu-id="e17fd-114">서명은 다음 항목과 함께 속성 또는 프로시저 이름으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="e17fd-114">The signature comprises the property or procedure name together with the following:</span></span>

  - <span data-ttu-id="e17fd-115">매개 변수 수</span><span class="sxs-lookup"><span data-stu-id="e17fd-115">the number of parameters</span></span>

  - <span data-ttu-id="e17fd-116">매개 변수의 순서</span><span class="sxs-lookup"><span data-stu-id="e17fd-116">the order of the parameters</span></span>

  - <span data-ttu-id="e17fd-117">매개 변수의 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="e17fd-117">the data types of the parameters</span></span>

  - <span data-ttu-id="e17fd-118">형식 매개 변수의 수(제네릭 프로시저의 경우)</span><span class="sxs-lookup"><span data-stu-id="e17fd-118">the number of type parameters (for a generic procedure)</span></span>

  - <span data-ttu-id="e17fd-119">반환 형식(변환 연산자 프로시저의 경우만)</span><span class="sxs-lookup"><span data-stu-id="e17fd-119">the return type (only for a conversion operator procedure)</span></span>

  <span data-ttu-id="e17fd-120">모든 오버로드는 이름이 같아야 하지만 앞에서 설명한 하나 이상의 측면과 관련하여 각각은 다른 모든 오버로드와 달라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e17fd-120">All overloads must have the same name, but each must differ from all the others in one or more of the preceding respects.</span></span> <span data-ttu-id="e17fd-121">그러면 컴파일러가 코드에서 속성 또는 프로시저를 호출할 때 사용할 버전을 구분할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e17fd-121">This allows the compiler to distinguish which version to use when code calls the property or procedure.</span></span>

- <span data-ttu-id="e17fd-122">**차이 허용 안 함.**</span><span class="sxs-lookup"><span data-stu-id="e17fd-122">**Disallowed Differences.**</span></span> <span data-ttu-id="e17fd-123">다음 중 하나 이상은 서명의 일부가 아니므로 속성 또는 프로시저를 오버로드하기 위해 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e17fd-123">Changing one or more of the following is not valid for overloading a property or procedure, because they are not part of the signature:</span></span>

  - <span data-ttu-id="e17fd-124">값을 반환하는지 여부(프로시저의 경우)</span><span class="sxs-lookup"><span data-stu-id="e17fd-124">whether or not it returns a value (for a procedure)</span></span>

  - <span data-ttu-id="e17fd-125">반환 값의 데이터 형식(변환 연산자 제외)</span><span class="sxs-lookup"><span data-stu-id="e17fd-125">the data type of the return value (except for a conversion operator)</span></span>

  - <span data-ttu-id="e17fd-126">매개 변수 또는 형식 매개 변수의 이름</span><span class="sxs-lookup"><span data-stu-id="e17fd-126">the names of the parameters or type parameters</span></span>

  - <span data-ttu-id="e17fd-127">형식 매개 변수에 대한 제약 조건(제네릭 프로시저의 경우)</span><span class="sxs-lookup"><span data-stu-id="e17fd-127">the constraints on the type parameters (for a generic procedure)</span></span>

  - <span data-ttu-id="e17fd-128">매개 변수 한정자 키워드(예: `ByRef` 또는 `Optional`)</span><span class="sxs-lookup"><span data-stu-id="e17fd-128">parameter modifier keywords (such as `ByRef` or `Optional`)</span></span>

  - <span data-ttu-id="e17fd-129">속성 또는 프로시저 한정자 키워드(예: `Public` 또는 `Shared`)</span><span class="sxs-lookup"><span data-stu-id="e17fd-129">property or procedure modifier keywords (such as `Public` or `Shared`)</span></span>

- <span data-ttu-id="e17fd-130">**선택적 한정자.**</span><span class="sxs-lookup"><span data-stu-id="e17fd-130">**Optional Modifier.**</span></span> <span data-ttu-id="e17fd-131">`Overloads`동일한 클래스에서 여러 오버 로드 된 속성 또는 프로시저를 정의 하는 경우 한정자를 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e17fd-131">You do not have to use the `Overloads` modifier when you are defining multiple overloaded properties or procedures in the same class.</span></span> <span data-ttu-id="e17fd-132">그러나 선언 중 하나에서 `Overloads`를 사용하는 경우에는 모든 선언에서 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e17fd-132">However, if you use `Overloads` in one of the declarations, you must use it in all of them.</span></span>

- <span data-ttu-id="e17fd-133">**숨김 및 오버 로드.**</span><span class="sxs-lookup"><span data-stu-id="e17fd-133">**Shadowing and Overloading.**</span></span> <span data-ttu-id="e17fd-134">`Overloads`를 사용 하 여 기본 클래스에서 기존 멤버 또는 오버 로드 된 멤버 집합을 숨길 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e17fd-134">`Overloads` can also be used to shadow an existing member, or set of overloaded members, in a base class.</span></span> <span data-ttu-id="e17fd-135">이런 방식으로 `Overloads`를 사용하는 경우 기본 클래스 멤버와 동일한 이름 및 동일한 매개 변수 목록을 사용하여 속성 또는 메서드를 선언하고 `Shadows` 키워드는 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e17fd-135">When you use `Overloads` in this way, you declare the property or method with the same name and the same parameter list as the base class member, and you do not supply the `Shadows` keyword.</span></span>

<span data-ttu-id="e17fd-136">`Overrides`를 사용하는 경우 라이브러리 API가 보다 쉽게 C#으로 작업할 수 있도록 컴파일러에서 암시적으로 `Overloads`를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e17fd-136">If you use `Overrides`, the compiler implicitly adds `Overloads` so that your library APIs work with C# more easily.</span></span>

<span data-ttu-id="e17fd-137">`Overloads` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e17fd-137">The `Overloads` modifier can be used in these contexts:</span></span>

- [<span data-ttu-id="e17fd-138">Function 문</span><span class="sxs-lookup"><span data-stu-id="e17fd-138">Function Statement</span></span>](../statements/function-statement.md)

- [<span data-ttu-id="e17fd-139">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="e17fd-139">Operator Statement</span></span>](../statements/operator-statement.md)

- [<span data-ttu-id="e17fd-140">Property Statement</span><span class="sxs-lookup"><span data-stu-id="e17fd-140">Property Statement</span></span>](../statements/property-statement.md)

- [<span data-ttu-id="e17fd-141">Sub 문</span><span class="sxs-lookup"><span data-stu-id="e17fd-141">Sub Statement</span></span>](../statements/sub-statement.md)

## <a name="see-also"></a><span data-ttu-id="e17fd-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e17fd-142">See also</span></span>

- [<span data-ttu-id="e17fd-143">Overloads</span><span class="sxs-lookup"><span data-stu-id="e17fd-143">Shadows</span></span>](shadows.md)
- [<span data-ttu-id="e17fd-144">프로시저 오버로딩</span><span class="sxs-lookup"><span data-stu-id="e17fd-144">Procedure Overloading</span></span>](../../programming-guide/language-features/procedures/procedure-overloading.md)
- [<span data-ttu-id="e17fd-145">Visual Basic의 제네릭 형식</span><span class="sxs-lookup"><span data-stu-id="e17fd-145">Generic Types in Visual Basic</span></span>](../../programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="e17fd-146">연산자 프로시저</span><span class="sxs-lookup"><span data-stu-id="e17fd-146">Operator Procedures</span></span>](../../programming-guide/language-features/procedures/operator-procedures.md)
- [<span data-ttu-id="e17fd-147">방법: 변환 연산자 정의</span><span class="sxs-lookup"><span data-stu-id="e17fd-147">How to: Define a Conversion Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
