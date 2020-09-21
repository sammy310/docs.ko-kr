---
title: 자동으로 구현된 속성 - C# 프로그래밍 가이드
description: C#에서 자동으로 구현된 속성의 경우 컴파일러는 속성의 get 및 set 접근자를 통해서만 액세스하는 전용 익명 지원 필드를 만듭니다.
ms.date: 01/31/2020
helpviewer_keywords:
- auto-implemented properties [C#]
- properties [C#], auto-implemented
ms.assetid: aa55fa97-ccec-431f-b5e9-5ac789fd32b7
ms.openlocfilehash: 72f774d84266292412be9b954fc206debc8ac55e
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555902"
---
# <a name="auto-implemented-properties-c-programming-guide"></a><span data-ttu-id="011d1-103">자동으로 구현된 속성(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="011d1-103">Auto-Implemented Properties (C# Programming Guide)</span></span>

<span data-ttu-id="011d1-104">C# 3.0 이상에서는 속성 접근자에 추가적인 논리가 필요하지 않을 경우 자동 구현 속성을 통해 속성 선언이 더 간결해집니다.</span><span class="sxs-lookup"><span data-stu-id="011d1-104">In C# 3.0 and later, auto-implemented properties make property-declaration more concise when no additional logic is required in the property accessors.</span></span> <span data-ttu-id="011d1-105">이를 통해 클라이언트 코드에서 개체를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="011d1-105">They also enable client code to create objects.</span></span> <span data-ttu-id="011d1-106">다음 예제와 같이 속성을 선언할 때 컴파일러는 속성의 `get` 및 `set` 접근자를 통해서만 액세스할 수 있는 전용 익명 지원 필드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="011d1-106">When you declare a property as shown in the following example, the compiler creates a private, anonymous backing field that can only be accessed through the property's `get` and `set` accessors.</span></span>
  
## <a name="example"></a><span data-ttu-id="011d1-107">예제</span><span class="sxs-lookup"><span data-stu-id="011d1-107">Example</span></span>

<span data-ttu-id="011d1-108">다음 예제에서는 일부 자동 구현 속성이 있는 간단한 클래스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="011d1-108">The following example shows a simple class that has some auto-implemented properties:</span></span>  

[!code-csharp[csProgGuideLINQ#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#28)]  

<span data-ttu-id="011d1-109">인터페이스에서는 자동 구현 속성을 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="011d1-109">You can't declare auto-implemented properties in interfaces.</span></span> <span data-ttu-id="011d1-110">자동 구현 속성은 private 인스턴스 지원 필드를 선언하는데, 인터페이스는 인스턴스 필드를 선언할 수 없기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="011d1-110">Auto-implemented properties declare a private instance backing field, and interfaces may not declare instance fields.</span></span> <span data-ttu-id="011d1-111">인터페이스에서 본문을 정의하지 않고 속성을 선언하면 해당 인터페이스를 구현하는 각 형식에 의해 구현되어야 하는 접근자와 함께 속성이 선언됩니다.</span><span class="sxs-lookup"><span data-stu-id="011d1-111">Declaring a property in an interface without defining a body declares a property with accessors that must be implemented by each type that implements that interface.</span></span>

<span data-ttu-id="011d1-112">C# 6 이상 버전에서는 필드와 유사하게 자동 구현 속성을 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="011d1-112">In C# 6 and later, you can initialize auto-implemented properties similarly to fields:</span></span>  

```csharp  
public string FirstName { get; set; } = "Jane";  
```  

<span data-ttu-id="011d1-113">앞의 예제에 표시된 클래스는 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="011d1-113">The class that is shown in the previous example is mutable.</span></span> <span data-ttu-id="011d1-114">클라이언트 코드에서는 개체가 만들어진 후에 개체의 값을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="011d1-114">Client code can change the values in objects after creation.</span></span> <span data-ttu-id="011d1-115">데이터 및 중요 동작(메서드)을 포함하는 복잡한 클래스에는 public 속성이 필요한 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="011d1-115">In complex classes that contain significant behavior (methods) as well as data, it's often necessary to have public properties.</span></span> <span data-ttu-id="011d1-116">그러나 값 집합(데이터)만 캡슐화하고 동작이 적거나 없는 작은 클래스나 구조체의 경우 set 접근자를 [private](../../language-reference/keywords/private.md)로 선언하거나(소비자에 대한 변경 불가능) get 접근자만 선언하여(생성자를 제외한 모든 위치에서 변경 불가능) 개체를 변경 불가능으로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="011d1-116">However, for small classes or structs that just encapsulate a set of values (data) and have little or no behaviors, you should either make the objects immutable by declaring the set accessor as [private](../../language-reference/keywords/private.md) (immutable to consumers) or by declaring only a get accessor (immutable everywhere except the constructor).</span></span>  <span data-ttu-id="011d1-117">자세한 내용은 [자동으로 구현된 속성을 사용하여 간단한 클래스를 구현하는 방법](./how-to-implement-a-lightweight-class-with-auto-implemented-properties.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="011d1-117">For more information, see [How to implement a lightweight class with auto-implemented properties](./how-to-implement-a-lightweight-class-with-auto-implemented-properties.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="011d1-118">참조</span><span class="sxs-lookup"><span data-stu-id="011d1-118">See also</span></span>

- [<span data-ttu-id="011d1-119">속성</span><span class="sxs-lookup"><span data-stu-id="011d1-119">Properties</span></span>](./properties.md)
- [<span data-ttu-id="011d1-120">한정자</span><span class="sxs-lookup"><span data-stu-id="011d1-120">Modifiers</span></span>](../../language-reference/keywords/index.md)
