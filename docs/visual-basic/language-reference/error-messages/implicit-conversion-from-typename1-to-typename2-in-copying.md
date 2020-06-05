---
title: ByRef' 매개 변수 '<typename1>'의 값을 해당 인수에 다시 복사하는 동안 발생하는 '<typename2>'에서 '<parametername>'(으)로의 암시적 변환입니다.
ms.date: 07/20/2015
f1_keywords:
- vbc41999
- bc41999
helpviewer_keywords:
- BC41999
ms.assetid: ae48c738-dff8-4c0f-8931-bbb70b2c8b03
ms.openlocfilehash: 4d0f9aac795f683cf58210ea38b3783e451ccfc3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402864"
---
# <a name="implicit-conversion-from-typename1-to-typename2-in-copying-the-value-of-byref-parameter-parametername-back-to-the-matching-argument"></a><span data-ttu-id="bef1f-102">ByRef' 매개 변수 '\<typename1>'의 값을 해당 인수에 다시 복사하는 동안 발생하는 '\<typename2>'에서 '\<parametername>'(으)로의 암시적 변환입니다.</span><span class="sxs-lookup"><span data-stu-id="bef1f-102">Implicit conversion from '\<typename1>' to '\<typename2>' in copying the value of 'ByRef' parameter '\<parametername>' back to the matching argument.</span></span>
<span data-ttu-id="bef1f-103">해당 매개 변수와 다른 형식의 [ByRef](../modifiers/byref.md) 인수를 사용 하 여 프로시저를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef1f-103">A procedure is called with a [ByRef](../modifiers/byref.md) argument of a different type than that of its corresponding parameter.</span></span>  
  
 <span data-ttu-id="bef1f-104">인수를 전달 하는 경우 Visual Basic는 경우 `ByRef` 에 따라 참조를 전달 하는 대신 프로시저의 지역 변수에 인수 값을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef1f-104">If you pass an argument `ByRef`, Visual Basic sometimes copies the argument value into a local variable in the procedure instead of passing a reference.</span></span> <span data-ttu-id="bef1f-105">이 경우 프로시저가 반환 될 때 Visual Basic는 지역 변수 값을 호출 코드의 인수에 다시 복사 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef1f-105">In such a case, when the procedure returns, Visual Basic must then copy the local variable value back into the argument in the calling code.</span></span>  
  
 <span data-ttu-id="bef1f-106">`ByRef` 인수 값이 프로시저에 복사되고 인수 및 매개 변수가 동일한 형식인 경우에는 변환이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bef1f-106">If a `ByRef` argument value is copied into the procedure and the argument and parameter are of the same type, no conversion is necessary.</span></span> <span data-ttu-id="bef1f-107">그러나 형식이 서로 다르면 Visual Basic 양방향으로 변환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef1f-107">But if the types are different, Visual Basic must convert in both directions.</span></span> <span data-ttu-id="bef1f-108">`CType`프로시저 인수나 매개 변수에서 또는 다른 변환 키워드를 사용할 수 없기 때문에 이러한 변환은 항상 암시적입니다.</span><span class="sxs-lookup"><span data-stu-id="bef1f-108">Because you cannot use `CType` or any of the other conversion keywords on a procedure argument or parameter, such a conversion is always implicit.</span></span>  
  
 <span data-ttu-id="bef1f-109">이 메시지는 기본적으로 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="bef1f-109">By default, this message is a warning.</span></span> <span data-ttu-id="bef1f-110">경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bef1f-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="bef1f-111">**오류 ID:** BC41999</span><span class="sxs-lookup"><span data-stu-id="bef1f-111">**Error ID:** BC41999</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="bef1f-112">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="bef1f-112">To correct this error</span></span>  
  
- <span data-ttu-id="bef1f-113">가능 하면 프로시저 매개 변수와 동일한 형식의 호출 인수를 사용 하므로 Visual Basic는 변환을 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bef1f-113">If possible, use a calling argument of the same type as the procedure parameter, so Visual Basic does not need to do any conversion.</span></span>  
  
- <span data-ttu-id="bef1f-114">매개 변수 형식과 다른 인수 형식을 사용하여 프로시저를 호출해야 하지만 호출 인수에 값을 반환할 필요가 없는 경우 매개 변수를 [ByRef](../modifiers/byval.md) 가 아니라 `ByRef`로 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="bef1f-114">If you need to call the procedure with an argument type different from the parameter type but do not need to return a value into the calling argument, define the parameter to be [ByVal](../modifiers/byval.md) instead of `ByRef`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bef1f-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bef1f-115">See also</span></span>

- [<span data-ttu-id="bef1f-116">절차</span><span class="sxs-lookup"><span data-stu-id="bef1f-116">Procedures</span></span>](../../programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="bef1f-117">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="bef1f-117">Procedure Parameters and Arguments</span></span>](../../programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)
- [<span data-ttu-id="bef1f-118">값 또는 참조로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="bef1f-118">Passing Arguments by Value and by Reference</span></span>](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="bef1f-119">암시적 변환과 명시적 변환</span><span class="sxs-lookup"><span data-stu-id="bef1f-119">Implicit and Explicit Conversions</span></span>](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
