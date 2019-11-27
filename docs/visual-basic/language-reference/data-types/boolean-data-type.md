---
title: Boolean 데이터 형식
ms.date: 07/20/2015
f1_keywords:
- vb.FALSE
- vb.TRUE
- vb.Boolean
helpviewer_keywords:
- Boolean data type
- Boolean values [Visual Basic], False keyword
- False keyword [Visual Basic]
- True keyword [Visual Basic]
- Boolean values [Visual Basic], True keyword
ms.assetid: 4858e630-4813-4216-a55e-f4d0feb884e4
ms.openlocfilehash: 5d05514207c5d07e81aab897f40f728570f6bd87
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347844"
---
# <a name="boolean-data-type-visual-basic"></a><span data-ttu-id="e41d4-102">Boolean 데이터 형식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e41d4-102">Boolean Data Type (Visual Basic)</span></span>

<span data-ttu-id="e41d4-103">`True` 또는 `False`만 될 수 있는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="e41d4-103">Holds values that can be only `True` or `False`.</span></span> <span data-ttu-id="e41d4-104">`True` 및 `False` 키워드는 `Boolean` 변수의 두 상태에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="e41d4-104">The keywords `True` and `False` correspond to the two states of `Boolean` variables.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e41d4-105">주의</span><span class="sxs-lookup"><span data-stu-id="e41d4-105">Remarks</span></span>  

 <span data-ttu-id="e41d4-106">[Boolean 데이터 형식 (Visual Basic)](../../../visual-basic/language-reference/data-types/boolean-data-type.md) 을 사용 하 여 true/false, 예/아니요 또는 설정/해제와 같은 두 가지 상태 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="e41d4-106">Use the [Boolean Data Type (Visual Basic)](../../../visual-basic/language-reference/data-types/boolean-data-type.md) to contain two-state values such as true/false, yes/no, or on/off.</span></span>  
  
 <span data-ttu-id="e41d4-107">`Boolean`의 기본값은 `False`입니다.</span><span class="sxs-lookup"><span data-stu-id="e41d4-107">The default value of `Boolean` is `False`.</span></span>  
  
 <span data-ttu-id="e41d4-108">`Boolean` 값은 숫자로 저장 되지 않으며 저장 된 값은 숫자와 동일 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e41d4-108">`Boolean` values are not stored as numbers, and the stored values are not intended to be equivalent to numbers.</span></span> <span data-ttu-id="e41d4-109">`True` 및 `False`에 대해 동일한 숫자 값을 사용 하는 코드를 작성 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e41d4-109">You should never write code that relies on equivalent numeric values for `True` and `False`.</span></span> <span data-ttu-id="e41d4-110">가능 하면 `Boolean` 변수의 사용을 디자인 된 논리 값으로 제한 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e41d4-110">Whenever possible, you should restrict usage of `Boolean` variables to the logical values for which they are designed.</span></span>  
  
