---
title: <proceduresignature1> 오버 로드 하므로 CLS 규격이 아닙니다 <proceduresignature2> 배열 매개 변수 형식의 배열 또는 배열 매개 변수 형식의 차수만에서 달리
ms.date: 07/20/2015
f1_keywords:
- vbc40035
- bc40035
helpviewer_keywords:
- BC40035
ms.assetid: 50a66dbe-2c1e-41bf-96bc-369301c891ac
ms.openlocfilehash: 0bda4ad6a4d5368d93e2ca603b78bf9db6aca858
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61920915"
---
# <a name="proceduresignature1-is-not-cls-compliant-because-it-overloads-proceduresignature2-which-differs-from-it-only-by-array-of-array-parameter-types-or-by-the-rank-of-the-array-parameter-types"></a><span data-ttu-id="47164-102">\<proceduresignature1 > 오버 로드 하므로 CLS 규격이 아닙니다 \<proceduresignature2 > 배열 매개 변수 형식의 배열 또는 배열 매개 변수 형식의 차수만에서 달리</span><span class="sxs-lookup"><span data-stu-id="47164-102">\<proceduresignature1> is not CLS-compliant because it overloads \<proceduresignature2> which differs from it only by array of array parameter types or by the rank of the array parameter types</span></span>
<span data-ttu-id="47164-103">프로시저 또는 속성으로 표시 되어 `<CLSCompliant(True)>` 때 다른 프로시저 또는 속성을 재정의 하 고 해당 매개 변수 목록 간의 유일한 차이점은 가변 배열의 중첩 수준 또는 배열 차수입니다.</span><span class="sxs-lookup"><span data-stu-id="47164-103">A procedure or property is marked as `<CLSCompliant(True)>` when it overrides another procedure or property and the only difference between their parameter lists is the nesting level of a jagged array or the rank of an array.</span></span>  
  
 <span data-ttu-id="47164-104">두 번째 및 세 번째 선언 다음 선언에서이 오류를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="47164-104">In the following declarations, the second and third declarations generate this error.</span></span>  
  
 `Overloads Sub processArray(ByVal arrayParam() As Integer)`  
  
 `Overloads Sub processArray(ByVal arrayParam()() As Integer)`  
  
 `Overloads Sub processArray(ByVal arrayParam(,) As Integer)`  
  
 <span data-ttu-id="47164-105">두 번째 선언에는 1 차원 원래 매개 변수 변경 `arrayParam` 하는 배열로 이루어진 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="47164-105">The second declaration changes the original one-dimensional parameter `arrayParam` to an array of arrays.</span></span> <span data-ttu-id="47164-106">세 번째 선언 변경 `arrayParam` 를 2 차원 배열 (순위 2).</span><span class="sxs-lookup"><span data-stu-id="47164-106">The third declaration changes `arrayParam` to a two-dimensional array (rank 2).</span></span> <span data-ttu-id="47164-107">Visual Basic에 이러한 변경 사항 중 하나에 의해서만 달라 지는 오버 로드를 허용 하는 동안 이러한 오버 로드와 호환 되지 않는 합니다 [Language Independence and Language-independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span><span class="sxs-lookup"><span data-stu-id="47164-107">While Visual Basic allows overloads to differ only by one of these changes, such overloading is not compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span></span>  
  
 <span data-ttu-id="47164-108"><xref:System.CLSCompliantAttribute>를 프로그래밍 요소에 적용하는 경우 특성의 `isCompliant` 매개 변수를 `True` 또는 `False`로 설정하여 준수 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="47164-108">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="47164-109">이 매개 변수에는 기본값이 없으며 값을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47164-109">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="47164-110">요소에 <xref:System.CLSCompliantAttribute> 를 적용하지 않으면 비규격인 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="47164-110">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="47164-111">이 메시지는 기본적으로 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="47164-111">By default, this message is a warning.</span></span> <span data-ttu-id="47164-112">경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="47164-112">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="47164-113">**오류 ID:** BC40035</span><span class="sxs-lookup"><span data-stu-id="47164-113">**Error ID:** BC40035</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="47164-114">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="47164-114">To correct this error</span></span>  
  
-   <span data-ttu-id="47164-115">CLS 규격이 필요 하면,이 도움말 페이지에 언급 된 변경 내용만 보다 많은 방법으로 서로 다를 오버 로드를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="47164-115">If you require CLS compliance, define your overloads to differ from each other in more ways than only the changes cited on this Help page.</span></span>  
  
-   <span data-ttu-id="47164-116">오버 로드 다는 필요한 경우이 도움말에 언급 된 변경에 의해서만 페이지에서 제거 합니다 <xref:System.CLSCompliantAttribute> 해당 정의에서 그대로 표시 또는 `<CLSCompliant(False)>`합니다.</span><span class="sxs-lookup"><span data-stu-id="47164-116">If you require that the overloads differ only by the changes cited on this Help page, remove the <xref:System.CLSCompliantAttribute> from their definitions or mark them as `<CLSCompliant(False)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47164-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="47164-117">See also</span></span>

- [<span data-ttu-id="47164-118">프로시저 오버로딩</span><span class="sxs-lookup"><span data-stu-id="47164-118">Procedure Overloading</span></span>](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)
- [<span data-ttu-id="47164-119">오버로드</span><span class="sxs-lookup"><span data-stu-id="47164-119">Overloads</span></span>](../../../visual-basic/language-reference/modifiers/overloads.md)
