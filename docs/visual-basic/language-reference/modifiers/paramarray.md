---
title: ParamArray
ms.date: 07/20/2015
f1_keywords:
- vb.ParamArray
- ParamArray
helpviewer_keywords:
- ParamArray keyword [Visual Basic]
- ParamArray keyword [Visual Basic], syntax
ms.assetid: a5f18789-92bd-488f-9c7e-cf3719963635
ms.openlocfilehash: baf9303101eea9eed27e8a4eee9e04d255c798e9
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867824"
---
# <a name="paramarray-visual-basic"></a><span data-ttu-id="55615-102">ParamArray(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="55615-102">ParamArray (Visual Basic)</span></span>

<span data-ttu-id="55615-103">프로시저 매개 변수가 지정 된 형식의 선택적 요소 배열을 사용 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="55615-103">Specifies that a procedure parameter takes an optional array of elements of the specified type.</span></span> <span data-ttu-id="55615-104">`ParamArray` 은 매개 변수 목록의 마지막 매개 변수 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55615-104">`ParamArray` can be used only on the last parameter of a parameter list.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="55615-105">설명</span><span class="sxs-lookup"><span data-stu-id="55615-105">Remarks</span></span>  

 <span data-ttu-id="55615-106">`ParamArray` 임의 개수의 인수를 프로시저에 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55615-106">`ParamArray` allows you to pass an arbitrary number of arguments to the procedure.</span></span> <span data-ttu-id="55615-107">`ParamArray` 매개 변수는 항상 [ByVal](byval.md)을 사용하여 선언됩니다.</span><span class="sxs-lookup"><span data-stu-id="55615-107">A `ParamArray` parameter is always declared using [ByVal](byval.md).</span></span>  
  
 <span data-ttu-id="55615-108">`ParamArray`적절 한 데이터 형식의 배열이 나 쉼표로 구분 된 값 목록을 전달 하거나 아무 것도 지정 하지 않으면 매개 변수에 하나 이상의 인수를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55615-108">You can supply one or more arguments to a `ParamArray` parameter by passing an array of the appropriate data type, a comma-separated list of values, or nothing at all.</span></span> <span data-ttu-id="55615-109">자세한 내용은 [매개 변수 배열의](../../programming-guide/language-features/procedures/parameter-arrays.md)"ParamArray 호출"을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="55615-109">For details, see "Calling a ParamArray" in [Parameter Arrays](../../programming-guide/language-features/procedures/parameter-arrays.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="55615-110">무한정 클 수 있는 배열을 처리할 때마다 응용 프로그램의 내부 용량을 overrunning 위험이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55615-110">Whenever you deal with an array which can be indefinitely large, there is a risk of overrunning some internal capacity of your application.</span></span> <span data-ttu-id="55615-111">호출 코드에서 매개 변수 배열을 허용 하는 경우 응용 프로그램에 비해 길이를 테스트 하 고, 응용 프로그램에 적합 한 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55615-111">If you accept a parameter array from the calling code, you should test its length and take appropriate steps if it is too large for your application.</span></span>  
  
 <span data-ttu-id="55615-112">`ParamArray` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55615-112">The `ParamArray` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="55615-113">Declare 문</span><span class="sxs-lookup"><span data-stu-id="55615-113">Declare Statement</span></span>](../statements/declare-statement.md)  
  
 [<span data-ttu-id="55615-114">Function 문</span><span class="sxs-lookup"><span data-stu-id="55615-114">Function Statement</span></span>](../statements/function-statement.md)  
  
 [<span data-ttu-id="55615-115">Property Statement</span><span class="sxs-lookup"><span data-stu-id="55615-115">Property Statement</span></span>](../statements/property-statement.md)  
  
 [<span data-ttu-id="55615-116">Sub 문</span><span class="sxs-lookup"><span data-stu-id="55615-116">Sub Statement</span></span>](../statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="55615-117">참조</span><span class="sxs-lookup"><span data-stu-id="55615-117">See also</span></span>

- [<span data-ttu-id="55615-118">키워드</span><span class="sxs-lookup"><span data-stu-id="55615-118">Keywords</span></span>](../keywords/index.md)
- [<span data-ttu-id="55615-119">매개 변수 배열</span><span class="sxs-lookup"><span data-stu-id="55615-119">Parameter Arrays</span></span>](../../programming-guide/language-features/procedures/parameter-arrays.md)
