---
title: 호환성이 손상되는 변경의 형식
description: .Net Core가 .NET 버전에서 개발자에 대한 호환성을 유지하는 방법 및 호환성이 손상되는 변경으로 간주되는 변경 사항 유형을 알아보세요.
ms.date: 06/10/2019
ms.openlocfilehash: bf0cc35d69e6bb501640455604a99a1f48962c4a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "77628594"
---
# <a name="changes-that-affect-compatibility"></a><span data-ttu-id="850af-103">호환성에 영향을 미치는 변경 사항</span><span class="sxs-lookup"><span data-stu-id="850af-103">Changes that affect compatibility</span></span>

<span data-ttu-id="850af-104">지금까지 .NET은 버전 간은 물론 .NET 버전 전체에서 높은 수준의 호환성을 유지해 왔습니다.</span><span class="sxs-lookup"><span data-stu-id="850af-104">Throughout its history, .NET has attempted to maintain a high level of compatibility from version to version and across flavors of .NET.</span></span> <span data-ttu-id="850af-105">이러한 노력은 .NET Core에서도 그대로 이어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="850af-105">This continues to be true for .NET Core.</span></span> <span data-ttu-id="850af-106">.NET Core는 .NET Framework와 독립적인 새로운 기술로 간주될 수 있지만, 다음 두 가지 주요 요인으로 인해 .NET Framework에서 .NET Core를 완전히 분리하기는 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="850af-106">Although .NET Core can be considered as a new technology that is independent of the .NET Framework, two major factors limit the ability of .NET Core to diverge from .NET Framework:</span></span>

- <span data-ttu-id="850af-107">많은 개발자가 원래 .NET Framework 애플리케이션을 개발했거나 계속 개발하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="850af-107">A large number of developers either originally developed or continue to develop .NET Framework applications.</span></span> <span data-ttu-id="850af-108">이러한 개발자는 .NET 구현 전체에서 일관된 동작을 기대합니다.</span><span class="sxs-lookup"><span data-stu-id="850af-108">They expect consistent behavior across .NET implementations.</span></span>

- <span data-ttu-id="850af-109">.NET Standard 라이브러리 프로젝트를 사용하면 개발자가 .NET Core와 .NET Framework에서 공유하는 공통 API를 대상으로 하는 라이브러리를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="850af-109">.NET Standard library projects allow developers to create libraries that target common APIs shared by .NET Core and .NET Framework.</span></span> <span data-ttu-id="850af-110">개발자는 .NET Core 애플리케이션에서 사용되는 라이브러리가 .NET Framework 애플리케이션에서 사용되는 동일한 라이브러리와 똑같이 동작할 것으로 기대합니다.</span><span class="sxs-lookup"><span data-stu-id="850af-110">Developers expect that a library used in a .NET Core application should behave identically to the same library used in a .NET Framework application.</span></span>

<span data-ttu-id="850af-111">.NET 구현 전체의 호환성과 더불어, 개발자는 .NET Core 버전 전체에서 높은 수준의 호환성을 기대합니다.</span><span class="sxs-lookup"><span data-stu-id="850af-111">Along with compatibility across .NET implementations, developers expect a high level of compatibility across .NET Core versions.</span></span> <span data-ttu-id="850af-112">특히, 이전 버전의 .NET Core용으로 작성된 코드가 최신 .NET Core 버전에서 원활하게 실행되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="850af-112">In particular, code written for an earlier version of .NET Core should run seamlessly on a later version of .NET Core.</span></span> <span data-ttu-id="850af-113">사실 대부분의 개발자는 새로 릴리스된 .NET Core 버전의 새 API가 해당 API를 도입한 시험판 버전과도 호환되어야 한다고 기대합니다.</span><span class="sxs-lookup"><span data-stu-id="850af-113">In fact, many developers expect that the new APIs found in newly released versions of .NET Core should also be compatible with the pre-release versions in which those APIs were introduced.</span></span>

