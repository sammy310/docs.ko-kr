---
title: Overload Resolution
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- overload resolution
- procedures [Visual Basic], overloading
- procedures [Visual Basic], calling
- procedure overloading [Visual Basic], overload resolution
- signatures [Visual Basic], procedure
- overloads [Visual Basic], resolution
ms.assetid: 766115d1-4352-45fb-859f-6063e0de0ec0
ms.openlocfilehash: bcb99ef3845c1ce3998dc9dc8d9f1d335515c0a9
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84364372"
---
# <a name="overload-resolution-visual-basic"></a><span data-ttu-id="8ba4a-102">오버로드 확인(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8ba4a-102">Overload Resolution (Visual Basic)</span></span>
<span data-ttu-id="8ba4a-103">Visual Basic 컴파일러가 여러 오버 로드 된 버전에 정의 된 프로시저에 대 한 호출을 발견할 경우 컴파일러는 호출할 오버 로드를 결정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ba4a-103">When the Visual Basic compiler encounters a call to a procedure that is defined in several overloaded versions, the compiler must decide which of the overloads to call.</span></span> <span data-ttu-id="8ba4a-104">이렇게 하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ba4a-104">It does this by performing the following steps:</span></span>  
  
1. <span data-ttu-id="8ba4a-105">**내게.**</span><span class="sxs-lookup"><span data-stu-id="8ba4a-105">**Accessibility.**</span></span> <span data-ttu-id="8ba4a-106">호출 코드에서 호출할 수 없도록 하는 액세스 수준으로 오버 로드를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ba4a-106">It eliminates any overload with an access level that prevents the calling code from calling it.</span></span>  
  
2. <span data-ttu-id="8ba4a-107">**매개 변수 수입니다.**</span><span class="sxs-lookup"><span data-stu-id="8ba4a-107">**Number of Parameters.**</span></span> <span data-ttu-id="8ba4a-108">호출에 제공 되는 것과 다른 개수의 매개 변수를 정의 하는 오버 로드를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ba4a-108">It eliminates any overload that defines a different number of parameters than are supplied in the call.</span></span>  
  
3. <span data-ttu-id="8ba4a-109">**매개 변수 데이터 형식입니다.**</span><span class="sxs-lookup"><span data-stu-id="8ba4a-109">**Parameter Data Types.**</span></span> <span data-ttu-id="8ba4a-110">컴파일러는 확장 메서드에 대 한 인스턴스 메서드 기본 설정을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ba4a-110">The compiler gives instance methods preference over extension methods.</span></span> <span data-ttu-id="8ba4a-111">프로시저 호출과 일치 하기 위해 확대 변환만 수행 해야 하는 인스턴스 메서드가 있는 경우 모든 확장 메서드가 삭제 되 고 컴파일러는 인스턴스 메서드 후보로만 계속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ba4a-111">If any instance method is found that requires only widening conversions to match the procedure call, all extension methods are dropped and the compiler continues with only the instance method candidates.</span></span> <span data-ttu-id="8ba4a-112">이러한 인스턴스 메서드를 찾을 수 없으면 인스턴스와 확장 메서드를 모두 사용 하 여 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ba4a-112">If no such instance method is found, it continues with both instance and extension methods.</span></span>  
  
     <span data-ttu-id="8ba4a-113">이 단계에서는 호출 인수의 데이터 형식을 오버 로드에 정의 된 매개 변수 형식으로 변환할 수 없는 오버 로드를 모두 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ba4a-113">In this step, it eliminates any overload for which the data types of the calling arguments cannot be converted to the parameter types defined in the overload.</span></span>  
  
4. <span data-ttu-id="8ba4a-114">**축소 변환.**</span><span class="sxs-lookup"><span data-stu-id="8ba4a-114">**Narrowing Conversions.**</span></span> <span data-ttu-id="8ba4a-115">호출 하는 인수 형식에서 정의 된 매개 변수 형식으로 축소 변환 해야 하는 오버 로드를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ba4a-115">It eliminates any overload that requires a narrowing conversion from the calling argument types to the defined parameter types.</span></span> <span data-ttu-id="8ba4a-116">이는 형식 검사 스위치 ([Option Strict 문](../../../language-reference/statements/option-strict-statement.md))가 또는 인지 여부에 해당 `On` `Off` 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ba4a-116">This is true whether the type checking switch ([Option Strict Statement](../../../language-reference/statements/option-strict-statement.md)) is `On` or `Off`.</span></span>  
  
