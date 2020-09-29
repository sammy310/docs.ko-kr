---
title: 사용자 지정 특성 만들기(C#)
description: Attribute 클래스에서 파생되는 특성 클래스를 정의하여 C#에서 사용자 지정 특성을 작성하는 방법에 대해 알아봅니다.
ms.date: 07/20/2015
ms.assetid: 500e1977-c6de-462d-abce-78a0eb1eda22
ms.openlocfilehash: 6946b707134b2bdbc245b8786f144517a5870440
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202606"
---
# <a name="creating-custom-attributes-c"></a><span data-ttu-id="3cce1-103">사용자 지정 특성 만들기(C#)</span><span class="sxs-lookup"><span data-stu-id="3cce1-103">Creating Custom Attributes (C#)</span></span>

<span data-ttu-id="3cce1-104">메타데이터를 통해 특성의 정의를 빠르고 쉽게 식별할 수 있도록 해주는 <xref:System.Attribute>로부터 직접적으로 또는 간접적으로 상속한 특성 클래스를 정의하여 사용자 지정 특성을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3cce1-104">You can create your own custom attributes by defining an attribute class, a class that derives directly or indirectly from <xref:System.Attribute>, which makes identifying attribute definitions in metadata fast and easy.</span></span> <span data-ttu-id="3cce1-105">형식을 작성한 프로그래머의 이름을 형식에 태그로 지정한다고 가정해봅시다.</span><span class="sxs-lookup"><span data-stu-id="3cce1-105">Suppose you want to tag types with the name of the programmer who wrote the type.</span></span> <span data-ttu-id="3cce1-106">사용자 지정 `Author` 특성 클래스를 아래와 같이 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3cce1-106">You might define a custom `Author` attribute class:</span></span>  
  
```csharp  
[System.AttributeUsage(System.AttributeTargets.Class |  
                       System.AttributeTargets.Struct)  
]  
public class AuthorAttribute : System.Attribute  
{  
    private string name;  
    public double version;  
  
    public AuthorAttribute(string name)  
    {  
        this.name = name;  
        version = 1.0;  
    }  
}  
```  
  
 <span data-ttu-id="3cce1-107">클래스 이름 `AuthorAttribute`는 특성의 이름인 `Author`와 `Attribute` 접미사입니다.</span><span class="sxs-lookup"><span data-stu-id="3cce1-107">The class name `AuthorAttribute` is the attribute's name, `Author`, plus the `Attribute` suffix.</span></span> <span data-ttu-id="3cce1-108">이 클래스는 `System.Attribute`를 상속하므로 사용자 지정 특성 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="3cce1-108">It is derived from `System.Attribute`, so it is a custom attribute class.</span></span> <span data-ttu-id="3cce1-109">생성자의 매개 변수는 사용자 지정 특성의 위치 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="3cce1-109">The constructor's parameters are the custom attribute's positional parameters.</span></span> <span data-ttu-id="3cce1-110">이 예제에서는 `name`이 위치 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="3cce1-110">In this example, `name` is a positional parameter.</span></span> <span data-ttu-id="3cce1-111">모든 public 읽기-쓰기 필드 또는 속성은 명명된 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="3cce1-111">Any public read-write fields or properties are named parameters.</span></span> <span data-ttu-id="3cce1-112">이 경우에는 `version`이 유일한 명명된 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="3cce1-112">In this case, `version` is the only named parameter.</span></span> <span data-ttu-id="3cce1-113">클래스 및 `struct` 선언에서만 `Author` 특성을 유효하게 설정하려면 `AttributeUsage` 특성을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cce1-113">Note the use of the `AttributeUsage` attribute to make the `Author` attribute valid only on class and `struct` declarations.</span></span>  
  
 <span data-ttu-id="3cce1-114">이 새로운 특성은 다음과 같이 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3cce1-114">You could use this new attribute as follows:</span></span>  
  
```csharp  
[Author("P. Ackerman", version = 1.1)]  
class SampleClass  
{  
    // P. Ackerman's code goes here...  
}  
```  
  
 <span data-ttu-id="3cce1-115">`AttributeUsage`에는 사용자 지정 특성을 한 번 또는 여러 번 사용하도록 설정하기 위해 사용하는 명명된 매개 변수인 `AllowMultiple`이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3cce1-115">`AttributeUsage` has a named parameter, `AllowMultiple`, with which you can make a custom attribute single-use or multiuse.</span></span> <span data-ttu-id="3cce1-116">다음 코드 예제에서는 다중 사용 특성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3cce1-116">In the following code example, a multiuse attribute is created.</span></span>  
  
```csharp  
[System.AttributeUsage(System.AttributeTargets.Class |  
                       System.AttributeTargets.Struct,  
                       AllowMultiple = true)  // multiuse attribute  
]  
public class AuthorAttribute : System.Attribute  
```  
  
 <span data-ttu-id="3cce1-117">다음 코드 예제에서는 같은 형식의 여러 특성이 한 클래스에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3cce1-117">In the following code example, multiple attributes of the same type are applied to a class.</span></span>  
  
```csharp  
[Author("P. Ackerman", version = 1.1)]  
[Author("R. Koch", version = 1.2)]  
class SampleClass  
{  
    // P. Ackerman's code goes here...  
    // R. Koch's code goes here...  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="3cce1-118">참조</span><span class="sxs-lookup"><span data-stu-id="3cce1-118">See also</span></span>

- <xref:System.Reflection>
- [<span data-ttu-id="3cce1-119">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="3cce1-119">C# Programming Guide</span></span>](../../index.md)
- [<span data-ttu-id="3cce1-120">사용자 지정 특성 작성</span><span class="sxs-lookup"><span data-stu-id="3cce1-120">Writing Custom Attributes</span></span>](../../../../standard/attributes/writing-custom-attributes.md)
- [<span data-ttu-id="3cce1-121">리플렉션(C#)</span><span class="sxs-lookup"><span data-stu-id="3cce1-121">Reflection (C#)</span></span>](../reflection.md)
- [<span data-ttu-id="3cce1-122">특성(C#)</span><span class="sxs-lookup"><span data-stu-id="3cce1-122">Attributes (C#)</span></span>](./index.md)
- [<span data-ttu-id="3cce1-123">리플렉션을 사용하여 특성 액세스(C#)</span><span class="sxs-lookup"><span data-stu-id="3cce1-123">Accessing Attributes by Using Reflection (C#)</span></span>](./accessing-attributes-by-using-reflection.md)
- [<span data-ttu-id="3cce1-124">AttributeUsage(C#)</span><span class="sxs-lookup"><span data-stu-id="3cce1-124">AttributeUsage (C#)</span></span>](../../../language-reference/attributes/general.md)