<span data-ttu-id="850af-114">이 문서에서는 호환성 변경(또는 호환성이 손상되는 변경) 범주와 .NET 팀이 이러한 각 범주의 변경 내용을 평가하는 방법을 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="850af-114">This article outlines the categories of compatibility changes (or breaking changes) and the way in which the .NET team evaluates changes in each of these categories.</span></span> <span data-ttu-id="850af-115">.NET 팀이 호환성이 손상되는 가능한 변경에 접근하는 방법을 이해하는 것은 [dotnet/runtime](https://github.com/dotnet/runtime) GitHub 리포지토리에서 기존 API의 동작을 수정하는 끌어오기 요청을 여는 개발자에게 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="850af-115">Understanding how the .NET team approaches possible breaking changes is particularly helpful for developers who open pull requests in the [dotnet/runtime](https://github.com/dotnet/runtime) GitHub repository that modify the behavior of existing APIs.</span></span>

> [!NOTE]
> <span data-ttu-id="850af-116">이진 호환성, 이전 버전과 호환성 등의 호환성 범주에 대한 정의는 [호환성이 손상되는 변경 범주](categories.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="850af-116">For a definition of compatibility categories, such as binary compatibility and backward compatibility, see [Breaking change categories](categories.md).</span></span>

<span data-ttu-id="850af-117">다음 섹션에서는 .NET Core API의 변경 범주 및 애플리케이션 호환성에 미치는 영향을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="850af-117">The following sections describe the categories of changes made to .NET Core APIs and their impact on application compatibility.</span></span> <span data-ttu-id="850af-118">변경 내용은 허용 ✔️ 또는 허용되지 않음 ❌으로 적용되고, 이전 동작이 얼마나 예측 가능하고 명백하며 일관성이 있었는지 ❓에 대한 판단과 평가가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="850af-118">Changes are either allowed ✔️, disallowed ❌, or require judgment and an evaluation of how predictable, obvious, and consistent the previous behavior was ❓.</span></span>

> [!NOTE]
> <span data-ttu-id="850af-119">.NET Core 라이브러리의 변경 내용을 평가하는 방법에 대한 가이드 역할을 할 뿐 아니라, 라이브러리 개발자는 이러한 기준을 사용하여 여러 .NET 구현과 버전을 대상으로 하는 고유한 라이브러리의 변경 내용을 평가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="850af-119">In addition to serving as a guide to how changes to .NET Core libraries are evaluated, library developers can also use these criteria to evaluate changes to their libraries that target multiple .NET implementations and versions.</span></span>

## <a name="modifications-to-the-public-contract"></a><span data-ttu-id="850af-120">공용 계약 수정</span><span class="sxs-lookup"><span data-stu-id="850af-120">Modifications to the public contract</span></span>

<span data-ttu-id="850af-121">이 범주의 변경 내용은 형식의 공용 노출 영역을 ‘수정’합니다.</span><span class="sxs-lookup"><span data-stu-id="850af-121">Changes in this category modify the public surface area of a type.</span></span> <span data-ttu-id="850af-122">이 범주의 변경 내용은 대부분 *이전 버전과의 호환성*(이전 버전의 API로 개발된 애플리케이션이 최신 버전에서 다시 컴파일하지 않고도 실행되는 기능)을 위반하기 때문에 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="850af-122">Most of the changes in this category are disallowed since they violate *backwards compatibility* (the ability of an application that was developed with a previous version of an API to execute without recompilation on a later version).</span></span>

### <a name="types"></a><span data-ttu-id="850af-123">유형</span><span class="sxs-lookup"><span data-stu-id="850af-123">Types</span></span>

- <span data-ttu-id="850af-124">✔️ **허용: 인터페이스가 기본 형식을 통해 이미 구현된 경우 형식에서 인터페이스 구현 제거**</span><span class="sxs-lookup"><span data-stu-id="850af-124">✔️ **ALLOWED: Removing an interface implementation from a type when the interface is already implemented by a base type**</span></span>

- <span data-ttu-id="850af-125">❓ **판단 필요: 형식에 새 인터페이스 구현 추가**</span><span class="sxs-lookup"><span data-stu-id="850af-125">❓ **REQUIRES JUDGMENT: Adding a new interface implementation to a type**</span></span>

  <span data-ttu-id="850af-126">이 변경 내용은 기존 클라이언트에 부정적인 영향을 주지 않으므로 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="850af-126">This is an acceptable change because it does not adversely affect existing clients.</span></span> <span data-ttu-id="850af-127">새 구현이 허용되려면 형식의 모든 변경 내용이 여기서 정의된 허용되는 변경 내용의 경계를 넘지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="850af-127">Any changes to the type must work within the boundaries of acceptable changes defined here for the new implementation to remain acceptable.</span></span> <span data-ttu-id="850af-128">하위 수준에서 사용할 수 없는 코드 또는 데이터를 생성하는 디자이너 또는 직렬 변환기의 기능에 직접 영향을 주는 인터페이스를 추가할 때는 각별한 주의가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="850af-128">Extreme caution is necessary when adding interfaces that directly affect the ability of a designer or serializer to generate code or data that cannot be consumed down-level.</span></span> <span data-ttu-id="850af-129">예를 들어 <xref:System.Runtime.Serialization.ISerializable> 인터페이스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="850af-129">An example is the <xref:System.Runtime.Serialization.ISerializable> interface.</span></span>

- <span data-ttu-id="850af-130">❓ **판단 필요: 새 기본 클래스 도입**</span><span class="sxs-lookup"><span data-stu-id="850af-130">❓ **REQUIRES JUDGMENT: Introducing a new base class**</span></span>

  <span data-ttu-id="850af-131">새 [추상](../../csharp/language-reference/keywords/abstract.md) 구성원을 도입하거나 기존 형식의 의미 체계 또는 동작을 변경하지 않는 경우, 계층 구조에서 두 기존 형식 사이에 형식을 도입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="850af-131">A type can be introduced into a hierarchy between two existing types if it doesn't introduce any new [abstract](../../csharp/language-reference/keywords/abstract.md) members or change the semantics or behavior of existing types.</span></span> <span data-ttu-id="850af-132">예를 들어 .NET Framework 2.0에서는 <xref:System.Data.Common.DbConnection> 클래스가 이전에 <xref:System.ComponentModel.Component>에서 직접 파생된 <xref:System.Data.SqlClient.SqlConnection>의 새 기본 클래스가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="850af-132">For example, in .NET Framework 2.0, the <xref:System.Data.Common.DbConnection> class became a new base class for <xref:System.Data.SqlClient.SqlConnection>, which had previously derived directly from <xref:System.ComponentModel.Component>.</span></span>

- <span data-ttu-id="850af-133">✔️ **허용: 어셈블리 간에 형식 이동**</span><span class="sxs-lookup"><span data-stu-id="850af-133">✔️ **ALLOWED: Moving a type from one assembly to another**</span></span>

  <span data-ttu-id="850af-134">*이전* 어셈블리는 새 어셈블리를 가리키는 <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute>로 표시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="850af-134">The *old* assembly must be marked with the <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> that points to the new assembly.</span></span>

- <span data-ttu-id="850af-135">✔️ **허용: [구조체](../../csharp/language-reference/builtin-types/struct.md) 형식을 `readonly struct` 형식으로 변경**</span><span class="sxs-lookup"><span data-stu-id="850af-135">✔️ **ALLOWED: Changing a [struct](../../csharp/language-reference/builtin-types/struct.md) type to a `readonly struct` type**</span></span>

  <span data-ttu-id="850af-136">`readonly struct` 형식을 `struct` 형식으로 변경할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="850af-136">Changing a `readonly struct` type to a `struct` type is not allowed.</span></span>

- <span data-ttu-id="850af-137">✔️ **허용: *액세스할 수 있는*(공용 또는 보호된) 생성자**가 없는 경우 형식에 [봉인된](../../csharp/language-reference/keywords/sealed.md) 또는 [추상](../../csharp/language-reference/keywords/abstract.md) 키워드 추가</span><span class="sxs-lookup"><span data-stu-id="850af-137">✔️ **ALLOWED: Adding the [sealed](../../csharp/language-reference/keywords/sealed.md) or [abstract](../../csharp/language-reference/keywords/abstract.md) keyword to a type when there are no *accessible* (public or protected) constructors**</span></span>

- <span data-ttu-id="850af-138">✔️ **허용: 형식의 표시 유형 확장**</span><span class="sxs-lookup"><span data-stu-id="850af-138">✔️ **ALLOWED: Expanding the visibility of a type**</span></span>

- <span data-ttu-id="850af-139">❌ **허용 안 함: 형식의 네임스페이스 또는 이름 변경**</span><span class="sxs-lookup"><span data-stu-id="850af-139">❌ **DISALLOWED: Changing the namespace or name of a type**</span></span>

- <span data-ttu-id="850af-140">❌ **허용 안 함: 공용 형식 이름 바꾸기 또는 제거**</span><span class="sxs-lookup"><span data-stu-id="850af-140">❌ **DISALLOWED: Renaming or removing a public type**</span></span>

   <span data-ttu-id="850af-141">이 경우 이름이 바뀌었거나 제거된 형식을 사용하는 모든 코드가 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="850af-141">This breaks all code that uses the renamed or removed type.</span></span>

- <span data-ttu-id="850af-142">❌ **허용 안 함: 열거형의 기본 형식 변경**</span><span class="sxs-lookup"><span data-stu-id="850af-142">❌ **DISALLOWED: Changing the underlying type of an enumeration**</span></span>

   <span data-ttu-id="850af-143">특성 인수를 구문 분석할 수 없게 만드는 호환성이 손상되는 이진 변경일 뿐만 아니라 호환성이 손상되는 컴파일 시간 및 동작 변경입니다.</span><span class="sxs-lookup"><span data-stu-id="850af-143">This is a compile-time and behavioral breaking change as well as a binary breaking change that can make attribute arguments unparsable.</span></span>

- <span data-ttu-id="850af-144">❌ **허용 안 함: 이전에 봉인되지 않은 형식 봉인**</span><span class="sxs-lookup"><span data-stu-id="850af-144">❌ **DISALLOWED: Sealing a type that was previously unsealed**</span></span>

- <span data-ttu-id="850af-145">❌ **허용 안 함: 인터페이스의 기본 형식 세트에 인터페이스 추가**</span><span class="sxs-lookup"><span data-stu-id="850af-145">❌ **DISALLOWED: Adding an interface to the set of base types of an interface**</span></span>

   <span data-ttu-id="850af-146">인터페이스가 이전에 구현하지 않은 인터페이스를 구현하는 경우, 원래 버전의 인터페이스를 구현한 모든 형식이 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="850af-146">If an interface implements an interface that it previously did not implement, all types that implemented the original version of the interface are broken.</span></span>

- <span data-ttu-id="850af-147">❓ **판단 필요: 기본 클래스 세트에서 클래스 제거 또는 구현된 인터페이스 세트에서 인터페이스 제거**</span><span class="sxs-lookup"><span data-stu-id="850af-147">❓ **REQUIRES JUDGMENT: Removing a class from the set of base classes or an interface from the set of implemented interfaces**</span></span>

  <span data-ttu-id="850af-148">인터페이스 제거 규칙의 한 가지 예외로, 제거한 인터페이스에서 파생되는 인터페이스 구현을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="850af-148">There is one exception to the rule for interface removal: you can add the implementation of an interface that derives from the removed interface.</span></span> <span data-ttu-id="850af-149">예를 들어 이제 <xref:System.IDisposable>을 구현하는 <xref:System.ComponentModel.IComponent>를 형식 또는 인터페이스가 구현하는 경우 <xref:System.IDisposable>을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="850af-149">For example, you can remove <xref:System.IDisposable> if the type or interface now implements <xref:System.ComponentModel.IComponent>, which implements <xref:System.IDisposable>.</span></span>

- <span data-ttu-id="850af-150">❌ **허용 안 함: `readonly struct` 형식을 [구조체 ](../../csharp/language-reference/builtin-types/struct.md) 형식으로 변경**</span><span class="sxs-lookup"><span data-stu-id="850af-150">❌ **DISALLOWED: Changing a `readonly struct` type to a [struct](../../csharp/language-reference/builtin-types/struct.md) type**</span></span>

  <span data-ttu-id="850af-151">`struct` 형식은 `readonly struct` 형식으로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="850af-151">The change of a `struct` type to a `readonly struct` type is allowed, however.</span></span>

- <span data-ttu-id="850af-152">❌ **허용 안 함: [구조체](../../csharp/language-reference/builtin-types/struct.md) 형식을 `ref struct` 형식으로 변경하거나 그 반대로 변경**</span><span class="sxs-lookup"><span data-stu-id="850af-152">❌ **DISALLOWED: Changing a [struct](../../csharp/language-reference/builtin-types/struct.md) type to a `ref struct` type, and vice versa**</span></span>

- <span data-ttu-id="850af-153">❌ **허용 안 함: 표시 형식 축소**</span><span class="sxs-lookup"><span data-stu-id="850af-153">❌ **DISALLOWED: Reducing the visibility of a type**</span></span>

   <span data-ttu-id="850af-154">단, 형식의 표시 유형을 늘릴 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="850af-154">However, increasing the visibility of a type is allowed.</span></span>

### <a name="members"></a><span data-ttu-id="850af-155">멤버</span><span class="sxs-lookup"><span data-stu-id="850af-155">Members</span></span>

- <span data-ttu-id="850af-156">✔️ **허용: [가상](../../csharp/language-reference/keywords/sealed.md)이 아닌 구성원의 표시 유형 확장**</span><span class="sxs-lookup"><span data-stu-id="850af-156">✔️ **ALLOWED: Expanding the visibility of a member that is not [virtual](../../csharp/language-reference/keywords/sealed.md)**</span></span>

- <span data-ttu-id="850af-157">✔️ **허용: *액세스할 수 있는*(공용 또는 보호된) 생성자가 없거나 [봉인된](../../csharp/language-reference/keywords/sealed.md) 형식인 경우 공용 형식에 추상 구성원 추가**</span><span class="sxs-lookup"><span data-stu-id="850af-157">✔️ **ALLOWED: Adding an abstract member to a public type that has no *accessible* (public or protected) constructors, or the type is [sealed](../../csharp/language-reference/keywords/sealed.md)**</span></span>

  <span data-ttu-id="850af-158">단, 액세스할 수 있는(public 또는 protected) 생성자가 있고 `sealed`가 아닌 형식에는 추상 멤버를 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="850af-158">However, adding an abstract member to a type that has accessible (public or protected) constructors and is not `sealed` is not allowed.</span></span>

- <span data-ttu-id="850af-159">✔️ **허용: 형식에 액세스할 수 있는(공용 또는 보호된) 생성자가 없거나 [봉인된](../../csharp/language-reference/keywords/sealed.md) 형식인 경우 [보호된](../../csharp/language-reference/keywords/protected.md) 구성원의 표시 유형 제한**</span><span class="sxs-lookup"><span data-stu-id="850af-159">✔️ **ALLOWED: Restricting the visibility of a [protected](../../csharp/language-reference/keywords/protected.md) member when the type has no accessible (public or protected) constructors, or the type is [sealed](../../csharp/language-reference/keywords/sealed.md)**</span></span>

- <span data-ttu-id="850af-160">✔️ **허용: 구성원이 제거된 형식보다 계층 구조의 상위 클래스로 해당 구성원 이동**</span><span class="sxs-lookup"><span data-stu-id="850af-160">✔️ **ALLOWED: Moving a member into a class higher in the hierarchy than the type from which it was removed**</span></span>

- <span data-ttu-id="850af-161">✔️ **허용: 재정의 추가 또는 제거**</span><span class="sxs-lookup"><span data-stu-id="850af-161">✔️ **ALLOWED: Adding or removing an override**</span></span>

  <span data-ttu-id="850af-162">재정의를 도입하는 경우 [base](../../csharp/language-reference/keywords/base.md)를 호출하면 이전 소비자가 재정의를 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="850af-162">Introducing an override might cause previous consumers to skip over the override when calling [base](../../csharp/language-reference/keywords/base.md).</span></span>

- <span data-ttu-id="850af-163">✔️ **허용: 이전에 클래스에 생성자가 없었던 경우 매개 변수가 없는 생성자와 함께 클래스에 생성자 추가**</span><span class="sxs-lookup"><span data-stu-id="850af-163">✔️ **ALLOWED: Adding a constructor to a class, along with a parameterless constructor if the class previously had no constructors**</span></span>

   <span data-ttu-id="850af-164">단, 매개 변수가 없는 생성자를 추가하지 ‘않고’ 이전에 생성자가 없었던 클래스에 생성자를 추가할 수는 없습니다. </span><span class="sxs-lookup"><span data-stu-id="850af-164">However, adding a constructor to a class that previously had no constructors *without* adding the parameterless constructor is not allowed.</span></span>

- <span data-ttu-id="850af-165">✔️ **허용: 구성원을 [추상](../../csharp/language-reference/keywords/abstract.md)에서 [가상](../../csharp/language-reference/keywords/virtual.md)으로 변경**</span><span class="sxs-lookup"><span data-stu-id="850af-165">✔️ **ALLOWED: Changing a member from [abstract](../../csharp/language-reference/keywords/abstract.md) to [virtual](../../csharp/language-reference/keywords/virtual.md)**</span></span>

- <span data-ttu-id="850af-166">✔️ **허용: `ref readonly`에서 `ref` 반환 값으로 변경(가상 메서드 또는 인터페이스 제외)**</span><span class="sxs-lookup"><span data-stu-id="850af-166">✔️ **ALLOWED: Changing from a `ref readonly` to a `ref` return value (except for virtual methods or interfaces)**</span></span>

- <span data-ttu-id="850af-167">✔️ **허용: 필드의 정적 형식이 변경할 수 있는 값 형식이 아닌 경우 필드에서 [readonly](../../csharp/language-reference/keywords/readonly.md) 제거**</span><span class="sxs-lookup"><span data-stu-id="850af-167">✔️ **ALLOWED: Removing [readonly](../../csharp/language-reference/keywords/readonly.md) from a field, unless the static type of the field is a mutable value type**</span></span>

- <span data-ttu-id="850af-168">✔️ **허용: 이전에 정의되지 않았던 새 이벤트 호출**</span><span class="sxs-lookup"><span data-stu-id="850af-168">✔️ **ALLOWED: Calling a new event that wasn't previously defined**</span></span>

- <span data-ttu-id="850af-169">❓ **판단 필요: 형식에 새 인스턴스 필드 추가**</span><span class="sxs-lookup"><span data-stu-id="850af-169">❓ **REQUIRES JUDGMENT: Adding a new instance field to a type**</span></span>

   <span data-ttu-id="850af-170">이 변경 내용은 serialization에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="850af-170">This change impacts serialization.</span></span>

- <span data-ttu-id="850af-171">❌ **허용 안 함: 공용 구성원 또는 매개 변수 이름 바꾸기 또는 제거**</span><span class="sxs-lookup"><span data-stu-id="850af-171">❌ **DISALLOWED: Renaming or removing a public member or parameter**</span></span>

   <span data-ttu-id="850af-172">이 경우 이름이 바뀌었거나 제거된 멤버 또는 매개 변수를 사용하는 모든 코드가 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="850af-172">This breaks all code that uses the renamed or removed member, or parameter.</span></span>

   <span data-ttu-id="850af-173">여기에는 속성에서 getter 또는 setter 제거 또는 이름 바꾸기, 열거형 구성원 이름 바꾸기 또는 제거가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="850af-173">This includes removing or renaming a getter or setter from a property, as well as renaming or removing enumeration members.</span></span>

- <span data-ttu-id="850af-174">❌ **허용 안 함: 인터페이스에 구성원 추가**</span><span class="sxs-lookup"><span data-stu-id="850af-174">❌ **DISALLOWED: Adding a member to an interface**</span></span>

- <span data-ttu-id="850af-175">❌ **허용 안 함: 공용 상수 또는 열거형 구성원의 값 변경**</span><span class="sxs-lookup"><span data-stu-id="850af-175">❌ **DISALLOWED: Changing the value of a public constant or enumeration member**</span></span>

- <span data-ttu-id="850af-176">❌ **허용 안 함: 속성, 필드, 매개 변수 또는 반환 값의 형식 변경**</span><span class="sxs-lookup"><span data-stu-id="850af-176">❌ **DISALLOWED: Changing the type of a property, field, parameter, or return value**</span></span>

- <span data-ttu-id="850af-177">❌ **허용 안 함: 매개 변수 추가, 제거 또는 순서 변경**</span><span class="sxs-lookup"><span data-stu-id="850af-177">❌ **DISALLOWED: Adding, removing, or changing the order of parameters**</span></span>

- <span data-ttu-id="850af-178">❌ **허용 안 함: 매개 변수에서 [in](../../csharp/language-reference/keywords/in.md), [out](../../csharp/language-reference/keywords/out.md) 또는 [ref](../../csharp/language-reference/keywords/ref.md) 키워드 추가 또는 제거**</span><span class="sxs-lookup"><span data-stu-id="850af-178">❌ **DISALLOWED: Adding or removing the [in](../../csharp/language-reference/keywords/in.md), [out](../../csharp/language-reference/keywords/out.md) , or [ref](../../csharp/language-reference/keywords/ref.md) keyword from a parameter**</span></span>

- <span data-ttu-id="850af-179">❌ **허용 안 함: 매개 변수 이름 바꾸기(대/소문자 변경 포함)**</span><span class="sxs-lookup"><span data-stu-id="850af-179">❌ **DISALLOWED: Renaming a parameter (including changing its case)**</span></span>

  <span data-ttu-id="850af-180">다음 두 가지 이유로 호환성이 손상되는 변경으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="850af-180">This is considered breaking for two reasons:</span></span>

  - <span data-ttu-id="850af-181">Visual Basic의 런타임에 바인딩 기능, C#의 [dynamic](../../csharp/language-reference/builtin-types/reference-types.md#the-dynamic-type)과 같은 런타임에 바인딩 시나리오의 호환성이 손상됩니다.</span><span class="sxs-lookup"><span data-stu-id="850af-181">It breaks late-bound scenarios such as the late binding feature in Visual Basic and [dynamic](../../csharp/language-reference/builtin-types/reference-types.md#the-dynamic-type) in C#.</span></span>

  - <span data-ttu-id="850af-182">개발자가 [명명된 인수](../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md#named-arguments)를 사용하는 경우 [소스 호환성](categories.md#source-compatibility)이 손상됩니다.</span><span class="sxs-lookup"><span data-stu-id="850af-182">It breaks [source compatibility](categories.md#source-compatibility) when developers use [named arguments](../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md#named-arguments).</span></span>

- <span data-ttu-id="850af-183">❌ **허용 안 함: `ref` 반환 값에서 `ref readonly` 반환 값으로 변경**</span><span class="sxs-lookup"><span data-stu-id="850af-183">❌ **DISALLOWED: Changing from a `ref` return value to a `ref readonly` return value**</span></span>

- <span data-ttu-id="850af-184">❌️ **허용 안 함: 가상 메서드 또는 인터페이스의 `ref readonly`에서 `ref` 반환 값으로 변경**</span><span class="sxs-lookup"><span data-stu-id="850af-184">❌️ **DISALLOWED: Changing from a `ref readonly` to a `ref` return value on a virtual method or interface**</span></span>

- <span data-ttu-id="850af-185">❌ **허용 안 함: 구성원에서 [추상](../../csharp/language-reference/keywords/abstract.md) 추가 또는 제거**</span><span class="sxs-lookup"><span data-stu-id="850af-185">❌ **DISALLOWED: Adding or removing [abstract](../../csharp/language-reference/keywords/abstract.md) from a member**</span></span>

- <span data-ttu-id="850af-186">❌ **허용 안 함: 구성원에서 [가상](../../csharp/language-reference/keywords/virtual.md) 키워드 제거**</span><span class="sxs-lookup"><span data-stu-id="850af-186">❌ **DISALLOWED: Removing the [virtual](../../csharp/language-reference/keywords/virtual.md) keyword from a member**</span></span>

  <span data-ttu-id="850af-187">C# 컴파일러는 비가상 메서드를 호출하기 위해 [callvirt](<xref:System.Reflection.Emit.OpCodes.Callvirt>) IL(중간 언어) 명령을 내보내는 경향이 있으므로(`callvirt`는 일반 호출과 달리 null 검사를 수행함) 호환성이 손상되는 변경이 아닌 경우가 많지만, 이 동작은 다음과 같은 몇 가지 이유로 가변적입니다.</span><span class="sxs-lookup"><span data-stu-id="850af-187">While this often is not a breaking change because the C# compiler tends to emit [callvirt](<xref:System.Reflection.Emit.OpCodes.Callvirt>) Intermediate Language (IL) instructions to call non-virtual methods (`callvirt` performs a null check, while a normal call doesn't), this behavior is not invariable for several reasons:</span></span>
  - <span data-ttu-id="850af-188">.NET의 대상 언어가 C#만은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="850af-188">C# is not the only language that .NET targets.</span></span>

  - <span data-ttu-id="850af-189">대상 메서드가 비가상이고 null이 아닐 수 있는 경우(예: [?. null 전파 연산자](../../csharp/language-reference/operators/member-access-operators.md#null-conditional-operators--and-)를 통해 액세스한 메서드), C# 컴파일러는 항상 `callvirt`를 일반 호출에 최적화하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="850af-189">The C# compiler increasingly tries to optimize `callvirt` to a normal call whenever the target method is non-virtual and is probably not null (such as a method accessed through the [?. null propagation operator](../../csharp/language-reference/operators/member-access-operators.md#null-conditional-operators--and-)).</span></span>

  <span data-ttu-id="850af-190">메서드를 virtual로 설정하면 소비자 코드에서 비가상적으로 메서드를 호출하게 되는 경우가 자주 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="850af-190">Making a method virtual means that the consumer code would often end up calling it non-virtually.</span></span>

- <span data-ttu-id="850af-191">❌ **허용 안 함: 구성원에 [가상](../../csharp/language-reference/keywords/virtual.md) 키워드 추가**</span><span class="sxs-lookup"><span data-stu-id="850af-191">❌ **DISALLOWED: Adding the [virtual](../../csharp/language-reference/keywords/virtual.md) keyword to a member**</span></span>

- <span data-ttu-id="850af-192">❌ **허용 안 함: 가상 구성원을 추상으로 설정**</span><span class="sxs-lookup"><span data-stu-id="850af-192">❌ **DISALLOWED: Making a virtual member abstract**</span></span>

  <span data-ttu-id="850af-193">[가상 멤버](../../csharp/language-reference/keywords/virtual.md)는 파생 클래스에서 재정의할 수 있는 메서드 구현을 제공합니다. </span><span class="sxs-lookup"><span data-stu-id="850af-193">A [virtual member](../../csharp/language-reference/keywords/virtual.md) provides a method implementation that *can be* overridden by a derived class.</span></span> <span data-ttu-id="850af-194">[추상 멤버](../../csharp/language-reference/keywords/abstract.md)는 구현을 제공하지 않으므로 재정의해야 합니다. </span><span class="sxs-lookup"><span data-stu-id="850af-194">An [abstract member](../../csharp/language-reference/keywords/abstract.md) provides no implementation and *must be* overridden.</span></span>

- <span data-ttu-id="850af-195">❌ **허용 안 함: 액세스할 수 있는(공용 또는 보호된) 생성자가 있고 [봉인된](../../csharp/language-reference/keywords/sealed.md) 형식이 아닌 공용 형식에 추상 구성원 추가**</span><span class="sxs-lookup"><span data-stu-id="850af-195">❌ **DISALLOWED: Adding an abstract member to a public type that has accessible (public or protected) constructors and that is not [sealed](../../csharp/language-reference/keywords/sealed.md)**</span></span>

- <span data-ttu-id="850af-196">❌ **허용 안 함: 구성원에서 [고정](../../csharp/language-reference/keywords/static.md) 키워드 추가 또는 제거**</span><span class="sxs-lookup"><span data-stu-id="850af-196">❌ **DISALLOWED: Adding or removing the [static](../../csharp/language-reference/keywords/static.md) keyword from a member**</span></span>

- <span data-ttu-id="850af-197">❌ **허용 안 함: 기존 오버로드를 차단하고 다른 동작을 정의하는 오버로드 추가**</span><span class="sxs-lookup"><span data-stu-id="850af-197">❌ **DISALLOWED: Adding an overload that precludes an existing overload and defines a different behavior**</span></span>

  <span data-ttu-id="850af-198">이전 오버로드에 바인딩된 기존 클라이언트의 호환성이 손상됩니다.</span><span class="sxs-lookup"><span data-stu-id="850af-198">This breaks existing clients that were bound to the previous overload.</span></span> <span data-ttu-id="850af-199">예를 들어 클래스에 <xref:System.UInt32>를 허용하는 메서드의 단일 버전이 있는 경우, 기존 소비자가 <xref:System.Int32> 값을 전달할 때 해당 오버로드에 성공적으로 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="850af-199">For example, if a class has a single version of a method that accepts a <xref:System.UInt32>, an existing consumer will successfully bind to that overload when passing a <xref:System.Int32> value.</span></span> <span data-ttu-id="850af-200">그러나 <xref:System.Int32>를 허용하는 오버로드를 추가하면, 다시 컴파일하거나 런타임에 바인딩을 사용할 때 이제 컴파일러가 새 오버로드에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="850af-200">However, if you add an overload that accepts an <xref:System.Int32>, when recompiling or using late-binding, the compiler now binds to the new overload.</span></span> <span data-ttu-id="850af-201">다른 동작이 발생하는 경우 호환성이 손상되는 변경입니다.</span><span class="sxs-lookup"><span data-stu-id="850af-201">If different behavior results, this is a breaking change.</span></span>

- <span data-ttu-id="850af-202">❌ **허용 안 함: 매개 변수가 없는 생성자를 추가하지 않고 이전에 생성자가 없었던 클래스에 생성자 추가**</span><span class="sxs-lookup"><span data-stu-id="850af-202">❌ **DISALLOWED: Adding a constructor to a class that previously had no constructor without adding the parameterless constructor**</span></span>

- <span data-ttu-id="850af-203">❌️ **허용 안 함: 필드에 [readonly](../../csharp/language-reference/keywords/readonly.md) 추가**</span><span class="sxs-lookup"><span data-stu-id="850af-203">❌️ **DISALLOWED: Adding [readonly](../../csharp/language-reference/keywords/readonly.md) to a field**</span></span>

- <span data-ttu-id="850af-204">❌ **허용 안 함: 구성원의 표시 유형 축소**</span><span class="sxs-lookup"><span data-stu-id="850af-204">❌ **DISALLOWED: Reducing the visibility of a member**</span></span>

   <span data-ttu-id="850af-205">여기에는 형식에 *액세스할 수 있는*(`public` 또는 `protected`) 생성자가 있고 [봉인된](../../csharp/language-reference/keywords/sealed.md) 형식이 *아닌* 경우 [보호된](../../csharp/language-reference/keywords/protected.md) 구성원의 표시 유형을 줄이는 경우가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="850af-205">This includes reducing the visibility of a [protected](../../csharp/language-reference/keywords/protected.md) member when there are *accessible* (`public` or `protected`) constructors and the type is *not* [sealed](../../csharp/language-reference/keywords/sealed.md).</span></span> <span data-ttu-id="850af-206">이러한 경우가 아니면 보호된 멤버의 표시 유형을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="850af-206">If this is not the case, reducing the visibility of a protected member is allowed.</span></span>

   <span data-ttu-id="850af-207">구성원의 표시 유형은 늘릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="850af-207">Increasing the visibility of a member is allowed.</span></span>

- <span data-ttu-id="850af-208">❌ **허용 안 함: 구성원의 형식 변경**</span><span class="sxs-lookup"><span data-stu-id="850af-208">❌ **DISALLOWED: Changing the type of a member**</span></span>

   <span data-ttu-id="850af-209">메서드의 반환 값이나 속성 또는 필드의 형식을 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="850af-209">The return value of a method or the type of a property or field cannot be modified.</span></span> <span data-ttu-id="850af-210">예를 들어 <xref:System.Object>가 반환되는 메서드의 시그니처를 <xref:System.String>이 반환되도록 변경할 수 없으며, 그 반대의 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="850af-210">For example, the signature of a method that returns an <xref:System.Object> cannot be changed to return a <xref:System.String>, or vice versa.</span></span>

- <span data-ttu-id="850af-211">❌ **허용 안 함: 이전에 상태가 없었던 구조체에 필드 추가**</span><span class="sxs-lookup"><span data-stu-id="850af-211">❌ **DISALLOWED: Adding a field to a struct that previously had no state**</span></span>

  <span data-ttu-id="850af-212">변수 형식이 상태 비저장 구조체이기만 하면, 한정된 할당 규칙에서 초기화되지 않은 변수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="850af-212">Definite assignment rules allow the use of uninitialized variables so long as the variable type is a stateless struct.</span></span> <span data-ttu-id="850af-213">구조체를 상태 저장으로 설정하면, 코드에서 초기화되지 않은 데이터가 생성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="850af-213">If the struct is made stateful, code could end up with uninitialized data.</span></span> <span data-ttu-id="850af-214">이 변경은 잠재적으로 호환성이 손상되는 소스 및 이진 변경입니다.</span><span class="sxs-lookup"><span data-stu-id="850af-214">This is both potentially a source breaking and a binary breaking change.</span></span>

- <span data-ttu-id="850af-215">❌ **허용 안 함: 이전에는 발생하지 않았던 시기에 기존 이벤트 발생**</span><span class="sxs-lookup"><span data-stu-id="850af-215">❌ **DISALLOWED: Firing an existing event when it was never fired before**</span></span>

## <a name="behavioral-changes"></a><span data-ttu-id="850af-216">동작 변경</span><span class="sxs-lookup"><span data-stu-id="850af-216">Behavioral changes</span></span>

### <a name="assemblies"></a><span data-ttu-id="850af-217">어셈블리</span><span class="sxs-lookup"><span data-stu-id="850af-217">Assemblies</span></span>

- <span data-ttu-id="850af-218">✔️ **허용: 동일한 플랫폼이 여전히 지원될 때 어셈블리를 이식 가능으로 설정**</span><span class="sxs-lookup"><span data-stu-id="850af-218">✔️ **ALLOWED: Making an assembly portable when the same platforms are still supported**</span></span>

- <span data-ttu-id="850af-219">❌ **허용 안 함: 어셈블리 이름 변경**</span><span class="sxs-lookup"><span data-stu-id="850af-219">❌ **DISALLOWED: Changing the name of an assembly**</span></span>
- <span data-ttu-id="850af-220">❌ **허용 안 함: 어셈블리의 공개 키 변경**</span><span class="sxs-lookup"><span data-stu-id="850af-220">❌ **DISALLOWED: Changing the public key of an assembly**</span></span>

### <a name="properties-fields-parameters-and-return-values"></a><span data-ttu-id="850af-221">속성, 필드, 매개 변수 및 반환 값</span><span class="sxs-lookup"><span data-stu-id="850af-221">Properties, fields, parameters, and return values</span></span>

- <span data-ttu-id="850af-222">✔️ **허용: 속성, 필드, 반환 값 또는 [out](../../csharp/language-reference/keywords/out-parameter-modifier.md) 매개 변수의 값을 더 파생된 형식으로 변경**</span><span class="sxs-lookup"><span data-stu-id="850af-222">✔️ **ALLOWED: Changing the value of a property, field, return value, or [out](../../csharp/language-reference/keywords/out-parameter-modifier.md) parameter to a more derived type**</span></span>

  <span data-ttu-id="850af-223">예를 들어 <xref:System.Object> 형식을 반환하는 메서드는 <xref:System.String> 인스턴스를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="850af-223">For example, a method that returns a type of <xref:System.Object> can return a <xref:System.String> instance.</span></span> <span data-ttu-id="850af-224">단, 메서드 시그니처는 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="850af-224">(However, the method signature cannot change.)</span></span>

- <span data-ttu-id="850af-225">✔️ **허용: 구성원이 [가상](../../csharp/language-reference/keywords/virtual.md)이 아닌 경우 속성 또는 매개 변수에 허용되는 값의 범위 확장**</span><span class="sxs-lookup"><span data-stu-id="850af-225">✔️ **ALLOWED: Increasing the range of accepted values for a property or parameter if the member is not [virtual](../../csharp/language-reference/keywords/virtual.md)**</span></span>

  <span data-ttu-id="850af-226">메서드에 전달할 수 있거나 구성원에서 반환되는 값의 범위는 확장할 수 있지만, 매개 변수 또는 구성원 형식은 확장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="850af-226">While the range of values that can be passed to the method or are returned by the member can expand, the parameter or member type cannot.</span></span> <span data-ttu-id="850af-227">예를 들어 메서드에 전달되는 값은 0~124에서 0~255로 확장할 수 있지만, 매개 변수 형식은 <xref:System.Byte>에서 <xref:System.Int32>로 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="850af-227">For example, while the values passed to a method can expand from 0-124 to 0-255, the parameter type cannot change from <xref:System.Byte> to <xref:System.Int32>.</span></span>

- <span data-ttu-id="850af-228">❌ **허용 안 함: 구성원이 [가상](../../csharp/language-reference/keywords/virtual.md)인 경우 속성 또는 매개 변수에 허용되는 값의 범위 확장**</span><span class="sxs-lookup"><span data-stu-id="850af-228">❌ **DISALLOWED: Increasing the range of accepted values for a property or parameter if the member is [virtual](../../csharp/language-reference/keywords/virtual.md)**</span></span>

   <span data-ttu-id="850af-229">이 변경으로 인해 확장된 값 범위에서 제대로 작동하지 않는 재정의된 기존 멤버의 호환성이 손상됩니다.</span><span class="sxs-lookup"><span data-stu-id="850af-229">This change breaks existing overridden members, which will not function correctly for the extended range of values.</span></span>

- <span data-ttu-id="850af-230">❌ **허용 안 함: 속성 또는 매개 변수에 허용되는 값의 범위 축소**</span><span class="sxs-lookup"><span data-stu-id="850af-230">❌ **DISALLOWED: Decreasing the range of accepted values for a property or parameter**</span></span>

- <span data-ttu-id="850af-231">❌ **허용 안 함: 속성, 필드, 반환 값 또는 [out](../../csharp/language-reference/keywords/out-parameter-modifier.md) 매개 변수의 반환 값 범위 확장**</span><span class="sxs-lookup"><span data-stu-id="850af-231">❌ **DISALLOWED: Increasing the range of returned values for a property, field, return value, or [out](../../csharp/language-reference/keywords/out-parameter-modifier.md) parameter**</span></span>

- <span data-ttu-id="850af-232">❌ **허용 안 함: 속성, 필드, 메서드 반환 값 또는 [out](../../csharp/language-reference/keywords/out-parameter-modifier.md) 매개 변수의 반환 값 변경**</span><span class="sxs-lookup"><span data-stu-id="850af-232">❌ **DISALLOWED: Changing the returned values for a property, field, method return value, or [out](../../csharp/language-reference/keywords/out-parameter-modifier.md) parameter**</span></span>

- <span data-ttu-id="850af-233">❌ **허용 안 함: 속성, 필드 또는 매개 변수의 기본값 변경**</span><span class="sxs-lookup"><span data-stu-id="850af-233">❌ **DISALLOWED: Changing the default value of a property, field, or parameter**</span></span>

- <span data-ttu-id="850af-234">❌ **허용 안 함: 숫자 반환 값의 정밀도 변경**</span><span class="sxs-lookup"><span data-stu-id="850af-234">❌ **DISALLOWED: Changing the precision of a numeric return value**</span></span>

- <span data-ttu-id="850af-235">❓ **판단 필요: 입력 구문 분석 및 새 예외 throw 변경(구문 분석 동작이 문서에 지정되지 않은 경우 포함)**</span><span class="sxs-lookup"><span data-stu-id="850af-235">❓ **REQUIRES JUDGMENT: A change in the parsing of input and throwing new exceptions (even if parsing behavior is not specified in the documentation**</span></span>

### <a name="exceptions"></a><span data-ttu-id="850af-236">예외</span><span class="sxs-lookup"><span data-stu-id="850af-236">Exceptions</span></span>

- <span data-ttu-id="850af-237">✔️ **허용: 기존 예외보다 더 파생된 예외 throw**</span><span class="sxs-lookup"><span data-stu-id="850af-237">✔️ **ALLOWED: Throwing a more derived exception than an existing exception**</span></span>

  <span data-ttu-id="850af-238">새 예외가 기존 예외의 서브클래스이기 때문에, 이전 예외 처리 코드에서 계속 예외를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="850af-238">Because the new exception is a subclass of an existing exception, previous exception handling code continues to handle the exception.</span></span> <span data-ttu-id="850af-239">예를 들어 .NET Framework 4에서는 문화권을 찾을 수 없는 경우 문화권 만들기 및 검색 메서드가 <xref:System.ArgumentException> 대신 <xref:System.Globalization.CultureNotFoundException>을 throw하기 시작했습니다.</span><span class="sxs-lookup"><span data-stu-id="850af-239">For example, in .NET Framework 4, culture creation and retrieval methods began to throw a <xref:System.Globalization.CultureNotFoundException> instead of an <xref:System.ArgumentException> if the culture could not be found.</span></span> <span data-ttu-id="850af-240"><xref:System.Globalization.CultureNotFoundException>은 <xref:System.ArgumentException>에서 파생되기 때문에 허용되는 변경입니다.</span><span class="sxs-lookup"><span data-stu-id="850af-240">Because <xref:System.Globalization.CultureNotFoundException> derives from <xref:System.ArgumentException>, this is an acceptable change.</span></span>

- <span data-ttu-id="850af-241">✔️ **허용: <xref:System.NotSupportedException>, <xref:System.NotImplementedException>, <xref:System.NullReferenceException>보다 더 구체적인 예외 throw**</span><span class="sxs-lookup"><span data-stu-id="850af-241">✔️ **ALLOWED: Throwing a more specific exception than <xref:System.NotSupportedException>, <xref:System.NotImplementedException>, <xref:System.NullReferenceException>**</span></span>

- <span data-ttu-id="850af-242">✔️ **허용: 복구할 수 없는 것으로 간주되는 예외 throw**</span><span class="sxs-lookup"><span data-stu-id="850af-242">✔️ **ALLOWED: Throwing an exception that is considered unrecoverable**</span></span>

  <span data-ttu-id="850af-243">복구할 수 없는 예외는 catch하지 않고, 높은 수준의 범용 처리기에서 처리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="850af-243">Unrecoverable exceptions should not be caught but instead should be handled by a high-level catch-all handler.</span></span> <span data-ttu-id="850af-244">따라서 사용자는 이러한 명시적 예외를 catch하는 코드를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="850af-244">Therefore, users are not expected to have code that catches these explicit exceptions.</span></span> <span data-ttu-id="850af-245">복구할 수 없는 예외는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="850af-245">The unrecoverable exceptions are:</span></span>

  - <xref:System.AccessViolationException>
  - <xref:System.ExecutionEngineException>
  - <xref:System.Runtime.InteropServices.SEHException>
  - <xref:System.StackOverflowException>

- <span data-ttu-id="850af-246">✔️ **허용: 새 코드 경로에서 새 예외 throw**</span><span class="sxs-lookup"><span data-stu-id="850af-246">✔️ **ALLOWED: Throwing a new exception in a new code path**</span></span>

  <span data-ttu-id="850af-247">새 매개 변수 값 또는 상태로 실행되었으며, 이전 버전을 대상으로 하는 기존 코드에서 실행할 수 없는 새 코드 경로에만 예외를 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="850af-247">The exception must apply only to a new code-path that's executed with new parameter values or state and that can't be executed by existing code that targets the previous version.</span></span>

- <span data-ttu-id="850af-248">✔️ **허용: 더욱 강력한 동작이나 새로운 시나리오를 사용하기 위해 예외 제거**</span><span class="sxs-lookup"><span data-stu-id="850af-248">✔️ **ALLOWED: Removing an exception to enable more robust behavior or new scenarios**</span></span>

  <span data-ttu-id="850af-249">예를 들어 이전에는 양수 값만 처리하고, 양수 값이 아닐 경우 <xref:System.ArgumentOutOfRangeException>을 throw한 `Divide` 메서드에서 예외를 throw하지 않고 음수 값과 양수 값을 모두 지원하도록 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="850af-249">For example, a `Divide` method that previously only handled positive values and threw an <xref:System.ArgumentOutOfRangeException> otherwise can be changed to support both negative and positive values without throwing an exception.</span></span>

- <span data-ttu-id="850af-250">✔️ **허용: 오류 메시지의 텍스트 변경**</span><span class="sxs-lookup"><span data-stu-id="850af-250">✔️ **ALLOWED: Changing the text of an error message**</span></span>

  <span data-ttu-id="850af-251">개발자는 사용자의 문화권에 따라 변경되는 오류 메시지의 텍스트에 의존해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="850af-251">Developers should not rely on the text of error messages, which also change based on the user's culture.</span></span>

- <span data-ttu-id="850af-252">❌ **허용 안 함: 위에 나열되지 않은 다른 모든 경우의 예외 throw**</span><span class="sxs-lookup"><span data-stu-id="850af-252">❌ **DISALLOWED: Throwing an exception in any other case not listed above**</span></span>

- <span data-ttu-id="850af-253">❌ **허용 안 함: 위에 나열되지 않은 다른 모든 경우의 예외 제거**</span><span class="sxs-lookup"><span data-stu-id="850af-253">❌ **DISALLOWED: Removing an exception in any other case not listed above**</span></span>

### <a name="attributes"></a><span data-ttu-id="850af-254">특성</span><span class="sxs-lookup"><span data-stu-id="850af-254">Attributes</span></span>

- <span data-ttu-id="850af-255">✔️ **허용: 식별할 수 *없는* 특성 값 변경**</span><span class="sxs-lookup"><span data-stu-id="850af-255">✔️ **ALLOWED: Changing the value of an attribute that is *not* observable**</span></span>

- <span data-ttu-id="850af-256">❌ **허용 안 함: 식별할 수 *있는* 특성 값 변경**</span><span class="sxs-lookup"><span data-stu-id="850af-256">❌ **DISALLOWED: Changing the value of an attribute that *is* observable**</span></span>

- <span data-ttu-id="850af-257">❓ **판단 필요: 특성 제거**</span><span class="sxs-lookup"><span data-stu-id="850af-257">❓ **REQUIRES JUDGMENT: Removing an attribute**</span></span>

  <span data-ttu-id="850af-258">대부분의 경우, <xref:System.NonSerializedAttribute>와 같은 특성 제거는 호환성이 손상되는 변경입니다.</span><span class="sxs-lookup"><span data-stu-id="850af-258">In most cases, removing an attribute (such as <xref:System.NonSerializedAttribute>) is a breaking change.</span></span>

## <a name="platform-support"></a><span data-ttu-id="850af-259">플랫폼 지원</span><span class="sxs-lookup"><span data-stu-id="850af-259">Platform support</span></span>

- <span data-ttu-id="850af-260">✔️ **허용: 플랫폼에서 이전에 지원되지 않았던 작업 지원**</span><span class="sxs-lookup"><span data-stu-id="850af-260">✔️ **ALLOWED: Supporting an operation on a platform that was previously not supported**</span></span>

- <span data-ttu-id="850af-261">❌ **허용 안 함: 이전에 플랫폼에서 지원된 작업에 대해 특정 서비스 팩 요구 또는 지원 안 함**</span><span class="sxs-lookup"><span data-stu-id="850af-261">❌ **DISALLOWED: Not supporting or now requiring a specific service pack for an operation that was previously supported on a platform**</span></span>

## <a name="internal-implementation-changes"></a><span data-ttu-id="850af-262">내부 구현 변경</span><span class="sxs-lookup"><span data-stu-id="850af-262">Internal implementation changes</span></span>

- <span data-ttu-id="850af-263">❓ **판단 필요: 내부 형식의 노출 영역 변경**</span><span class="sxs-lookup"><span data-stu-id="850af-263">❓ **REQUIRES JUDGMENT: Changing the surface area of an internal type**</span></span>

   <span data-ttu-id="850af-264">해당 변경은 프라이빗 리플렉션의 호환성이 손상되는 변경이지만 일반적으로 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="850af-264">Such changes are generally allowed, although they break private reflection.</span></span> <span data-ttu-id="850af-265">인기 있는 타사 라이브러리 또는 많은 개발자가 내부 API를 사용하는 경우에는 이러한 변경이 허용되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="850af-265">In some cases, where popular third-party libraries or a large number of developers depend on the internal APIs, such changes may not be allowed.</span></span>

- <span data-ttu-id="850af-266">❓ **판단 필요: 구성원의 내부 구현 변경**</span><span class="sxs-lookup"><span data-stu-id="850af-266">❓ **REQUIRES JUDGMENT: Changing the internal implementation of a member**</span></span>

  <span data-ttu-id="850af-267">이러한 변경은 프라이빗 리플렉션의 호환성이 손상되는 변경이지만 일반적으로 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="850af-267">These changes are generally allowed, although they break private reflection.</span></span> <span data-ttu-id="850af-268">고객 코드가 프라이빗 리플렉션에 자주 종속되거나, 이 변경으로 인해 의도하지 않은 부작용이 도입되는 경우에는 이러한 변경이 허용되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="850af-268">In some cases, where customer code frequently depends on private reflection or where the change introduces unintended side effects, these changes may not be allowed.</span></span>

- <span data-ttu-id="850af-269">✔️ **허용: 작업 성능 향상**</span><span class="sxs-lookup"><span data-stu-id="850af-269">✔️ **ALLOWED: Improving the performance of an operation**</span></span>

   <span data-ttu-id="850af-270">작업 성능을 수정하는 기능은 필수지만, 이러한 변경으로 인해 현재 작업 속도에 의존하는 코드의 호환성이 손상될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="850af-270">The ability to modify the performance of an operation is essential, but such changes can break code that relies upon the current speed of an operation.</span></span> <span data-ttu-id="850af-271">비동기 작업 타이밍에 종속된 코드의 경우 특히 그렇습니다.</span><span class="sxs-lookup"><span data-stu-id="850af-271">This is particularly true of code that depends on the timing of asynchronous operations.</span></span> <span data-ttu-id="850af-272">성능 변경은 해당 API의 다른 동작에 영향을 주지 않아야 합니다. 영향을 주면 호환성이 손상되는 변경이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="850af-272">The performance change should have no effect on other behavior of the API in question; otherwise, the change will be breaking.</span></span>

- <span data-ttu-id="850af-273">✔️ **허용: 간접적으로(때로는 부정적으로) 작업 성능 변경**</span><span class="sxs-lookup"><span data-stu-id="850af-273">✔️ **ALLOWED: Indirectly (and often adversely) changing the performance of an operation**</span></span>

  <span data-ttu-id="850af-274">해당 변경이 다른 이유로 호환성이 손상되는 변경으로 분류되지 않은 경우에는 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="850af-274">If the change in question is not categorized as breaking for some other reason, this is acceptable.</span></span> <span data-ttu-id="850af-275">추가 작업을 포함할 수 있거나 새 기능을 추가하는 조치를 수행해야 하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="850af-275">Often, actions need to be taken that may include extra operations or that add new functionality.</span></span> <span data-ttu-id="850af-276">이 변경은 거의 항상, 성능에 영향을 주지만 해당 API가 예상대로 작동하는 데 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="850af-276">This will almost always affect performance but may be essential to make the API in question function as expected.</span></span>

- <span data-ttu-id="850af-277">❌ **허용 안 함: 동기 API를 비동기로 변경하거나 그 반대로 변경**</span><span class="sxs-lookup"><span data-stu-id="850af-277">❌ **DISALLOWED: Changing a synchronous API to asynchronous (and vice versa)**</span></span>

## <a name="code-changes"></a><span data-ttu-id="850af-278">코드 변경 내용</span><span class="sxs-lookup"><span data-stu-id="850af-278">Code changes</span></span>

- <span data-ttu-id="850af-279">✔️ **허용: 매개 변수에 [params](../../csharp/language-reference/keywords/params.md) 추가**</span><span class="sxs-lookup"><span data-stu-id="850af-279">✔️ **ALLOWED: Adding [params](../../csharp/language-reference/keywords/params.md) to a parameter**</span></span>

- <span data-ttu-id="850af-280">❌ **허용 안 함: [구조체](../../csharp/language-reference/builtin-types/struct.md)를 [클래스](../../csharp/language-reference/keywords/class.md)로 변경하거나 그 반대로 변경**</span><span class="sxs-lookup"><span data-stu-id="850af-280">❌ **DISALLOWED: Changing a [struct](../../csharp/language-reference/builtin-types/struct.md) to a [class](../../csharp/language-reference/keywords/class.md) and vice versa**</span></span>

- <span data-ttu-id="850af-281">❌ **허용 안 함: 코드 블록에 [확인됨](../../csharp/language-reference/keywords/virtual.md) 키워드 추가**</span><span class="sxs-lookup"><span data-stu-id="850af-281">❌ **DISALLOWED: Adding the [checked](../../csharp/language-reference/keywords/virtual.md) keyword to a code block**</span></span>

   <span data-ttu-id="850af-282">이 변경으로 인해 이전에 실행되었던 코드에서 <xref:System.OverflowException>이 throw될 수 있으므로 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="850af-282">This change may cause code that previously executed to throw an <xref:System.OverflowException> and is unacceptable.</span></span>

- <span data-ttu-id="850af-283">❌ **허용 안 함: 매개 변수에서 [params](../../csharp/language-reference/keywords/params.md) 제거**</span><span class="sxs-lookup"><span data-stu-id="850af-283">❌ **DISALLOWED: Removing [params](../../csharp/language-reference/keywords/params.md) from a parameter**</span></span>

- <span data-ttu-id="850af-284">❌ **허용 안 함: 이벤트 발생 순서 변경**</span><span class="sxs-lookup"><span data-stu-id="850af-284">❌ **DISALLOWED: Changing the order in which events are fired**</span></span>

  <span data-ttu-id="850af-285">개발자는 이벤트가 동일한 순서로 발생할 것으로 기대할 수 있으며, 개발자 코드가 이벤트 발생 순서에 종속된 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="850af-285">Developers can reasonably expect events to fire in the same order, and developer code frequently depends on the order in which events are fired.</span></span>

- <span data-ttu-id="850af-286">❌ **허용 안 함: 지정된 동작에서 이벤트 발생 제거**</span><span class="sxs-lookup"><span data-stu-id="850af-286">❌ **DISALLOWED: Removing the raising of an event on a given action**</span></span>

- <span data-ttu-id="850af-287">❌ **허용 안 함: 지정된 이벤트 호출 횟수 변경**</span><span class="sxs-lookup"><span data-stu-id="850af-287">❌ **DISALLOWED: Changing the number of times given events are called**</span></span>

- <span data-ttu-id="850af-288">❌ **허용 안 함: 열거형 형식에 <xref:System.FlagsAttribute> 추가**</span><span class="sxs-lookup"><span data-stu-id="850af-288">❌ **DISALLOWED: Adding the <xref:System.FlagsAttribute> to an enumeration type**</span></span>
