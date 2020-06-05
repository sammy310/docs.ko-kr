---
title: 프로시저 오버로딩
ms.date: 07/20/2015
helpviewer_keywords:
- signatures
- Overloads keyword [Visual Basic]
- hiding by signature
- Visual Basic code, procedures
- procedures [Visual Basic], signatures for
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
- parameters [Visual Basic], lists
- signatures [Visual Basic], procedure
- parameter lists [Visual Basic]
- Visual Basic code, parameter lists
- Shadows keyword [Visual Basic]
- procedure overloading
- procedures [Visual Basic], parameter lists
ms.assetid: fbc7fb18-e3b2-48b6-b554-64c00ed09d2a
ms.openlocfilehash: f8accc74fbdd9b1d8cf9bc3d8f6ddd26f73452b8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84363878"
---
# <a name="procedure-overloading-visual-basic"></a><span data-ttu-id="59c77-102">프로시저 오버로딩(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="59c77-102">Procedure Overloading (Visual Basic)</span></span>

<span data-ttu-id="59c77-103">프로시저를 *오버 로드* 하는 것은 동일한 이름을 사용 하지만 매개 변수 목록을 사용 하 여 여러 버전으로 정의 하는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="59c77-103">*Overloading* a procedure means defining it in multiple versions, using the same name but different parameter lists.</span></span> <span data-ttu-id="59c77-104">오버 로드의 목적은 프로시저를 이름으로 구분 하지 않고도 긴밀 하 게 관련 된 여러 버전을 정의 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="59c77-104">The purpose of overloading is to define several closely related versions of a procedure without having to differentiate them by name.</span></span> <span data-ttu-id="59c77-105">매개 변수 목록을 변경 하 여이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="59c77-105">You do this by varying the parameter list.</span></span>

## <a name="overloading-rules"></a><span data-ttu-id="59c77-106">오버 로드 규칙</span><span class="sxs-lookup"><span data-stu-id="59c77-106">Overloading Rules</span></span>

<span data-ttu-id="59c77-107">프로시저를 오버 로드 하는 경우 다음 규칙이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="59c77-107">When you overload a procedure, the following rules apply:</span></span>

- <span data-ttu-id="59c77-108">**동일한 이름**입니다.</span><span class="sxs-lookup"><span data-stu-id="59c77-108">**Same Name**.</span></span> <span data-ttu-id="59c77-109">오버 로드 된 각 버전은 동일한 프로시저 이름을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="59c77-109">Each overloaded version must use the same procedure name.</span></span>

- <span data-ttu-id="59c77-110">**서명이 다릅니다**.</span><span class="sxs-lookup"><span data-stu-id="59c77-110">**Different Signature**.</span></span> <span data-ttu-id="59c77-111">오버 로드 된 각 버전은 다음 중 하나 이상의 오버 로드 된 버전과 달라 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="59c77-111">Each overloaded version must differ from all other overloaded versions in at least one of the following respects:</span></span>

  - <span data-ttu-id="59c77-112">매개 변수 수</span><span class="sxs-lookup"><span data-stu-id="59c77-112">Number of parameters</span></span>

  - <span data-ttu-id="59c77-113">매개 변수의 순서</span><span class="sxs-lookup"><span data-stu-id="59c77-113">Order of the parameters</span></span>

  - <span data-ttu-id="59c77-114">매개 변수의 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="59c77-114">Data types of the parameters</span></span>

  - <span data-ttu-id="59c77-115">제네릭 프로시저에 대 한 형식 매개 변수 수</span><span class="sxs-lookup"><span data-stu-id="59c77-115">Number of type parameters (for a generic procedure)</span></span>

  - <span data-ttu-id="59c77-116">반환 형식 (변환 연산자의 경우에만)</span><span class="sxs-lookup"><span data-stu-id="59c77-116">Return type (only for a conversion operator)</span></span>

  <span data-ttu-id="59c77-117">프로시저 이름과 함께 위의 항목을 통칭 하 여 프로시저의 *시그니처* 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="59c77-117">Together with the procedure name, the preceding items are collectively called the *signature* of the procedure.</span></span> <span data-ttu-id="59c77-118">오버 로드 된 프로시저를 호출 하면 컴파일러는 서명을 사용 하 여 호출이 정의와 정확히 일치 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="59c77-118">When you call an overloaded procedure, the compiler uses the signature to check that the call correctly matches the definition.</span></span>