5. <span data-ttu-id="8ba4a-117">**최소 확대.**</span><span class="sxs-lookup"><span data-stu-id="8ba4a-117">**Least Widening.**</span></span> <span data-ttu-id="8ba4a-118">컴파일러는 나머지 오버 로드를 쌍으로 간주 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ba4a-118">The compiler considers the remaining overloads in pairs.</span></span> <span data-ttu-id="8ba4a-119">각 쌍에 대해 정의 된 매개 변수의 데이터 형식을 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ba4a-119">For each pair, it compares the data types of the defined parameters.</span></span> <span data-ttu-id="8ba4a-120">오버 로드 중 하나의 형식이 다른의 해당 형식으로 확장 되 면 컴파일러는 후자를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ba4a-120">If the types in one of the overloads all widen to the corresponding types in the other, the compiler eliminates the latter.</span></span> <span data-ttu-id="8ba4a-121">즉, 최소한의 확대를 필요로 하는 오버 로드를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ba4a-121">That is, it retains the overload that requires the least amount of widening.</span></span>  
  
6. <span data-ttu-id="8ba4a-122">**단일 후보.**</span><span class="sxs-lookup"><span data-stu-id="8ba4a-122">**Single Candidate.**</span></span> <span data-ttu-id="8ba4a-123">하나의 오버 로드만 유지 되 고 해당 오버 로드에 대 한 호출을 확인 하는 오버 로드를 쌍으로 계속 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ba4a-123">It continues considering overloads in pairs until only one overload remains, and it resolves the call to that overload.</span></span> <span data-ttu-id="8ba4a-124">컴파일러가 오버 로드를 단일 후보로 줄일 수 없는 경우 오류를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ba4a-124">If the compiler cannot reduce the overloads to a single candidate, it generates an error.</span></span>  
  
 <span data-ttu-id="8ba4a-125">다음 그림에서는 호출할 오버 로드 된 버전 집합을 결정 하는 프로세스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8ba4a-125">The following illustration shows the process that determines which of a set of overloaded versions to call.</span></span>  
  
 <span data-ttu-id="8ba4a-126">![오버로드 확인 프로세스의 흐름도](./media/overload-resolution/determine-overloaded-version.gif "오버 로드 된 버전 간 확인")</span><span class="sxs-lookup"><span data-stu-id="8ba4a-126">![Flow diagram of overload resolution process](./media/overload-resolution/determine-overloaded-version.gif "Resolving among overloaded versions")</span></span>
  
 <span data-ttu-id="8ba4a-127">다음 예제에서는이 오버 로드 확인 프로세스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8ba4a-127">The following example illustrates this overload resolution process.</span></span>  
  
 [!code-vb[VbVbcnProcedures#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#62)]  
  
 [!code-vb[VbVbcnProcedures#63](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#63)]  
  
 <span data-ttu-id="8ba4a-128">첫 번째 호출에서 컴파일러는 첫 번째 인수 ()의 형식이 `Short` 해당 매개 변수 ()의 형식으로 축소 되기 때문에 첫 번째 오버 로드를 제거 합니다 `Byte` .</span><span class="sxs-lookup"><span data-stu-id="8ba4a-128">In the first call, the compiler eliminates the first overload because the type of the first argument (`Short`) narrows to the type of the corresponding parameter (`Byte`).</span></span> <span data-ttu-id="8ba4a-129">그런 다음 두 번째 오버 로드 (및)의 각 인수 형식이 세 번째 `Short` 오버 `Single` 로드 (및)에서 해당 형식으로 확대 되기 때문에 세 번째 오버 로드를 제거 합니다 `Integer` `Single` .</span><span class="sxs-lookup"><span data-stu-id="8ba4a-129">It then eliminates the third overload because each argument type in the second overload (`Short` and `Single`) widens to the corresponding type in the third overload (`Integer` and `Single`).</span></span> <span data-ttu-id="8ba4a-130">두 번째 오버 로드는 더 적게 확대 해야 하므로 컴파일러에서 호출에이 오버 로드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ba4a-130">The second overload requires less widening, so the compiler uses it for the call.</span></span>  
  
 <span data-ttu-id="8ba4a-131">두 번째 호출에서 컴파일러는 축소를 기준으로 오버 로드를 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8ba4a-131">In the second call, the compiler cannot eliminate any of the overloads on the basis of narrowing.</span></span> <span data-ttu-id="8ba4a-132">첫 번째 호출에서와 같은 이유로 세 번째 오버 로드를 제거 합니다 .이는 두 번째 오버 로드를 사용 하 여 인수 형식의 확대/축소를 줄일 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="8ba4a-132">It eliminates the third overload for the same reason as in the first call, because it can call the second overload with less widening of the argument types.</span></span> <span data-ttu-id="8ba4a-133">그러나 컴파일러는 첫 번째 및 두 번째 오버 로드 사이를 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8ba4a-133">However, the compiler cannot resolve between the first and second overloads.</span></span> <span data-ttu-id="8ba4a-134">각각에는 다른의 해당 형식으로 확대 되는 하나의 정의 된 매개 변수 형식이 있습니다 ( `Byte` `Short` 에서로 `Single` `Double` ).</span><span class="sxs-lookup"><span data-stu-id="8ba4a-134">Each has one defined parameter type that widens to the corresponding type in the other (`Byte` to `Short`, but `Single` to `Double`).</span></span> <span data-ttu-id="8ba4a-135">따라서 컴파일러는 오버 로드 확인 오류를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ba4a-135">The compiler therefore generates an overload resolution error.</span></span>  
  
## <a name="overloaded-optional-and-paramarray-arguments"></a><span data-ttu-id="8ba4a-136">오버 로드 된 선택적 및 ParamArray 인수</span><span class="sxs-lookup"><span data-stu-id="8ba4a-136">Overloaded Optional and ParamArray Arguments</span></span>  
 <span data-ttu-id="8ba4a-137">프로시저의 두 오버 로드에 동일한 시그니처가 있는 경우, 즉 마지막 매개 변수가 하나에서 [선택적](../../../language-reference/modifiers/optional.md) 으로 선언 되는 경우를 제외 [하 고,](../../../language-reference/modifiers/paramarray.md) 컴파일러는 다음과 같이 해당 프로시저에 대 한 호출을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ba4a-137">If two overloads of a procedure have identical signatures except that the last parameter is declared [Optional](../../../language-reference/modifiers/optional.md) in one and [ParamArray](../../../language-reference/modifiers/paramarray.md) in the other, the compiler resolves a call to that procedure as follows:</span></span>  
  
|<span data-ttu-id="8ba4a-138">호출에서로 마지막 인수를 제공 하는 경우</span><span class="sxs-lookup"><span data-stu-id="8ba4a-138">If the call supplies the last argument as</span></span>|<span data-ttu-id="8ba4a-139">컴파일러는 마지막 인수를로 선언 하는 오버 로드에 대 한 호출을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ba4a-139">The compiler resolves the call to the overload declaring the last argument as</span></span>|  
|---|---|  
|<span data-ttu-id="8ba4a-140">값 없음 (인수 생략)</span><span class="sxs-lookup"><span data-stu-id="8ba4a-140">No value (argument omitted)</span></span>|`Optional`|  
|<span data-ttu-id="8ba4a-141">단일 값</span><span class="sxs-lookup"><span data-stu-id="8ba4a-141">A single value</span></span>|`Optional`|  
|<span data-ttu-id="8ba4a-142">쉼표로 구분 된 목록에 있는 두 개 이상의 값</span><span class="sxs-lookup"><span data-stu-id="8ba4a-142">Two or more values in a comma-separated list</span></span>|`ParamArray`|  
|<span data-ttu-id="8ba4a-143">임의의 길이 (빈 배열 포함)의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="8ba4a-143">An array of any length (including an empty array)</span></span>|`ParamArray`|  
  
## <a name="see-also"></a><span data-ttu-id="8ba4a-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8ba4a-144">See also</span></span>

- [<span data-ttu-id="8ba4a-145">선택적 매개 변수</span><span class="sxs-lookup"><span data-stu-id="8ba4a-145">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="8ba4a-146">매개 변수 배열</span><span class="sxs-lookup"><span data-stu-id="8ba4a-146">Parameter Arrays</span></span>](./parameter-arrays.md)
- [<span data-ttu-id="8ba4a-147">프로시저 오버로딩</span><span class="sxs-lookup"><span data-stu-id="8ba4a-147">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="8ba4a-148">프로시저 문제 해결</span><span class="sxs-lookup"><span data-stu-id="8ba4a-148">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="8ba4a-149">방법: 여러 버전의 프로시저 정의</span><span class="sxs-lookup"><span data-stu-id="8ba4a-149">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="8ba4a-150">방법: 오버로드된 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="8ba4a-150">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)
- [<span data-ttu-id="8ba4a-151">방법: 선택적 매개 변수를 사용하는 프로시저 오버로드</span><span class="sxs-lookup"><span data-stu-id="8ba4a-151">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [<span data-ttu-id="8ba4a-152">방법: 매개 변수를 무제한으로 사용하는 프로시저 오버로드</span><span class="sxs-lookup"><span data-stu-id="8ba4a-152">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [<span data-ttu-id="8ba4a-153">프로시저 오버로드에서 고려해야 할 사항</span><span class="sxs-lookup"><span data-stu-id="8ba4a-153">Considerations in Overloading Procedures</span></span>](./considerations-in-overloading-procedures.md)
- [<span data-ttu-id="8ba4a-154">오버로드</span><span class="sxs-lookup"><span data-stu-id="8ba4a-154">Overloads</span></span>](../../../language-reference/modifiers/overloads.md)
- [<span data-ttu-id="8ba4a-155">확장명 메서드</span><span class="sxs-lookup"><span data-stu-id="8ba4a-155">Extension Methods</span></span>](./extension-methods.md)
