---
title: 개체 식
description: 사용 하는 방법을 알아봅니다 F# 명명 된 형식을 새 만들려면 개체 식 추가 코드와 오버 헤드를 방지 하려는 경우 필요 합니다.
ms.date: 02/08/2019
ms.openlocfilehash: 63f2c1d7128721b7b8c744e4cf02d73c2a8b4a07
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59157854"
---
# <a name="object-expressions"></a><span data-ttu-id="3038e-103">개체 식</span><span class="sxs-lookup"><span data-stu-id="3038e-103">Object Expressions</span></span>

<span data-ttu-id="3038e-104">*식을 개체* 동적으로 생성 하는 익명 개체 형식의 새 인스턴스를 만드는 식입니다 되는 기존의 기본 형식, 인터페이스 또는 인터페이스의 집합 기반 합니다.</span><span class="sxs-lookup"><span data-stu-id="3038e-104">An *object expression* is an expression that creates a new instance of a dynamically created, anonymous object type that is based on an existing base type, interface, or set of interfaces.</span></span>

## <a name="syntax"></a><span data-ttu-id="3038e-105">구문</span><span class="sxs-lookup"><span data-stu-id="3038e-105">Syntax</span></span>

```fsharp
// When typename is a class:
{ new typename [type-params]arguments with
    member-definitions
    [ additional-interface-definitions ]
}
// When typename is not a class:
{ new typename [generic-type-args] with
    member-definitions
    [ additional-interface-definitions ]
}
```

## <a name="remarks"></a><span data-ttu-id="3038e-106">설명</span><span class="sxs-lookup"><span data-stu-id="3038e-106">Remarks</span></span>

<span data-ttu-id="3038e-107">위 구문에는 *typename* 은 기존 클래스 유형 또는 인터페이스 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="3038e-107">In the previous syntax, the *typename* represents an existing class type or interface type.</span></span> <span data-ttu-id="3038e-108">*형식-params* 선택적 제네릭 형식 매개 변수를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="3038e-108">*type-params* describes the optional generic type parameters.</span></span> <span data-ttu-id="3038e-109">합니다 *인수* 생성자 매개 변수를 필요로 하는 클래스 형식에만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3038e-109">The *arguments* are used only for class types, which require constructor parameters.</span></span> <span data-ttu-id="3038e-110">합니다 *멤버 정의* 기본 클래스 또는 인터페이스에서 추상 메서드의 구현 또는 기본 클래스 메서드를 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="3038e-110">The *member-definitions* are overrides of base class methods, or implementations of abstract methods from either a base class or an interface.</span></span>

<span data-ttu-id="3038e-111">다음 예제에서는 여러 다른 유형의 개체 식 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3038e-111">The following example illustrates several different types of object expressions.</span></span>

```fsharp
// This object expression specifies a System.Object but overrides the
// ToString method.
let obj1 = { new System.Object() with member x.ToString() = "F#" }
printfn "%A" obj1

// This object expression implements the IFormattable interface.
let delimiter(delim1: string, delim2: string, value: string) =
    { new System.IFormattable with
        member x.ToString(format: string, provider: System.IFormatProvider) =
            if format = "D" then
                delim1 + value + delim2
            else
                value }

let obj2 = delimiter("{","}", "Bananas!");

printfn "%A" (System.String.Format("{0:D}", obj2))

// Define two interfaces
type IFirst =
  abstract F : unit -> unit
  abstract G : unit -> unit

type ISecond =
  inherit IFirst
  abstract H : unit -> unit
  abstract J : unit -> unit

// This object expression implements both interfaces.
let implementer() =
    { new ISecond with
        member this.H() = ()
        member this.J() = ()
      interface IFirst with
        member this.F() = ()
        member this.G() = () }
```

## <a name="using-object-expressions"></a><span data-ttu-id="3038e-112">개체 식 사용</span><span class="sxs-lookup"><span data-stu-id="3038e-112">Using Object Expressions</span></span>

<span data-ttu-id="3038e-113">추가 코드와 명명 된 형식을 새로 만드는 데 필요한는 오버 헤드를 방지 하려면 개체 식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3038e-113">You use object expressions when you want to avoid the extra code and overhead that is required to create a new, named type.</span></span> <span data-ttu-id="3038e-114">개체 식을 사용 하 여 프로그램에서 생성 하는 형식의 수를 최소화 하는 경우 코드 줄의 수를 줄일 수 있으며 형식의 불필요 한 확산을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3038e-114">If you use object expressions to minimize the number of types created in a program, you can reduce the number of lines of code and prevent the unnecessary proliferation of types.</span></span> <span data-ttu-id="3038e-115">다양 한 형식을 특정 상황을 처리할 수만 만드는 대신 기존 형식을 사용자 지정 하거나 특정 사례에 대 한 인터페이스의 적절 한 구현을 제공 하는 개체 식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3038e-115">Instead of creating many types just to handle specific situations, you can use an object expression that customizes an existing type or provides an appropriate implementation of an interface for the specific case at hand.</span></span>

## <a name="see-also"></a><span data-ttu-id="3038e-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="3038e-116">See also</span></span>

- [<span data-ttu-id="3038e-117">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="3038e-117">F# Language Reference</span></span>](index.md)
