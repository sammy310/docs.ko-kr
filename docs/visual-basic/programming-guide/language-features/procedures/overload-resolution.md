---
title: 오버로드 확인(Visual Basic)
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
ms.openlocfilehash: e7a05a5fb0b2053e92d9f947f197bdb2dcfa7ce0
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58832283"
---
# <a name="overload-resolution-visual-basic"></a><span data-ttu-id="c8080-102">오버로드 확인(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c8080-102">Overload Resolution (Visual Basic)</span></span>
<span data-ttu-id="c8080-103">Visual Basic 컴파일러는 여러 오버 로드 된 버전에 정의 된 프로시저 호출을 발견 하면, 오버 로드를 호출 하는 결정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8080-103">When the Visual Basic compiler encounters a call to a procedure that is defined in several overloaded versions, the compiler must decide which of the overloads to call.</span></span> <span data-ttu-id="c8080-104">다음 단계를 수행 하 여 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8080-104">It does this by performing the following steps:</span></span>  
  
1.  <span data-ttu-id="c8080-105">**접근성.**</span><span class="sxs-lookup"><span data-stu-id="c8080-105">**Accessibility.**</span></span> <span data-ttu-id="c8080-106">호출 코드를 호출 하지 못하도록 제한 하는 액세스 수준 가진 오버 로드 모두 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8080-106">It eliminates any overload with an access level that prevents the calling code from calling it.</span></span>  
  
2.  <span data-ttu-id="c8080-107">**매개 변수 개수입니다.**</span><span class="sxs-lookup"><span data-stu-id="c8080-107">**Number of Parameters.**</span></span> <span data-ttu-id="c8080-108">호출에서 제공 하는 다른 개수의 매개 변수를 정의 하는 오버 로드 모두 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8080-108">It eliminates any overload that defines a different number of parameters than are supplied in the call.</span></span>  
  
3.  <span data-ttu-id="c8080-109">**매개 변수 데이터 형식입니다.**</span><span class="sxs-lookup"><span data-stu-id="c8080-109">**Parameter Data Types.**</span></span> <span data-ttu-id="c8080-110">컴파일러는 확장 방법에 대 한 기본 설정 인스턴스 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c8080-110">The compiler gives instance methods preference over extension methods.</span></span> <span data-ttu-id="c8080-111">만 확장 프로시저 호출에 맞게 변환 해야 하는 모든 인스턴스 메서드가 있으면 모든 확장 메서드를 삭제 하 고 컴파일러 인스턴스 메서드 후보만를 사용 하 여 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8080-111">If any instance method is found that requires only widening conversions to match the procedure call, all extension methods are dropped and the compiler continues with only the instance method candidates.</span></span> <span data-ttu-id="c8080-112">이러한 인스턴스 메서드가 있으면 인스턴스와 확장 메서드를 사용 하 여 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8080-112">If no such instance method is found, it continues with both instance and extension methods.</span></span>  
  
     <span data-ttu-id="c8080-113">이 단계에서는 오버 로드는 데이터 형식의 호출 인수 오버 로드에 정의 된 매개 변수 형식으로 변환 없습니다 모두 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8080-113">In this step, it eliminates any overload for which the data types of the calling arguments cannot be converted to the parameter types defined in the overload.</span></span>  
  
4.  <span data-ttu-id="c8080-114">**축소 변환입니다.**</span><span class="sxs-lookup"><span data-stu-id="c8080-114">**Narrowing Conversions.**</span></span> <span data-ttu-id="c8080-115">호출 인수 형식에서 정의 된 매개 변수 형식 축소 변환 되어야 하는 오버 로드 모두 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8080-115">It eliminates any overload that requires a narrowing conversion from the calling argument types to the defined parameter types.</span></span> <span data-ttu-id="c8080-116">이것이 사실이 여부 형식 검사 스위치 ([Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md))은 `On` 또는 `Off`합니다.</span><span class="sxs-lookup"><span data-stu-id="c8080-116">This is true whether the type checking switch ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) is `On` or `Off`.</span></span>  
  
5.  <span data-ttu-id="c8080-117">**최소 확대 합니다.**</span><span class="sxs-lookup"><span data-stu-id="c8080-117">**Least Widening.**</span></span> <span data-ttu-id="c8080-118">컴파일러는 쌍에는 나머지 오버 로드를 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="c8080-118">The compiler considers the remaining overloads in pairs.</span></span> <span data-ttu-id="c8080-119">각 쌍에 대해 정의 된 매개 변수의 데이터 형식을 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8080-119">For each pair, it compares the data types of the defined parameters.</span></span> <span data-ttu-id="c8080-120">다른의 해당 형식으로 모든 오버 로드 중 하나에서 형식을 확대 변환, 컴파일러는 후자를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8080-120">If the types in one of the overloads all widen to the corresponding types in the other, the compiler eliminates the latter.</span></span> <span data-ttu-id="c8080-121">즉, 최소한의 확대 되는 오버 로드를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8080-121">That is, it retains the overload that requires the least amount of widening.</span></span>  
  
