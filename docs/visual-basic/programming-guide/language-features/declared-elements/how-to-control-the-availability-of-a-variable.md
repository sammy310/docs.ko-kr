---
description: '자세히 알아보기: 방법: 변수의 가용성 제어 (Visual Basic)'
title: '방법: 변수의 사용 가능성 제어'
ms.date: 07/20/2015
helpviewer_keywords:
- access levels, declared elements
- Private keyword [Visual Basic], accessing variables
- access levels, variables
- Public keyword [Visual Basic], accessing variables
- Friend keyword [Visual Basic], accessing variables
- variables [Visual Basic], access level
- declared elements [Visual Basic], access level
- Protected keyword [Visual Basic], accessing variables
ms.assetid: eaf4f073-7922-43ce-ae1e-90ff376ae947
ms.openlocfilehash: 3fa21a804008f31da9003aa847752f749154d602
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100429886"
---
# <a name="how-to-control-the-availability-of-a-variable-visual-basic"></a><span data-ttu-id="79415-103">방법: 변수의 사용 가능성 제어(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="79415-103">How to: Control the Availability of a Variable (Visual Basic)</span></span>

<span data-ttu-id="79415-104">*액세스 수준을* 지정 하 여 변수의 가용성을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="79415-104">You control the availability of a variable by specifying its *access level*.</span></span> <span data-ttu-id="79415-105">액세스 수준에 따라 변수에 대 한 읽기 또는 쓰기 권한이 있는 코드가 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="79415-105">The access level determines what code has permission to read or write to the variable.</span></span>  
  
- <span data-ttu-id="79415-106">*멤버 변수* (모듈 수준 및 프로시저 외부에서 정의 됨)는 기본적으로 공용 액세스로 사용 됩니다. 즉, 해당 변수를 볼 수 있는 모든 코드에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79415-106">*Member variables* (defined at module level and outside any procedure) default to public access, which means any code that can see them can access them.</span></span> <span data-ttu-id="79415-107">액세스 한정자를 지정 하 여이를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79415-107">You can change this by specifying an access modifier.</span></span>  
  
