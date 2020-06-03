---
title: Shared
ms.date: 07/20/2015
f1_keywords:
- vb.Shared
helpviewer_keywords:
- Shared keyword [Visual Basic]
- members [Visual Basic], shared
- shared members
- nonshared
- shared [elements VB]
- elements [Visual Basic], shared
ms.assetid: 2bf7cf2c-b0dd-485e-8749-b5d674dab4cd
ms.openlocfilehash: 000cc13bc6e80914e9a21b6ee60e91127809ee08
ms.sourcegitcommit: 5280b2aef60a1ed99002dba44e4b9e7f6c830604
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/03/2020
ms.locfileid: "84307087"
---
# <a name="shared-visual-basic"></a><span data-ttu-id="5ed1b-102">Shared(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5ed1b-102">Shared (Visual Basic)</span></span>

<span data-ttu-id="5ed1b-103">하나 이상의 선언 된 프로그래밍 요소가 클래스 또는 구조체의 특정 인스턴스가 아닌 여러 클래스 또는 구조체와 연결 되도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ed1b-103">Specifies that one or more declared programming elements are associated with a class or structure at large, and not with a specific instance of the class or structure.</span></span>

## <a name="when-to-use-shared"></a><span data-ttu-id="5ed1b-104">공유를 사용 하는 경우</span><span class="sxs-lookup"><span data-stu-id="5ed1b-104">When to Use Shared</span></span>

<span data-ttu-id="5ed1b-105">클래스 또는 구조체의 멤버를 공유 하면 *비공유*가 아닌 모든 인스턴스에서 사용할 수 있습니다. 여기서 각 인스턴스는 자체 복사본을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ed1b-105">Sharing a member of a class or structure makes it available to every instance, rather than *non-shared*, where each instance keeps its own copy.</span></span> <span data-ttu-id="5ed1b-106">이는 예를 들어 변수 값이 전체 응용 프로그램에 적용 되는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ed1b-106">This is useful, for example, if the value of a variable applies to the entire application.</span></span> <span data-ttu-id="5ed1b-107">해당 변수를로 선언 하는 경우 `Shared` 모든 인스턴스가 동일한 저장소 위치에 액세스 하 고 한 인스턴스가 변수의 값을 변경 하는 경우 모든 인스턴스에서 업데이트 된 값에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ed1b-107">If you declare that variable to be `Shared`, then all instances access the same storage location, and if one instance changes the variable's value, all instances access the updated value.</span></span>

