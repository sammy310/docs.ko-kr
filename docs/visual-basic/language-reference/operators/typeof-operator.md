---
description: '자세한 정보: TypeOf 연산자 (Visual Basic)'
title: TypeOf 연산자
ms.date: 07/20/2015
f1_keywords:
- TypeOf
- vb.TypeOf
helpviewer_keywords:
- types [Visual Basic], compatible
- comparison operators [Visual Basic]
- TypeOf...Is expression
- data types [Visual Basic], compatible
- TypeOf operator [Visual Basic]
- compatible data types [Visual Basic]
ms.assetid: 33f65296-659a-4b9a-9a29-c2a91cff68b2
ms.openlocfilehash: 59a03095b2abbaa304221b30402b9a058954db63
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795237"
---
# <a name="typeof-operator-visual-basic"></a><span data-ttu-id="91b55-103">TypeOf 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="91b55-103">TypeOf Operator (Visual Basic)</span></span>

<span data-ttu-id="91b55-104">식의 결과에 대 한 런타임 형식이 지정 된 형식과 호환 되는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="91b55-104">Checks whether the runtime type of an expression's result is type-compatible with the specified type.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="91b55-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="91b55-105">Syntax</span></span>  
  
```vb  
result = TypeOf objectexpression Is typename  
```  
  
```vb  
result = TypeOf objectexpression IsNot typename  
```  
  
## <a name="parts"></a><span data-ttu-id="91b55-106">부분</span><span class="sxs-lookup"><span data-stu-id="91b55-106">Parts</span></span>  

 `result`  
 <span data-ttu-id="91b55-107">반환됨.</span><span class="sxs-lookup"><span data-stu-id="91b55-107">Returned.</span></span> <span data-ttu-id="91b55-108">`Boolean` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="91b55-108">A `Boolean` value.</span></span>  
  
 `objectexpression`  
 <span data-ttu-id="91b55-109">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="91b55-109">Required.</span></span> <span data-ttu-id="91b55-110">참조 형식으로 계산되는 모든 식입니다.</span><span class="sxs-lookup"><span data-stu-id="91b55-110">Any expression that evaluates to a reference type.</span></span>  
  
 `typename`  
 <span data-ttu-id="91b55-111">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="91b55-111">Required.</span></span> <span data-ttu-id="91b55-112">모든 데이터 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="91b55-112">Any data type name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="91b55-113">설명</span><span class="sxs-lookup"><span data-stu-id="91b55-113">Remarks</span></span>  

 <span data-ttu-id="91b55-114">`TypeOf` 연산자는 `objectexpression`의 런타임 형식이 `typename`과 호환되는지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="91b55-114">The `TypeOf` operator determines whether the run-time type of `objectexpression` is compatible with `typename`.</span></span> <span data-ttu-id="91b55-115">호환성은 `typename`의 형식 범주에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="91b55-115">The compatibility depends on the type category of `typename`.</span></span> <span data-ttu-id="91b55-116">다음 표에서 호환성이 결정되는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="91b55-116">The following table shows how compatibility is determined.</span></span>  
  
|<span data-ttu-id="91b55-117">`typename`의 형식 범주</span><span class="sxs-lookup"><span data-stu-id="91b55-117">Type category of `typename`</span></span>|<span data-ttu-id="91b55-118">호환성 조건</span><span class="sxs-lookup"><span data-stu-id="91b55-118">Compatibility criterion</span></span>|  
|---------------------------------|-----------------------------|  
|<span data-ttu-id="91b55-119">인스턴스</span><span class="sxs-lookup"><span data-stu-id="91b55-119">Class</span></span>|<span data-ttu-id="91b55-120">`objectexpression`이 `typename` 형식이거나 `typename`에서 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="91b55-120">`objectexpression` is of type `typename` or inherits from `typename`</span></span>|  
|<span data-ttu-id="91b55-121">구조체</span><span class="sxs-lookup"><span data-stu-id="91b55-121">Structure</span></span>|<span data-ttu-id="91b55-122">`objectexpression`이 `typename` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="91b55-122">`objectexpression` is of type `typename`</span></span>|  
|<span data-ttu-id="91b55-123">인터페이스</span><span class="sxs-lookup"><span data-stu-id="91b55-123">Interface</span></span>|<span data-ttu-id="91b55-124">`objectexpression`이 `typename`을 구현하거나 `typename`을 구현하는 클래스에서 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="91b55-124">`objectexpression` implements `typename` or inherits from a class that implements `typename`</span></span>|  
  
 <span data-ttu-id="91b55-125">`objectexpression`의 런타임 형식이 호환성 조건을 충족하면 `result`가 `True`이고,</span><span class="sxs-lookup"><span data-stu-id="91b55-125">If the run-time type of `objectexpression` satisfies the compatibility criterion, `result` is `True`.</span></span> <span data-ttu-id="91b55-126">그렇지 않으면 `result`가 `False`입니다.</span><span class="sxs-lookup"><span data-stu-id="91b55-126">Otherwise, `result` is `False`.</span></span>  <span data-ttu-id="91b55-127">`objectexpression`이 null이면 `TypeOf`...`Is`는 `False`를 반환하고 ...`IsNot`은 `True`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="91b55-127">If `objectexpression` is null, then `TypeOf`...`Is` returns `False`, and ...`IsNot` returns `True`.</span></span>  
  
 <span data-ttu-id="91b55-128">`TypeOf`는 항상 `Is` 키워드와 함께 사용되어 `TypeOf`...`Is` 식을 생성하거나 `IsNot` 키워드와 함께 사용되어 `TypeOf`...`IsNot` 식을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="91b55-128">`TypeOf` is always used with the `Is` keyword to construct a `TypeOf`...`Is` expression, or with the `IsNot` keyword to construct a `TypeOf`...`IsNot` expression.</span></span>  
  
