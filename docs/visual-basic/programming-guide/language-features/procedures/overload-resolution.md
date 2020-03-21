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
ms.openlocfilehash: 84d52bbbfb34c2e5d67ed6a1810ab3e32fafda22
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266874"
---
# <a name="overload-resolution-visual-basic"></a><span data-ttu-id="14189-102">오버로드 확인(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="14189-102">Overload Resolution (Visual Basic)</span></span>
<span data-ttu-id="14189-103">Visual Basic 컴파일러가 여러 오버로드된 버전에서 정의된 프로시저에 대한 호출이 발생하면 컴파일러는 호출할 오버로드를 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14189-103">When the Visual Basic compiler encounters a call to a procedure that is defined in several overloaded versions, the compiler must decide which of the overloads to call.</span></span> <span data-ttu-id="14189-104">다음 단계를 수행 하 여이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="14189-104">It does this by performing the following steps:</span></span>  
  
1. <span data-ttu-id="14189-105">**접근성.**</span><span class="sxs-lookup"><span data-stu-id="14189-105">**Accessibility.**</span></span> <span data-ttu-id="14189-106">호출 코드가 호출하지 못하도록 하는 액세스 수준이 있는 오버로드를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="14189-106">It eliminates any overload with an access level that prevents the calling code from calling it.</span></span>  
  
2. <span data-ttu-id="14189-107">**매개 변수 수입니다.**</span><span class="sxs-lookup"><span data-stu-id="14189-107">**Number of Parameters.**</span></span> <span data-ttu-id="14189-108">호출에서 제공되는 것과 다른 수의 매개 변수를 정의하는 오버로드를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="14189-108">It eliminates any overload that defines a different number of parameters than are supplied in the call.</span></span>  
  
3. <span data-ttu-id="14189-109">**매개 변수 데이터 유형입니다.**</span><span class="sxs-lookup"><span data-stu-id="14189-109">**Parameter Data Types.**</span></span> <span data-ttu-id="14189-110">컴파일러는 인스턴스 메서드가 확장 메서드보다 기본 설정을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="14189-110">The compiler gives instance methods preference over extension methods.</span></span> <span data-ttu-id="14189-111">프로시저 호출과 일치하도록 확대 변환만 필요한 인스턴스 메서드가 발견되면 모든 확장 메서드가 삭제되고 컴파일러는 인스턴스 메서드 후보만 으로 계속됩니다.</span><span class="sxs-lookup"><span data-stu-id="14189-111">If any instance method is found that requires only widening conversions to match the procedure call, all extension methods are dropped and the compiler continues with only the instance method candidates.</span></span> <span data-ttu-id="14189-112">이러한 인스턴스 메서드를 찾을 수 없는 경우 인스턴스 및 확장 메서드를 모두 사용 하 고 계속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14189-112">If no such instance method is found, it continues with both instance and extension methods.</span></span>  
  
     <span data-ttu-id="14189-113">이 단계에서는 호출 인수의 데이터 형식을 오버로드에 정의된 매개 변수 유형으로 변환할 수 없는 오버로드를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="14189-113">In this step, it eliminates any overload for which the data types of the calling arguments cannot be converted to the parameter types defined in the overload.</span></span>  
  
4. <span data-ttu-id="14189-114">**전환 범위 축소.**</span><span class="sxs-lookup"><span data-stu-id="14189-114">**Narrowing Conversions.**</span></span> <span data-ttu-id="14189-115">호출 인수 형식에서 정의된 매개 변수 형식으로 의 축소 변환이 필요한 오버로드를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="14189-115">It eliminates any overload that requires a narrowing conversion from the calling argument types to the defined parameter types.</span></span> <span data-ttu-id="14189-116">형식 검사 스위치(옵션 엄격 명령문)가 `On` `Off`있는지 여부에 관계없이 이 사실은 다음과 같은 것입니다.[Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)</span><span class="sxs-lookup"><span data-stu-id="14189-116">This is true whether the type checking switch ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) is `On` or `Off`.</span></span>  
  