<span data-ttu-id="5ed1b-108">공유는 멤버의 액세스 수준을 변경 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5ed1b-108">Sharing does not alter the access level of a member.</span></span> <span data-ttu-id="5ed1b-109">예를 들어 클래스 멤버는 shared 및 private (클래스 내 에서만 액세스할 수 있음) 또는 비공유 및 public 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ed1b-109">For example, a class member can be shared and private (accessible only from within the class), or non-shared and public.</span></span> <span data-ttu-id="5ed1b-110">자세한 내용은 [Visual Basic의 액세스 수준](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5ed1b-110">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

## <a name="rules"></a><span data-ttu-id="5ed1b-111">규칙</span><span class="sxs-lookup"><span data-stu-id="5ed1b-111">Rules</span></span>

- <span data-ttu-id="5ed1b-112">**선언 컨텍스트.**</span><span class="sxs-lookup"><span data-stu-id="5ed1b-112">**Declaration Context.**</span></span> <span data-ttu-id="5ed1b-113">`Shared`는 모듈 수준에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ed1b-113">You can use `Shared` only at module level.</span></span> <span data-ttu-id="5ed1b-114">즉, 요소에 대 한 선언 컨텍스트는 `Shared` 클래스 또는 구조체 여야 하며 소스 파일, 네임 스페이스 또는 프로시저일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5ed1b-114">This means the declaration context for a `Shared` element must be a class or structure, and cannot be a source file, namespace, or procedure.</span></span>

- <span data-ttu-id="5ed1b-115">**결합된 한정자.**</span><span class="sxs-lookup"><span data-stu-id="5ed1b-115">**Combined Modifiers.**</span></span> <span data-ttu-id="5ed1b-116">`Shared`동일한 선언에서 [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md), [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md), [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md), [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)또는 [Static](../../../visual-basic/language-reference/modifiers/static.md) 을 함께 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5ed1b-116">You cannot specify `Shared` together with [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md), [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md), [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md), [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md), or [Static](../../../visual-basic/language-reference/modifiers/static.md) in the same declaration.</span></span>

- <span data-ttu-id="5ed1b-117">**하.**</span><span class="sxs-lookup"><span data-stu-id="5ed1b-117">**Accessing.**</span></span> <span data-ttu-id="5ed1b-118">해당 클래스 또는 구조체의 특정 인스턴스의 변수 이름이 아니라 클래스 또는 구조체 이름으로 정규화 하 여 공유 요소에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ed1b-118">You access a shared element by qualifying it with its class or structure name, not with the variable name of a specific instance of its class or structure.</span></span> <span data-ttu-id="5ed1b-119">클래스 또는 구조체의 인스턴스를 만들어 해당 공유 멤버에 액세스할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5ed1b-119">You do not even have to create an instance of a class or structure to access its shared members.</span></span>

     <span data-ttu-id="5ed1b-120">다음 예에서는 <xref:System.Double.IsNaN%2A> 구조에 의해 노출 되는 공유 프로시저를 호출 합니다 <xref:System.Double> .</span><span class="sxs-lookup"><span data-stu-id="5ed1b-120">The following example calls the shared procedure <xref:System.Double.IsNaN%2A> exposed by the <xref:System.Double> structure.</span></span>

     ```vb
     If Double.IsNaN(result) Then Console.WriteLine("Result is mathematically undefined.")
     ```

- <span data-ttu-id="5ed1b-121">**암시적 공유.**</span><span class="sxs-lookup"><span data-stu-id="5ed1b-121">**Implicit Sharing.**</span></span> <span data-ttu-id="5ed1b-122">`Shared` [Const 문에](../../../visual-basic/language-reference/statements/const-statement.md)는 한정자를 사용할 수 없지만 상수는 암시적으로 공유 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ed1b-122">You cannot use the `Shared` modifier in a [Const Statement](../../../visual-basic/language-reference/statements/const-statement.md), but constants are implicitly shared.</span></span> <span data-ttu-id="5ed1b-123">마찬가지로, 모듈 또는 인터페이스의 멤버를로 선언할 수 `Shared` 없지만 암시적으로 공유 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ed1b-123">Similarly, you cannot declare a member of a module or an interface to be `Shared`, but they are implicitly shared.</span></span>

## <a name="behavior"></a><span data-ttu-id="5ed1b-124">동작</span><span class="sxs-lookup"><span data-stu-id="5ed1b-124">Behavior</span></span>

- <span data-ttu-id="5ed1b-125">**저장할.**</span><span class="sxs-lookup"><span data-stu-id="5ed1b-125">**Storage.**</span></span> <span data-ttu-id="5ed1b-126">공유 변수나 이벤트는 해당 클래스 또는 구조체를 만든 인스턴스 수에 관계 없이 한 번만 메모리에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ed1b-126">A shared variable or event is stored in memory only once, no matter how many or few instances you create of its class or structure.</span></span> <span data-ttu-id="5ed1b-127">마찬가지로 공유 프로시저 또는 속성은 하나의 지역 변수 집합만 보유 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ed1b-127">Similarly, a shared procedure or property holds only one set of local variables.</span></span>

- <span data-ttu-id="5ed1b-128">**인스턴스 변수를 통해 액세스 합니다.**</span><span class="sxs-lookup"><span data-stu-id="5ed1b-128">**Accessing through an Instance Variable.**</span></span> <span data-ttu-id="5ed1b-129">해당 클래스 또는 구조체의 특정 인스턴스를 포함 하는 변수의 이름으로 정규화 하 여 공유 요소에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ed1b-129">It is possible to access a shared element by qualifying it with the name of a variable that contains a specific instance of its class or structure.</span></span> <span data-ttu-id="5ed1b-130">일반적으로 정상적으로 작동 하지만 컴파일러는 경고 메시지를 생성 하 고 변수 대신 클래스 또는 구조체 이름을 통해 액세스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5ed1b-130">Although this usually works as expected, the compiler generates a warning message and makes the access through the class or structure name instead of the variable.</span></span>

- <span data-ttu-id="5ed1b-131">**인스턴스 식을 통해 액세스 합니다.**</span><span class="sxs-lookup"><span data-stu-id="5ed1b-131">**Accessing through an Instance Expression.**</span></span> <span data-ttu-id="5ed1b-132">클래스 또는 구조체의 인스턴스를 반환 하는 식을 통해 공유 요소에 액세스 하는 경우 컴파일러는 식을 계산 하는 대신 클래스 또는 구조체 이름을 통해 액세스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5ed1b-132">If you access a shared element through an expression that returns an instance of its class or structure, the compiler makes the access through the class or structure name instead of evaluating the expression.</span></span> <span data-ttu-id="5ed1b-133">이렇게 하면 다른 작업을 수행 하 고 인스턴스를 반환 하는 식을 의도 한 경우 예기치 않은 결과가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ed1b-133">This produces unexpected results if you intended the expression to perform other actions as well as returning the instance.</span></span> <span data-ttu-id="5ed1b-134">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="5ed1b-134">The following example illustrates this.</span></span>
  
    ```vb
    Sub Main()
        ' The following line is the preferred way to access Total.
        ShareTotal.Total = 10

        ' The following line generates a compiler warning message and
        ' accesses total through class ShareTotal instead of through
        ' the variable instanceVar. This works as expected and adds
        ' 100 to Total.
        Dim instanceVar As New ShareTotal
        instanceVar.Total += 100

        ' The following line generates a compiler warning message and
        ' accesses total through class ShareTotal instead of calling
        ' ReturnClass(). This adds 1000 to total but does not work as
        ' expected, because the WriteLine in ReturnClass() does not run.
        Console.WriteLine("Value of total is " & CStr(ShareTotal.Total))
        ReturnClass().Total += 1000
    End Sub

    Public Function ReturnClass() As ShareTotal
        Console.WriteLine("Function ReturnClass() called")
        Return New ShareTotal
    End Function

    Public Class ShareTotal
        Public Shared Property Total As Integer
    End Class
    ```

     <span data-ttu-id="5ed1b-135">앞의 예제에서 컴파일러는 코드에서 인스턴스를 통해 공유 속성에 액세스 하는 두 번 모두 경고 메시지를 생성 합니다 `Total` .</span><span class="sxs-lookup"><span data-stu-id="5ed1b-135">In the preceding example, the compiler generates a warning message both times the code accesses the shared property `Total` through an instance.</span></span> <span data-ttu-id="5ed1b-136">각각의 경우에서 클래스를 통해 직접 액세스를 수행 `ShareTotal` 하 고 인스턴스를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5ed1b-136">In each case it makes the access directly through the class `ShareTotal` and does not make use of any instance.</span></span> <span data-ttu-id="5ed1b-137">프로시저에 대 한 의도 된 호출의 경우 `ReturnClass` 이는에 대 한 호출도 생성 하지 않으므로 `ReturnClass` "함수 returnclass ()를 표시 하는 추가 작업은 수행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5ed1b-137">In the case of the intended call to the procedure `ReturnClass`, this means it does not even generate a call to `ReturnClass`, so the additional action of displaying "Function ReturnClass() called" is not performed.</span></span>

<span data-ttu-id="5ed1b-138">`Shared` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ed1b-138">The `Shared` modifier can be used in these contexts:</span></span>

- [<span data-ttu-id="5ed1b-139">Dim 문</span><span class="sxs-lookup"><span data-stu-id="5ed1b-139">Dim Statement</span></span>](../statements/dim-statement.md)
- [<span data-ttu-id="5ed1b-140">Event 문</span><span class="sxs-lookup"><span data-stu-id="5ed1b-140">Event Statement</span></span>](../statements/event-statement.md)
- [<span data-ttu-id="5ed1b-141">Function 문</span><span class="sxs-lookup"><span data-stu-id="5ed1b-141">Function Statement</span></span>](../statements/function-statement.md)
- [<span data-ttu-id="5ed1b-142">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="5ed1b-142">Operator Statement</span></span>](../statements/operator-statement.md)
- [<span data-ttu-id="5ed1b-143">Property Statement</span><span class="sxs-lookup"><span data-stu-id="5ed1b-143">Property Statement</span></span>](../statements/property-statement.md)
- [<span data-ttu-id="5ed1b-144">Sub 문</span><span class="sxs-lookup"><span data-stu-id="5ed1b-144">Sub Statement</span></span>](../statements/sub-statement.md)
  
## <a name="see-also"></a><span data-ttu-id="5ed1b-145">참조</span><span class="sxs-lookup"><span data-stu-id="5ed1b-145">See also</span></span>

- [<span data-ttu-id="5ed1b-146">Overloads</span><span class="sxs-lookup"><span data-stu-id="5ed1b-146">Shadows</span></span>](shadows.md)
- [<span data-ttu-id="5ed1b-147">정적인</span><span class="sxs-lookup"><span data-stu-id="5ed1b-147">Static</span></span>](static.md)
- [<span data-ttu-id="5ed1b-148">Visual Basic의 수명</span><span class="sxs-lookup"><span data-stu-id="5ed1b-148">Lifetime in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/lifetime.md)
- [<span data-ttu-id="5ed1b-149">절차</span><span class="sxs-lookup"><span data-stu-id="5ed1b-149">Procedures</span></span>](../../programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="5ed1b-150">구조체</span><span class="sxs-lookup"><span data-stu-id="5ed1b-150">Structures</span></span>](../../programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="5ed1b-151">개체 및 클래스</span><span class="sxs-lookup"><span data-stu-id="5ed1b-151">Objects and Classes</span></span>](../../programming-guide/language-features/objects-and-classes/index.md)
