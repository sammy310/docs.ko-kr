---
title: 도메인 모델 레이어에서 유효성 검사 디자인
description: 컨테이너화된 .NET 애플리케이션용 .NET 마이크로 서비스 아키텍처 | 도메인 모델 유효성 검사의 주요 개념을 이해합니다.
ms.date: 10/08/2018
ms.openlocfilehash: f1e2d7430c642ad47f79cdd34d3a65e2cc70e239
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164275"
---
# <a name="design-validations-in-the-domain-model-layer"></a><span data-ttu-id="2432b-103">도메인 모델 레이어에서 유효성 검사 디자인</span><span class="sxs-lookup"><span data-stu-id="2432b-103">Design validations in the domain model layer</span></span>

<span data-ttu-id="2432b-104">DDD에서 유효성 검사 규칙을 고정으로 생각할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2432b-104">In DDD, validation rules can be thought as invariants.</span></span> <span data-ttu-id="2432b-105">집계의 기본 역할은 해당 집계 내의 모든 엔터티에 대한 상태 변경 내용에 고정을 적용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2432b-105">The main responsibility of an aggregate is to enforce invariants across state changes for all the entities within that aggregate.</span></span>

<span data-ttu-id="2432b-106">도메인 엔터티는 항상 유효한 엔터티여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2432b-106">Domain entities should always be valid entities.</span></span> <span data-ttu-id="2432b-107">항상 true여야 하는 개체에 대한 특정 수의 고정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2432b-107">There are a certain number of invariants for an object that should always be true.</span></span> <span data-ttu-id="2432b-108">예를 들어 주문 항목 개체는 항상 양의 정수 더하기 아티클 이름 및 가격이어야 하는 수량을 가져야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2432b-108">For example, an order item object always has to have a quantity that must be a positive integer, plus an article name and price.</span></span> <span data-ttu-id="2432b-109">따라서 고정 적용은 도메인 엔터티(특히 집계 루트)의 책임이며 엔터티 개체는 유효하지 않고 존재할 수 없어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2432b-109">Therefore, invariants enforcement is the responsibility of the domain entities (especially of the aggregate root) and an entity object should not be able to exist without being valid.</span></span> <span data-ttu-id="2432b-110">고정 규칙은 단순히 계약으로 표시되고 위반될 때 예외 또는 알림이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="2432b-110">Invariant rules are simply expressed as contracts, and exceptions or notifications are raised when they are violated.</span></span>

