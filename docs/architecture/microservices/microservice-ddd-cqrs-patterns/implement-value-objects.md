---
title: 값 개체 구현
description: 컨테이너화된 .NET 애플리케이션의 .NET 마이크로 서비스 아키텍처 | 새로운 Entity Framework 기능을 사용하여 값 개체를 구현하는 세부 정보 및 옵션을 가져옵니다.
ms.date: 01/30/2020
ms.openlocfilehash: 4ace5c141b1cbd2dcfefb7ea7165a4006b130479
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "77502510"
---
# <a name="implement-value-objects"></a><span data-ttu-id="61ee0-103">값 개체 구현</span><span class="sxs-lookup"><span data-stu-id="61ee0-103">Implement value objects</span></span>

<span data-ttu-id="61ee0-104">엔터티 및 집계에 대한 이전 섹션에서 설명한 대로, ID는 엔터티의 근본입니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-104">As discussed in earlier sections about entities and aggregates, identity is fundamental for entities.</span></span> <span data-ttu-id="61ee0-105">그러나 시스템에는 값 개체처럼 ID 및 ID 추적이 필요 없는 여러 개체와 데이터 항목이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-105">However, there are many objects and data items in a system that do not require an identity and identity tracking, such as value objects.</span></span>

<span data-ttu-id="61ee0-106">값 개체는 다른 엔터티를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-106">A value object can reference other entities.</span></span> <span data-ttu-id="61ee0-107">예를 들어 한 지점에서 다른 지점으로 이동하는 경로를 생성하는 애플리케이션에서는 해당 경로가 값 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-107">For example, in an application that generates a route that describes how to get from one point to another, that route would be a value object.</span></span> <span data-ttu-id="61ee0-108">특정 경로에 있는 지점의 스냅샷이 되겠지만, 이 제안 경로는 내부적으로 도시, 로드 등의 엔터티를 참조하더라도 ID를 갖지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-108">It would be a snapshot of points on a specific route, but this suggested route would not have an identity, even though internally it might refer to entities like City, Road, etc.</span></span>

<span data-ttu-id="61ee0-109">그림 7-13은 순서 집계 내의 주소 값 개체를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-109">Figure 7-13 shows the Address value object within the Order aggregate.</span></span>

![순서 집계 내의 주소 값 개체를 보여주는 다이어그램입니다.](./media/implement-value-objects/value-object-within-aggregate.png)

<span data-ttu-id="61ee0-111">**그림 7-13**</span><span class="sxs-lookup"><span data-stu-id="61ee0-111">**Figure 7-13**.</span></span> <span data-ttu-id="61ee0-112">순서 집계 내부의 주소 값 개체</span><span class="sxs-lookup"><span data-stu-id="61ee0-112">Address value object within the Order aggregate</span></span>

<span data-ttu-id="61ee0-113">그림 7-13에 표시된 것처럼, 엔터티는 일반적으로 여러 특성으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-113">As shown in Figure 7-13, an entity is usually composed of multiple attributes.</span></span> <span data-ttu-id="61ee0-114">예를 들어 `Order` 엔터티는 ID가 있는 엔터티로 모델링하고 내부적으로 OrderId, OrderDate, OrderItems 등의 특성 집합으로 구성할 수 있습니다. 하지만 국가/지역, 거리, 도시 등으로 구성되고 이 도메인의 ID를 갖지 않는 복잡한 값인 주소는 값 개체로 모델링되고 처리되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-114">For example, the `Order` entity can be modeled as an entity with an identity and composed internally of a set of attributes such as OrderId, OrderDate, OrderItems, etc. But the address, which is simply a complex-value composed of country/region, street, city, etc. and has no identity in this domain, must be modeled and treated as a value object.</span></span>

## <a name="important-characteristics-of-value-objects"></a><span data-ttu-id="61ee0-115">값 개체의 중요한 특징</span><span class="sxs-lookup"><span data-stu-id="61ee0-115">Important characteristics of value objects</span></span>

<span data-ttu-id="61ee0-116">값 개체의 두 가지 주요 특징이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-116">There are two main characteristics for value objects:</span></span>

- <span data-ttu-id="61ee0-117">ID가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-117">They have no identity.</span></span>

- <span data-ttu-id="61ee0-118">변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-118">They are immutable.</span></span>