5. <span data-ttu-id="14189-117">**최소 확대.**</span><span class="sxs-lookup"><span data-stu-id="14189-117">**Least Widening.**</span></span> <span data-ttu-id="14189-118">컴파일러는 나머지 오버로드를 쌍으로 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="14189-118">The compiler considers the remaining overloads in pairs.</span></span> <span data-ttu-id="14189-119">각 쌍에 대해 정의된 매개 변수의 데이터 형식을 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="14189-119">For each pair, it compares the data types of the defined parameters.</span></span> <span data-ttu-id="14189-120">오버로드 중 하나의 형식이 모두 다른 형식의 해당 형식으로 확대되면 컴파일러는 후자를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="14189-120">If the types in one of the overloads all widen to the corresponding types in the other, the compiler eliminates the latter.</span></span> <span data-ttu-id="14189-121">즉, 최소한의 확대가 필요한 오버로드를 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="14189-121">That is, it retains the overload that requires the least amount of widening.</span></span>  
  
6. <span data-ttu-id="14189-122">**단일 후보.**</span><span class="sxs-lookup"><span data-stu-id="14189-122">**Single Candidate.**</span></span> <span data-ttu-id="14189-123">하나의 오버로드만 남아 있고 해당 오버로드에 대한 호출을 해결할 때까지 쌍으로 오버로드를 계속 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="14189-123">It continues considering overloads in pairs until only one overload remains, and it resolves the call to that overload.</span></span> <span data-ttu-id="14189-124">컴파일러가 단일 후보로 오버로드를 줄일 수 없는 경우 오류가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="14189-124">If the compiler cannot reduce the overloads to a single candidate, it generates an error.</span></span>  
  
 <span data-ttu-id="14189-125">다음 그림에서는 호출할 오버로드된 버전 집합을 결정하는 프로세스를 보여 주며, 이 프로세스를 보여 주시면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14189-125">The following illustration shows the process that determines which of a set of overloaded versions to call.</span></span>  
  
 <span data-ttu-id="14189-126">![오버로드 확인 프로세스의 흐름도](./media/overload-resolution/determine-overloaded-version.gif "오버로드된 버전 간 해결")</span><span class="sxs-lookup"><span data-stu-id="14189-126">![Flow diagram of overload resolution process](./media/overload-resolution/determine-overloaded-version.gif "Resolving among overloaded versions")</span></span>
  
 <span data-ttu-id="14189-127">다음 예제에서는 이 오버로드 해결 프로세스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="14189-127">The following example illustrates this overload resolution process.</span></span>  
  
 [!code-vb[VbVbcnProcedures#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#62)]  
  
 [!code-vb[VbVbcnProcedures#63](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#63)]  
  
 <span data-ttu-id="14189-128">첫 번째 호출에서 컴파일러는 첫 번째 인수 ()`Short`형식이 해당 매개 변수 ()의`Byte`유형으로 좁혀지므로 첫 번째 오버로드를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="14189-128">In the first call, the compiler eliminates the first overload because the type of the first argument (`Short`) narrows to the type of the corresponding parameter (`Byte`).</span></span> <span data-ttu-id="14189-129">그런`Short` 다음 두 번째 오버로드(및)의 `Single`각 인수 유형이 세 번째 오버로드(및)의`Integer` `Single`해당 유형으로 확장되므로 세 번째 오버로드를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="14189-129">It then eliminates the third overload because each argument type in the second overload (`Short` and `Single`) widens to the corresponding type in the third overload (`Integer` and `Single`).</span></span> <span data-ttu-id="14189-130">두 번째 오버로드는 더 적은 확대가 필요하므로 컴파일러는 호출에 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="14189-130">The second overload requires less widening, so the compiler uses it for the call.</span></span>  
  
 <span data-ttu-id="14189-131">두 번째 호출에서 컴파일러는 축소를 기준으로 오버로드를 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="14189-131">In the second call, the compiler cannot eliminate any of the overloads on the basis of narrowing.</span></span> <span data-ttu-id="14189-132">인수 형식의 확대가 적어 두 번째 오버로드를 호출할 수 있기 때문에 첫 번째 호출과 동일한 이유로 세 번째 오버로드를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="14189-132">It eliminates the third overload for the same reason as in the first call, because it can call the second overload with less widening of the argument types.</span></span> <span data-ttu-id="14189-133">그러나 컴파일러는 첫 번째 오버로드와 두 번째 오버로드 사이에서 해결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="14189-133">However, the compiler cannot resolve between the first and second overloads.</span></span> <span data-ttu-id="14189-134">각각에는 다른 형식의 해당 유형으로 확장되는 정의된`Byte` `Short`매개 `Single` 변수 `Double`유형이 하나 있습니다(하지만 )로 확장됩니다.</span><span class="sxs-lookup"><span data-stu-id="14189-134">Each has one defined parameter type that widens to the corresponding type in the other (`Byte` to `Short`, but `Single` to `Double`).</span></span> <span data-ttu-id="14189-135">따라서 컴파일러는 오버로드 확인 오류를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="14189-135">The compiler therefore generates an overload resolution error.</span></span>  
  
## <a name="overloaded-optional-and-paramarray-arguments"></a><span data-ttu-id="14189-136">오버로드된 옵션 및 ParamArray 인수</span><span class="sxs-lookup"><span data-stu-id="14189-136">Overloaded Optional and ParamArray Arguments</span></span>  
 <span data-ttu-id="14189-137">프로시저의 두 오버로드에 마지막 매개 변수가 하나의 [경우 Optional로](../../../../visual-basic/language-reference/modifiers/optional.md) 선언되고 다른 하나는 [ParamArray로](../../../../visual-basic/language-reference/modifiers/paramarray.md) 선언되는 경우 컴파일러는 다음과 같이 해당 프로시저에 대한 호출을 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="14189-137">If two overloads of a procedure have identical signatures except that the last parameter is declared [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) in one and [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) in the other, the compiler resolves a call to that procedure as follows:</span></span>  
  
|<span data-ttu-id="14189-138">호출이 마지막 인수를 다음으로 제공하는 경우</span><span class="sxs-lookup"><span data-stu-id="14189-138">If the call supplies the last argument as</span></span>|<span data-ttu-id="14189-139">컴파일러는 마지막 인수를 선언하는 오버로드에 대한 호출을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="14189-139">The compiler resolves the call to the overload declaring the last argument as</span></span>|  
|---|---|  
|<span data-ttu-id="14189-140">값 없음(인수생략)</span><span class="sxs-lookup"><span data-stu-id="14189-140">No value (argument omitted)</span></span>|`Optional`|  
|<span data-ttu-id="14189-141">단일 값</span><span class="sxs-lookup"><span data-stu-id="14189-141">A single value</span></span>|`Optional`|  
|<span data-ttu-id="14189-142">쉼표로 구분된 목록에서 둘 이상의 값</span><span class="sxs-lookup"><span data-stu-id="14189-142">Two or more values in a comma-separated list</span></span>|`ParamArray`|  
|<span data-ttu-id="14189-143">모든 길이의 배열(빈 배열 포함)</span><span class="sxs-lookup"><span data-stu-id="14189-143">An array of any length (including an empty array)</span></span>|`ParamArray`|  
  
## <a name="see-also"></a><span data-ttu-id="14189-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="14189-144">See also</span></span>

- [<span data-ttu-id="14189-145">선택적 매개 변수</span><span class="sxs-lookup"><span data-stu-id="14189-145">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="14189-146">매개 변수 배열</span><span class="sxs-lookup"><span data-stu-id="14189-146">Parameter Arrays</span></span>](./parameter-arrays.md)
- [<span data-ttu-id="14189-147">프로시저 오버로딩</span><span class="sxs-lookup"><span data-stu-id="14189-147">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="14189-148">프로시저 문제 해결</span><span class="sxs-lookup"><span data-stu-id="14189-148">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="14189-149">방법: 여러 버전의 프로시저 정의</span><span class="sxs-lookup"><span data-stu-id="14189-149">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="14189-150">방법: 오버로드된 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="14189-150">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)
- [<span data-ttu-id="14189-151">방법: 선택적 매개 변수를 사용하는 프로시저 오버로드</span><span class="sxs-lookup"><span data-stu-id="14189-151">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [<span data-ttu-id="14189-152">방법: 매개 변수를 무제한으로 사용하는 프로시저 오버로드</span><span class="sxs-lookup"><span data-stu-id="14189-152">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [<span data-ttu-id="14189-153">프로시저를 오버로드할 때 고려해야 할 사항</span><span class="sxs-lookup"><span data-stu-id="14189-153">Considerations in Overloading Procedures</span></span>](./considerations-in-overloading-procedures.md)
- [<span data-ttu-id="14189-154">오버 로드</span><span class="sxs-lookup"><span data-stu-id="14189-154">Overloads</span></span>](../../../../visual-basic/language-reference/modifiers/overloads.md)
- [<span data-ttu-id="14189-155">확장 메서드</span><span class="sxs-lookup"><span data-stu-id="14189-155">Extension Methods</span></span>](./extension-methods.md)
