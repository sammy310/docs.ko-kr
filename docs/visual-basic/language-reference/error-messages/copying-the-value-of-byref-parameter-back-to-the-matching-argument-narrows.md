---
description: "자세한 정보: BC32053: ' ByRef ' 매개 변수 ' '의 값을 <parametername> 일치 하는 인수에 다시 복사 ' '에서 ' <typename1> ' 형식으로 축소<typename2>"
title: ByRef' 매개 변수 '<parametername>'의 값을 해당 인수에 다시 복사하면 '<typename1>' 형식에서 '<typename2>' 형식으로 축소 변환됩니다.
ms.date: 07/20/2015
f1_keywords:
- bc32053
- vbc32053
helpviewer_keywords:
- BC32053
ms.assetid: 281564b7-99f7-451f-b10d-f985e831bb25
ms.openlocfilehash: a90e64cd81443831a7b8f934fea646411eb5a220
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796706"
---
# <a name="bc32053-copying-the-value-of-byref-parameter-parametername-back-to-the-matching-argument-narrows-from-type-typename1-to-type-typename2"></a><span data-ttu-id="d98ad-103">BC32053: ' ByRef ' 매개 변수 ' '의 값을 일치 하는 \<parametername> 인수에 다시 복사 하면 ' \<typename1> ' 형식에서 ' ' 형식으로 축소 변환 됩니다. \<typename2></span><span class="sxs-lookup"><span data-stu-id="d98ad-103">BC32053: Copying the value of 'ByRef' parameter '\<parametername>' back to the matching argument narrows from type '\<typename1>' to type '\<typename2>'</span></span>

<span data-ttu-id="d98ad-104">해당 매개 변수 형식으로 확대 되는 인수를 사용 하 여 프로시저를 호출 하 고 매개 변수에서 인수로 변환 하는 것은 축소입니다.</span><span class="sxs-lookup"><span data-stu-id="d98ad-104">A procedure is called with an argument that widens to the corresponding parameter type, and the conversion from the parameter to the argument is narrowing.</span></span>

 <span data-ttu-id="d98ad-105">클래스 또는 구조체를 정의하는 경우 해당 클래스 또는 구조체 형식을 다른 형식으로 변환하는 변환 연산자를 하나 이상 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d98ad-105">When you define a class or structure, you can define one or more conversion operators to convert that class or structure type to other types.</span></span> <span data-ttu-id="d98ad-106">다른 형식을 클래스 또는 구조체 형식으로 다시 변환하는 역방향 변환 연산자를 정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d98ad-106">You can also define reverse conversion operators to convert those other types back to your class or structure type.</span></span> <span data-ttu-id="d98ad-107">프로시저 호출에서 클래스 또는 구조체 형식을 사용 하는 경우 이러한 변환 연산자를 사용 하 여 인수 형식을 해당 매개 변수의 형식으로 변환할 수 Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d98ad-107">When you use your class or structure type in a procedure call, Visual Basic can use these conversion operators to convert the type of an argument to the type of its corresponding parameter.</span></span>

 <span data-ttu-id="d98ad-108">[ByRef](../modifiers/byref.md)인수를 전달 하는 경우 Visual Basic는 경우에 따라 참조를 전달 하는 대신 프로시저의 지역 변수에 인수 값을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="d98ad-108">If you pass the argument [ByRef](../modifiers/byref.md), Visual Basic sometimes copies the argument value into a local variable in the procedure instead of passing a reference.</span></span> <span data-ttu-id="d98ad-109">이 경우 프로시저가 반환 될 때 Visual Basic는 지역 변수 값을 호출 코드의 인수에 다시 복사 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d98ad-109">In such a case, when the procedure returns, Visual Basic must then copy the local variable value back into the argument in the calling code.</span></span>

 <span data-ttu-id="d98ad-110">`ByRef` 인수 값이 프로시저에 복사되고 인수 및 매개 변수가 동일한 형식인 경우에는 변환이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d98ad-110">If a `ByRef` argument value is copied into the procedure and the argument and parameter are of the same type, no conversion is necessary.</span></span> <span data-ttu-id="d98ad-111">그러나 형식이 서로 다르면 Visual Basic 양방향으로 변환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d98ad-111">But if the types are different, Visual Basic must convert in both directions.</span></span> <span data-ttu-id="d98ad-112">형식 중 하나가 클래스 또는 구조체 형식이 면 Visual Basic 다른 형식으로 변환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d98ad-112">If one of the types is your class or structure type, Visual Basic must convert it both to and from the other type.</span></span> <span data-ttu-id="d98ad-113">이러한 변환 중 하나가 확대 되는 경우 역방향 변환은 축소 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d98ad-113">If one of these conversions is widening, the reverse conversion might be narrowing.</span></span>

 <span data-ttu-id="d98ad-114">**오류 ID:** BC32053</span><span class="sxs-lookup"><span data-stu-id="d98ad-114">**Error ID:** BC32053</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="d98ad-115">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="d98ad-115">To correct this error</span></span>

- <span data-ttu-id="d98ad-116">가능 하면 프로시저 매개 변수와 동일한 형식의 호출 인수를 사용 하므로 Visual Basic는 변환을 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d98ad-116">If possible, use a calling argument of the same type as the procedure parameter, so Visual Basic does not need to do any conversion.</span></span>

- <span data-ttu-id="d98ad-117">매개 변수 형식과 다른 인수 형식을 사용하여 프로시저를 호출해야 하지만 호출 인수에 값을 반환할 필요가 없는 경우 매개 변수를 [ByRef](../modifiers/byval.md) 가 아니라 `ByRef`로 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d98ad-117">If you need to call the procedure with an argument type different from the parameter type but do not need to return a value into the calling argument, define the parameter to be [ByVal](../modifiers/byval.md) instead of `ByRef`.</span></span>

- <span data-ttu-id="d98ad-118">호출 인수에 값을 반환 해야 하는 경우 가능한 경우 역방향 변환 연산자를 [확대](../modifiers/widening.md)로 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="d98ad-118">If you need to return a value into the calling argument, define the reverse conversion operator as [Widening](../modifiers/widening.md), if possible.</span></span>

## <a name="see-also"></a><span data-ttu-id="d98ad-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d98ad-119">See also</span></span>

- [<span data-ttu-id="d98ad-120">절차</span><span class="sxs-lookup"><span data-stu-id="d98ad-120">Procedures</span></span>](../../programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="d98ad-121">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="d98ad-121">Procedure Parameters and Arguments</span></span>](../../programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)
- [<span data-ttu-id="d98ad-122">값 또는 참조로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="d98ad-122">Passing Arguments by Value and by Reference</span></span>](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="d98ad-123">연산자 프로시저</span><span class="sxs-lookup"><span data-stu-id="d98ad-123">Operator Procedures</span></span>](../../programming-guide/language-features/procedures/operator-procedures.md)
- [<span data-ttu-id="d98ad-124">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="d98ad-124">Operator Statement</span></span>](../statements/operator-statement.md)
- [<span data-ttu-id="d98ad-125">방법: 연산자 정의</span><span class="sxs-lookup"><span data-stu-id="d98ad-125">How to: Define an Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="d98ad-126">방법: 변환 연산자 정의</span><span class="sxs-lookup"><span data-stu-id="d98ad-126">How to: Define a Conversion Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="d98ad-127">Visual Basic의 형식 변환</span><span class="sxs-lookup"><span data-stu-id="d98ad-127">Type Conversions in Visual Basic</span></span>](../../programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="d98ad-128">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="d98ad-128">Widening and Narrowing Conversions</span></span>](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