<span data-ttu-id="61ee0-119">첫 번째 특징은 이미 설명했습니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-119">The first characteristic was already discussed.</span></span> <span data-ttu-id="61ee0-120">변경 불가능은 중요한 요구 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-120">Immutability is an important requirement.</span></span> <span data-ttu-id="61ee0-121">일단 개체가 생성된 후에는 값 개체의 값을 변경할 수 없어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-121">The values of a value object must be immutable once the object is created.</span></span> <span data-ttu-id="61ee0-122">따라서 개체가 생성될 때 필요한 값을 제공해야 하지만, 개체의 수명 주기 동안 값이 변경되는 것을 허용하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-122">Therefore, when the object is constructed, you must provide the required values, but you must not allow them to change during the object’s lifetime.</span></span>

<span data-ttu-id="61ee0-123">값 개체의 변경 불가능이라는 성질 덕분에 값 개체를 사용하여 성능을 높일 수 있는 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-123">Value objects allow you to perform certain tricks for performance, thanks to their immutable nature.</span></span> <span data-ttu-id="61ee0-124">특히 수천 개의 값 개체 인스턴스가 있고 그 중 많은 수가 같은 값을 갖는 시스템에서 더욱 그렇습니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-124">This is especially true in systems where there may be thousands of value object instances, many of which have the same values.</span></span> <span data-ttu-id="61ee0-125">변경 불가능이라는 성질 덕분에 재사용이 가능합니다. 값이 같고 ID가 없기 때문에 교환이 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-125">Their immutable nature allows them to be reused; they can be interchangeable objects, since their values are the same and they have no identity.</span></span> <span data-ttu-id="61ee0-126">이와 같은 유형의 최적화는 때때로 느리게 실행되는 소프트웨어와 고성능 소프트웨어 간의 차이를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-126">This type of optimization can sometimes make a difference between software that runs slowly and software with good performance.</span></span> <span data-ttu-id="61ee0-127">물론, 이 모든 것은 애플리케이션 환경과 배포 상황에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-127">Of course, all these cases depend on the application environment and deployment context.</span></span>

## <a name="value-object-implementation-in-c"></a><span data-ttu-id="61ee0-128">C에서 값 개체 구현\#</span><span class="sxs-lookup"><span data-stu-id="61ee0-128">Value object implementation in C\#</span></span>

<span data-ttu-id="61ee0-129">구현의 측면에서, 모든 특성(값 개체는 ID를 기반으로 할 수 없으므로)과 기타 기본 특성 간의 동등함처럼 기본 유틸리티 메서드가 있는 개체 기본 클래스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-129">In terms of implementation, you can have a value object base class that has basic utility methods like equality based on comparison between all the attributes (since a value object must not be based on identity) and other fundamental characteristics.</span></span> <span data-ttu-id="61ee0-130">다음 예제에서는 eShopOnContainers의 주문 마이크로 서비스에 사용되는 값 개체 기본 클래스를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-130">The following example shows a value object base class used in the ordering microservice from eShopOnContainers.</span></span>

```csharp
public abstract class ValueObject
{
    protected static bool EqualOperator(ValueObject left, ValueObject right)
    {
        if (ReferenceEquals(left, null) ^ ReferenceEquals(right, null))
        {
            return false;
        }
        return ReferenceEquals(left, null) || left.Equals(right);
    }

    protected static bool NotEqualOperator(ValueObject left, ValueObject right)
    {
        return !(EqualOperator(left, right));
    }

    protected abstract IEnumerable<object> GetAtomicValues();

    public override bool Equals(object obj)
    {
        if (obj == null || obj.GetType() != GetType())
        {
            return false;
        }

        ValueObject other = (ValueObject)obj;
        IEnumerator<object> thisValues = GetAtomicValues().GetEnumerator();
        IEnumerator<object> otherValues = other.GetAtomicValues().GetEnumerator();
        while (thisValues.MoveNext() && otherValues.MoveNext())
        {
            if (ReferenceEquals(thisValues.Current, null) ^
                ReferenceEquals(otherValues.Current, null))
            {
                return false;
            }

            if (thisValues.Current != null &&
                !thisValues.Current.Equals(otherValues.Current))
            {
                return false;
            }
        }
        return !thisValues.MoveNext() && !otherValues.MoveNext();
    }

    public override int GetHashCode()
    {
        return GetAtomicValues()
         .Select(x => x != null ? x.GetHashCode() : 0)
         .Aggregate((x, y) => x ^ y);
    }
    // Other utility methods
}
```

<span data-ttu-id="61ee0-131">다음 예제의 주소 값 개체와 마찬가지로, 실제 값 개체를 구현할 때 이 클래스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-131">You can use this class when implementing your actual value object, as with the Address value object shown in the following example:</span></span>

