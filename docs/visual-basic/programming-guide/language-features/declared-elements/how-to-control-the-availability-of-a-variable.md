---
title: '방법: 변수 (Visual Basic)의 사용 가능성 제어'
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
ms.openlocfilehash: fb7c04ac6c24648dfb2a8cfa5e01bf97c6b0b3be
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58841695"
---
# <a name="how-to-control-the-availability-of-a-variable-visual-basic"></a><span data-ttu-id="f603e-102">방법: 변수 (Visual Basic)의 사용 가능성 제어</span><span class="sxs-lookup"><span data-stu-id="f603e-102">How to: Control the Availability of a Variable (Visual Basic)</span></span>
<span data-ttu-id="f603e-103">지정 하 여 변수의 사용 가능성 제어 해당 *액세스 수준*합니다.</span><span class="sxs-lookup"><span data-stu-id="f603e-103">You control the availability of a variable by specifying its *access level*.</span></span> <span data-ttu-id="f603e-104">액세스 수준 변수에 쓰거나 읽을 수 있는 코드를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f603e-104">The access level determines what code has permission to read or write to the variable.</span></span>  
  
-   <span data-ttu-id="f603e-105">*멤버 변수* (다른 프로시저 외부 모듈 수준에서 정의 됨) 기본적으로 공용 액세스를 확인 하는 코드에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f603e-105">*Member variables* (defined at module level and outside any procedure) default to public access, which means any code that can see them can access them.</span></span> <span data-ttu-id="f603e-106">액세스 한정자를 지정 하 여이 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f603e-106">You can change this by specifying an access modifier.</span></span>  
  
-   <span data-ttu-id="f603e-107">*지역 변수* (프로시저 내에서 정의 됨)가 프로시저 내의 코드만 액세스할 수 있지만 공용 액세스를 명목상 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f603e-107">*Local variables* (defined inside a procedure) nominally have public access, although only code within their procedure can access them.</span></span> <span data-ttu-id="f603e-108">지역 변수에서의 액세스 수준을 변경할 수 없지만 포함 하는 프로시저의 액세스 수준을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f603e-108">You cannot change the access level of a local variable, but you can change the access level of the procedure that contains it.</span></span>  
  
 <span data-ttu-id="f603e-109">자세한 내용은 [액세스 수준을 Visual Basic의](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f603e-109">For more information, see [Access levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
## <a name="private-and-public-access"></a><span data-ttu-id="f603e-110">개인 및 공용 액세스</span><span class="sxs-lookup"><span data-stu-id="f603e-110">Private and Public Access</span></span>  
  
#### <a name="to-make-a-variable-accessible-only-from-within-its-module-class-or-structure"></a><span data-ttu-id="f603e-111">변수를 해당 모듈, 클래스 또는 구조체 내 에서만 액세스할 수 있도록 하려면</span><span class="sxs-lookup"><span data-stu-id="f603e-111">To make a variable accessible only from within its module, class, or structure</span></span>  
  
1.  <span data-ttu-id="f603e-112">위치는 [Dim 문](../../../../visual-basic/language-reference/statements/dim-statement.md) 모듈, 클래스 또는 구조체 내 서 다른 프로시저 외부 변수에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="f603e-112">Place the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) for the variable inside the module, class, or structure, but outside any procedure.</span></span>  
  