## <a name="example"></a><span data-ttu-id="91b55-129">예제</span><span class="sxs-lookup"><span data-stu-id="91b55-129">Example</span></span>  

 <span data-ttu-id="91b55-130">다음 예제에서는 `TypeOf`...`Is` 식을 사용하여 데이터 형식이 다양한 두 개체 참조 변수의 형식 호환성을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="91b55-130">The following example uses `TypeOf`...`Is` expressions to test the type compatibility of two object reference variables with various data types.</span></span>  
  
 [!code-vb[VbVbalrOperators#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#39)]  
  
 <span data-ttu-id="91b55-131">`refInteger` 변수에 `Integer`의 런타임 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91b55-131">The variable `refInteger` has a run-time type of `Integer`.</span></span> <span data-ttu-id="91b55-132">이 변수는 `Integer`와 호환되지만 `Double`과는 호환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="91b55-132">It is compatible with `Integer` but not with `Double`.</span></span> <span data-ttu-id="91b55-133">`refForm` 변수에 <xref:System.Windows.Forms.Form>의 런타임 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91b55-133">The variable `refForm` has a run-time type of <xref:System.Windows.Forms.Form>.</span></span> <span data-ttu-id="91b55-134">이 변수는 해당 형식이기 때문에 <xref:System.Windows.Forms.Form>과 호환되고, <xref:System.Windows.Forms.Form>이 <xref:System.Windows.Forms.Control>에서 상속되기 때문에 <xref:System.Windows.Forms.Control>과 호환되며, <xref:System.Windows.Forms.Form>이 <xref:System.ComponentModel.IComponent>를 구현하는 <xref:System.ComponentModel.Component>에서 상속되기 때문에 <xref:System.ComponentModel.IComponent>와 호환됩니다.</span><span class="sxs-lookup"><span data-stu-id="91b55-134">It is compatible with <xref:System.Windows.Forms.Form> because that is its type, with <xref:System.Windows.Forms.Control> because <xref:System.Windows.Forms.Form> inherits from <xref:System.Windows.Forms.Control>, and with <xref:System.ComponentModel.IComponent> because <xref:System.Windows.Forms.Form> inherits from <xref:System.ComponentModel.Component>, which implements <xref:System.ComponentModel.IComponent>.</span></span> <span data-ttu-id="91b55-135">그러나 `refForm`은 <xref:System.Windows.Forms.Label>과 호환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="91b55-135">However, `refForm` is not compatible with <xref:System.Windows.Forms.Label>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91b55-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="91b55-136">See also</span></span>

- [<span data-ttu-id="91b55-137">Is 연산자</span><span class="sxs-lookup"><span data-stu-id="91b55-137">Is Operator</span></span>](is-operator.md)
- [<span data-ttu-id="91b55-138">IsNot 연산자</span><span class="sxs-lookup"><span data-stu-id="91b55-138">IsNot Operator</span></span>](isnot-operator.md)
- [<span data-ttu-id="91b55-139">Comparison Operators in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="91b55-139">Comparison Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [<span data-ttu-id="91b55-140">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="91b55-140">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="91b55-141">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="91b55-141">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="91b55-142">연산자 및 식</span><span class="sxs-lookup"><span data-stu-id="91b55-142">Operators and Expressions</span></span>](../../programming-guide/language-features/operators-and-expressions/index.md)