```csharp
public class Address : ValueObject
{
    public String Street { get; private set; }
    public String City { get; private set; }
    public String State { get; private set; }
    public String Country { get; private set; }
    public String ZipCode { get; private set; }

    private Address() { }

    public Address(string street, string city, string state, string country, string zipcode)
    {
        Street = street;
        City = city;
        State = state;
        Country = country;
        ZipCode = zipcode;
    }

    protected override IEnumerable<object> GetAtomicValues()
    {
        // Using a yield return statement to return each element one at a time
        yield return Street;
        yield return City;
        yield return State;
        yield return Country;
        yield return ZipCode;
    }
}
```

<span data-ttu-id="61ee0-132">주소의 이 값 개체 구현에 ID가 없으며 따라서 Address 클래스 및 ValueObject 클래스에도 ID 필드가 없도록 하는 방법을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-132">You can see how this value object implementation of Address has no identity and therefore, no ID field, neither at the Address class not even at the ValueObject class.</span></span>

<span data-ttu-id="61ee0-133">ID가 없는 값 개체를 구현하는 데 크게 데 도움이 되는 EF Core 2.0까지는 클래스에 EF(Entity Framework)에서 사용할 ID 필드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-133">Having no ID field in a class to be used by Entity Framework (EF) was not possible until EF Core 2.0, which greatly helps to implement better value objects with no ID.</span></span> <span data-ttu-id="61ee0-134">정확한 다음 섹션의 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-134">That is precisely the explanation of the next section.</span></span>

<span data-ttu-id="61ee0-135">변경할 수 없는 개체 값이 읽기 전용(즉, 가져오기 전용 속성을 가짐)이라고 주장할 수 있고 실제로 그렇습니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-135">It could be argued that value objects, being immutable, should be read-only (that is, have get-only properties), and that’s indeed true.</span></span> <span data-ttu-id="61ee0-136">그러나 값 개체는 일반적으로 직렬화되고 역직렬화되어 메시지 큐를 거치고, 읽기 전용이므로 역직렬 변환기가 값을 할당하지 않도록 중지합니다. 따라서 값 개체를 읽기 전용이 충분히 실용적인 비공개 세트로 둡니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-136">However, value objects are usually serialized and deserialized to go through message queues, and being read-only stops the deserializer from assigning values, so we just leave them as private set which is read-only enough to be practical.</span></span>

## <a name="how-to-persist-value-objects-in-the-database-with-ef-core-20-and-later"></a><span data-ttu-id="61ee0-137">EF Core 2.0 이상을 사용하여 데이터베이스에서 개체 값을 유지하는 방법</span><span class="sxs-lookup"><span data-stu-id="61ee0-137">How to persist value objects in the database with EF Core 2.0 and later</span></span>

<span data-ttu-id="61ee0-138">도메인 모델에서 값 개체를 정의하는 방법을 알아보았습니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-138">You just saw how to define a value object in your domain model.</span></span> <span data-ttu-id="61ee0-139">하지만 일반적으로 ID가 있는 엔터티를 대상으로 하므로 Entity Framework Core를 사용하여 개체 값을 데이터베이스에 유지하려면 어떻게 해야 할까요?</span><span class="sxs-lookup"><span data-stu-id="61ee0-139">But how can you actually persist it into the database using Entity Framework Core since it usually targets entities with identity?</span></span>

### <a name="background-and-older-approaches-using-ef-core-11"></a><span data-ttu-id="61ee0-140">배경 지식 및 EF Core 1.1을 사용한 기존의 접근 방식</span><span class="sxs-lookup"><span data-stu-id="61ee0-140">Background and older approaches using EF Core 1.1</span></span>