2.  <span data-ttu-id="f603e-113">포함 된 [개인](../../../../visual-basic/language-reference/modifiers/private.md) 키워드를 `Dim` 문.</span><span class="sxs-lookup"><span data-stu-id="f603e-113">Include the [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="f603e-114">읽거나 아닌 하지만 모듈, 클래스 또는 구조체 내에서 변수를 쓸 수 밖에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f603e-114">You can read or write to the variable from anywhere within the module, class, or structure, but not from outside it.</span></span>  
  
#### <a name="to-make-a-variable-accessible-from-any-code-that-can-see-it"></a><span data-ttu-id="f603e-115">변수를 볼 수 있는 모든 코드에서 액세스할 수 있도록 하려면</span><span class="sxs-lookup"><span data-stu-id="f603e-115">To make a variable accessible from any code that can see it</span></span>  
  
1.  <span data-ttu-id="f603e-116">멤버 변수를 배치 합니다 `Dim` 모듈, 클래스 또는 구조체 내 서 다른 프로시저 외부 변수에 대 한 문을 합니다.</span><span class="sxs-lookup"><span data-stu-id="f603e-116">For a member variable, place the `Dim` statement for the variable inside a module, class, or structure, but outside any procedure.</span></span>  
  
2.  <span data-ttu-id="f603e-117">포함 된 [공용](../../../../visual-basic/language-reference/modifiers/public.md) 키워드를 `Dim` 문.</span><span class="sxs-lookup"><span data-stu-id="f603e-117">Include the [Public](../../../../visual-basic/language-reference/modifiers/public.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="f603e-118">읽기 또는 어셈블리를 사용 하 여 상호 운용 하는 코드에서 변수를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f603e-118">You can read or write to the variable from any code that interoperates with your assembly.</span></span>  
  
 <span data-ttu-id="f603e-119">또는</span><span class="sxs-lookup"><span data-stu-id="f603e-119">-or-</span></span>  
  
1.  <span data-ttu-id="f603e-120">지역 변수를 배치 합니다 `Dim` 문을 프로시저 내에서 변수에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="f603e-120">For a local variable, place the `Dim` statement for the variable inside a procedure.</span></span>  
  
2.  <span data-ttu-id="f603e-121">포함 되지 않습니다 합니다 `Public` 키워드는 `Dim` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="f603e-121">Do not include the `Public` keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="f603e-122">읽기 또는 프로시저 내에서 아무 곳 이나 있지만 아닌에서 변수를 쓸 수 밖에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f603e-122">You can read or write to the variable from anywhere within the procedure, but not from outside it.</span></span>  
  
## <a name="protected-and-friend-access"></a><span data-ttu-id="f603e-123">보호 및 Friend 액세스</span><span class="sxs-lookup"><span data-stu-id="f603e-123">Protected and Friend Access</span></span>  
 <span data-ttu-id="f603e-124">액세스 수준 또는 해당 어셈블리의 클래스와 모든 파생된 클래스에 변수를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f603e-124">You can limit the access level of a variable to its class and any derived classes, or to its assembly.</span></span> <span data-ttu-id="f603e-125">또한 동일한 어셈블리의 다른 위치 또는 파생된 클래스에서 코드에서 액세스를 허용 하는 이러한 제한의 합집합을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f603e-125">You can also specify the union of these limitations, which allows access from code in any derived class or in any other place in the same assembly.</span></span> <span data-ttu-id="f603e-126">결합 하 여이 공용 구조체를 지정 합니다 `Protected` 및 `Friend` 동일한 선언에서 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="f603e-126">You specify this union by combining the `Protected` and `Friend` keywords in the same declaration.</span></span>  
  
#### <a name="to-make-a-variable-accessible-only-from-within-its-class-and-any-derived-classes"></a><span data-ttu-id="f603e-127">변수를 해당 클래스와 모든 파생된 클래스 내 에서만 액세스할 수 있도록 하려면</span><span class="sxs-lookup"><span data-stu-id="f603e-127">To make a variable accessible only from within its class and any derived classes</span></span>  
  
1.  <span data-ttu-id="f603e-128">위치는 `Dim` 클래스 내부 이지만 다른 프로시저 외부 변수에 대 한 문입니다.</span><span class="sxs-lookup"><span data-stu-id="f603e-128">Place the `Dim` statement for the variable inside a class, but outside any procedure.</span></span>  
  
2.  <span data-ttu-id="f603e-129">포함 된 [보호 된](../../../../visual-basic/language-reference/modifiers/protected.md) 키워드를 `Dim` 문.</span><span class="sxs-lookup"><span data-stu-id="f603e-129">Include the [Protected](../../../../visual-basic/language-reference/modifiers/protected.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="f603e-130">읽거나,에서 파생 된 클래스 내에서 뿐만 아니라 해당 클래스에서 변수를 쓸 수 파생 체인의 모든 클래스 외부입니다.</span><span class="sxs-lookup"><span data-stu-id="f603e-130">You can read or write to the variable from anywhere within the class, as well as from within any class derived from it, but not from outside any class in the derivation chain.</span></span>  
  
#### <a name="to-make-a-variable-accessible-only-from-within-the-same-assembly"></a><span data-ttu-id="f603e-131">변수를 동일한 어셈블리 내 에서만 액세스할 수 있도록 하려면</span><span class="sxs-lookup"><span data-stu-id="f603e-131">To make a variable accessible only from within the same assembly</span></span>  
  
1.  <span data-ttu-id="f603e-132">위치는 `Dim` 모듈, 클래스 또는 구조체 내 서 다른 프로시저 외부 변수에 대 한 문입니다.</span><span class="sxs-lookup"><span data-stu-id="f603e-132">Place the `Dim` statement for the variable inside a module, class, or structure, but outside any procedure.</span></span>  
  
2.  <span data-ttu-id="f603e-133">포함 된 [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) 키워드를 `Dim` 문.</span><span class="sxs-lookup"><span data-stu-id="f603e-133">Include the [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="f603e-134">읽거나 아닌 하지만 동일한 어셈블리의 코드 뿐만 아니라 모듈, 클래스 또는 구조체 내에서 변수를 쓸 수 어셈블리 외부에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f603e-134">You can read or write to the variable from anywhere within the module, class, or structure, as well as from any code in the same assembly, but not from outside the assembly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f603e-135">예제</span><span class="sxs-lookup"><span data-stu-id="f603e-135">Example</span></span>  
 <span data-ttu-id="f603e-136">다음 예제에서는 사용 하 여 변수의 선언을 `Public`, `Protected`를 `Friend`, `Protected Friend`, 및 `Private` 액세스 수준을 합니다.</span><span class="sxs-lookup"><span data-stu-id="f603e-136">The following example shows declarations of variables with `Public`, `Protected`, `Friend`, `Protected Friend`, and `Private` access levels.</span></span> <span data-ttu-id="f603e-137">경우는 `Dim` 문에 대 한 액세스 수준을 지정, 포함할 필요가 없습니다를 `Dim` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="f603e-137">Note that when the `Dim` statement specifies an access level, you do not need to include the `Dim` keyword.</span></span>  
  
```  
Public Class classForEverybody  
Protected Class classForMyHeirs  
Friend stringForThisProject As String  
Protected Friend stringForProjectAndHeirs As String  
Private numberForMeOnly As Integer  
```  
  
## <a name="net-framework-security"></a><span data-ttu-id="f603e-138">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="f603e-138">.NET Framework Security</span></span>  
 <span data-ttu-id="f603e-139">더 제한적인 변수를 액세스 수준에 악성 코드가 부적절 하 게 가능성이 줄어듭니다 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f603e-139">The more restrictive the access level of a variable, the smaller the chances that malicious code can make improper use of it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f603e-140">참고자료</span><span class="sxs-lookup"><span data-stu-id="f603e-140">See also</span></span>

- [<span data-ttu-id="f603e-141">Visual Basic의 액세스 수준</span><span class="sxs-lookup"><span data-stu-id="f603e-141">Access levels in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="f603e-142">Dim 문</span><span class="sxs-lookup"><span data-stu-id="f603e-142">Dim Statement</span></span>](../../../../visual-basic/language-reference/statements/dim-statement.md)
- [<span data-ttu-id="f603e-143">공용</span><span class="sxs-lookup"><span data-stu-id="f603e-143">Public</span></span>](../../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="f603e-144">보호됨</span><span class="sxs-lookup"><span data-stu-id="f603e-144">Protected</span></span>](../../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="f603e-145">Friend</span><span class="sxs-lookup"><span data-stu-id="f603e-145">Friend</span></span>](../../../../visual-basic/language-reference/modifiers/friend.md)
- [<span data-ttu-id="f603e-146">전용</span><span class="sxs-lookup"><span data-stu-id="f603e-146">Private</span></span>](../../../../visual-basic/language-reference/modifiers/private.md)
