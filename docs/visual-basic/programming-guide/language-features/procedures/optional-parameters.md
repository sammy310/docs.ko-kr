---
description: '자세한 정보: 선택적 매개 변수 (Visual Basic)'
title: 선택적 매개 변수
ms.date: 07/20/2015
helpviewer_keywords:
- parameters [Visual Basic], optional
- Visual Basic code, procedures
- procedures [Visual Basic], optional arguments
- optional arguments
- named arguments [Visual Basic], and optional arguments
- optional parameters
- Optional keyword [Visual Basic], optional arguments
- arguments [Visual Basic], optional
- optional arguments [Visual Basic], and named arguments
ms.assetid: 398d2845-1069-4e94-b934-a73b545c8b87
ms.openlocfilehash: 048f940f25fc05a66245e267ff23dc9845fcafdd
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100436138"
---
# <a name="optional-parameters-visual-basic"></a><span data-ttu-id="844da-103">선택적 매개 변수(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="844da-103">Optional Parameters (Visual Basic)</span></span>

<span data-ttu-id="844da-104">프로시저 매개 변수를 선택적 요소로 지정하여 프로시저를 호출할 때 인수를 지정하지 않아도 되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="844da-104">You can specify that a procedure parameter is optional and no argument has to be supplied for it when the procedure is called.</span></span> <span data-ttu-id="844da-105">*선택적 매개 변수* 는 `Optional` 프로시저 정의에서 키워드로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="844da-105">*Optional parameters* are indicated by the `Optional` keyword in the procedure definition.</span></span> <span data-ttu-id="844da-106">다음 규칙이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="844da-106">The following rules apply:</span></span>  
  
- <span data-ttu-id="844da-107">프로시저 정의의 모든 선택적 매개 변수에는 기본값을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="844da-107">Every optional parameter in the procedure definition must specify a default value.</span></span>  
  
- <span data-ttu-id="844da-108">선택적 매개 변수의 기본값은 상수 식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="844da-108">The default value for an optional parameter must be a constant expression.</span></span>  
  
- <span data-ttu-id="844da-109">프로시저 정의에서 선택적 매개 변수 뒤에 오는 매개 변수도 모두 선택적 요소여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="844da-109">Every parameter following an optional parameter in the procedure definition must also be optional.</span></span>  
  
 <span data-ttu-id="844da-110">다음 구문은 선택적 매개 변수를 사용하여 프로시저를 선언하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="844da-110">The following syntax shows a procedure declaration with an optional parameter:</span></span>  
  
```vb  
Sub name(ByVal parameter1 As datatype1, Optional ByVal parameter2 As datatype2 = defaultvalue)  
```  
  
## <a name="calling-procedures-with-optional-parameters"></a><span data-ttu-id="844da-111">선택적 매개 변수가 있는 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="844da-111">Calling Procedures with Optional Parameters</span></span>  

 <span data-ttu-id="844da-112">선택적 매개 변수가 있는 프로시저를 호출하는 경우 해당 인수를 지정할지 여부를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="844da-112">When you call a procedure with an optional parameter, you can choose whether to supply the argument.</span></span> <span data-ttu-id="844da-113">선택하지 않으면 선택적 매개 변수에 대해 선언된 기본값이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="844da-113">If you do not, the procedure uses the default value declared for that parameter.</span></span>  
  
 <span data-ttu-id="844da-114">인수 목록에서 하나 이상의 선택적 인수를 생략하는 경우 그 자리에 쉼표를 사용하여 생략된 위치를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="844da-114">When you omit one or more optional arguments in the argument list, you use successive commas to mark their positions.</span></span> <span data-ttu-id="844da-115">다음 호출 샘플에서는 첫 번째와 네 번째 인수가 제공되고 두 번째와 세 번째 인수는 제공되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="844da-115">The following example call supplies the first and fourth arguments but not the second or third:</span></span>  
  
