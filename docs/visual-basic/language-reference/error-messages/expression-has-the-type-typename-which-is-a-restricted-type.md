---
description: "자세한 정보: BC31393: Expression의 ' <typename> ' 형식은 제한 된 형식 이므로 ' Object ' 또는 ' ValueType '에서 상속 된 멤버에 액세스 하는 데 사용할 수 없습니다."
title: 식에 있는 '<typename>' 형식은 제한된 형식이므로 'Object' 또는 'ValueType'에서 상속된 멤버에 액세스하는 데 사용할 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- bc31393
- vbc31393
helpviewer_keywords:
- BC31393
ms.assetid: 2963cf3f-c527-4aa7-b67c-ee80b6d23186
ms.openlocfilehash: 3b5f9bbb85d1645936286ea0e907e3e25764f69a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796381"
---
# <a name="bc31393-expression-has-the-type-typename-which-is-a-restricted-type-and-cannot-be-used-to-access-members-inherited-from-object-or-valuetype"></a><span data-ttu-id="6e7cf-103">BC31393: Expression의 ' ' 형식은 \<typename> 제한 된 형식 이므로 ' Object ' 또는 ' ValueType '에서 상속 된 멤버에 액세스 하는 데 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6e7cf-103">BC31393: Expression has the type '\<typename>' which is a restricted type and cannot be used to access members inherited from 'Object' or 'ValueType'</span></span>

<span data-ttu-id="6e7cf-104">식이 CLR (공용 언어 런타임)에 의해 boxing 될 수 없는 형식으로 계산 되지만 boxing이 필요한 멤버에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e7cf-104">An expression evaluates to a type that cannot be boxed by the common language runtime (CLR) but accesses a member that requires boxing.</span></span>

 <span data-ttu-id="6e7cf-105">*Boxing* 은 형식을 경우에 따라 `Object` 또는 <xref:System.ValueType>으로 변환하는 데 필요한 처리를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="6e7cf-105">*Boxing* refers to the processing necessary to convert a type to `Object` or, on occasion, to <xref:System.ValueType>.</span></span> <span data-ttu-id="6e7cf-106">공용 언어 런타임에서는 특정 구조체 형식 (예:, 및)을 box 할 수 없습니다 <xref:System.ArgIterator> <xref:System.RuntimeArgumentHandle> <xref:System.TypedReference> .</span><span class="sxs-lookup"><span data-stu-id="6e7cf-106">The common language runtime cannot box certain structure types, for example <xref:System.ArgIterator>, <xref:System.RuntimeArgumentHandle>, and <xref:System.TypedReference>.</span></span>

 <span data-ttu-id="6e7cf-107">이 식은 또는와 같이 제한 된 형식을 사용 하 여 또는에서 상속 된 메서드를 호출 하려고 <xref:System.Object> <xref:System.ValueType> <xref:System.Object.GetHashCode%2A> <xref:System.Object.ToString%2A> 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e7cf-107">This expression attempts to use the restricted type to call a method inherited from <xref:System.Object> or <xref:System.ValueType>, such as <xref:System.Object.GetHashCode%2A> or <xref:System.Object.ToString%2A>.</span></span> <span data-ttu-id="6e7cf-108">이 메서드에 액세스 하기 위해 Visual Basic에서이 오류를 발생 시키는 암시적 boxing 변환을 시도 했습니다.</span><span class="sxs-lookup"><span data-stu-id="6e7cf-108">To access this method, Visual Basic has attempted an implicit boxing conversion that causes this error.</span></span>

 <span data-ttu-id="6e7cf-109">**오류 ID:** BC31393</span><span class="sxs-lookup"><span data-stu-id="6e7cf-109">**Error ID:** BC31393</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="6e7cf-110">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="6e7cf-110">To correct this error</span></span>

1. <span data-ttu-id="6e7cf-111">제시된 형식으로 계산되는 식을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="6e7cf-111">Locate the expression that evaluates to the cited type.</span></span>

2. <span data-ttu-id="6e7cf-112">또는에서 상속 된 메서드를 호출 하려고 하는 문의 일부를 찾습니다 <xref:System.Object> <xref:System.ValueType> .</span><span class="sxs-lookup"><span data-stu-id="6e7cf-112">Locate the part of your statement that attempts to call the method inherited from <xref:System.Object> or <xref:System.ValueType>.</span></span>

3. <span data-ttu-id="6e7cf-113">메서드 호출을 방지 하려면 문을 다시 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e7cf-113">Rewrite the statement to avoid the method call.</span></span>

## <a name="see-also"></a><span data-ttu-id="6e7cf-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6e7cf-114">See also</span></span>

- [<span data-ttu-id="6e7cf-115">암시적 변환과 명시적 변환</span><span class="sxs-lookup"><span data-stu-id="6e7cf-115">Implicit and Explicit Conversions</span></span>](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