<span data-ttu-id="2432b-111">이에 대한 이유는 개체가 있어 본 적 없어야 하는 상태에 있으므로 많은 버그가 발생하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="2432b-111">The reasoning behind this is that many bugs occur because objects are in a state they should never have been in.</span></span> <span data-ttu-id="2432b-112">이 [온라인 토론](http://codebetter.com/gregyoung/2009/05/22/always-valid/)은 Greg Young의 좋은 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="2432b-112">This [online discussion](http://codebetter.com/gregyoung/2009/05/22/always-valid/) is a good explanation from Greg Young.</span></span>

<span data-ttu-id="2432b-113">사용자 프로필을 사용하는 SendUserCreationEmailService가 있다고 제안해 보겠습니다. 해당 서비스에서 해당 이름이 Null이 아니라고 어떻게 합리화할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="2432b-113">Let's propose we now have a SendUserCreationEmailService that takes a UserProfile ... how can we rationalize in that service that Name is not null?</span></span> <span data-ttu-id="2432b-114">다시 확인할까요?</span><span class="sxs-lookup"><span data-stu-id="2432b-114">Do we check it again?</span></span> <span data-ttu-id="2432b-115">또는 확인을 하지 않고 낙관할 가능성이 있습니다. 누군가가 당신에게 보내기 전에 유효성 검사를 고려했기를 희망합니다.</span><span class="sxs-lookup"><span data-stu-id="2432b-115">Or more likely ... you just don't bother to check and "hope for the best"—you hope that someone bothered to validate it before sending it to you.</span></span> <span data-ttu-id="2432b-116">물론 TDD를 사용하여 작성해야 하는 첫 번째 테스트 중 하나는 Null 이름으로 고객에게 보내면 오류를 발생시켜야 한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2432b-116">Of course, using TDD one of the first tests we should be writing is that if I send a customer with a null name that it should raise an error.</span></span> <span data-ttu-id="2432b-117">하지만 이러한 종류의 테스트를 계속해서 다시 작성하면 "잠깐, Null이 되는 이름을 허용하지 않았다면 이런 모든 테스트를 하지 않았을 텐데"라는 것을 깨닫게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2432b-117">But once we start writing these kinds of tests over and over again we realize ... "wait if we never allowed name to become null we wouldn't have all of these tests".</span></span>

## <a name="implement-validations-in-the-domain-model-layer"></a><span data-ttu-id="2432b-118">도메인 모델 레이어에서 유효성 검사 구현</span><span class="sxs-lookup"><span data-stu-id="2432b-118">Implement validations in the domain model layer</span></span>

<span data-ttu-id="2432b-119">유효성 검사는 도메인 엔터티 생성자 또는 엔터티를 업데이트할 수 있는 메서드에서 일반적으로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="2432b-119">Validations are usually implemented in domain entity constructors or in methods that can update the entity.</span></span> <span data-ttu-id="2432b-120">데이터를 확인하고 유효성 검사에 실패하는 경우 예외를 발생하는 것과 같은 유효성 검사를 구현하는 여러 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2432b-120">There are multiple ways to implement validations, such as verifying data and raising exceptions if the validation fails.</span></span> <span data-ttu-id="2432b-121">유효성 검사에 대해 사양 패턴을 사용하고 발생할 때 각 유효성 검사에 대한 예외를 반환하는 대신 오류 컬렉션을 반환하는 알림 패턴과 같은 더 많은 고급 패턴이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2432b-121">There are also more advanced patterns such as using the Specification pattern for validations, and the Notification pattern to return a collection of errors instead of returning an exception for each validation as it occurs.</span></span>

### <a name="validate-conditions-and-throw-exceptions"></a><span data-ttu-id="2432b-122">조건 유효성 검사 및 예외 throw</span><span class="sxs-lookup"><span data-stu-id="2432b-122">Validate conditions and throw exceptions</span></span>

<span data-ttu-id="2432b-123">다음 코드 예제에서는 예외를 발생시켜 도메인 엔터티에서 유효성을 검사하는 가장 간단한 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2432b-123">The following code example shows the simplest approach to validation in a domain entity by raising an exception.</span></span> <span data-ttu-id="2432b-124">이 섹션 끝의 참조 테이블에서 이전에 설명한 패턴을 기반으로 하는 더 많은 고급 구현에 대한 링크를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2432b-124">In the references table at the end of this section you can see links to more advanced implementations based on the patterns we have discussed previously.</span></span>

```csharp
public void SetAddress(Address address)
{
    _shippingAddress = address?? throw new ArgumentNullException(nameof(address));
}
```

<span data-ttu-id="2432b-125">적절한 예제는 내부 상태가 변경되지 않았거나 메서드에 대한 모든 변경이 발생했다는 것을 확인해야 함을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2432b-125">A better example would demonstrate the need to ensure that either the internal state did not change, or that all the mutations for a method occurred.</span></span> <span data-ttu-id="2432b-126">예를 들어 다음 구현은 개체를 유효하지 않은 상태에 둘 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2432b-126">For example, the following implementation would leave the object in an invalid state:</span></span>

```csharp
public void SetAddress(string line1, string line2,
    string city, string state, int zip)
{
    _shippingAddress.line1 = line1 ?? throw new ...
    _shippingAddress.line2 = line2;
    _shippingAddress.city = city ?? throw new ...
    _shippingAddress.state = (IsValid(state) ? state : throw new …);
}
```

<span data-ttu-id="2432b-127">상태 값이 유효하지 않은 경우 첫 번째 주소 줄 및 도시는 이미 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2432b-127">If the value of the state is invalid, the first address line and the city have already been changed.</span></span> <span data-ttu-id="2432b-128">잘못된 주소를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2432b-128">That might make the address invalid.</span></span>

<span data-ttu-id="2432b-129">만들어진 후 엔터티가 유효한지 확인하도록 예외를 발생시켜 엔터티 생성자에서 유사한 방법을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2432b-129">A similar approach can be used in the entity's constructor, raising an exception to make sure that the entity is valid once it is created.</span></span>

### <a name="use-validation-attributes-in-the-model-based-on-data-annotations"></a><span data-ttu-id="2432b-130">데이터 주석을 기반으로 하는 모델에서 유효성 검사 특성 사용</span><span class="sxs-lookup"><span data-stu-id="2432b-130">Use validation attributes in the model based on data annotations</span></span>

<span data-ttu-id="2432b-131">필수 또는 MaxLength 특성과 같은 데이터 주석은 [테이블 매핑](infrastructure-persistence-layer-implementation-entity-framework-core.md#table-mapping) 섹션에서 자세히 설명된 바와 같이 EF Core 데이터베이스 필드 속성을 구성하는 데 사용할 수 있지만, .NET Framework의 EF 4.x 이후 해온 것처럼 [EF Core에서 엔터티 유효성 검사를 위해 더 이상 작동하지 않습니다](https://github.com/dotnet/efcore/issues/3680)(<xref:System.ComponentModel.DataAnnotations.IValidatableObject.Validate%2A?displayProperty=nameWithType> 메서드도 수행하지 않음).</span><span class="sxs-lookup"><span data-stu-id="2432b-131">Data annotations, like the Required or MaxLength attributes, can be used to configure EF Core database field properties, as explained in detail in the [Table mapping](infrastructure-persistence-layer-implementation-entity-framework-core.md#table-mapping) section, but [they no longer work for entity validation in EF Core](https://github.com/dotnet/efcore/issues/3680) (neither does the <xref:System.ComponentModel.DataAnnotations.IValidatableObject.Validate%2A?displayProperty=nameWithType> method), as they have done since EF 4.x in .NET Framework.</span></span>

<span data-ttu-id="2432b-132">데이터 주석과 <xref:System.ComponentModel.DataAnnotations.IValidatableObject> 인터페이스는 일반적으로 컨트롤러의 작업을 호출하기 전 모델 바인딩 중에 모델 유효성 검사에 여전히 사용할 수 있지만, 해당 모델은 ViewModel 또는 DTO여야 하며 이는 도메인 모델 문제가 아닌 MVC 또는 API 관련 문제입니다.</span><span class="sxs-lookup"><span data-stu-id="2432b-132">Data annotations and the <xref:System.ComponentModel.DataAnnotations.IValidatableObject> interface can still be used for model validation during model binding, prior to the controller's actions invocation as usual, but that model is meant to be a ViewModel or DTO and that's an MVC or API concern not a domain model concern.</span></span>

<span data-ttu-id="2432b-133">개념적 차이를 명확히 했으므로 작업이 권장되지 않는 엔터티 클래스 개체 매개 변수를 받는 경우 유효성 검사를 위해 엔터티 클래스에서 데이터 주석과 `IValidatableObject`를 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2432b-133">Having made the conceptual difference clear, you can still use data annotations and `IValidatableObject` in the entity class for validation, if your actions receive an entity class object parameter, which is not recommended.</span></span> <span data-ttu-id="2432b-134">이 경우 유효성 검사는 모델 바인딩 시 수행되며, 작업을 호출하기 직전에 컨트롤러의 ModelState.IsValid 속성을 검사하여 결과를 확인할 수 있지만, 다시 한번 EF 4.x 이후 해온 것처럼 DbContext에서 엔터티 개체를 유지하기 전에는 컨트롤러에서 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="2432b-134">In that case, validation will occur upon model binding, just before invoking the action and you can check the controller's ModelState.IsValid property to check the result, but then again, it happens in the controller, not before persisting the entity object in the DbContext, as it had done since EF 4.x.</span></span>

<span data-ttu-id="2432b-135">DbContext의 SaveChanges 메서드를 재정의하여 데이터 주석 및 `IValidatableObject.Validate` 메서드를 사용하여 엔터티 클래스에 사용자 지정 유효성 검사를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2432b-135">You can still implement custom validation in the entity class using data annotations and the `IValidatableObject.Validate` method, by overriding the DbContext's SaveChanges method.</span></span>

<span data-ttu-id="2432b-136">[GitHub에 대한 이 주석](https://github.com/dotnet/efcore/issues/3680#issuecomment-155502539)에서 `IValidatableObject` 엔터티의 유효성 검사를 위한 샘플 구현을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2432b-136">You can see a sample implementation for validating `IValidatableObject` entities in [this comment on GitHub](https://github.com/dotnet/efcore/issues/3680#issuecomment-155502539).</span></span> <span data-ttu-id="2432b-137">해당 샘플은 특성 기반 유효성 검사를 수행하지 않지만 동일한 재정의에서 리플렉션을 사용하여 쉽게 구현할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2432b-137">That sample doesn't do attribute-based validations, but they should be easy to implement using reflection in the same override.</span></span>

<span data-ttu-id="2432b-138">그러나 DDD의 관점에서 도메인 모델은 엔터티의 동작 메서드에서 예외를 사용하거나 유효성 검사 규칙을 적용하도록 사양 및 알림 패턴을 구현하여 가장 잘 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="2432b-138">However, from a DDD point of view, the domain model is best kept lean with the use of exceptions in your entity's behavior methods, or by implementing the Specification and Notification patterns to enforce validation rules.</span></span>

<span data-ttu-id="2432b-139">UI 계층 내에서 모델 유효성 검사를 허용하도록 입력을 허용하는 ViewModel 클래스(도메인 엔터티 대신)의 애플리케이션 계층에서 데이터 주석을 사용하는 것이 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="2432b-139">It can make sense to use data annotations at the application layer in ViewModel classes (instead of domain entities) that will accept input, to allow for model validation within the UI layer.</span></span> <span data-ttu-id="2432b-140">그러나 도메인 모델 내의 유효성 검사를 제외하고 수행되어서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2432b-140">However, this should not be done at the exclusion of validation within the domain model.</span></span>

### <a name="validate-entities-by-implementing-the-specification-pattern-and-the-notification-pattern"></a><span data-ttu-id="2432b-141">사양 패턴 및 알림 패턴을 구현하여 엔터티의 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="2432b-141">Validate entities by implementing the Specification pattern and the Notification pattern</span></span>

<span data-ttu-id="2432b-142">마지막으로 도메인 모델에서 유효성 검사를 구현하는 보다 정교한 방법은 나중에 나열된 추가 리소스의 일부에서 설명된 것처럼 알림 패턴과 함께 사양 패턴을 구현하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2432b-142">Finally, a more elaborate approach to implementing validations in the domain model is by implementing the Specification pattern in conjunction with the Notification pattern, as explained in some of the additional resources listed later.</span></span>

<span data-ttu-id="2432b-143">이러한 패턴 중 하나만 사용할 수도 있습니다. 예를 들어 제어 문을 사용하여 수동으로 유효성을 검사하지만 유효성 검사 오류 목록을 배치하고 반환하도록 알림 패턴을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2432b-143">It is worth mentioning that you can also use just one of those patterns—for example, validating manually with control statements, but using the Notification pattern to stack and return a list of validation errors.</span></span>

### <a name="use-deferred-validation-in-the-domain"></a><span data-ttu-id="2432b-144">도메인에서 지연된 유효성 검사 사용</span><span class="sxs-lookup"><span data-stu-id="2432b-144">Use deferred validation in the domain</span></span>

<span data-ttu-id="2432b-145">도메인에서 지연된 유효성 검사를 처리하는 다양한 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2432b-145">There are various approaches to deal with deferred validations in the domain.</span></span> <span data-ttu-id="2432b-146">Vaughn Vernon은 그의 저서 [도메인 기반 디자인 구현](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577)의 유효성 검사에 대한 섹션에서 이에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2432b-146">In his book [Implementing Domain-Driven Design](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577), Vaughn Vernon discusses these in the section on validation.</span></span>

### <a name="two-step-validation"></a><span data-ttu-id="2432b-147">2단계 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="2432b-147">Two-step validation</span></span>

<span data-ttu-id="2432b-148">또한 2단계 유효성 검사를 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="2432b-148">Also consider two-step validation.</span></span> <span data-ttu-id="2432b-149">명령 DTO(데이터 전송 개체) 및 엔터티 내 도메인 수준 유효성 검사에서 필드 수준 유효성 검사를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2432b-149">Use field-level validation on your command Data Transfer Objects (DTOs) and domain-level validation inside your entities.</span></span> <span data-ttu-id="2432b-150">유효성 검사 오류를 더 쉽게 처리할 수 있도록 예외 대신 결과 개체를 반환하여 이를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2432b-150">You can do this by returning a result object instead of exceptions in order to make it easier to deal with the validation errors.</span></span>

<span data-ttu-id="2432b-151">예를 들어 데이터 주석과 함께 필드 유효성 검사를 사용하여 유효성 검사 정의를 중복하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2432b-151">Using field validation with data annotations, for example, you do not duplicate the validation definition.</span></span> <span data-ttu-id="2432b-152">그러나 실행은 DTO의 경우 서버 쪽 및 클라이언트 쪽 모두가 될 수 있습니다(예: 명령 및 Viewmodel).</span><span class="sxs-lookup"><span data-stu-id="2432b-152">The execution, though, can be both server-side and client-side in the case of DTOs (commands and ViewModels, for instance).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2432b-153">추가 자료</span><span class="sxs-lookup"><span data-stu-id="2432b-153">Additional resources</span></span>

- <span data-ttu-id="2432b-154">**Rachel Appel. ASP.NET Core MVC의 모델 유효성 검사 소개** </span><span class="sxs-lookup"><span data-stu-id="2432b-154">**Rachel Appel. Introduction to model validation in ASP.NET Core MVC** </span></span>\
  <https://docs.microsoft.com/aspnet/core/mvc/models/validation>

- <span data-ttu-id="2432b-155">**Rick Anderson. 유효성 검사 추가** </span><span class="sxs-lookup"><span data-stu-id="2432b-155">**Rick Anderson. Adding validation** </span></span>\
  <https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation>

- <span data-ttu-id="2432b-156">**Martin Fowler. 유효성 검사에서 예외 Throw를 알림으로 교체** </span><span class="sxs-lookup"><span data-stu-id="2432b-156">**Martin Fowler. Replacing Throwing Exceptions with Notification in Validations** </span></span>\
  <https://martinfowler.com/articles/replaceThrowWithNotification.html>

- <span data-ttu-id="2432b-157">**사양 및 알림 패턴** </span><span class="sxs-lookup"><span data-stu-id="2432b-157">**Specification and Notification Patterns** </span></span>\
  <https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns>

- <span data-ttu-id="2432b-158">**Lev Gorodinski. DDD(도메인 기반 디자인)에서 유효성 검사** </span><span class="sxs-lookup"><span data-stu-id="2432b-158">**Lev Gorodinski. Validation in Domain-Driven Design (DDD)** </span></span>\
  <http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/>

- <span data-ttu-id="2432b-159">**Colin Jack. 도메인 모델 유효성 검사** </span><span class="sxs-lookup"><span data-stu-id="2432b-159">**Colin Jack. Domain Model Validation** </span></span>\
  <https://colinjack.blogspot.com/2008/03/domain-model-validation.html>

- <span data-ttu-id="2432b-160">**Jimmy Bogard. DDD 세계에서 유효성 검사** </span><span class="sxs-lookup"><span data-stu-id="2432b-160">**Jimmy Bogard. Validation in a DDD world** </span></span>\
  <https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/>

> [!div class="step-by-step"]
> <span data-ttu-id="2432b-161">[이전](enumeration-classes-over-enum-types.md)
> [다음](client-side-validation.md)</span><span class="sxs-lookup"><span data-stu-id="2432b-161">[Previous](enumeration-classes-over-enum-types.md)
[Next](client-side-validation.md)</span></span>