- <span data-ttu-id="79415-108">*지역 변수* (프로시저 내에서 정의 됨)에는 공용 액세스 권한이 있지만 프로시저 내의 코드만 액세스할 수 있는 명목상 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79415-108">*Local variables* (defined inside a procedure) nominally have public access, although only code within their procedure can access them.</span></span> <span data-ttu-id="79415-109">지역 변수의 액세스 수준을 변경할 수는 없지만 해당 변수의 액세스 수준을 포함 하는 프로시저의 액세스 수준을 변경할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79415-109">You cannot change the access level of a local variable, but you can change the access level of the procedure that contains it.</span></span>  
  
 <span data-ttu-id="79415-110">자세한 내용은 [Visual Basic의 액세스 수준](access-levels.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="79415-110">For more information, see [Access levels in Visual Basic](access-levels.md).</span></span>  
  
## <a name="private-and-public-access"></a><span data-ttu-id="79415-111">개인 및 공용 액세스</span><span class="sxs-lookup"><span data-stu-id="79415-111">Private and Public Access</span></span>  
  
#### <a name="to-make-a-variable-accessible-only-from-within-its-module-class-or-structure"></a><span data-ttu-id="79415-112">모듈, 클래스 또는 구조체 내 에서만 변수를 액세스할 수 있도록 하려면</span><span class="sxs-lookup"><span data-stu-id="79415-112">To make a variable accessible only from within its module, class, or structure</span></span>  
  
1. <span data-ttu-id="79415-113">모듈, 클래스 또는 구조체 내에서 프로시저 외부에 있는 변수에 [Dim 문을](../../../language-reference/statements/dim-statement.md) 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="79415-113">Place the [Dim Statement](../../../language-reference/statements/dim-statement.md) for the variable inside the module, class, or structure, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="79415-114">문에 [Private](../../../language-reference/modifiers/private.md) 키워드를 포함 `Dim` 합니다.</span><span class="sxs-lookup"><span data-stu-id="79415-114">Include the [Private](../../../language-reference/modifiers/private.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="79415-115">모듈, 클래스 또는 구조체 내의 어디에서 나 변수를 읽거나 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79415-115">You can read or write to the variable from anywhere within the module, class, or structure, but not from outside it.</span></span>  
  
#### <a name="to-make-a-variable-accessible-from-any-code-that-can-see-it"></a><span data-ttu-id="79415-116">변수를 볼 수 있는 모든 코드에서 액세스할 수 있도록 하려면</span><span class="sxs-lookup"><span data-stu-id="79415-116">To make a variable accessible from any code that can see it</span></span>  
  
1. <span data-ttu-id="79415-117">멤버 변수의 경우 `Dim` 모듈, 클래스 또는 구조체 내에서 프로시저 외부에 변수에 대 한 문을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="79415-117">For a member variable, place the `Dim` statement for the variable inside a module, class, or structure, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="79415-118">문에 [Public](../../../language-reference/modifiers/public.md) 키워드를 포함 `Dim` 합니다.</span><span class="sxs-lookup"><span data-stu-id="79415-118">Include the [Public](../../../language-reference/modifiers/public.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="79415-119">어셈블리와 상호 작용 하는 모든 코드에서 변수를 읽거나 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79415-119">You can read or write to the variable from any code that interoperates with your assembly.</span></span>  
  
 <span data-ttu-id="79415-120">또는</span><span class="sxs-lookup"><span data-stu-id="79415-120">-or-</span></span>  
  
1. <span data-ttu-id="79415-121">지역 변수의 경우 `Dim` 프로시저 안에 변수에 대 한 문을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="79415-121">For a local variable, place the `Dim` statement for the variable inside a procedure.</span></span>  
  
2. <span data-ttu-id="79415-122">문에 키워드를 포함 하지 마십시오 `Public` `Dim` .</span><span class="sxs-lookup"><span data-stu-id="79415-122">Do not include the `Public` keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="79415-123">프로시저 내의 어디에서 나 변수를 읽거나 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79415-123">You can read or write to the variable from anywhere within the procedure, but not from outside it.</span></span>  
  
## <a name="protected-and-friend-access"></a><span data-ttu-id="79415-124">보호 및 Friend 액세스</span><span class="sxs-lookup"><span data-stu-id="79415-124">Protected and Friend Access</span></span>  

 <span data-ttu-id="79415-125">변수의 액세스 수준을 해당 클래스 및 파생 클래스 또는 해당 어셈블리로 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79415-125">You can limit the access level of a variable to its class and any derived classes, or to its assembly.</span></span> <span data-ttu-id="79415-126">이러한 제한의 합집합을 지정 하 여 파생 클래스의 코드나 동일한 어셈블리에 있는 다른 위치의 코드에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79415-126">You can also specify the union of these limitations, which allows access from code in any derived class or in any other place in the same assembly.</span></span> <span data-ttu-id="79415-127">`Protected`동일한 선언에서 및 키워드를 결합 하 여이 union을 지정 `Friend` 합니다.</span><span class="sxs-lookup"><span data-stu-id="79415-127">You specify this union by combining the `Protected` and `Friend` keywords in the same declaration.</span></span>  
  
#### <a name="to-make-a-variable-accessible-only-from-within-its-class-and-any-derived-classes"></a><span data-ttu-id="79415-128">해당 클래스 및 파생 클래스 에서만 변수를 액세스할 수 있도록 하려면</span><span class="sxs-lookup"><span data-stu-id="79415-128">To make a variable accessible only from within its class and any derived classes</span></span>  
  
1. <span data-ttu-id="79415-129">`Dim`프로시저 외부에 있는 변수에 대 한 문을 클래스 내부에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="79415-129">Place the `Dim` statement for the variable inside a class, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="79415-130">문에 [Protected](../../../language-reference/modifiers/protected.md) 키워드를 포함 `Dim` 합니다.</span><span class="sxs-lookup"><span data-stu-id="79415-130">Include the [Protected](../../../language-reference/modifiers/protected.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="79415-131">클래스 내 어디에서 나 클래스 내에서 파생 된 클래스 내에서 또는 파생 체인의 모든 클래스 외부에서 변수를 읽거나 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79415-131">You can read or write to the variable from anywhere within the class, as well as from within any class derived from it, but not from outside any class in the derivation chain.</span></span>  
  
#### <a name="to-make-a-variable-accessible-only-from-within-the-same-assembly"></a><span data-ttu-id="79415-132">동일한 어셈블리 내 에서만 변수를 액세스할 수 있도록 하려면</span><span class="sxs-lookup"><span data-stu-id="79415-132">To make a variable accessible only from within the same assembly</span></span>  
  
1. <span data-ttu-id="79415-133">`Dim`모듈, 클래스 또는 구조체 내에서 프로시저 외부에 변수에 대 한 문을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="79415-133">Place the `Dim` statement for the variable inside a module, class, or structure, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="79415-134">문에 [Friend](../../../language-reference/modifiers/friend.md) 키워드를 포함 `Dim` 합니다.</span><span class="sxs-lookup"><span data-stu-id="79415-134">Include the [Friend](../../../language-reference/modifiers/friend.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="79415-135">모듈, 클래스 또는 구조체의 모든 위치 뿐만 아니라 동일한 어셈블리의 모든 코드에서 변수를 읽거나 쓸 수 있습니다. 단, 어셈블리 외부에서는 읽을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="79415-135">You can read or write to the variable from anywhere within the module, class, or structure, as well as from any code in the same assembly, but not from outside the assembly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="79415-136">예</span><span class="sxs-lookup"><span data-stu-id="79415-136">Example</span></span>  

 <span data-ttu-id="79415-137">다음 예제에서는 `Public` ,, `Protected` `Friend` , `Protected Friend` 및 `Private` 액세스 수준을 사용 하 여 변수 선언을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="79415-137">The following example shows declarations of variables with `Public`, `Protected`, `Friend`, `Protected Friend`, and `Private` access levels.</span></span> <span data-ttu-id="79415-138">`Dim`문이 액세스 수준을 지정 하는 경우 키워드를 포함할 필요가 없습니다 `Dim` .</span><span class="sxs-lookup"><span data-stu-id="79415-138">Note that when the `Dim` statement specifies an access level, you do not need to include the `Dim` keyword.</span></span>  
  
```vb  
Public Class classForEverybody  
Protected Class classForMyHeirs  
Friend stringForThisProject As String  
Protected Friend stringForProjectAndHeirs As String  
Private numberForMeOnly As Integer  
```  
  
## <a name="net-framework-security"></a><span data-ttu-id="79415-139">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="79415-139">.NET Framework Security</span></span>  

 <span data-ttu-id="79415-140">변수의 액세스 수준이 더 제한적 이면 악의적인 코드가이를 부적절 하 게 사용할 수 있는 가능성이 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="79415-140">The more restrictive the access level of a variable, the smaller the chances that malicious code can make improper use of it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79415-141">추가 정보</span><span class="sxs-lookup"><span data-stu-id="79415-141">See also</span></span>

- [<span data-ttu-id="79415-142">Visual Basic의 액세스 수준</span><span class="sxs-lookup"><span data-stu-id="79415-142">Access levels in Visual Basic</span></span>](access-levels.md)
- [<span data-ttu-id="79415-143">Dim 문</span><span class="sxs-lookup"><span data-stu-id="79415-143">Dim Statement</span></span>](../../../language-reference/statements/dim-statement.md)
- [<span data-ttu-id="79415-144">공용</span><span class="sxs-lookup"><span data-stu-id="79415-144">Public</span></span>](../../../language-reference/modifiers/public.md)
- [<span data-ttu-id="79415-145">보호됨</span><span class="sxs-lookup"><span data-stu-id="79415-145">Protected</span></span>](../../../language-reference/modifiers/protected.md)
- [<span data-ttu-id="79415-146">Friend</span><span class="sxs-lookup"><span data-stu-id="79415-146">Friend</span></span>](../../../language-reference/modifiers/friend.md)
- [<span data-ttu-id="79415-147">개인</span><span class="sxs-lookup"><span data-stu-id="79415-147">Private</span></span>](../../../language-reference/modifiers/private.md)