- <span data-ttu-id="59c77-119">**항목은 시그니처의 일부가 아닙니다**.</span><span class="sxs-lookup"><span data-stu-id="59c77-119">**Items Not Part of Signature**.</span></span> <span data-ttu-id="59c77-120">시그니처를 변경 하지 않고 프로시저를 오버 로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="59c77-120">You cannot overload a procedure without varying the signature.</span></span> <span data-ttu-id="59c77-121">특히 다음 항목 중 하나 이상을 변경 하 여 프로시저를 오버 로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="59c77-121">In particular, you cannot overload a procedure by varying only one or more of the following items:</span></span>

  - <span data-ttu-id="59c77-122">프로시저 한정자 키워드 (예: `Public` , `Shared` 및)`Static`</span><span class="sxs-lookup"><span data-stu-id="59c77-122">Procedure modifier keywords, such as `Public`, `Shared`, and `Static`</span></span>

  - <span data-ttu-id="59c77-123">매개 변수 또는 형식 매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="59c77-123">Parameter or type parameter names</span></span>

  - <span data-ttu-id="59c77-124">형식 매개 변수 제약 조건 (제네릭 프로시저의 경우)</span><span class="sxs-lookup"><span data-stu-id="59c77-124">Type parameter constraints (for a generic procedure)</span></span>

  - <span data-ttu-id="59c77-125">매개 변수 한정자 키워드 (예: `ByRef` 및)`Optional`</span><span class="sxs-lookup"><span data-stu-id="59c77-125">Parameter modifier keywords, such as `ByRef` and `Optional`</span></span>

  - <span data-ttu-id="59c77-126">값을 반환 하는지 여부</span><span class="sxs-lookup"><span data-stu-id="59c77-126">Whether it returns a value</span></span>

  - <span data-ttu-id="59c77-127">반환 값의 데이터 형식 (변환 연산자 제외)</span><span class="sxs-lookup"><span data-stu-id="59c77-127">The data type of the return value (except for a conversion operator)</span></span>

  <span data-ttu-id="59c77-128">위의 목록에 있는 항목은 시그니처의 일부가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="59c77-128">The items in the preceding list are not part of the signature.</span></span> <span data-ttu-id="59c77-129">오버 로드 된 버전을 구분 하는 데 사용할 수는 없지만 해당 시그니처로 적절히 구분 되는 오버 로드 된 버전 간에는 이러한 버전을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59c77-129">Although you cannot use them to differentiate between overloaded versions, you can vary them among overloaded versions that are properly differentiated by their signatures.</span></span>

- <span data-ttu-id="59c77-130">**런타임에 바인딩된 인수**입니다.</span><span class="sxs-lookup"><span data-stu-id="59c77-130">**Late-Bound Arguments**.</span></span> <span data-ttu-id="59c77-131">런타임에 바인딩된 개체 변수를 오버 로드 된 버전에 전달 하려는 경우에는 적절 한 매개 변수를로 선언 해야 합니다 <xref:System.Object> .</span><span class="sxs-lookup"><span data-stu-id="59c77-131">If you intend to pass a late bound object variable to an overloaded version, you must declare the appropriate parameter as <xref:System.Object>.</span></span>

## <a name="multiple-versions-of-a-procedure"></a><span data-ttu-id="59c77-132">프로시저의 여러 버전</span><span class="sxs-lookup"><span data-stu-id="59c77-132">Multiple Versions of a Procedure</span></span>

<span data-ttu-id="59c77-133">`Sub`고객의 잔액에 대해 트랜잭션을 게시 하는 프로시저를 작성 하는 경우 이름 또는 계정 번호를 기준으로 고객을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59c77-133">Suppose you are writing a `Sub` procedure to post a transaction against a customer's balance, and you want to be able to refer to the customer either by name or by account number.</span></span> <span data-ttu-id="59c77-134">이를 수용 하기 위해 `Sub` 다음 예제와 같이 두 가지 다른 프로시저를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59c77-134">To accommodate this, you can define two different `Sub` procedures, as in the following example:</span></span>

