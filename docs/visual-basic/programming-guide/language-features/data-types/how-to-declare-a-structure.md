---
title: '방법: 구조 선언'
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], structures
- structure statements [Visual Basic]
- statements [Visual Basic], structure
- structures [Visual Basic], declaring
ms.assetid: d5e98381-eb81-47d4-af83-48cc534a2572
ms.openlocfilehash: bffdc5974eff6b71e0abc4780a61aa300769eed6
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91058549"
---
# <a name="how-to-declare-a-structure-visual-basic"></a><span data-ttu-id="4403b-102">방법: 구조체 선언(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4403b-102">How to: Declare a Structure (Visual Basic)</span></span>

<span data-ttu-id="4403b-103">Structure [문을](../../../language-reference/statements/structure-statement.md)사용 하 여 구조체 선언을 시작 하 고 `End Structure` 문으로 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="4403b-103">You begin a structure declaration with the [Structure Statement](../../../language-reference/statements/structure-statement.md), and you end it with the `End Structure` statement.</span></span> <span data-ttu-id="4403b-104">이러한 두 문 사이에는 하나 이상의 *요소*를 선언 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4403b-104">Between these two statements you must declare at least one *element*.</span></span> <span data-ttu-id="4403b-105">요소는 모든 데이터 형식이 될 수 있지만 하나 이상 비공유 변수 이거나 비공유 noncustom 이벤트 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4403b-105">The elements can be of any data type, but at least one must be either a nonshared variable or a nonshared, noncustom event.</span></span>  
  
 <span data-ttu-id="4403b-106">구조체 선언에서 구조체 요소를 초기화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4403b-106">You cannot initialize any of the structure elements in the structure declaration.</span></span> <span data-ttu-id="4403b-107">구조체 형식으로 변수를 선언 하는 경우 변수를 통해 값에 액세스 하 여 요소에 값을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="4403b-107">When you declare a variable to be of a structure type, you assign values to the elements by accessing them through the variable.</span></span>  
  
 <span data-ttu-id="4403b-108">구조와 클래스 간의 차이점에 대 한 설명은 [구조체 및 클래스](structures-and-classes.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4403b-108">For a discussion of the differences between structures and classes, see [Structures and Classes](structures-and-classes.md).</span></span>  
  
 <span data-ttu-id="4403b-109">데모용으로 직원의 이름, 전화 내선 및 급여를 추적 하려는 상황을 고려해 보세요.</span><span class="sxs-lookup"><span data-stu-id="4403b-109">For demonstration purposes, consider a situation where you want to keep track of an employee's name, telephone extension, and salary.</span></span> <span data-ttu-id="4403b-110">구조체를 사용 하면 단일 변수에서이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4403b-110">A structure allows you to do this in a single variable.</span></span>  
  
### <a name="to-declare-a-structure"></a><span data-ttu-id="4403b-111">구조체를 선언 하려면</span><span class="sxs-lookup"><span data-stu-id="4403b-111">To declare a structure</span></span>  
  
1. <span data-ttu-id="4403b-112">구조체에 대 한 시작 및 종료 문을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4403b-112">Create the beginning and ending statements for the structure.</span></span>  
  
     <span data-ttu-id="4403b-113">[Public](../../../language-reference/modifiers/public.md), [Protected](../../../language-reference/modifiers/protected.md), [Friend](../../../language-reference/modifiers/friend.md)또는 [Private](../../../language-reference/modifiers/private.md) 키워드를 사용 하 여 구조체의 액세스 수준을 지정 하거나를 기본값으로 지정할 수 있습니다 `Public` .</span><span class="sxs-lookup"><span data-stu-id="4403b-113">You can specify the access level of a structure using the [Public](../../../language-reference/modifiers/public.md), [Protected](../../../language-reference/modifiers/protected.md), [Friend](../../../language-reference/modifiers/friend.md), or [Private](../../../language-reference/modifiers/private.md) keyword, or you can let it default to `Public`.</span></span>  
  
    ```vb  
    Private Structure employee  
    End Structure  
    ```  
  
2. <span data-ttu-id="4403b-114">구조 본문에 요소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="4403b-114">Add elements to the body of the structure.</span></span>  
  
     <span data-ttu-id="4403b-115">구조체에는 요소가 하나 이상 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4403b-115">A structure must have at least one element.</span></span> <span data-ttu-id="4403b-116">모든 요소를 선언 하 고 해당 요소에 대 한 액세스 수준을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4403b-116">You must declare every element and specify an access level for it.</span></span> <span data-ttu-id="4403b-117">키워드 없이 [Dim 문을](../../../language-reference/statements/dim-statement.md) 사용 하는 경우 액세스 가능성은 기본적으로로 설정 `Public` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4403b-117">If you use the [Dim Statement](../../../language-reference/statements/dim-statement.md) without any keywords, the accessibility defaults to `Public`.</span></span>  
  
    ```vb  
    Private Structure employee  
        Public givenName As String  
        Public familyName As String  
        Public phoneExtension As Long  
        Private salary As Decimal  
        Public Sub giveRaise(raise As Double)  
            salary *= raise  
        End Sub  
        Public Event salaryReviewTime()  
    End Structure  
    ```  
  
     <span data-ttu-id="4403b-118">`salary`앞의 예제에서 필드는 `Private` 를 포함 하는 클래스 에서도 구조체 외부에서 액세스할 수 없음을 의미 하는입니다.</span><span class="sxs-lookup"><span data-stu-id="4403b-118">The `salary` field in the preceding example is `Private`, which means it is inaccessible outside the structure, even from the containing class.</span></span> <span data-ttu-id="4403b-119">그러나 프로시저는 이므로 `giveRaise` `Public` 구조 외부에서 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4403b-119">However, the `giveRaise` procedure is `Public`, so it can be called from outside the structure.</span></span> <span data-ttu-id="4403b-120">마찬가지로 구조 외부에서 이벤트를 발생 시킬 수 있습니다 `salaryReviewTime` .</span><span class="sxs-lookup"><span data-stu-id="4403b-120">Similarly, you can raise the `salaryReviewTime` event from outside the structure.</span></span>  
  
     <span data-ttu-id="4403b-121">변수, `Sub` 프로시저 및 이벤트 외에도 구조에서 상수, 프로시저 및 속성을 정의할 수 있습니다 `Function` .</span><span class="sxs-lookup"><span data-stu-id="4403b-121">In addition to variables, `Sub` procedures, and events, you can also define constants, `Function` procedures, and properties in a structure.</span></span> <span data-ttu-id="4403b-122">하나 이상의 인수를 사용 하는 경우 *기본 속성*으로 최대 하나의 속성을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4403b-122">You can designate at most one property as the *default property*, provided it takes at least one argument.</span></span> <span data-ttu-id="4403b-123">[공유](../../../language-reference/modifiers/shared.md) 프로시저를 사용 하 여 이벤트를 처리할 수 있습니다 `Sub` .</span><span class="sxs-lookup"><span data-stu-id="4403b-123">You can handle an event with a [Shared](../../../language-reference/modifiers/shared.md)`Sub` procedure.</span></span> <span data-ttu-id="4403b-124">자세한 내용은 [방법: Visual Basic에서 기본 속성 선언 및 호출](../procedures/how-to-declare-and-call-a-default-property.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4403b-124">For more information, see [How to: Declare and Call a Default Property in Visual Basic](../procedures/how-to-declare-and-call-a-default-property.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4403b-125">참조</span><span class="sxs-lookup"><span data-stu-id="4403b-125">See also</span></span>

- [<span data-ttu-id="4403b-126">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4403b-126">Data Types</span></span>](index.md)
- [<span data-ttu-id="4403b-127">기본 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4403b-127">Elementary Data Types</span></span>](elementary-data-types.md)
- [<span data-ttu-id="4403b-128">복합 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4403b-128">Composite Data Types</span></span>](composite-data-types.md)
- [<span data-ttu-id="4403b-129">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="4403b-129">Value Types and Reference Types</span></span>](value-types-and-reference-types.md)
- [<span data-ttu-id="4403b-130">구조체</span><span class="sxs-lookup"><span data-stu-id="4403b-130">Structures</span></span>](structures.md)
- [<span data-ttu-id="4403b-131">데이터 형식 문제 해결</span><span class="sxs-lookup"><span data-stu-id="4403b-131">Troubleshooting Data Types</span></span>](troubleshooting-data-types.md)
- [<span data-ttu-id="4403b-132">구조체 변수</span><span class="sxs-lookup"><span data-stu-id="4403b-132">Structure Variables</span></span>](structure-variables.md)
- [<span data-ttu-id="4403b-133">구조체 및 기타 프로그래밍 요소</span><span class="sxs-lookup"><span data-stu-id="4403b-133">Structures and Other Programming Elements</span></span>](structures-and-other-programming-elements.md)
- [<span data-ttu-id="4403b-134">구조체와 클래스</span><span class="sxs-lookup"><span data-stu-id="4403b-134">Structures and Classes</span></span>](structures-and-classes.md)
- [<span data-ttu-id="4403b-135">사용자 정의 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4403b-135">User-Defined Data Type</span></span>](../../../language-reference/data-types/user-defined-data-type.md)