## <a name="type-conversions"></a><span data-ttu-id="e41d4-111">형식 변환</span><span class="sxs-lookup"><span data-stu-id="e41d4-111">Type Conversions</span></span>  

 <span data-ttu-id="e41d4-112">Visual Basic 숫자 데이터 형식 값을 `Boolean`변환 하면 0이 `False` 되 고 다른 모든 값은 `True`됩니다.</span><span class="sxs-lookup"><span data-stu-id="e41d4-112">When Visual Basic converts numeric data type values to `Boolean`, 0 becomes `False` and all other values become `True`.</span></span> <span data-ttu-id="e41d4-113">Visual Basic `Boolean` 값을 숫자 형식으로 변환 하는 경우 `False` 0이 되며 `True`는-1이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e41d4-113">When Visual Basic converts `Boolean` values to numeric types, `False` becomes 0 and `True` becomes -1.</span></span>  
  
 <span data-ttu-id="e41d4-114">`Boolean` 값과 숫자 데이터 형식 간에 변환 하는 경우 .NET Framework 변환 메서드는 항상 Visual Basic 변환 키워드와 동일한 결과를 생성 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e41d4-114">When you convert between `Boolean` values and numeric data types, keep in mind that the .NET Framework conversion methods do not always produce the same results as the Visual Basic conversion keywords.</span></span> <span data-ttu-id="e41d4-115">Visual Basic 변환은 이전 버전과 호환 되는 동작을 유지 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="e41d4-115">This is because the Visual Basic conversion retains behavior compatible with previous versions.</span></span> <span data-ttu-id="e41d4-116">자세한 내용은 [데이터 형식 문제 해결](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)의 "부울 형식이 숫자 형식으로 정확 하 게 변환 되지 않습니다."를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e41d4-116">For more information, see "Boolean Type Does Not Convert to Numeric Type Accurately" in [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="e41d4-117">프로그래밍 팁</span><span class="sxs-lookup"><span data-stu-id="e41d4-117">Programming Tips</span></span>  
  
- <span data-ttu-id="e41d4-118">**음수.**</span><span class="sxs-lookup"><span data-stu-id="e41d4-118">**Negative Numbers.**</span></span> <span data-ttu-id="e41d4-119">`Boolean`는 숫자 형식이 아니므로 음수 값을 나타낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e41d4-119">`Boolean` is not a numeric type and cannot represent a negative value.</span></span> <span data-ttu-id="e41d4-120">어떤 경우 든 `Boolean`를 사용 하 여 숫자 값을 저장 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e41d4-120">In any case, you should not use `Boolean` to hold numeric values.</span></span>  
  
- <span data-ttu-id="e41d4-121">**문자를 입력 합니다.**</span><span class="sxs-lookup"><span data-stu-id="e41d4-121">**Type Characters.**</span></span> <span data-ttu-id="e41d4-122">`Boolean`에는 리터럴 형식 문자 또는 식별자 형식 문자가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e41d4-122">`Boolean` has no literal type character or identifier type character.</span></span>  
  
- <span data-ttu-id="e41d4-123">**프레임 워크 형식입니다.**</span><span class="sxs-lookup"><span data-stu-id="e41d4-123">**Framework Type.**</span></span> <span data-ttu-id="e41d4-124">.NET Framework에서 해당하는 형식은 <xref:System.Boolean?displayProperty=nameWithType> 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="e41d4-124">The corresponding type in the .NET Framework is the <xref:System.Boolean?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e41d4-125">예제</span><span class="sxs-lookup"><span data-stu-id="e41d4-125">Example</span></span>  

 <span data-ttu-id="e41d4-126">다음 예제에서 `runningVB`는 간단한 예/아니요 설정을 저장 하는 `Boolean` 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="e41d4-126">In the following example, `runningVB` is a `Boolean` variable, which stores a simple yes/no setting.</span></span>  
  
```vb  
Dim runningVB As Boolean  
' Check to see if program is running on Visual Basic engine.  
If scriptEngine = "VB" Then  
    runningVB = True  
End If  
```  
  
## <a name="see-also"></a><span data-ttu-id="e41d4-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e41d4-127">See also</span></span>

- <xref:System.Boolean?displayProperty=nameWithType>
- [<span data-ttu-id="e41d4-128">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="e41d4-128">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="e41d4-129">CString</span><span class="sxs-lookup"><span data-stu-id="e41d4-129">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="e41d4-130">변환 요약</span><span class="sxs-lookup"><span data-stu-id="e41d4-130">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="e41d4-131">데이터 형식의 효율적 사용</span><span class="sxs-lookup"><span data-stu-id="e41d4-131">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [<span data-ttu-id="e41d4-132">데이터 형식 문제 해결</span><span class="sxs-lookup"><span data-stu-id="e41d4-132">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="e41d4-133">CType Function</span><span class="sxs-lookup"><span data-stu-id="e41d4-133">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)
