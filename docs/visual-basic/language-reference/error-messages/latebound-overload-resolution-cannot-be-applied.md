---
title: 액세스 인스턴스가 인터페이스 형식이므로 런타임에 바인딩 오버로드 확인을 '<procedurename>'에 적용할 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc30933
- bc30933
helpviewer_keywords:
- overload resolution [Visual Basic], with late-bound argument
- BC30933
ms.assetid: 8182eea0-dd34-4d6e-9ca0-41d8713e9dc4
ms.openlocfilehash: 1fe3c4a29b542302b3615459142a3c565aa8244f
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/26/2019
ms.locfileid: "68513019"
---
# <a name="latebound-overload-resolution-cannot-be-applied-to-procedurename-because-the-accessing-instance-is-an-interface-type"></a><span data-ttu-id="68305-102">액세스 하는 인스턴스가 인터페이스 형식 이므로 런타임에\<바인딩 오버 로드 확인을 ' e > '에 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="68305-102">Latebound overload resolution cannot be applied to '\<procedurename>' because the accessing instance is an interface type</span></span>

<span data-ttu-id="68305-103">컴파일러가 오버 로드 된 속성 또는 프로시저에 대 한 참조를 확인 하려고 시도 하지만 인수가 형식이 `Object` 고 참조 하는 개체에 인터페이스의 데이터 형식이 있으므로 참조가 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="68305-103">The compiler is attempting to resolve a reference to an overloaded property or procedure, but the reference fails because an argument is of type `Object` and the referring object has the data type of an interface.</span></span> <span data-ttu-id="68305-104">인수 `Object` 를 통해 컴파일러가 참조를 런타임에 바인딩된 것으로 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="68305-104">The `Object` argument forces the compiler to resolve the reference as late-bound.</span></span>

<span data-ttu-id="68305-105">이러한 경우 컴파일러는 기본 인터페이스를 통하지 않고 구현 클래스를 통해 오버 로드를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="68305-105">In these circumstances, the compiler resolves the overload through the implementing class instead of through the underlying interface.</span></span> <span data-ttu-id="68305-106">클래스가 오버 로드 된 버전 중 하나의 이름을 바꾸면 컴파일러가 해당 버전의 이름이 다르기 때문에 오버 로드로 간주 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="68305-106">If the class renames one of the overloaded versions, the compiler does not consider that version to be an overload because its name is different.</span></span> <span data-ttu-id="68305-107">이렇게 하면 참조를 확인 하는 데 올바른 선택이 될 수 있는 경우 컴파일러에서 이름이 바뀐 버전을 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="68305-107">This in turn causes the compiler to ignore the renamed version when it might have been the correct choice to resolve the reference.</span></span>

<span data-ttu-id="68305-108">**오류 ID:** BC30933</span><span class="sxs-lookup"><span data-stu-id="68305-108">**Error ID:** BC30933</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="68305-109">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="68305-109">To correct this error</span></span>

- <span data-ttu-id="68305-110">를 `CType` 사용 하 여의 `Object` 인수를 호출 하려는 오버 로드의 서명으로 지정 된 형식으로 캐스팅 합니다.</span><span class="sxs-lookup"><span data-stu-id="68305-110">Use `CType` to cast the argument from `Object` to the type specified by the signature of the overload you want to call.</span></span>

  <span data-ttu-id="68305-111">참조 하는 개체를 기본 인터페이스로 캐스팅 하는 것은 도움이 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="68305-111">Note that it does not help to cast the referring object to the underlying interface.</span></span> <span data-ttu-id="68305-112">이 오류를 방지 하려면 인수를 캐스팅 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="68305-112">You must cast the argument to avoid this error.</span></span>

## <a name="example"></a><span data-ttu-id="68305-113">예제</span><span class="sxs-lookup"><span data-stu-id="68305-113">Example</span></span>

<span data-ttu-id="68305-114">다음 예제에서는 컴파일 타임에이 오류가 발생 `Sub` 하는 오버 로드 된 프로시저를 호출 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="68305-114">The following example shows a call to an overloaded `Sub` procedure that causes this error at compile time.</span></span>

```vb
Module m1
    Interface i1
        Sub s1(ByVal p1 As Integer)
        Sub s1(ByVal p1 As Double)
    End Interface
    Class c1
        Implements i1
        Public Overloads Sub s1(ByVal p1 As Integer) Implements i1.s1
        End Sub
        Public Overloads Sub s2(ByVal p1 As Double) Implements i1.s1
        End Sub
    End Class
    Sub Main()
        Dim refer As i1 = New c1
        Dim o1 As Object = 3.1415
        ' The following reference is INVALID and causes a compiler error.
        refer.s1(o1)
    End Sub
End Module
```

<span data-ttu-id="68305-115">앞의 예제에서 컴파일러가 작성 된 대로에 대 `s1` 한 호출을 허용 하는 경우, 확인은 인터페이스 `i1`대신 클래스 `c1` 를 통해 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="68305-115">In the preceding example, if the compiler allowed the call to `s1` as written, the resolution would take place through the class `c1` instead of the interface `i1`.</span></span> <span data-ttu-id="68305-116">이는에서 정의한 대로 `s2` `i1`올바른 선택 이더라도 컴파일러가의 `c1`이름을 다르게 고려 하지 않는다는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="68305-116">This would mean that the compiler would not consider `s2` because its name is different in `c1`, even though it is the correct choice as defined by `i1`.</span></span>

<span data-ttu-id="68305-117">다음 코드 줄 중 하나에 대 한 호출을 변경 하 여 오류를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68305-117">You can correct the error by changing the call to either of the following lines of code:</span></span>

```vb
refer.s1(CType(o1, Integer))
refer.s1(CType(o1, Double))
```

<span data-ttu-id="68305-118">위의 각 코드 줄은 변수 `Object` `o1` 를 오버 로드에 대해 정의 된 매개 변수 형식 중 하나로 명시적으로 캐스팅 합니다.</span><span class="sxs-lookup"><span data-stu-id="68305-118">Each of the preceding lines of code explicitly casts the `Object` variable `o1` to one of the parameter types defined for the overloads.</span></span>

## <a name="see-also"></a><span data-ttu-id="68305-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="68305-119">See also</span></span>

- [<span data-ttu-id="68305-120">프로시저 오버로딩</span><span class="sxs-lookup"><span data-stu-id="68305-120">Procedure Overloading</span></span>](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)
- [<span data-ttu-id="68305-121">오버로드 확인</span><span class="sxs-lookup"><span data-stu-id="68305-121">Overload Resolution</span></span>](../../../visual-basic/programming-guide/language-features/procedures/overload-resolution.md)
- [<span data-ttu-id="68305-122">CType 함수</span><span class="sxs-lookup"><span data-stu-id="68305-122">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)
