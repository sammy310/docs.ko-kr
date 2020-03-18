---
title: 열거형 형식 대신 열거형 클래스 사용
description: 컨테이너화된 .NET 애플리케이션용 .NET 마이크로 서비스 아키텍처 | 후자의 몇 가지 제한 사항을 해결하는 방법으로 열거형 대신 열거형 클래스를 사용하는 방법을 배웁니다.
ms.date: 10/08/2018
ms.openlocfilehash: fb2cbcd744f29c70a86e6f3300721934192eb752
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "78847182"
---
# <a name="use-enumeration-classes-instead-of-enum-types"></a><span data-ttu-id="6fd09-103">열거형 형식 대신 열거형 클래스 사용하기</span><span class="sxs-lookup"><span data-stu-id="6fd09-103">Use enumeration classes instead of enum types</span></span>

<span data-ttu-id="6fd09-104">[열거형](../../../csharp/language-reference/builtin-types/enum.md)(또는 줄여서 *열거형 형식*)은 정수 형식에 대한 씬 언어 래퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="6fd09-104">[Enumerations](../../../csharp/language-reference/builtin-types/enum.md) (or *enum types* for short) are a thin language wrapper around an integral type.</span></span> <span data-ttu-id="6fd09-105">닫힌 값 집합에서 값을 저장하는 경우 해당 사용을 제한해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fd09-105">You might want to limit their use to when you are storing one value from a closed set of values.</span></span> <span data-ttu-id="6fd09-106">크기(소규모, 중간 규모, 대규모)를 기반으로 하는 분류가 좋은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="6fd09-106">Classification based on sizes (small, medium, large) is a good example.</span></span> <span data-ttu-id="6fd09-107">제어 흐름 또는 추가 추상화에 열거형을 사용하는 것은 [코드 스멜](https://deviq.com/code-smells/)일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fd09-107">Using enums for control flow or more robust abstractions can be a [code smell](https://deviq.com/code-smells/).</span></span> <span data-ttu-id="6fd09-108">이 형식으로 사용하면 열거형의 값을 확인하는 여러 제어 흐름 문을 사용하여 취약한 코드가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="6fd09-108">This type of usage leads to fragile code with many control flow statements checking values of the enum.</span></span>

<span data-ttu-id="6fd09-109">대신 개체 지향 언어의 모든 풍부한 기능을 활성화하는 열거형 클래스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fd09-109">Instead, you can create Enumeration classes that enable all the rich features of an object-oriented language.</span></span>

<span data-ttu-id="6fd09-110">그러나 중요한 항목은 아니며 대부분의 경우에 간단한 설명을 위해 기본 설정된 기본 [열거형 형식](../../../csharp/language-reference/builtin-types/enum.md)을 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fd09-110">However, this isn't a critical topic and in many cases, for simplicity, you can still use regular [enum types](../../../csharp/language-reference/builtin-types/enum.md) if that's your preference.</span></span> <span data-ttu-id="6fd09-111">그래도 열거형 클래스의 사용은 업무와 연관된 개념과 더 관련되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fd09-111">Anyway, the use of enumeration classes is more related to business-related concepts.</span></span>

## <a name="implement-an-enumeration-base-class"></a><span data-ttu-id="6fd09-112">열거형 기본 클래스 구현하기</span><span class="sxs-lookup"><span data-stu-id="6fd09-112">Implement an Enumeration base class</span></span>

<span data-ttu-id="6fd09-113">다음 예제와 같이 eShopOnContainers의 마이크로 서비스를 정렬하면 샘플 열거형 기본 클래스 구현을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6fd09-113">The ordering microservice in eShopOnContainers provides a sample Enumeration base class implementation, as shown in the following example:</span></span>

```csharp
public abstract class Enumeration : IComparable
{
    public string Name { get; private set; }

    public int Id { get; private set; }

    protected Enumeration(int id, string name)
    {
        Id = id;
        Name = name;
    }

    public override string ToString() => Name;

    public static IEnumerable<T> GetAll<T>() where T : Enumeration
    {
        var fields = typeof(T).GetFields(BindingFlags.Public |
                                         BindingFlags.Static |
                                         BindingFlags.DeclaredOnly);

        return fields.Select(f => f.GetValue(null)).Cast<T>();
    }

    public override bool Equals(object obj)
    {
        var otherValue = obj as Enumeration;

        if (otherValue == null)
            return false;

        var typeMatches = GetType().Equals(obj.GetType());
        var valueMatches = Id.Equals(otherValue.Id);

        return typeMatches && valueMatches;
    }

    public int CompareTo(object other) => Id.CompareTo(((Enumeration)other).Id);

    // Other utility methods ...
}
```

<span data-ttu-id="6fd09-114">다음 `CardType` : `Enumeration` 클래스와 같이 모든 엔터티 또는 값 개체의 형식으로 이 클래스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fd09-114">You can use this class as a type in any entity or value object, as for the following `CardType` : `Enumeration` class:</span></span>

```csharp
public class CardType : Enumeration
{
    public static readonly CardType Amex = new CardType(1, "Amex");
    public static readonly CardType Visa = new CardType(2, "Visa");
    public static readonly CardType MasterCard = new CardType(3, "MasterCard");

    public CardType(int id, string name)
        : base(id, name)
    {
    }
}
```

## <a name="additional-resources"></a><span data-ttu-id="6fd09-115">추가 자료</span><span class="sxs-lookup"><span data-stu-id="6fd09-115">Additional resources</span></span>

- <span data-ttu-id="6fd09-116">**Jimmy Bogard. 열거형 클래스** </span><span class="sxs-lookup"><span data-stu-id="6fd09-116">**Jimmy Bogard. Enumeration classes** </span></span>\
  <https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/>

- <span data-ttu-id="6fd09-117">**Steve Smith. C#의 열거형 대체 항목** </span><span class="sxs-lookup"><span data-stu-id="6fd09-117">**Steve Smith. Enum Alternatives in C#** </span></span>\
  <https://ardalis.com/enum-alternatives-in-c>

- <span data-ttu-id="6fd09-118">**Enumeration.cs.**</span><span class="sxs-lookup"><span data-stu-id="6fd09-118">**Enumeration.cs.**</span></span> <span data-ttu-id="6fd09-119">eShopOnContainers의 기본 열거형 클래스</span><span class="sxs-lookup"><span data-stu-id="6fd09-119">Base Enumeration class in eShopOnContainers </span></span>\
  <https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs>

- <span data-ttu-id="6fd09-120">**CardType.cs**.</span><span class="sxs-lookup"><span data-stu-id="6fd09-120">**CardType.cs**.</span></span> <span data-ttu-id="6fd09-121">eShopOnContainers의 샘플 열거형 클래스</span><span class="sxs-lookup"><span data-stu-id="6fd09-121">Sample Enumeration class in eShopOnContainers.</span></span> \
  <https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.Domain/AggregatesModel/BuyerAggregate/CardType.cs>

- <span data-ttu-id="6fd09-122">**SmartEnum**.</span><span class="sxs-lookup"><span data-stu-id="6fd09-122">**SmartEnum**.</span></span> <span data-ttu-id="6fd09-123">Ardalis-.NET에서 더 강력한 형식의 스마트한 열거형을 생성하는데 도움을 준 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="6fd09-123">Ardalis - Classes to help produce strongly typed smarter enums in .NET.</span></span> \
  <https://www.nuget.org/packages/Ardalis.SmartEnum/>

>[!div class="step-by-step"]
><span data-ttu-id="6fd09-124">[이전](implement-value-objects.md)
>[다음](domain-model-layer-validations.md)</span><span class="sxs-lookup"><span data-stu-id="6fd09-124">[Previous](implement-value-objects.md)
[Next](domain-model-layer-validations.md)</span></span>