```vb  
Sub name(argument 1, , , argument 4)  
```  
  
 <span data-ttu-id="844da-116">다음 예제에서는 `MsgBox` 함수를 여러 번 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="844da-116">The following example makes several calls to the `MsgBox` function.</span></span> <span data-ttu-id="844da-117">`MsgBox`에는 필수적 매개 변수 하나와 선택적 매개 변수 두 개가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="844da-117">`MsgBox` has one required parameter and two optional parameters.</span></span>  
  
 <span data-ttu-id="844da-118">`MsgBox`에 대한 첫 번째 호출에서 `MsgBox`에서 정의하는 순서대로 세 개의 인수를 모두 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="844da-118">The first call to `MsgBox` supplies all three arguments in the order that `MsgBox` defines them.</span></span> <span data-ttu-id="844da-119">두 번째 호출에서는 필수적 인수만 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="844da-119">The second call supplies only the required argument.</span></span> <span data-ttu-id="844da-120">세 번째와 네 번째 호출에서는 첫 번째 인수와 세 번째 인수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="844da-120">The third and fourth calls supply the first and third arguments.</span></span> <span data-ttu-id="844da-121">세 번째 호출에서는 위치로 인수를 지정하고, 네 번째 호출에서는 이름으로 인수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="844da-121">The third call does this by position, and the fourth call does it by name.</span></span>  
  
 [!code-vb[VbVbcnProcedures#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#47)]  
  
## <a name="determining-whether-an-optional-argument-is-present"></a><span data-ttu-id="844da-122">선택적 인수의 존재 여부 확인</span><span class="sxs-lookup"><span data-stu-id="844da-122">Determining Whether an Optional Argument Is Present</span></span>  

 <span data-ttu-id="844da-123">프로시저는 지정된 인수가 생략되었는지 또는 호출 코드가 명시적으로 기본값을 제공했는지 여부를 런타임에서 감지할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="844da-123">A procedure cannot detect at run time whether a given argument has been omitted or the calling code has explicitly supplied the default value.</span></span> <span data-ttu-id="844da-124">이를 알아보려면 특이한 값을 기본값으로 설정하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="844da-124">If you need to make this distinction, you can set an unlikely value as the default.</span></span> <span data-ttu-id="844da-125">다음 절차에서는 선택적 매개 변수 `office` 를 정의 하 고, `QJZ` 호출에서이 값이 생략 되었는지 여부를 확인 하기 위해 기본값을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="844da-125">The following procedure defines the optional parameter `office`, and tests for its default value, `QJZ`, to see if it has been omitted in the call:</span></span>  
  
 [!code-vb[VbVbcnProcedures#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#46)]  
  
 <span data-ttu-id="844da-126">선택적 매개 변수가 `String`과 같은 참조 형식일 경우 `Nothing`이 그 인수에 예상된 값이 아니면 이 값을 기본값으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="844da-126">If the optional parameter is a reference type such as a `String`, you can use `Nothing` as the default value, provided this is not an expected value for the argument.</span></span>  
  
## <a name="optional-parameters-and-overloading"></a><span data-ttu-id="844da-127">선택적 매개 변수 및 오버로드</span><span class="sxs-lookup"><span data-stu-id="844da-127">Optional Parameters and Overloading</span></span>  

 <span data-ttu-id="844da-128">선택적 매개 변수가 있는 프로시저를 정의하는 또 다른 방법은 오버로드를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="844da-128">Another way to define a procedure with optional parameters is to use overloading.</span></span> <span data-ttu-id="844da-129">선택적 매개 변수가 하나이면 프로시저의 오버로드된 두 버전을 매개 변수를 사용하는 버전과 매개 변수를 사용하지 않는 버전으로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="844da-129">If you have one optional parameter, you can define two overloaded versions of the procedure, one accepting the parameter and one without it.</span></span> <span data-ttu-id="844da-130">이러한 방식은 선택적 매개 변수의 개수가 증가할수록 더욱 복잡해지지만</span><span class="sxs-lookup"><span data-stu-id="844da-130">This approach becomes more complicated as the number of optional parameters increases.</span></span> <span data-ttu-id="844da-131">호출 프로그램이 각 선택적 인수를 제공했는지 여부를 확실히 알 수 있다는 장점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="844da-131">However, its advantage is that you can be absolutely sure whether the calling program supplied each optional argument.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="844da-132">추가 정보</span><span class="sxs-lookup"><span data-stu-id="844da-132">See also</span></span>

- [<span data-ttu-id="844da-133">절차</span><span class="sxs-lookup"><span data-stu-id="844da-133">Procedures</span></span>](./index.md)
- [<span data-ttu-id="844da-134">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="844da-134">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="844da-135">값 또는 참조로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="844da-135">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="844da-136">위치 및 이름으로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="844da-136">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="844da-137">매개 변수 배열</span><span class="sxs-lookup"><span data-stu-id="844da-137">Parameter Arrays</span></span>](./parameter-arrays.md)
- [<span data-ttu-id="844da-138">프로시저 오버로딩</span><span class="sxs-lookup"><span data-stu-id="844da-138">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="844da-139">선택 사항</span><span class="sxs-lookup"><span data-stu-id="844da-139">Optional</span></span>](../../../language-reference/modifiers/optional.md)
- [<span data-ttu-id="844da-140">ParamArray</span><span class="sxs-lookup"><span data-stu-id="844da-140">ParamArray</span></span>](../../../language-reference/modifiers/paramarray.md)