<span data-ttu-id="61ee0-141">배경지식으로 알려드리자면, EF Core 1.0 및 1.1을 사용하는 경우 기존 .NET Framework의 EF 6.x에서 정의된 것처럼 [복합 형식](xref:System.ComponentModel.DataAnnotations.Schema.ComplexTypeAttribute)을 사용할 수 없다는 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-141">As background, a limitation when using EF Core 1.0 and 1.1 was that you could not use [complex types](xref:System.ComponentModel.DataAnnotations.Schema.ComplexTypeAttribute) as defined in EF 6.x in the traditional .NET Framework.</span></span> <span data-ttu-id="61ee0-142">따라서 EF Core 1.0 또는 1.1을 사용하는 경우 값 개체를 ID 필드가 있는 EF 엔터티로 저장해야 했습니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-142">Therefore, if using EF Core 1.0 or 1.1, you needed to store your value object as an EF entity with an ID field.</span></span> <span data-ttu-id="61ee0-143">그래서 마치 ID가 없는 값 개체처럼 보이기 때문에 ID를 숨겨서 값 개체의 ID가 도메인 모델에서 중요하지 않다는 점을 분명히 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-143">Then, so it looked more like a value object with no identity, you could hide its ID so you make clear that the identity of a value object is not important in the domain model.</span></span> <span data-ttu-id="61ee0-144">ID를 [섀도 속성](https://docs.microsoft.com/ef/core/modeling/shadow-properties )으로 사용하여 해당 ID를 숨길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-144">You could hide that ID by using the ID as a [shadow property](https://docs.microsoft.com/ef/core/modeling/shadow-properties ).</span></span> <span data-ttu-id="61ee0-145">모델에서 ID를 숨기는 구성이 EF 인프라 수준에서 설정되므로 도메인 모델에 대해 투명하다고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-145">Since that configuration for hiding the ID in the model is set up in the EF infrastructure level, it would be kind of transparent for your domain model.</span></span>

<span data-ttu-id="61ee0-146">eShopOnContainers 초기 버전(.NET Core 1.1)에서, EF Core 인프라에 필요한 숨겨진 ID는 DbContext 수준에서 인프라 프로젝트에 흐름 API를 사용하여 다음과 같은 방식으로 구현되었습니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-146">In the initial version of eShopOnContainers (.NET Core 1.1), the hidden ID needed by EF Core infrastructure was implemented in the following way in the DbContext level, using Fluent API at the infrastructure project.</span></span> <span data-ttu-id="61ee0-147">따라서 ID가 보기의 도메인 모델 관점에서 숨겨지더라도 인프라에 계속 존재합니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-147">Therefore, the ID was hidden from the domain model point of view, but still present in the infrastructure.</span></span>

```csharp
// Old approach with EF Core 1.1
// Fluent API within the OrderingContext:DbContext in the Infrastructure project
void ConfigureAddress(EntityTypeBuilder<Address> addressConfiguration)
{
    addressConfiguration.ToTable("address", DEFAULT_SCHEMA);

    addressConfiguration.Property<int>("Id")  // Id is a shadow property
        .IsRequired();
    addressConfiguration.HasKey("Id");   // Id is a shadow property
}
```

<span data-ttu-id="61ee0-148">그러나 값 개체가 데이터베이스에 유지되는 것은 다른 테이블의 일반 엔터티처럼 수행되었습니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-148">However, the persistence of that value object into the database was performed like a regular entity in a different table.</span></span>

<span data-ttu-id="61ee0-149">EF Core 2.0 이상에서는 값 개체를 유지하는 보다 나은 방법이 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-149">With EF Core 2.0 and later, there are new and better ways to persist value objects.</span></span>

## <a name="persist-value-objects-as-owned-entity-types-in-ef-core-20-and-later"></a><span data-ttu-id="61ee0-150">EF Core 2.0 이상에서 소유 엔터티 형식으로 값 개체 유지</span><span class="sxs-lookup"><span data-stu-id="61ee0-150">Persist value objects as owned entity types in EF Core 2.0 and later</span></span>

<span data-ttu-id="61ee0-151">DDD의 정식 값 개체 패턴과 EF Core의 소유된 엔터티 형식 사이에 차이가 있더라도 현재는 EF Core 2.0 이상을 사용하여 값 개체를 유지하는 것이 가장 좋은 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-151">Even with some gaps between the canonical value object pattern in DDD and the owned entity type in EF Core, it's currently the best way to persist value objects with EF Core 2.0 and later.</span></span> <span data-ttu-id="61ee0-152">제한 사항은 이 섹션의 마지막 부분에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-152">You can see limitations at the end of this section.</span></span>

<span data-ttu-id="61ee0-153">소유된 엔터티 형식 기능은 EF Core 버전 2.0부터 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-153">The owned entity type feature was added to EF Core since version 2.0.</span></span>

<span data-ttu-id="61ee0-154">소유된 엔터티 형식을 사용하면 엔터티 내의 값 개체처럼 도메인 모델에 명시적으로 정의된 고유 ID가 없고 속성으로 사용되는 형식을 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-154">An owned entity type allows you to map types that do not have their own identity explicitly defined in the domain model and are used as properties, such as a value object, within any of your entities.</span></span> <span data-ttu-id="61ee0-155">소유된 엔터티 형식은 다른 엔터티 형식과 동일한 CLR 형식을 공유합니다(즉, 일반 클래스임).</span><span class="sxs-lookup"><span data-stu-id="61ee0-155">An owned entity type shares the same CLR type with another entity type (that is, it’s just a regular class).</span></span> <span data-ttu-id="61ee0-156">정의 탐색을 포함하는 엔터티는 소유자 엔터티입니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-156">The entity containing the defining navigation is the owner entity.</span></span> <span data-ttu-id="61ee0-157">소유자를 쿼리할 때 소유된 형식은 기본적으로 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-157">When querying the owner, the owned types are included by default.</span></span>

<span data-ttu-id="61ee0-158">도메인 모델을 그냥 보면 소유된 형식에는 ID가 없는 것처럼 보입니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-158">Just by looking at the domain model, an owned type looks like it doesn’t have any identity.</span></span> <span data-ttu-id="61ee0-159">하지만 내부로 들어가면 소유된 형식에 ID가 있고 소유자 탐색 속성은 이 ID의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-159">However, under the covers, owned types do have identity, but the owner navigation property is part of this identity.</span></span>

<span data-ttu-id="61ee0-160">고유 형식의 인스턴스 ID가 오직 그 자체로만 구성되는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-160">The identity of instances of owned types is not completely their own.</span></span> <span data-ttu-id="61ee0-161">다음과 같은 세 가지 구성 요소로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-161">It consists of three components:</span></span>

- <span data-ttu-id="61ee0-162">소유자 ID</span><span class="sxs-lookup"><span data-stu-id="61ee0-162">The identity of the owner</span></span>

- <span data-ttu-id="61ee0-163">소유자 ID를 가리키는 탐색 속성</span><span class="sxs-lookup"><span data-stu-id="61ee0-163">The navigation property pointing to them</span></span>

- <span data-ttu-id="61ee0-164">소유된 형식의 컬렉션인 경우 독립 구성 요소(EF Core 2.2 이상에서 지원됨).</span><span class="sxs-lookup"><span data-stu-id="61ee0-164">In the case of collections of owned types, an independent component (supported in EF Core 2.2 and later).</span></span>

<span data-ttu-id="61ee0-165">예를 들어 eShopOnContainers의 주문 도메인 모델에서, 주문 엔터티의 일부로 주소 값 개체가 소유자 엔터티 내부의 소유된 엔터티 형식으로 구현되며, 이것이 주문 엔터티입니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-165">For example, in the Ordering domain model at eShopOnContainers, as part of the Order entity, the Address value object is implemented as an owned entity type within the owner entity, which is the Order entity.</span></span> <span data-ttu-id="61ee0-166">주소는 도메인 모델에 정의된 ID 속성이 없는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-166">Address is a type with no identity property defined in the domain model.</span></span> <span data-ttu-id="61ee0-167">특정 주문의 배송 주소를 지정하기 위한 Order 형식 속성으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-167">It is used as a property of the Order type to specify the shipping address for a particular order.</span></span>

<span data-ttu-id="61ee0-168">규칙에 따라, 소유된 형식에 대해 섀도 기본 키가 만들어지며 테이블 분할을 사용하여 소유자와 동일한 테이블에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-168">By convention, a shadow primary key is created for the owned type and it will be mapped to the same table as the owner by using table splitting.</span></span> <span data-ttu-id="61ee0-169">따라서 기존 .NET Framework의 EF6에서 복합 형식이 사용되는 방식과 유사하게 소유된 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-169">This allows to use owned types similarly to how complex types are used in EF6 in the traditional .NET Framework.</span></span>

<span data-ttu-id="61ee0-170">소유된 형식은 규칙에 따라 EF Core에서 절대로 검색되지 않으므로 명시적으로 선언해야 한다는 점을 기억해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-170">It is important to note that owned types are never discovered by convention in EF Core, so you have to declare them explicitly.</span></span>

<span data-ttu-id="61ee0-171">EShopOnContainers에서, OrderingContext.cs의 OnModelCreating() 메서드 내부에는 여러 인프라 구성이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-171">In eShopOnContainers, at the OrderingContext.cs, within the OnModelCreating() method, there are multiple infrastructure configuration being applied.</span></span> <span data-ttu-id="61ee0-172">그 중 하나는 주문 엔터티와 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-172">One of them is related to the Order entity.</span></span>

```csharp
// Part of the OrderingContext.cs class at the Ordering.Infrastructure project
//
protected override void OnModelCreating(ModelBuilder modelBuilder)
{
    modelBuilder.ApplyConfiguration(new ClientRequestEntityTypeConfiguration());
    modelBuilder.ApplyConfiguration(new PaymentMethodEntityTypeConfiguration());
    modelBuilder.ApplyConfiguration(new OrderEntityTypeConfiguration());
    modelBuilder.ApplyConfiguration(new OrderItemEntityTypeConfiguration());
    //...Additional type configurations
}
```

<span data-ttu-id="61ee0-173">다음 코드에서는 주문 엔터티에 대해 지속성 인프라가 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-173">In the following code, the persistence infrastructure is defined for the Order entity:</span></span>

```csharp
// Part of the OrderEntityTypeConfiguration.cs class
//
public void Configure(EntityTypeBuilder<Order> orderConfiguration)
{
    orderConfiguration.ToTable("orders", OrderingContext.DEFAULT_SCHEMA);
    orderConfiguration.HasKey(o => o.Id);
    orderConfiguration.Ignore(b => b.DomainEvents);
    orderConfiguration.Property(o => o.Id)
        .ForSqlServerUseSequenceHiLo("orderseq", OrderingContext.DEFAULT_SCHEMA);

    //Address value object persisted as owned entity in EF Core 2.0
    orderConfiguration.OwnsOne(o => o.Address);

    orderConfiguration.Property<DateTime>("OrderDate").IsRequired();

    //...Additional validations, constraints and code...
    //...
}
```

<span data-ttu-id="61ee0-174">이전 코드에서 `orderConfiguration.OwnsOne(o => o.Address)` 메서드는 `Address` 속성을 `Order` 형식의 소유된 엔터티로 지정했습니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-174">In the previous code, the `orderConfiguration.OwnsOne(o => o.Address)` method specifies that the `Address` property is an owned entity of the `Order` type.</span></span>

<span data-ttu-id="61ee0-175">기본적으로 EF Core 규칙에서는 소유된 엔터티 형식의 속성에 대한 데이터베이스 열 이름을 `EntityProperty_OwnedEntityProperty`로 명명합니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-175">By default, EF Core conventions name the database columns for the properties of the owned entity type as `EntityProperty_OwnedEntityProperty`.</span></span> <span data-ttu-id="61ee0-176">그러므로 `Address`의 내부 속성이 `Orders` 테이블에 `Address_Street`, `Address_City`(`State`, `Country`, `ZipCode`에 대해서도 같은 방식으로)라는 이름으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-176">Therefore, the internal properties of `Address` will appear in the `Orders` table with the names `Address_Street`, `Address_City` (and so on for `State`, `Country` and `ZipCode`).</span></span>

<span data-ttu-id="61ee0-177">`Property().HasColumnName()` fluent 메서드를 추가하여 열 이름을 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-177">You can append the `Property().HasColumnName()` fluent method to rename those columns.</span></span> <span data-ttu-id="61ee0-178">`Address`가 공용 속성인 경우 매핑은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-178">In the case where `Address` is a public property, the mappings would be like the following:</span></span>

```csharp
orderConfiguration.OwnsOne(p => p.Address)
                            .Property(p=>p.Street).HasColumnName("ShippingStreet");

orderConfiguration.OwnsOne(p => p.Address)
                            .Property(p=>p.City).HasColumnName("ShippingCity");
```

<span data-ttu-id="61ee0-179">fluent 매핑에서 `OwnsOne` 메서드를 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-179">It's possible to chain the `OwnsOne` method in a fluent mapping.</span></span> <span data-ttu-id="61ee0-180">다음과 같은 가상의 예제에서 `OrderDetails`는 `BillingAddress` 및 `ShippingAddress`를 소유하며, 둘 다 `Address` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-180">In the following hypothetical example, `OrderDetails` owns `BillingAddress` and `ShippingAddress`, which are both `Address` types.</span></span> <span data-ttu-id="61ee0-181">그리고 `OrderDetails`는 `Order` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-181">Then `OrderDetails` is owned by the `Order` type.</span></span>

```csharp
orderConfiguration.OwnsOne(p => p.OrderDetails, cb =>
    {
        cb.OwnsOne(c => c.BillingAddress);
        cb.OwnsOne(c => c.ShippingAddress);
    });
//...
//...
public class Order
{
    public int Id { get; set; }
    public OrderDetails OrderDetails { get; set; }
}

public class OrderDetails
{
    public Address BillingAddress { get; set; }
    public Address ShippingAddress { get; set; }
}

public class Address
{
    public string Street { get; set; }
    public string City { get; set; }
}
```

### <a name="additional-details-on-owned-entity-types"></a><span data-ttu-id="61ee0-182">소유된 엔터티 형식에 대한 추가 정보</span><span class="sxs-lookup"><span data-stu-id="61ee0-182">Additional details on owned entity types</span></span>

- <span data-ttu-id="61ee0-183">소유된 형식은 OwnsOne 흐름 API를 사용하여 탐색 속성을 특정 형식으로 구성할 때 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-183">Owned types are defined when you configure a navigation property to a particular type using the OwnsOne fluent API.</span></span>

- <span data-ttu-id="61ee0-184">메타데이터 모델의 소유된 형식 정의는 소유된 형식의 소유자 형식, 탐색 속성 및 CLR 형식으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-184">The definition of an owned type in our metadata model is a composite of: the owner type, the navigation property, and the CLR type of the owned type.</span></span>

- <span data-ttu-id="61ee0-185">스택의 소유된 형식 인스턴스의 ID(키)는 소유자 형식의 ID와 소유된 형식의 정의로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-185">The identity (key) of an owned type instance in our stack is a composite of the identity of the owner type and the definition of the owned type.</span></span>

#### <a name="owned-entities-capabilities"></a><span data-ttu-id="61ee0-186">소유 엔터티 기능</span><span class="sxs-lookup"><span data-stu-id="61ee0-186">Owned entities capabilities</span></span>

- <span data-ttu-id="61ee0-187">소유된 형식은 소유된 엔터티(중첩된 소유된 형식) 또는 소유되지 않은 엔터티(다른 엔터티에 대한 일반 참조 탐색 속성)라는 다른 엔터티를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-187">Owned types can reference other entities, either owned (nested owned types) or non-owned (regular reference navigation properties to other entities).</span></span>

- <span data-ttu-id="61ee0-188">별도의 탐색 속성을 통해 동일한 소유자 엔터티의 다른 소유된 형식과 동일한 CLR 형식을 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-188">You can map the same CLR type as different owned types in the same owner entity through separate navigation properties.</span></span>

- <span data-ttu-id="61ee0-189">테이블 분할은 규칙에 따라 설정되지만, ToTable을 사용하여 소유된 형식을 다른 테이블로 매핑하여 옵트아웃할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-189">Table splitting is setup by convention, but you can opt out by mapping the owned type to a different table using ToTable.</span></span>

- <span data-ttu-id="61ee0-190">즉시 로드는 소유된 형식에서 자동으로 수행되므로 쿼리에서 `.Include()`를 호출할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-190">Eager loading is performed automatically on owned types, that is, there's no need to call `.Include()` on the query.</span></span>

- <span data-ttu-id="61ee0-191">EF Core 2.1 이상 버전을 사용하여 특성 `[Owned]`로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-191">Can be configured with attribute `[Owned]`, using EF Core 2.1 and later.</span></span>

- <span data-ttu-id="61ee0-192">소유된 형식의 컬렉션을 처리할 수 있습니다(2.2 이상 버전을 사용).</span><span class="sxs-lookup"><span data-stu-id="61ee0-192">Can handle collections of owned types (using version 2.2 and later).</span></span>

#### <a name="owned-entities-limitations"></a><span data-ttu-id="61ee0-193">소유 엔터티의 제한 사항</span><span class="sxs-lookup"><span data-stu-id="61ee0-193">Owned entities limitations</span></span>

- <span data-ttu-id="61ee0-194">소유된 형식의 `DbSet<T>`를 만들 수 없습니다(디자인임).</span><span class="sxs-lookup"><span data-stu-id="61ee0-194">You can't create a `DbSet<T>` of an owned type (by design).</span></span>

- <span data-ttu-id="61ee0-195">소유된 형식에는 `ModelBuilder.Entity<T>()`를 호출할 수 없습니다(현재 디자인임).</span><span class="sxs-lookup"><span data-stu-id="61ee0-195">You can't call `ModelBuilder.Entity<T>()` on owned types (currently by design).</span></span>

- <span data-ttu-id="61ee0-196">동일한 테이블(예: 테이블 분할 사용)에서 소유자로 매핑되는 선택적(즉, null 허용) 소유된 형식이 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-196">No support for optional (that is, nullable) owned types that are mapped with the owner in the same table (that is, using table splitting).</span></span> <span data-ttu-id="61ee0-197">각 속성에 대해 매핑이 수행되기 때문에 null 복합 값에 대한 별도 sentinel이 전체로 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-197">This is because mapping is done for each property, we don't have a separate sentinel for the null complex value a as whole.</span></span>

- <span data-ttu-id="61ee0-198">소유된 형식에 대한 상속 매핑이 지원되지 않지만, 다른 소유된 형식과 상속 계층 구조가 동일한 두 가지 리프 형식을 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-198">No inheritance mapping support for owned types, but you should be able to map two leaf types of the same inheritance hierarchies as different owned types.</span></span> <span data-ttu-id="61ee0-199">EF Core는 이러한 형식이 동일한 계층 구조의 일부라는 사실의 근거가 되지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-199">EF Core will not reason about the fact that they are part of the same hierarchy.</span></span>

#### <a name="main-differences-with-ef6s-complex-types"></a><span data-ttu-id="61ee0-200">EF6의 복합 형식과 다른 주요 차이점</span><span class="sxs-lookup"><span data-stu-id="61ee0-200">Main differences with EF6's complex types</span></span>

- <span data-ttu-id="61ee0-201">테이블 분할은 선택 사항입니다. 즉, 별도 테이블에 선택적으로 매핑할 수 있으며 계속해서 소유된 형식이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-201">Table splitting is optional, that is, they can optionally be mapped to a separate table and still be owned types.</span></span>

- <span data-ttu-id="61ee0-202">다른 엔터티를 참조할 수 있습니다. 즉, 다른 소유되지 않은 형식과의 관계에서 종속되는 쪽의 역할을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61ee0-202">They can reference other entities (that is, they can act as the dependent side on relationships to other non-owned types).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="61ee0-203">추가 자료</span><span class="sxs-lookup"><span data-stu-id="61ee0-203">Additional resources</span></span>

- <span data-ttu-id="61ee0-204">**Martin Fowler. ValueObject 패턴** </span><span class="sxs-lookup"><span data-stu-id="61ee0-204">**Martin Fowler. ValueObject pattern** </span></span>\
  <https://martinfowler.com/bliki/ValueObject.html>

- <span data-ttu-id="61ee0-205">**Eric Evans. 도메인 기반 디자인: 소프트웨어 핵심에서 복잡성을 처리합니다.**</span><span class="sxs-lookup"><span data-stu-id="61ee0-205">**Eric Evans. Domain-Driven Design: Tackling Complexity in the Heart of Software.**</span></span> <span data-ttu-id="61ee0-206">(도서; 값 개체의 토론 포함) </span><span class="sxs-lookup"><span data-stu-id="61ee0-206">(Book; includes a discussion of value objects) </span></span>\
  <https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/>

- <span data-ttu-id="61ee0-207">**Vaughn Vernon. 도메인 기반 디자인 구현.**</span><span class="sxs-lookup"><span data-stu-id="61ee0-207">**Vaughn Vernon. Implementing Domain-Driven Design.**</span></span> <span data-ttu-id="61ee0-208">(도서; 값 개체의 토론 포함) </span><span class="sxs-lookup"><span data-stu-id="61ee0-208">(Book; includes a discussion of value objects) </span></span>\
  <https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/>

- <span data-ttu-id="61ee0-209">**소유 엔터티 형식** </span><span class="sxs-lookup"><span data-stu-id="61ee0-209">**Owned Entity Types** </span></span>\
  <https://docs.microsoft.com/ef/core/modeling/owned-entities>

- <span data-ttu-id="61ee0-210">**섀도 속성** </span><span class="sxs-lookup"><span data-stu-id="61ee0-210">**Shadow Properties** </span></span>\
  <https://docs.microsoft.com/ef/core/modeling/shadow-properties>

- <span data-ttu-id="61ee0-211">**복합 형식 및/또는 값 개체**.</span><span class="sxs-lookup"><span data-stu-id="61ee0-211">**Complex types and/or value objects**.</span></span> <span data-ttu-id="61ee0-212">EF Core GitHub 리포지토리에서 토론(문제 탭) </span><span class="sxs-lookup"><span data-stu-id="61ee0-212">Discussion in the EF Core GitHub repo (Issues tab) </span></span>\
  <https://github.com/dotnet/efcore/issues/246>

- <span data-ttu-id="61ee0-213">**ValueObject.cs.**</span><span class="sxs-lookup"><span data-stu-id="61ee0-213">**ValueObject.cs.**</span></span> <span data-ttu-id="61ee0-214">eShopOnContainers의 기준 값 개체 클래스.</span><span class="sxs-lookup"><span data-stu-id="61ee0-214">Base value object class in eShopOnContainers.</span></span> \
  <https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.Domain/SeedWork/ValueObject.cs>

- <span data-ttu-id="61ee0-215">**주소 클래스.**</span><span class="sxs-lookup"><span data-stu-id="61ee0-215">**Address class.**</span></span> <span data-ttu-id="61ee0-216">eShopOnContainers의 동일한 값 개체 클래스.</span><span class="sxs-lookup"><span data-stu-id="61ee0-216">Sample value object class in eShopOnContainers.</span></span> \
  <https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Address.cs>

> [!div class="step-by-step"]
> <span data-ttu-id="61ee0-217">[이전](seedwork-domain-model-base-classes-interfaces.md)
> [다음](enumeration-classes-over-enum-types.md)</span><span class="sxs-lookup"><span data-stu-id="61ee0-217">[Previous](seedwork-domain-model-base-classes-interfaces.md)
[Next](enumeration-classes-over-enum-types.md)</span></span>