6.  <span data-ttu-id="c8080-122">**단일 후보입니다.**</span><span class="sxs-lookup"><span data-stu-id="c8080-122">**Single Candidate.**</span></span> <span data-ttu-id="c8080-123">오버 로드를 쌍 하나만 남을 때까지 유지 오버 로드 하 고 해당 오버 로드에 대 한 호출을 확인 고려할 때 계속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8080-123">It continues considering overloads in pairs until only one overload remains, and it resolves the call to that overload.</span></span> <span data-ttu-id="c8080-124">컴파일러는 단일 후보 오버 로드를 줄일 수 없습니다, 하는 경우 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8080-124">If the compiler cannot reduce the overloads to a single candidate, it generates an error.</span></span>  
  
 <span data-ttu-id="c8080-125">다음 그림에서는 호출 오버 로드 된 버전 집합을 결정 하는 프로세스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c8080-125">The following illustration shows the process that determines which of a set of overloaded versions to call.</span></span>  
  
 <span data-ttu-id="c8080-126">![오버 로드 확인 프로세스의 흐름도](./media/overload-resolution/determine-overloaded-version.gif "오버 로드 버전에서 해결")</span><span class="sxs-lookup"><span data-stu-id="c8080-126">![Flow diagram of overload resolution process](./media/overload-resolution/determine-overloaded-version.gif "Resolving among overloaded versions")</span></span>    
  
 <span data-ttu-id="c8080-127">다음 예제에서는이 오버 로드 확인 프로세스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c8080-127">The following example illustrates this overload resolution process.</span></span>  
  
 [!code-vb[VbVbcnProcedures#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#62)]  
  
 [!code-vb[VbVbcnProcedures#63](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#63)]  
  
 <span data-ttu-id="c8080-128">첫 번째 호출에서 컴파일러 첫 번째 오버 로드를 제거 하기 때문에 첫 번째 인수의 형식 (`Short`) 해당 매개 변수의 형식으로 축소 변환 (`Byte`).</span><span class="sxs-lookup"><span data-stu-id="c8080-128">In the first call, the compiler eliminates the first overload because the type of the first argument (`Short`) narrows to the type of the corresponding parameter (`Byte`).</span></span> <span data-ttu-id="c8080-129">두 번째 오버 로드의 각 인수 형식 때문에 다음 세 번째 오버 로드를 제거 (`Short` 하 고 `Single`) 세 번째 오버 로드에서 해당 형식으로 확장 되는지를 (`Integer` 고 `Single`).</span><span class="sxs-lookup"><span data-stu-id="c8080-129">It then eliminates the third overload because each argument type in the second overload (`Short` and `Single`) widens to the corresponding type in the third overload (`Integer` and `Single`).</span></span> <span data-ttu-id="c8080-130">두 번째 오버 로드를 컴파일러 호출에 사용 되므로 적은 확대 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8080-130">The second overload requires less widening, so the compiler uses it for the call.</span></span>  
  
 <span data-ttu-id="c8080-131">두 번째 호출에서 컴파일러 축소를 기준으로 오버 로드를 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c8080-131">In the second call, the compiler cannot eliminate any of the overloads on the basis of narrowing.</span></span> <span data-ttu-id="c8080-132">작은 확대 인수 형식의 두 번째 오버 로드를 호출할 수 있으므로 첫 번째 호출에서와 같이 동일한 이유로 세 번째 오버 로드를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8080-132">It eliminates the third overload for the same reason as in the first call, because it can call the second overload with less widening of the argument types.</span></span> <span data-ttu-id="c8080-133">그러나 컴파일러는 첫 번째와 두 번째 오버 로드 간의 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c8080-133">However, the compiler cannot resolve between the first and second overloads.</span></span> <span data-ttu-id="c8080-134">다른 해당 형식으로 확대 되는 하나의 정의 된 매개 변수 형식에 각 (`Byte` 하 `Short`, 되지만 `Single` 를 `Double`).</span><span class="sxs-lookup"><span data-stu-id="c8080-134">Each has one defined parameter type that widens to the corresponding type in the other (`Byte` to `Short`, but `Single` to `Double`).</span></span> <span data-ttu-id="c8080-135">따라서 컴파일러는 오버 로드 확인 오류를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="c8080-135">The compiler therefore generates an overload resolution error.</span></span>  
  
## <a name="overloaded-optional-and-paramarray-arguments"></a><span data-ttu-id="c8080-136">선택적 오버 로드 및 ParamArray 인수</span><span class="sxs-lookup"><span data-stu-id="c8080-136">Overloaded Optional and ParamArray Arguments</span></span>  
 <span data-ttu-id="c8080-137">마지막 매개 변수가 선언 된 점을 제외 하 고 프로시저의 두 오버 로드 시그니처가 동일한 경우 [선택 사항](../../../../visual-basic/language-reference/modifiers/optional.md) 하나로 및 [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) 다른 컴파일러는 해당 프로시저에 대 한 호출 확인 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c8080-137">If two overloads of a procedure have identical signatures except that the last parameter is declared [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) in one and [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) in the other, the compiler resolves a call to that procedure as follows:</span></span>  
  
|<span data-ttu-id="c8080-138">호출으로 마지막 인수를 제공 하는 경우</span><span class="sxs-lookup"><span data-stu-id="c8080-138">If the call supplies the last argument as</span></span>|<span data-ttu-id="c8080-139">컴파일러와 마지막 인수를 선언 하는 오버 로드에 대 한 호출을 확인</span><span class="sxs-lookup"><span data-stu-id="c8080-139">The compiler resolves the call to the overload declaring the last argument as</span></span>|  
|---|---|  
|<span data-ttu-id="c8080-140">값 없음 (인수를 생략)</span><span class="sxs-lookup"><span data-stu-id="c8080-140">No value (argument omitted)</span></span>|`Optional`|  
|<span data-ttu-id="c8080-141">단일 값</span><span class="sxs-lookup"><span data-stu-id="c8080-141">A single value</span></span>|`Optional`|  
|<span data-ttu-id="c8080-142">쉼표로 구분 된 목록에서 두 개 이상 값</span><span class="sxs-lookup"><span data-stu-id="c8080-142">Two or more values in a comma-separated list</span></span>|`ParamArray`|  
|<span data-ttu-id="c8080-143">빈 배열을 등 임의 길이의 배열</span><span class="sxs-lookup"><span data-stu-id="c8080-143">An array of any length (including an empty array)</span></span>|`ParamArray`|  
  
## <a name="see-also"></a><span data-ttu-id="c8080-144">참고자료</span><span class="sxs-lookup"><span data-stu-id="c8080-144">See also</span></span>

- [<span data-ttu-id="c8080-145">선택적 매개 변수</span><span class="sxs-lookup"><span data-stu-id="c8080-145">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="c8080-146">매개 변수 배열</span><span class="sxs-lookup"><span data-stu-id="c8080-146">Parameter Arrays</span></span>](./parameter-arrays.md)
- [<span data-ttu-id="c8080-147">프로시저 오버로딩</span><span class="sxs-lookup"><span data-stu-id="c8080-147">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="c8080-148">프로시저 문제 해결</span><span class="sxs-lookup"><span data-stu-id="c8080-148">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="c8080-149">방법: 여러 버전의 프로시저 정의</span><span class="sxs-lookup"><span data-stu-id="c8080-149">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="c8080-150">방법: 오버 로드 된 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="c8080-150">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)
- [<span data-ttu-id="c8080-151">방법: 선택적 매개 변수를 사용 하는 프로시저 오버 로드</span><span class="sxs-lookup"><span data-stu-id="c8080-151">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [<span data-ttu-id="c8080-152">방법: 무한 개수의 매개 변수를 사용 하는 프로시저 오버 로드</span><span class="sxs-lookup"><span data-stu-id="c8080-152">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [<span data-ttu-id="c8080-153">프로시저를 오버로드할 때 고려해야 할 사항</span><span class="sxs-lookup"><span data-stu-id="c8080-153">Considerations in Overloading Procedures</span></span>](./considerations-in-overloading-procedures.md)
- [<span data-ttu-id="c8080-154">오버로드</span><span class="sxs-lookup"><span data-stu-id="c8080-154">Overloads</span></span>](../../../../visual-basic/language-reference/modifiers/overloads.md)
- [<span data-ttu-id="c8080-155">확장명 메서드</span><span class="sxs-lookup"><span data-stu-id="c8080-155">Extension Methods</span></span>](./extension-methods.md)