[!code-vb[VbVbcnProcedures#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#73)]

### <a name="overloaded-versions"></a><span data-ttu-id="59c77-135">오버 로드 된 버전</span><span class="sxs-lookup"><span data-stu-id="59c77-135">Overloaded Versions</span></span>

<span data-ttu-id="59c77-136">또 다른 방법은 단일 프로시저 이름을 오버 로드 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="59c77-136">An alternative is to overload a single procedure name.</span></span> <span data-ttu-id="59c77-137">다음과 같이 [Overloads](../../../language-reference/modifiers/overloads.md) 키워드를 사용 하 여 각 매개 변수 목록에 대 한 프로시저의 버전을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59c77-137">You can use the [Overloads](../../../language-reference/modifiers/overloads.md) keyword to define a version of the procedure for each parameter list, as follows:</span></span>

[!code-vb[VbVbcnProcedures#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#72)]

#### <a name="additional-overloads"></a><span data-ttu-id="59c77-138">추가 오버 로드</span><span class="sxs-lookup"><span data-stu-id="59c77-138">Additional Overloads</span></span>

<span data-ttu-id="59c77-139">또는에서 트랜잭션 양을 허용 하려는 경우 `Decimal` `Single` `post` 이 변형에 대해 허용할 추가 오버 로드를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59c77-139">If you also wanted to accept a transaction amount in either `Decimal` or `Single`, you could further overload `post` to allow for this variation.</span></span> <span data-ttu-id="59c77-140">앞의 예제에서 각 오버 로드에 대해이를 수행한 경우 네 가지 `Sub` 절차를 모두 포함 하 고 네 개의 다른 서명을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="59c77-140">If you did this to each of the overloads in the preceding example, you would have four `Sub` procedures, all with the same name but with four different signatures.</span></span>

## <a name="advantages-of-overloading"></a><span data-ttu-id="59c77-141">오버 로드의 이점</span><span class="sxs-lookup"><span data-stu-id="59c77-141">Advantages of Overloading</span></span>

<span data-ttu-id="59c77-142">프로시저 오버 로드의 이점은 호출의 유연성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="59c77-142">The advantage of overloading a procedure is in the flexibility of the call.</span></span> <span data-ttu-id="59c77-143">`post`앞의 예제에서 선언한 프로시저를 사용 하려면 호출 하는 코드에서 또는로 고객 id를 가져온 `String` `Integer` 다음 두 경우 모두 동일한 프로시저를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59c77-143">To use the `post` procedure declared in the preceding example, the calling code can obtain the customer identification as either a `String` or an `Integer`, and then call the same procedure in either case.</span></span> <span data-ttu-id="59c77-144">다음 예제에서는 이에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="59c77-144">The following example illustrates this:</span></span>

[!code-vb[VbVbcnProcedures#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#56)]

[!code-vb[VbVbcnProcedures#57](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#57)]

## <a name="see-also"></a><span data-ttu-id="59c77-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="59c77-145">See also</span></span>

- [<span data-ttu-id="59c77-146">절차</span><span class="sxs-lookup"><span data-stu-id="59c77-146">Procedures</span></span>](./index.md)
- [<span data-ttu-id="59c77-147">방법: 여러 버전의 프로시저 정의</span><span class="sxs-lookup"><span data-stu-id="59c77-147">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="59c77-148">방법: 오버로드된 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="59c77-148">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)
- [<span data-ttu-id="59c77-149">방법: 선택적 매개 변수를 사용하는 프로시저 오버로드</span><span class="sxs-lookup"><span data-stu-id="59c77-149">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [<span data-ttu-id="59c77-150">방법: 매개 변수를 무제한으로 사용하는 프로시저 오버로드</span><span class="sxs-lookup"><span data-stu-id="59c77-150">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [<span data-ttu-id="59c77-151">프로시저 오버로드에서 고려해야 할 사항</span><span class="sxs-lookup"><span data-stu-id="59c77-151">Considerations in Overloading Procedures</span></span>](./considerations-in-overloading-procedures.md)
- [<span data-ttu-id="59c77-152">오버 로드 확인</span><span class="sxs-lookup"><span data-stu-id="59c77-152">Overload Resolution</span></span>](./overload-resolution.md)
- [<span data-ttu-id="59c77-153">오버로드</span><span class="sxs-lookup"><span data-stu-id="59c77-153">Overloads</span></span>](../../../language-reference/modifiers/overloads.md)
- [<span data-ttu-id="59c77-154">Visual Basic의 제네릭 형식</span><span class="sxs-lookup"><span data-stu-id="59c77-154">Generic Types in Visual Basic</span></span>](../data-types/generic-types.md)
