---
title: 언어 독립성 및 언어 독립적 구성 요소
description: C#, C++/CLI, F#, IronPython, VB, Visual COBOL, PowerShell 등 .NET에서 지원되는 많은 언어 중 하나로 개발할 수 있는 방법을 알아봅니다.
dev_langs:
- csharp
- vb
ms.date: 07/22/2016
ms.assetid: 2dbed1bc-86f5-43cd-9a57-adbb1c5efba4
ms.openlocfilehash: 0cd8179de929ea55212d600844e658d6946861ab
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102103077"
---
# <a name="language-independence-and-language-independent-components"></a><span data-ttu-id="d6622-103">언어 독립성 및 언어 독립적 구성 요소</span><span class="sxs-lookup"><span data-stu-id="d6622-103">Language independence and language-independent components</span></span>

<span data-ttu-id="d6622-104">.NET은 언어 독립적입니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-104">.NET is language independent.</span></span> <span data-ttu-id="d6622-105">즉, 개발자는 C#, F#, Visual Basic 등의 .NET 구현을 대상으로 하는 많은 언어 중 하나로 개발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-105">This means that, as a developer, you can develop in one of the many languages that target .NET implementations, such as C#, F#, and Visual Basic.</span></span> <span data-ttu-id="d6622-106">원래 작성된 언어를 모르거나 원래의 언어 규칙을 따르지 않고도 .NET 구현용으로 개발된 클래스 라이브러리의 형식과 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-106">You can access the types and members of class libraries developed for .NET implementations without having to know the language in which they were originally written and without having to follow any of the original language's conventions.</span></span> <span data-ttu-id="d6622-107">구성 요소 개발자인 경우 해당 언어와 관계없이 모든 .NET 앱에서 구성 요소에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-107">If you're a component developer, your component can be accessed by any .NET app, regardless of its language.</span></span>

> [!NOTE]
> <span data-ttu-id="d6622-108">이 문서의 첫 부분에서는 언어 독립 구성 요소를 만드는 방법에 대해 설명합니다. 즉, 이러한 구성 요소는 어떠한 언어로 작성된 앱에서도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-108">This first part of this article discusses creating language-independent components, that is, components that can be consumed by apps that are written in any language.</span></span> <span data-ttu-id="d6622-109">여러 언어로 작성된 소스 코드에서 구성 요소나 앱을 하나 만들 수도 있습니다. 이 문서의 두 번째 부분에서 [언어 간 상호 운용성](#cross-language-interoperability)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d6622-109">You can also create a single component or app from source code written in multiple languages; see [Cross-Language Interoperability](#cross-language-interoperability) in the second part of this article.</span></span>

<span data-ttu-id="d6622-110">어떠한 언어로 작성된 다른 개체와도 완전하게 상호 작용하려면 개체는 모든 언어에 공통적인 기능만 호출자에게 노출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-110">To fully interact with other objects written in any language, objects must expose to callers only those features that are common to all languages.</span></span> <span data-ttu-id="d6622-111">기능의 공통 집합은 생성된 어셈블리에 적용되는 규칙 집합인 CLS(공용 언어 사양)에서 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-111">This common set of features is defined by the Common Language Specification (CLS), which is a set of rules that apply to generated assemblies.</span></span> <span data-ttu-id="d6622-112">공용 언어 사양은 [ECMA-335 Standard: Common Language Infrastructure](https://www.ecma-international.org/publications-and-standards/standards/ecma-335/)의 Partition I, Clauses 7~11에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-112">The Common Language Specification is defined in Partition I, Clauses 7 through 11 of the [ECMA-335 Standard: Common Language Infrastructure](https://www.ecma-international.org/publications-and-standards/standards/ecma-335/).</span></span>

<span data-ttu-id="d6622-113">구성 요소가 공용 언어 사양을 따르는 경우, 이 구성 요소는 CLS 규격임이 보장되고 CLS를 지원하는 모든 프로그래밍 언어로 작성된 어셈블리 코드에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-113">If your component conforms to the Common Language Specification, it is guaranteed to be CLS-compliant and can be accessed from code in assemblies written in any programming language that supports the CLS.</span></span> <span data-ttu-id="d6622-114">[CLSCompliantAttribute](xref:System.CLSCompliantAttribute) 특성을 소스 코드에 적용하여 구성 요소가 컴파일 시간에 공용 언어 사양을 준수하는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-114">You can determine whether your component conforms to the Common Language Specification at compile time by applying the [CLSCompliantAttribute](xref:System.CLSCompliantAttribute) attribute to your source code.</span></span> <span data-ttu-id="d6622-115">자세한 내용은 [CLSCompliantAttribute 특성](#the-clscompliantattribute-attribute)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d6622-115">For more information, see [The CLSCompliantAttribute attribute](#the-clscompliantattribute-attribute).</span></span>

## <a name="cls-compliance-rules"></a><span data-ttu-id="d6622-116">CLS 규격 규칙</span><span class="sxs-lookup"><span data-stu-id="d6622-116">CLS compliance rules</span></span>

<span data-ttu-id="d6622-117">이 섹션에서는 CLS 규격 구성 요소를 만드는 규칙을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-117">This section discusses the rules for creating a CLS-compliant component.</span></span> <span data-ttu-id="d6622-118">규칙의 전체 목록은 [ECMA-335 Standard: Common Language Infrastructure](https://www.ecma-international.org/publications-and-standards/standards/ecma-335/)의 Partition I, Clauses 11에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-118">For a complete list of rules, see Partition I, Clause 11 of the [ECMA-335 Standard: Common Language Infrastructure](https://www.ecma-international.org/publications-and-standards/standards/ecma-335/).</span></span>

> [!NOTE]
> <span data-ttu-id="d6622-119">공용 언어 사양에서는 소비자(CLS 규격인 구성 요소를 프로그래밍 방식으로 액세스하는 개발자), 프레임워크(언어 컴파일러를 사용하여 CLS 규격 라이브러리를 만드는 개발자) 및 extender(CLS 규격 구성 요소를 생성하는 언어 컴파일러 또는 코드 파서 등의 도구를 만드는 개발자)에게 적용되는 CLS 규격에 대한 각 규칙을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-119">The Common Language Specification discusses each rule for CLS compliance as it applies to consumers (developers who are programmatically accessing a component that is CLS-compliant), frameworks (developers who are using a language compiler to create CLS-compliant libraries), and extenders (developers who are creating a tool such as a language compiler or a code parser that creates CLS-compliant components).</span></span> <span data-ttu-id="d6622-120">이 문서에서는 프레임워크에 적용되는 규칙에 초점을 맞춥니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-120">This article focuses on the rules as they apply to frameworks.</span></span> <span data-ttu-id="d6622-121">그러나 extender에 적용되는 규칙 중 일부는 [Reflection.Emit](xref:System.Reflection.Emit)를 사용하여 만든 어셈블리에도 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-121">Note, though, that some of the rules that apply to extenders may also apply to assemblies that are created using [Reflection.Emit](xref:System.Reflection.Emit).</span></span>

<span data-ttu-id="d6622-122">언어 독립적인 구성 요소를 디자인하려면 CLS 규격의 규칙을 구성 요소의 공용 인터페이스에 적용하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-122">To design a component that is language independent, you only need to apply the rules for CLS compliance to your component's public interface.</span></span> <span data-ttu-id="d6622-123">private 구현은 사양을 준수할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-123">Your private implementation does not have to conform to the specification.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d6622-124">CLS 규격의 규칙은 구성 요소의 public 인터페이스에만 적용되고 private 구현에는 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-124">The rules for CLS compliance apply only to a component's public interface, not to its private implementation.</span></span>

<span data-ttu-id="d6622-125">예를 들어 [Byte](xref:System.Byte) 이외의 부호 없는 정수는 CLS 규격이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-125">For example, unsigned integers other than [Byte](xref:System.Byte) are not CLS-compliant.</span></span> <span data-ttu-id="d6622-126">다음 예제의 `Person` 클래스는 [UInt16](xref:System.UInt16) 형식의 `Age` 속성을 표시하므로 다음 코드에서 컴파일러 경고가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-126">Because the `Person` class in the following example exposes an `Age` property of type [UInt16](xref:System.UInt16), the following code displays a compiler warning.</span></span>

```csharp
using System;

[assembly: CLSCompliant(true)]

public class Person
{
   private UInt16 personAge = 0;

   public UInt16 Age
   { get { return personAge; } }
}
// The attempt to compile the example displays the following compiler warning:
//    Public1.cs(10,18): warning CS3003: Type of 'Person.Age' is not CLS-compliant
```

```vb
<Assembly: CLSCompliant(True)>

Public Class Person
   Private personAge As UInt16

   Public ReadOnly Property Age As UInt16
      Get
         Return personAge
      End Get
   End Property
End Class
' The attempt to compile the example displays the following compiler warning:
'    Public1.vb(9) : warning BC40027: Return type of function 'Age' is not CLS-compliant.
'
'       Public ReadOnly Property Age As UInt16
'                                ~~~
```

<span data-ttu-id="d6622-127">`Age` 속성의 형식을 `UInt16`에서 CLS 규격 16비트 부호 있는 정수인 [Int16](xref:System.Int16)으로 변경하여 Person 클래스를 CLS 규격으로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-127">You can make the Person class CLS-compliant by changing the type of `Age` property from `UInt16` to [Int16](xref:System.Int16), which is a CLS-compliant, 16-bit signed integer.</span></span> <span data-ttu-id="d6622-128">private `personAge` 필드의 형식을 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-128">You do not have to change the type of the private `personAge` field.</span></span>

```csharp
using System;

[assembly: CLSCompliant(true)]

public class Person
{
   private Int16 personAge = 0;

   public Int16 Age
   { get { return personAge; } }
}
```

```vb
<Assembly: CLSCompliant(True)>

Public Class Person
   Private personAge As UInt16

   Public ReadOnly Property Age As Int16
      Get
         Return CType(personAge, Int16)
      End Get
   End Property
End Class
```

<span data-ttu-id="d6622-129">라이브러리의 공용 인터페이스는 다음으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-129">A library's public interface consists of the following:</span></span>

* <span data-ttu-id="d6622-130">공용 클래스의 정의</span><span class="sxs-lookup"><span data-stu-id="d6622-130">Definitions of public classes.</span></span>

* <span data-ttu-id="d6622-131">공용 클래스의 공용 멤버에 대한 정의 및 파생 클래스에서 액세스할 수 있는 멤버에 대한 정의(즉, protected 멤버)</span><span class="sxs-lookup"><span data-stu-id="d6622-131">Definitions of the public members of public classes, and definitions of members accessible to derived classes (that is, protected members).</span></span>

* <span data-ttu-id="d6622-132">공용 클래스의 공용 메서드에 대한 매개 변수 및 반환 형식, 파생 클래스에서 액세스할 수 있는 메서드에 대한 매개 변수 및 반환 형식</span><span class="sxs-lookup"><span data-stu-id="d6622-132">Parameters and return types of public methods of public classes, and parameters and return types of methods accessible to derived classes.</span></span>

<span data-ttu-id="d6622-133">CLS 규격의 규칙은 다음 표에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-133">The rules for CLS compliance are listed in the following table.</span></span> <span data-ttu-id="d6622-134">규칙의 텍스트는 [ECMA-335 Standard: Common Language Infrastructure](https://www.ecma-international.org/publications-and-standards/standards/ecma-335/)(Copyright 2012 by Ecma International)에서 가져온 약어입니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-134">The text of the rules is taken verbatim from the [ECMA-335 Standard: Common Language Infrastructure](https://www.ecma-international.org/publications-and-standards/standards/ecma-335/), which is Copyright 2012 by Ecma International.</span></span> <span data-ttu-id="d6622-135">이러한 규칙에 대한 보다 자세한 내용은 다음 섹션에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-135">More detailed information about these rules is found in the following sections.</span></span>

<span data-ttu-id="d6622-136">범주</span><span class="sxs-lookup"><span data-stu-id="d6622-136">Category</span></span> | <span data-ttu-id="d6622-137">참조</span><span class="sxs-lookup"><span data-stu-id="d6622-137">See</span></span> | <span data-ttu-id="d6622-138">규칙</span><span class="sxs-lookup"><span data-stu-id="d6622-138">Rule</span></span> | <span data-ttu-id="d6622-139">규칙 번호</span><span class="sxs-lookup"><span data-stu-id="d6622-139">Rule Number</span></span>
-------- | --- | ---- | -----------
<span data-ttu-id="d6622-140">액세스 가능성</span><span class="sxs-lookup"><span data-stu-id="d6622-140">Accessibility</span></span> | [<span data-ttu-id="d6622-141">멤버 접근성</span><span class="sxs-lookup"><span data-stu-id="d6622-141">Member accessibility</span></span>](#member-accessibility) | <span data-ttu-id="d6622-142">`family-or-assembly` 액세스 가능성을 갖는 다른 어셈블리에서 상속된 메서드를 재정의하는 경우를 제외하고는, 상속된 메서드를 재정의할 때 액세스 가능성이 변경되어서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-142">Accessibility shall not be changed when overriding inherited methods, except when overriding a method inherited from a different assembly with accessibility `family-or-assembly`.</span></span> <span data-ttu-id="d6622-143">이 경우, 재정의는 `family` 액세스 가능성을 가져야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-143">In this case, the override shall have accessibility `family`.</span></span> | <span data-ttu-id="d6622-144">10</span><span class="sxs-lookup"><span data-stu-id="d6622-144">10</span></span>
<span data-ttu-id="d6622-145">액세스 가능성</span><span class="sxs-lookup"><span data-stu-id="d6622-145">Accessibility</span></span> | [<span data-ttu-id="d6622-146">멤버 접근성</span><span class="sxs-lookup"><span data-stu-id="d6622-146">Member accessibility</span></span>](#member-accessibility) | <span data-ttu-id="d6622-147">형식과 멤버의 표시 유형 및 접근성은 해당 멤버가 표시되고 액세스 가능한 경우 모든 멤버의 시그니처에 있는 해당 형식이 표시되고 액세스 가능해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-147">The visibility and accessibility of types and members shall be such that types in the signature of any member shall be visible and accessible whenever the member itself is visible and accessible.</span></span> <span data-ttu-id="d6622-148">예를 들어 어셈블리 외부에 표시되는 공용 메서드는 어셈블리 내부에서만 표시되는 형식의 인수를 가질 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-148">For example, a public method that is visible outside its assembly shall not have an argument whose type is visible only within the assembly.</span></span> <span data-ttu-id="d6622-149">해당 멤버가 표시되고 액세스 가능한 경우 모든 멤버의 시그니처에 사용된 인스턴스화된 제네릭 형식을 구성하는 형식의 표시 유형과 액세스 가능성은 표시되고 액세스 가능해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-149">The visibility and accessibility of types composing an instantiated generic type used in the signature of any member shall be visible and accessible whenever the member itself is visible and accessible.</span></span> <span data-ttu-id="d6622-150">예를 들어 어셈블리 외부에 표시되는 멤버의 시그니처에 있는 인스턴스화된 제네릭 형식은 어셈블리 내부에서만 표시되는 형식의 제네릭 인수를 가질 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-150">For example, an instantiated generic type present in the signature of a member that is visible outside its assembly shall not have a generic argument whose type is visible only within the assembly.</span></span> | <span data-ttu-id="d6622-151">12</span><span class="sxs-lookup"><span data-stu-id="d6622-151">12</span></span>
<span data-ttu-id="d6622-152">배열</span><span class="sxs-lookup"><span data-stu-id="d6622-152">Arrays</span></span> | [<span data-ttu-id="d6622-153">배열</span><span class="sxs-lookup"><span data-stu-id="d6622-153">Arrays</span></span>](#arrays) | <span data-ttu-id="d6622-154">배열에는 CLS 규격 형식의 요소가 있어야 하며 배열의 모든 차원은 하한이 0이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-154">Arrays shall have elements with a CLS-compliant type, and all dimensions of the array shall have lower bounds of zero.</span></span> <span data-ttu-id="d6622-155">항목은 배열이며 이 배열의 요소 형식은 오버로드 간에 구분되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-155">Only the fact that an item is an array and the element type of the array shall be required to distinguish between overloads.</span></span> <span data-ttu-id="d6622-156">오버로드가 2개 이상의 배열 형식에 기반하는 경우 요소 형식은 명명된 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-156">When overloading is based on two or more array types, the element types shall be named types.</span></span> | <span data-ttu-id="d6622-157">16</span><span class="sxs-lookup"><span data-stu-id="d6622-157">16</span></span>
<span data-ttu-id="d6622-158">특성</span><span class="sxs-lookup"><span data-stu-id="d6622-158">Attributes</span></span> | [<span data-ttu-id="d6622-159">특성</span><span class="sxs-lookup"><span data-stu-id="d6622-159">Attributes</span></span>](#attributes) | <span data-ttu-id="d6622-160">특성은 [System.Attribute](xref:System.Attribute) 형식 또는 이 형식에서 상속받는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-160">Attributes shall be of type [System.Attribute](xref:System.Attribute), or a type inheriting from it.</span></span> | <span data-ttu-id="d6622-161">41</span><span class="sxs-lookup"><span data-stu-id="d6622-161">41</span></span>
<span data-ttu-id="d6622-162">특성</span><span class="sxs-lookup"><span data-stu-id="d6622-162">Attributes</span></span> | [<span data-ttu-id="d6622-163">특성</span><span class="sxs-lookup"><span data-stu-id="d6622-163">Attributes</span></span>](#attributes) | <span data-ttu-id="d6622-164">CLS에서는 사용자 지정 특성 인코딩의 하위 집합만을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-164">The CLS only allows a subset of the encodings of custom attributes.</span></span> <span data-ttu-id="d6622-165">이러한 인코딩에 표시될 수 있는 유일한 형식은 다음과 같습니다(Partition IV 참조). [System.Type](xref:System.Type), [System.String](xref:System.String), [System.Char](xref:System.Char), [System.Boolean](xref:System.Boolean), [System.Byte](xref:System.Byte), [System.Int16](xref:System.Int16), [System.Int32](xref:System.Int32), [System.Int64](xref:System.Int64), [System.Single](xref:System.Single), [System.Double](xref:System.Double) 및 CLS 규격 기본 정수 형식을 기반으로 하는 열거형 형식</span><span class="sxs-lookup"><span data-stu-id="d6622-165">The only types that shall appear in these encodings are (see Partition IV): [System.Type](xref:System.Type), [System.String](xref:System.String), [System.Char](xref:System.Char), [System.Boolean](xref:System.Boolean), [System.Byte](xref:System.Byte), [System.Int16](xref:System.Int16), [System.Int32](xref:System.Int32), [System.Int64](xref:System.Int64), [System.Single](xref:System.Single), [System.Double](xref:System.Double), and any enumeration type based on a CLS-compliant base integer type.</span></span> | <span data-ttu-id="d6622-166">34</span><span class="sxs-lookup"><span data-stu-id="d6622-166">34</span></span>
<span data-ttu-id="d6622-167">특성</span><span class="sxs-lookup"><span data-stu-id="d6622-167">Attributes</span></span> | [<span data-ttu-id="d6622-168">특성</span><span class="sxs-lookup"><span data-stu-id="d6622-168">Attributes</span></span>](#attributes) | <span data-ttu-id="d6622-169">CLS에서는 공개적으로 표시되는 필수 한정자(`modreq`)를 허용하지 않지만, CLS에서 인식할 수 없는 선택적 한정자(`modopt`, Partition II 참조)는 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-169">The CLS does not allow publicly visible required modifiers (`modreq`, see Partition II), but does allow optional modifiers (`modopt`, see Partition II) it does not understand.</span></span> | <span data-ttu-id="d6622-170">35</span><span class="sxs-lookup"><span data-stu-id="d6622-170">35</span></span>
<span data-ttu-id="d6622-171">생성자</span><span class="sxs-lookup"><span data-stu-id="d6622-171">Constructors</span></span> | [<span data-ttu-id="d6622-172">생성자</span><span class="sxs-lookup"><span data-stu-id="d6622-172">Constructors</span></span>](#constructors) | <span data-ttu-id="d6622-173">개체 생성자는 상속된 인스턴스 데이터에 액세스하기 전에 기본 클래스의 일부 인스턴스 생성자를 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-173">An object constructor shall call some instance constructor of its base class before any access occurs to inherited instance data.</span></span> <span data-ttu-id="d6622-174">(생성자가 필요하지 않은 값 형식에는 적용되지 않습니다.)</span><span class="sxs-lookup"><span data-stu-id="d6622-174">(This does not apply to value types, which need not have constructors.)</span></span>  | <span data-ttu-id="d6622-175">21</span><span class="sxs-lookup"><span data-stu-id="d6622-175">21</span></span>
<span data-ttu-id="d6622-176">생성자</span><span class="sxs-lookup"><span data-stu-id="d6622-176">Constructors</span></span> | [<span data-ttu-id="d6622-177">생성자</span><span class="sxs-lookup"><span data-stu-id="d6622-177">Constructors</span></span>](#constructors) | <span data-ttu-id="d6622-178">개체 생성자는 개체 만들기 작업의 일부로 호출되는 것을 제외하고 호출되어서는 안 되며 개체는 두 번 초기화해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-178">An object constructor shall not be called except as part of the creation of an object, and an object shall not be initialized twice.</span></span> | <span data-ttu-id="d6622-179">22</span><span class="sxs-lookup"><span data-stu-id="d6622-179">22</span></span>
<span data-ttu-id="d6622-180">열거형</span><span class="sxs-lookup"><span data-stu-id="d6622-180">Enumerations</span></span> | [<span data-ttu-id="d6622-181">열거형</span><span class="sxs-lookup"><span data-stu-id="d6622-181">Enumerations</span></span>](#enumerations) | <span data-ttu-id="d6622-182">열거형의 기본 형식은 기본 제공 CLS 정수 형식이고, 필드의 이름은 "value__"이며, 해당 필드는 `RTSpecialName`으로 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-182">The underlying type of an enum shall be a built-in CLS integer type, the name of the field shall be "value__", and that field shall be marked `RTSpecialName`.</span></span> |  <span data-ttu-id="d6622-183">7</span><span class="sxs-lookup"><span data-stu-id="d6622-183">7</span></span>
<span data-ttu-id="d6622-184">열거형</span><span class="sxs-lookup"><span data-stu-id="d6622-184">Enumerations</span></span> | [<span data-ttu-id="d6622-185">열거형</span><span class="sxs-lookup"><span data-stu-id="d6622-185">Enumerations</span></span>](#enumerations) | <span data-ttu-id="d6622-186">[System.FlagsAttribute](xref:System.FlagsAttribute)(Partition IV 라이브러리 참조) 사용자 지정 특성의 존재 여부에 따라 지정되는 두 가지 종류의 열거형이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-186">There are two distinct kinds of enums, indicated by the presence or absence of the [System.FlagsAttribute](xref:System.FlagsAttribute) (see Partition IV Library) custom attribute.</span></span> <span data-ttu-id="d6622-187">하나는 명명된 정수 값을 나타내며, 다른 하나는 명명되지 않은 값을 생성하도록 결합될 수 있는 명명된 비트 플래그를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-187">One represents named integer values; the other represents named bit flags that can be combined to generate an unnamed value.</span></span> <span data-ttu-id="d6622-188">`enum`의 값은 지정된 값으로 제한되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-188">The value of an `enum` is not limited to the specified values.</span></span> |  <span data-ttu-id="d6622-189">8</span><span class="sxs-lookup"><span data-stu-id="d6622-189">8</span></span>
<span data-ttu-id="d6622-190">열거형</span><span class="sxs-lookup"><span data-stu-id="d6622-190">Enumerations</span></span> | [<span data-ttu-id="d6622-191">열거형</span><span class="sxs-lookup"><span data-stu-id="d6622-191">Enumerations</span></span>](#enumerations) | <span data-ttu-id="d6622-192">열거형의 리터럴 정적 필드는 그 자체가 열거형 형식을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-192">Literal static fields of an enum shall have the type of the enum itself.</span></span> |  <span data-ttu-id="d6622-193">9</span><span class="sxs-lookup"><span data-stu-id="d6622-193">9</span></span>
<span data-ttu-id="d6622-194">이벤트</span><span class="sxs-lookup"><span data-stu-id="d6622-194">Events</span></span> | [<span data-ttu-id="d6622-195">이벤트</span><span class="sxs-lookup"><span data-stu-id="d6622-195">Events</span></span>](#events) | <span data-ttu-id="d6622-196">이벤트를 구현하는 메서드는 메타데이터에서 `SpecialName`으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-196">The methods that implement an event shall be marked `SpecialName` in the metadata.</span></span> |<span data-ttu-id="d6622-197">29</span><span class="sxs-lookup"><span data-stu-id="d6622-197">29</span></span>
<span data-ttu-id="d6622-198">이벤트</span><span class="sxs-lookup"><span data-stu-id="d6622-198">Events</span></span> | [<span data-ttu-id="d6622-199">이벤트</span><span class="sxs-lookup"><span data-stu-id="d6622-199">Events</span></span>](#events) | <span data-ttu-id="d6622-200">이벤트와 접근자의 액세스 가능성이 동일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-200">The accessibility of an event and of its accessors shall be identical.</span></span> |<span data-ttu-id="d6622-201">30</span><span class="sxs-lookup"><span data-stu-id="d6622-201">30</span></span>
<span data-ttu-id="d6622-202">이벤트</span><span class="sxs-lookup"><span data-stu-id="d6622-202">Events</span></span> | [<span data-ttu-id="d6622-203">이벤트</span><span class="sxs-lookup"><span data-stu-id="d6622-203">Events</span></span>](#events) | <span data-ttu-id="d6622-204">이벤트에 대한 `add` 및 `remove` 메서드는 모두 있거나 모두 없어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-204">The `add` and `remove` methods for an event shall both either be present or absent.</span></span> |<span data-ttu-id="d6622-205">31</span><span class="sxs-lookup"><span data-stu-id="d6622-205">31</span></span>
<span data-ttu-id="d6622-206">이벤트</span><span class="sxs-lookup"><span data-stu-id="d6622-206">Events</span></span> | [<span data-ttu-id="d6622-207">이벤트</span><span class="sxs-lookup"><span data-stu-id="d6622-207">Events</span></span>](#events) | <span data-ttu-id="d6622-208">이벤트에 대한 `add` 및 `remove` 메서드는 이벤트 유형 정의 형식을 갖는 하나의 매개 변수를 각각 사용하며, 해당 형식은 [System.Delegate](xref:System.Delegate)에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-208">The `add` and `remove` methods for an event shall each take one parameter whose type defines the type of the event and that shall be derived from [System.Delegate](xref:System.Delegate).</span></span> |<span data-ttu-id="d6622-209">32</span><span class="sxs-lookup"><span data-stu-id="d6622-209">32</span></span>
<span data-ttu-id="d6622-210">이벤트</span><span class="sxs-lookup"><span data-stu-id="d6622-210">Events</span></span> | [<span data-ttu-id="d6622-211">이벤트</span><span class="sxs-lookup"><span data-stu-id="d6622-211">Events</span></span>](#events) | <span data-ttu-id="d6622-212">이벤트는 특정 이름 지정 패턴을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-212">Events shall adhere to a specific naming pattern.</span></span> <span data-ttu-id="d6622-213">CLS 규칙 29에서 참조되는 SpecialName 특성은 적절한 이름 비교에서 무시되고 식별자 규칙을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-213">The SpecialName attribute referred to in CLS rule 29 shall be ignored in appropriate name comparisons and shall adhere to identifier rules.</span></span>  |<span data-ttu-id="d6622-214">33</span><span class="sxs-lookup"><span data-stu-id="d6622-214">33</span></span>
<span data-ttu-id="d6622-215">예외</span><span class="sxs-lookup"><span data-stu-id="d6622-215">Exceptions</span></span> | [<span data-ttu-id="d6622-216">예외</span><span class="sxs-lookup"><span data-stu-id="d6622-216">Exceptions</span></span>](#exceptions) | <span data-ttu-id="d6622-217">throw되는 개체는 [System.Exception](xref:System.Exception) 형식 또는 이 형식에서 상속받는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-217">Objects that are thrown shall be of type [System.Exception](xref:System.Exception) or a type inheriting from it.</span></span> <span data-ttu-id="d6622-218">그렇더라도 다른 형식의 예외 전파를 차단하는 데 CLS 규격 메서드는 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-218">Nonetheless, CLS-compliant methods are not required to block the propagation of other types of exceptions.</span></span> | <span data-ttu-id="d6622-219">40</span><span class="sxs-lookup"><span data-stu-id="d6622-219">40</span></span>
<span data-ttu-id="d6622-220">일반</span><span class="sxs-lookup"><span data-stu-id="d6622-220">General</span></span> | [<span data-ttu-id="d6622-221">CLS 준수 규칙</span><span class="sxs-lookup"><span data-stu-id="d6622-221">CLS compliance rules</span></span>](#cls-compliance-rules) | <span data-ttu-id="d6622-222">CLS 규칙은 정의 어셈블리 외부에서 액세스하거나 볼 수 있는 형식의 해당 부분에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-222">CLS rules apply only to those parts of a type that are accessible or visible outside of the defining assembly.</span></span> | <span data-ttu-id="d6622-223">1</span><span class="sxs-lookup"><span data-stu-id="d6622-223">1</span></span>
<span data-ttu-id="d6622-224">일반</span><span class="sxs-lookup"><span data-stu-id="d6622-224">General</span></span> | [<span data-ttu-id="d6622-225">CLS 준수 규칙</span><span class="sxs-lookup"><span data-stu-id="d6622-225">CLS compliance rules</span></span>](#cls-compliance-rules) | <span data-ttu-id="d6622-226">CLS 규격 형식이 아닌 멤버를 CLS 규격으로 표시해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-226">Members of non-CLS compliant types shall not be marked CLS-compliant.</span></span> | <span data-ttu-id="d6622-227">2</span><span class="sxs-lookup"><span data-stu-id="d6622-227">2</span></span>
<span data-ttu-id="d6622-228">제네릭</span><span class="sxs-lookup"><span data-stu-id="d6622-228">Generics</span></span> | [<span data-ttu-id="d6622-229">제네릭 형식 및 멤버</span><span class="sxs-lookup"><span data-stu-id="d6622-229">Generic types and members</span></span>](#generic-types-and-members) | <span data-ttu-id="d6622-230">중첩 형식에는 적어도 바깥쪽 형식과 같은 수의 제네릭 매개 변수가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-230">Nested types shall have at least as many generic parameters as the enclosing type.</span></span> <span data-ttu-id="d6622-231">중첩 형식의 제네릭 매개 변수는 바깥쪽 형식의 제네릭 매개 변수와 위치가 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-231">Generic parameters in a nested type correspond by position to the generic parameters in its enclosing type.</span></span>  | <span data-ttu-id="d6622-232">42</span><span class="sxs-lookup"><span data-stu-id="d6622-232">42</span></span>
<span data-ttu-id="d6622-233">제네릭</span><span class="sxs-lookup"><span data-stu-id="d6622-233">Generics</span></span> | [<span data-ttu-id="d6622-234">제네릭 형식 및 멤버</span><span class="sxs-lookup"><span data-stu-id="d6622-234">Generic types and members</span></span>](#generic-types-and-members) | <span data-ttu-id="d6622-235">제네릭 형식의 이름은 중첩되지 않은 형식이나 중첩된 경우 앞에서 정의된 규칙에 따라 새롭게 도입된 형식으로 선언된 형식 매개 변수의 개수를 인코딩합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-235">The name of a generic type shall encode the number of type parameters declared on the non-nested type, or newly introduced to the type if nested, according to the rules defined above.</span></span> | <span data-ttu-id="d6622-236">43</span><span class="sxs-lookup"><span data-stu-id="d6622-236">43</span></span>
<span data-ttu-id="d6622-237">제네릭</span><span class="sxs-lookup"><span data-stu-id="d6622-237">Generics</span></span> | [<span data-ttu-id="d6622-238">제네릭 형식 및 멤버</span><span class="sxs-lookup"><span data-stu-id="d6622-238">Generic types and members</span></span>](#generic-types-and-members) | <span data-ttu-id="d6622-239">제네릭 형식에서는 제네릭 형식 제약 조건이 기본 형식이나 인터페이스에 대한 모든 제약 조건을 만족할 수 있도록 충분한 제약 조건을 다시 선언해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-239">A generic type shall redeclare sufficient constraints to guarantee that any constraints on the base type, or interfaces would be satisfied by the generic type constraints.</span></span> | <span data-ttu-id="d6622-240">44</span><span class="sxs-lookup"><span data-stu-id="d6622-240">44</span></span>
<span data-ttu-id="d6622-241">제네릭</span><span class="sxs-lookup"><span data-stu-id="d6622-241">Generics</span></span> | [<span data-ttu-id="d6622-242">제네릭 형식 및 멤버</span><span class="sxs-lookup"><span data-stu-id="d6622-242">Generic types and members</span></span>](#generic-types-and-members) | <span data-ttu-id="d6622-243">제네릭 매개 변수에 대한 제약 조건으로 사용되는 형식 자체는 CLS 규격이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-243">Types used as constraints on generic parameters shall themselves be CLS-compliant.</span></span> | <span data-ttu-id="d6622-244">45</span><span class="sxs-lookup"><span data-stu-id="d6622-244">45</span></span>
<span data-ttu-id="d6622-245">제네릭</span><span class="sxs-lookup"><span data-stu-id="d6622-245">Generics</span></span> | [<span data-ttu-id="d6622-246">제네릭 형식 및 멤버</span><span class="sxs-lookup"><span data-stu-id="d6622-246">Generic types and members</span></span>](#generic-types-and-members) | <span data-ttu-id="d6622-247">인스턴스화된 제네릭 형식에서 중첩 형식을 포함한 멤버의 표시 여부와 액세스 가능성의 범위는 전체 제네릭 형식이 아닌 특정 인스턴스로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-247">The visibility and accessibility of members (including nested types) in an instantiated generic type shall be considered to be scoped to the specific instantiation rather than the generic type declaration as a whole.</span></span> <span data-ttu-id="d6622-248">이러한 가정 하에 CLS 규칙 12의 표시 유형 및 액세스 가능성 규칙이 계속 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-248">Assuming this, the visibility and accessibility rules of CLS rule 12 still apply.</span></span> | <span data-ttu-id="d6622-249">46</span><span class="sxs-lookup"><span data-stu-id="d6622-249">46</span></span>
<span data-ttu-id="d6622-250">제네릭</span><span class="sxs-lookup"><span data-stu-id="d6622-250">Generics</span></span> | [<span data-ttu-id="d6622-251">제네릭 형식 및 멤버</span><span class="sxs-lookup"><span data-stu-id="d6622-251">Generic types and members</span></span>](#generic-types-and-members) | <span data-ttu-id="d6622-252">각 추상 또는 가상 제네릭 메서드마다 구체적인(비추상) 기본 구현이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-252">For each abstract or virtual generic method, there shall be a default concrete (nonabstract) implementation</span></span> | <span data-ttu-id="d6622-253">47</span><span class="sxs-lookup"><span data-stu-id="d6622-253">47</span></span>
<span data-ttu-id="d6622-254">인터페이스</span><span class="sxs-lookup"><span data-stu-id="d6622-254">Interfaces</span></span> | [<span data-ttu-id="d6622-255">인터페이스</span><span class="sxs-lookup"><span data-stu-id="d6622-255">Interfaces</span></span>](#interfaces) | <span data-ttu-id="d6622-256">CLS 규격 인터페이스는 구현을 위해 CLS 규격이 아닌 메서드의 정의가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-256">CLS-compliant interfaces shall not require the definition of non-CLS compliant methods in order to implement them.</span></span> | <span data-ttu-id="d6622-257">18</span><span class="sxs-lookup"><span data-stu-id="d6622-257">18</span></span>
<span data-ttu-id="d6622-258">인터페이스</span><span class="sxs-lookup"><span data-stu-id="d6622-258">Interfaces</span></span> | [<span data-ttu-id="d6622-259">인터페이스</span><span class="sxs-lookup"><span data-stu-id="d6622-259">Interfaces</span></span>](#interfaces) | <span data-ttu-id="d6622-260">CLS 규격 인터페이스에서는 정적 메서드나 필드를 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-260">CLS-compliant interfaces shall not define static methods, nor shall they define fields.</span></span> | <span data-ttu-id="d6622-261">19</span><span class="sxs-lookup"><span data-stu-id="d6622-261">19</span></span>
<span data-ttu-id="d6622-262">멤버</span><span class="sxs-lookup"><span data-stu-id="d6622-262">Members</span></span> | [<span data-ttu-id="d6622-263">형식 멤버 일반 사항</span><span class="sxs-lookup"><span data-stu-id="d6622-263">Type members in general</span></span>](#type-members-in-general) | <span data-ttu-id="d6622-264">전역 정적 필드 및 메서드는 CLS 규격입니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-264">Global static fields and methods are not CLS-compliant.</span></span> | <span data-ttu-id="d6622-265">36</span><span class="sxs-lookup"><span data-stu-id="d6622-265">36</span></span>
<span data-ttu-id="d6622-266">멤버</span><span class="sxs-lookup"><span data-stu-id="d6622-266">Members</span></span> | -- | <span data-ttu-id="d6622-267">리터럴 정적 값은 필드 초기화 메타데이터를 사용하여 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-267">The value of a literal static is specified through the use of field initialization metadata.</span></span> <span data-ttu-id="d6622-268">CLS 규격 리터럴에는 리터럴(또는 해당 리터럴이 `enum`인 경우 기본 형식)과 정확히 같은 형식인 필드 초기화 메타데이터에 지정된 값이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-268">A CLS-compliant literal must have a value specified in field initialization metadata that is of exactly the same type as the literal (or of the underlying type, if that literal is an `enum`).</span></span> | <span data-ttu-id="d6622-269">13</span><span class="sxs-lookup"><span data-stu-id="d6622-269">13</span></span>
<span data-ttu-id="d6622-270">멤버</span><span class="sxs-lookup"><span data-stu-id="d6622-270">Members</span></span> | [<span data-ttu-id="d6622-271">형식 멤버 일반 사항</span><span class="sxs-lookup"><span data-stu-id="d6622-271">Type members in general</span></span>](#type-members-in-general) | <span data-ttu-id="d6622-272">vararg 제약 조건은 CLS의 일부가 아니며, CLS에서는 관리되는 표준 호출 규칙만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-272">The vararg constraint is not part of the CLS, and the only calling convention supported by the CLS is the standard managed calling convention.</span></span> | <span data-ttu-id="d6622-273">15</span><span class="sxs-lookup"><span data-stu-id="d6622-273">15</span></span>
<span data-ttu-id="d6622-274">명명 규칙</span><span class="sxs-lookup"><span data-stu-id="d6622-274">Naming conventions</span></span> | [<span data-ttu-id="d6622-275">명명 규칙</span><span class="sxs-lookup"><span data-stu-id="d6622-275">Naming conventions</span></span>](#naming-conventions) | <span data-ttu-id="d6622-276">어셈블리는 시작하고 식별자에 포함할 수 있는 문자 집합을 규정하는 유니코드 표준 3.0 기술 보고서 15의 부록 7을 준수합니다. [Unicode Normalization Forms](https://unicode.org/reports/tr15/)에서 온라인으로 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-276">Assemblies shall follow Annex 7 of Technical Report 15 of the Unicode Standard3.0 governing the set of characters permitted to start and be included in identifiers, available online at [Unicode Normalization Forms](https://unicode.org/reports/tr15/).</span></span> <span data-ttu-id="d6622-277">식별자는 유니코드 정규화 형식 C에서 정의된 정규 형식입니다. CLS에서 소문자 매핑(유니코드 로캘 비구분으로 지정된, 일 대 일 소문자 매핑)이 같은 두 개의 식별자는 서로 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-277">Identifiers shall be in the canonical format defined by Unicode Normalization Form C. For CLS purposes, two identifiers are the same if their lowercase mappings (as specified by the Unicode locale-insensitive, one-to-one lowercase mappings) are the same.</span></span> <span data-ttu-id="d6622-278">즉, 두 식별자가 CLS에서 서로 다른 것으로 간주되는 경우 단순히 대/소문자 이상의 차이가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-278">That is, for two identifiers to be considered different under the CLS they shall differ in more than simply their case.</span></span> <span data-ttu-id="d6622-279">그러나 상속된 정의를 재정의하기 위해서는 CLI가 원래 선언에 정확한 인코딩을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-279">However, in order to override an inherited definition the CLI requires the precise encoding of the original declaration be used.</span></span> | <span data-ttu-id="d6622-280">4</span><span class="sxs-lookup"><span data-stu-id="d6622-280">4</span></span>
<span data-ttu-id="d6622-281">오버로딩</span><span class="sxs-lookup"><span data-stu-id="d6622-281">Overloading</span></span> | [<span data-ttu-id="d6622-282">명명 규칙</span><span class="sxs-lookup"><span data-stu-id="d6622-282">Naming conventions</span></span>](#naming-conventions) | <span data-ttu-id="d6622-283">CLS 규격 범위에 소개된 모든 이름은 이름이 동일한 경우를 제외하고는 종류가 독립적이고 고유한 이름이어야 하며 오버로드를 통해 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-283">All names introduced in a CLS-compliant scope shall be distinct independent of kind, except where the names are identical and resolved via overloading.</span></span> <span data-ttu-id="d6622-284">즉, CTS에서는 메서드 및 필드에 동일한 이름을 사용하는 단일 형식이 허용되지만 CLS에서는 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-284">That is, while the CTS allows a single type to use the same name for a method and a field, the CLS does not.</span></span> | <span data-ttu-id="d6622-285">5</span><span class="sxs-lookup"><span data-stu-id="d6622-285">5</span></span>
<span data-ttu-id="d6622-286">오버로딩</span><span class="sxs-lookup"><span data-stu-id="d6622-286">Overloading</span></span> | [<span data-ttu-id="d6622-287">명명 규칙</span><span class="sxs-lookup"><span data-stu-id="d6622-287">Naming conventions</span></span>](#naming-conventions) | <span data-ttu-id="d6622-288">CTS로 고유 시그니처가 구분될 수 있지만 필드 및 중첩 형식은 식별자 비교만으로 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-288">Fields and nested types shall be distinct by identifier comparison alone, even though the CTS allows distinct signatures to be distinguished.</span></span> <span data-ttu-id="d6622-289">식별자를 비교했을 때 CLS 규칙 39에 지정된 경우를 제외하고 동일한 이름을 갖는 메서드, 속성 및 이벤트는 반환 형식 이상의 차이가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-289">Methods, properties, and events that have the same name (by identifier comparison) shall differ by more than just the return type, except as specified in CLS Rule 39</span></span> | <span data-ttu-id="d6622-290">6</span><span class="sxs-lookup"><span data-stu-id="d6622-290">6</span></span>
<span data-ttu-id="d6622-291">오버로딩</span><span class="sxs-lookup"><span data-stu-id="d6622-291">Overloading</span></span> | [<span data-ttu-id="d6622-292">오버로드</span><span class="sxs-lookup"><span data-stu-id="d6622-292">Overloads</span></span>](#overloads) | <span data-ttu-id="d6622-293">속성 및 메서드만 오버로드될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-293">Only properties and methods can be overloaded.</span></span> | <span data-ttu-id="d6622-294">37</span><span class="sxs-lookup"><span data-stu-id="d6622-294">37</span></span>
<span data-ttu-id="d6622-295">오버로딩</span><span class="sxs-lookup"><span data-stu-id="d6622-295">Overloading</span></span> | [<span data-ttu-id="d6622-296">오버로드</span><span class="sxs-lookup"><span data-stu-id="d6622-296">Overloads</span></span>](#overloads) |<span data-ttu-id="d6622-297">반환 형식에 따라서도 오버로드될 수 있는 이름이 `op_Implicit` 및 `op_Explicit`인 변환 연산자를 제외하고, 속성 및 메서드는 매개 변수의 형식과 수에 따라서만 오버로드될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-297">Properties and methods can be overloaded based only on the number and types of their parameters, except the conversion operators named `op_Implicit` and `op_Explicit`, which can also be overloaded based on their return type.</span></span> | <span data-ttu-id="d6622-298">38</span><span class="sxs-lookup"><span data-stu-id="d6622-298">38</span></span>
<span data-ttu-id="d6622-299">오버로딩</span><span class="sxs-lookup"><span data-stu-id="d6622-299">Overloading</span></span> | -- | <span data-ttu-id="d6622-300">한 형식에서 선언된 둘 이상의 CLS 규격 메서드의 이름이 같고 형식 인스턴스화의 특정 집합에 대해 매개 변수와 반환 형식이 같다면 이러한 모든 메서드는 해당 형식 인스턴스화에서 의미상 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-300">If two or more CLS-compliant methods declared in a type have the same name and, for a specific set of type instantiations, they have the same parameter and return types, then all these methods shall be semantically equivalent at those type instantiations.</span></span> | <span data-ttu-id="d6622-301">48</span><span class="sxs-lookup"><span data-stu-id="d6622-301">48</span></span>
<span data-ttu-id="d6622-302">속성</span><span class="sxs-lookup"><span data-stu-id="d6622-302">Properties</span></span> | [<span data-ttu-id="d6622-303">속성</span><span class="sxs-lookup"><span data-stu-id="d6622-303">Properties</span></span>](#properties) | <span data-ttu-id="d6622-304">속성의 getter 및 setter 메서드를 구현하는 메서드는 메타데이터에서 `SpecialName`으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-304">The methods that implement the getter and setter methods of a property shall be marked `SpecialName` in the metadata.</span></span> | <span data-ttu-id="d6622-305">24</span><span class="sxs-lookup"><span data-stu-id="d6622-305">24</span></span>
<span data-ttu-id="d6622-306">속성</span><span class="sxs-lookup"><span data-stu-id="d6622-306">Properties</span></span> | [<span data-ttu-id="d6622-307">속성</span><span class="sxs-lookup"><span data-stu-id="d6622-307">Properties</span></span>](#properties) | <span data-ttu-id="d6622-308">속성의 접근자는 모두 static이거나 모두 virtual이거나 또는 모두 instance여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-308">A property's accessors shall all be static, all be virtual, or all be instance.</span></span> | <span data-ttu-id="d6622-309">26</span><span class="sxs-lookup"><span data-stu-id="d6622-309">26</span></span>
<span data-ttu-id="d6622-310">속성</span><span class="sxs-lookup"><span data-stu-id="d6622-310">Properties</span></span> | [<span data-ttu-id="d6622-311">속성</span><span class="sxs-lookup"><span data-stu-id="d6622-311">Properties</span></span>](#properties) | <span data-ttu-id="d6622-312">속성의 형식은 getter의 반환 형식이며 setter의 마지막 인수의 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-312">The type of a property shall be the return type of the getter and the type of the last argument of the setter.</span></span> <span data-ttu-id="d6622-313">속성의 매개 변수 형식은 getter의 매개 변수 형식 및 setter의 마지막 매개 변수 형식을 제외한 모든 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-313">The types of the parameters of the property shall be the types of the parameters to the getter and the types of all but the final parameter of the setter.</span></span> <span data-ttu-id="d6622-314">이들 형식은 모두 CLS 규격이어야 하며 관리되는 포인터일 수 없습니다. 즉, 참조로 전달될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-314">All of these types shall be CLS-compliant, and shall not be managed pointers (that is, shall not be passed by reference).</span></span> | <span data-ttu-id="d6622-315">27</span><span class="sxs-lookup"><span data-stu-id="d6622-315">27</span></span>
<span data-ttu-id="d6622-316">속성</span><span class="sxs-lookup"><span data-stu-id="d6622-316">Properties</span></span> | [<span data-ttu-id="d6622-317">속성</span><span class="sxs-lookup"><span data-stu-id="d6622-317">Properties</span></span>](#properties) | <span data-ttu-id="d6622-318">속성은 특정 이름 지정 패턴을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-318">Properties shall adhere to a specific naming pattern.</span></span> <span data-ttu-id="d6622-319">CLS 규칙 24에서 참조되는 `SpecialName` 특성은 적절한 이름 비교에서 무시되고 식별자 규칙을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-319">The `SpecialName` attribute referred to in CLS rule 24 shall be ignored in appropriate name comparisons and shall adhere to identifier rules.</span></span> <span data-ttu-id="d6622-320">속성에는 getter 메서드, setter 메서드 또는 둘 모두가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-320">A property shall have a getter method, a setter method, or both.</span></span> | <span data-ttu-id="d6622-321">28</span><span class="sxs-lookup"><span data-stu-id="d6622-321">28</span></span>
<span data-ttu-id="d6622-322">형식 변환</span><span class="sxs-lookup"><span data-stu-id="d6622-322">Type conversion</span></span> | [<span data-ttu-id="d6622-323">형식 변환</span><span class="sxs-lookup"><span data-stu-id="d6622-323">Type conversion</span></span>](#type-conversion) | <span data-ttu-id="d6622-324">op_Implicit 또는 op_Explicit가 제공되는 경우 강제 변환을 제공하는 대체 방법이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-324">If either op_Implicit or op_Explicit is provided, an alternate means of providing the coercion shall be provided.</span></span> | <span data-ttu-id="d6622-325">39</span><span class="sxs-lookup"><span data-stu-id="d6622-325">39</span></span>
<span data-ttu-id="d6622-326">유형</span><span class="sxs-lookup"><span data-stu-id="d6622-326">Types</span></span> | [<span data-ttu-id="d6622-327">형식 및 형식 멤버 시그니처</span><span class="sxs-lookup"><span data-stu-id="d6622-327">Types and type member signatures</span></span>](#types-and-type-member-signatures) | <span data-ttu-id="d6622-328">boxed 값 형식은 CLS 규격이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-328">Boxed value types are not CLS-compliant.</span></span> | <span data-ttu-id="d6622-329">3</span><span class="sxs-lookup"><span data-stu-id="d6622-329">3</span></span>
<span data-ttu-id="d6622-330">유형</span><span class="sxs-lookup"><span data-stu-id="d6622-330">Types</span></span> | [<span data-ttu-id="d6622-331">형식 및 형식 멤버 시그니처</span><span class="sxs-lookup"><span data-stu-id="d6622-331">Types and type member signatures</span></span>](#types-and-type-member-signatures) | <span data-ttu-id="d6622-332">시그니처에 나타나는 모든 형식은 CLS 규격이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-332">All types appearing in a signature shall be CLS-compliant.</span></span> <span data-ttu-id="d6622-333">인스턴스화된 제네릭 형식을 구성하는 모든 형식은 CLS 규격이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-333">All types composing an instantiated generic type shall be CLS-compliant.</span></span> | <span data-ttu-id="d6622-334">11</span><span class="sxs-lookup"><span data-stu-id="d6622-334">11</span></span>
<span data-ttu-id="d6622-335">유형</span><span class="sxs-lookup"><span data-stu-id="d6622-335">Types</span></span> | [<span data-ttu-id="d6622-336">형식 및 형식 멤버 시그니처</span><span class="sxs-lookup"><span data-stu-id="d6622-336">Types and type member signatures</span></span>](#types-and-type-member-signatures) | <span data-ttu-id="d6622-337">형식화된 참조는 CLS 규격이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-337">Typed references are not CLS-compliant.</span></span> | <span data-ttu-id="d6622-338">14</span><span class="sxs-lookup"><span data-stu-id="d6622-338">14</span></span>
<span data-ttu-id="d6622-339">유형</span><span class="sxs-lookup"><span data-stu-id="d6622-339">Types</span></span> | [<span data-ttu-id="d6622-340">형식 및 형식 멤버 시그니처</span><span class="sxs-lookup"><span data-stu-id="d6622-340">Types and type member signatures</span></span>](#types-and-type-member-signatures) | <span data-ttu-id="d6622-341">관리되지 않는 포인터 형식은 CLS 규격이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-341">Unmanaged pointer types are not CLS-compliant.</span></span> | <span data-ttu-id="d6622-342">17</span><span class="sxs-lookup"><span data-stu-id="d6622-342">17</span></span>
<span data-ttu-id="d6622-343">유형</span><span class="sxs-lookup"><span data-stu-id="d6622-343">Types</span></span> | [<span data-ttu-id="d6622-344">형식 및 형식 멤버 시그니처</span><span class="sxs-lookup"><span data-stu-id="d6622-344">Types and type member signatures</span></span>](#types-and-type-member-signatures) | <span data-ttu-id="d6622-345">CLS 규격 클래스, 값 형식 및 인터페이스에는 CLS 규격이 아닌 멤버 구현이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-345">CLS-compliant classes, value types, and interfaces shall not require the implementation of non-CLS-compliant members</span></span> | <span data-ttu-id="d6622-346">20</span><span class="sxs-lookup"><span data-stu-id="d6622-346">20</span></span>
<span data-ttu-id="d6622-347">유형</span><span class="sxs-lookup"><span data-stu-id="d6622-347">Types</span></span> | [<span data-ttu-id="d6622-348">형식 및 형식 멤버 시그니처</span><span class="sxs-lookup"><span data-stu-id="d6622-348">Types and type member signatures</span></span>](#types-and-type-member-signatures) | <span data-ttu-id="d6622-349">[System.Object](xref:System.Object)는 CLS 규격입니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-349">[System.Object](xref:System.Object) is CLS-compliant.</span></span> <span data-ttu-id="d6622-350">다른 CLS 규격 클래스는 모두 CLS 규격 클래스에서 상속해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-350">Any other CLS-compliant class shall inherit from a CLS-compliant class.</span></span> | <span data-ttu-id="d6622-351">23</span><span class="sxs-lookup"><span data-stu-id="d6622-351">23</span></span>

<span data-ttu-id="d6622-352">섹션의 하위 인덱스:</span><span class="sxs-lookup"><span data-stu-id="d6622-352">Index to subsections:</span></span>

* [<span data-ttu-id="d6622-353">형식 및 형식 멤버 시그니처</span><span class="sxs-lookup"><span data-stu-id="d6622-353">Types and type member signatures</span></span>](#types-and-type-member-signatures)
* [<span data-ttu-id="d6622-354">명명 규칙</span><span class="sxs-lookup"><span data-stu-id="d6622-354">Naming conventions</span></span>](#naming-conventions)
* [<span data-ttu-id="d6622-355">형식 변환</span><span class="sxs-lookup"><span data-stu-id="d6622-355">Type conversion</span></span>](#type-conversion)
* [<span data-ttu-id="d6622-356">배열</span><span class="sxs-lookup"><span data-stu-id="d6622-356">Arrays</span></span>](#arrays)
* [<span data-ttu-id="d6622-357">인터페이스</span><span class="sxs-lookup"><span data-stu-id="d6622-357">Interfaces</span></span>](#interfaces)
* [<span data-ttu-id="d6622-358">열거형</span><span class="sxs-lookup"><span data-stu-id="d6622-358">Enumerations</span></span>](#enumerations)
* [<span data-ttu-id="d6622-359">형식 멤버 일반 사항</span><span class="sxs-lookup"><span data-stu-id="d6622-359">Type members in general</span></span>](#type-members-in-general)
* [<span data-ttu-id="d6622-360">멤버 접근성</span><span class="sxs-lookup"><span data-stu-id="d6622-360">Member accessibility</span></span>](#member-accessibility)
* [<span data-ttu-id="d6622-361">제네릭 형식 및 멤버</span><span class="sxs-lookup"><span data-stu-id="d6622-361">Generic types and members</span></span>](#generic-types-and-members)
* [<span data-ttu-id="d6622-362">생성자</span><span class="sxs-lookup"><span data-stu-id="d6622-362">Constructors</span></span>](#constructors)
* [<span data-ttu-id="d6622-363">속성</span><span class="sxs-lookup"><span data-stu-id="d6622-363">Properties</span></span>](#properties)
* [<span data-ttu-id="d6622-364">이벤트</span><span class="sxs-lookup"><span data-stu-id="d6622-364">Events</span></span>](#events)
* [<span data-ttu-id="d6622-365">오버로드</span><span class="sxs-lookup"><span data-stu-id="d6622-365">Overloads</span></span>](#overloads)
* [<span data-ttu-id="d6622-366">예외</span><span class="sxs-lookup"><span data-stu-id="d6622-366">Exceptions</span></span>](#exceptions)
* [<span data-ttu-id="d6622-367">특성</span><span class="sxs-lookup"><span data-stu-id="d6622-367">Attributes</span></span>](#attributes)

### <a name="types-and-type-member-signatures"></a><span data-ttu-id="d6622-368">형식 및 형식 멤버 시그니처</span><span class="sxs-lookup"><span data-stu-id="d6622-368">Types and type member signatures</span></span>

<span data-ttu-id="d6622-369">[System.Object](xref:System.Object) 형식은 CLS 규격이고 .NET 형식 시스템의 모든 개체 형식의 기본 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-369">The [System.Object](xref:System.Object) type is CLS-compliant and is the base type of all object types in the .NET type system.</span></span> <span data-ttu-id="d6622-370">.NET의 상속은 암시적(예: [String](xref:System.String) 클래스는 `Object` 클래스에서 암시적으로 상속받음)이거나 명시적(예: [CultureNotFoundException](xref:System.Globalization.CultureNotFoundException) 클래스는 [ArgumentException](xref:System.ArgumentException) 클래스에서 명시적으로 상속받고, 이 클래스는 다시 [Exception](xref:System.Exception) 클래스에서 명시적으로 상속받음)입니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-370">Inheritance in .NET is either implicit (for example, the [String](xref:System.String) class implicitly inherits from the `Object` class) or explicit (for example, the [CultureNotFoundException](xref:System.Globalization.CultureNotFoundException) class explicitly inherits from the [ArgumentException](xref:System.ArgumentException) class, which explicitly inherits from the [Exception](xref:System.Exception) class.</span></span> <span data-ttu-id="d6622-371">파생된 형식은 CLS 규격이어야 하며, 그 기본 형식도 CLS 규격이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-371">For a derived type to be CLS compliant, its base type must also be CLS-compliant.</span></span>

<span data-ttu-id="d6622-372">다음 예제에서는 기본 형식이 CLS 규격이 아닌 파생 형식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-372">The following example shows a derived type whose base type is not CLS-compliant.</span></span> <span data-ttu-id="d6622-373">부호 없는 32비트 정수를 카운터로 사용하는 기본 `Counter` 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-373">It defines a base `Counter` class that uses an unsigned 32-bit integer as a counter.</span></span> <span data-ttu-id="d6622-374">이 클래스는 부호 없는 정수를 래핑하여 카운터 기능을 제공하므로 CLS 비규격으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-374">Because the class provides counter functionality by wrapping an unsigned integer, the class is marked as non-CLS-compliant.</span></span> <span data-ttu-id="d6622-375">따라서 파생된 클래스인 `NonZeroCounter`도 CLS 규격이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-375">As a result, a derived class, `NonZeroCounter`, is also not CLS-compliant.</span></span>

```csharp
using System;

[assembly: CLSCompliant(true)]

[CLSCompliant(false)]
public class Counter
{
   UInt32 ctr;

   public Counter()
   {
      ctr = 0;
   }

   protected Counter(UInt32 ctr)
   {
      this.ctr = ctr;
   }

   public override string ToString()
   {
      return $"{ctr}). ";
   }

   public UInt32 Value
   {
      get { return ctr; }
   }

   public void Increment()
   {
      ctr += (uint) 1;
   }
}

public class NonZeroCounter : Counter
{
   public NonZeroCounter(int startIndex) : this((uint) startIndex)
   {
   }

   private NonZeroCounter(UInt32 startIndex) : base(startIndex)
   {
   }
}
// Compilation produces a compiler warning like the following:
//    Type3.cs(37,14): warning CS3009: 'NonZeroCounter': base type 'Counter' is not
//            CLS-compliant
//    Type3.cs(7,14): (Location of symbol related to previous warning)
```

```vb
<Assembly: CLSCompliant(True)>

<CLSCompliant(False)> _
Public Class Counter
   Dim ctr As UInt32

   Public Sub New
      ctr = 0
   End Sub

   Protected Sub New(ctr As UInt32)
      ctr = ctr
   End Sub

   Public Overrides Function ToString() As String
      Return $"{ctr}). "
   End Function

   Public ReadOnly Property Value As UInt32
      Get
         Return ctr
      End Get
   End Property

   Public Sub Increment()
      ctr += CType(1, UInt32)
   End Sub
End Class

Public Class NonZeroCounter : Inherits Counter
   Public Sub New(startIndex As Integer)
      MyClass.New(CType(startIndex, UInt32))
   End Sub

   Private Sub New(startIndex As UInt32)
      MyBase.New(CType(startIndex, UInt32))
   End Sub
End Class
' Compilation produces a compiler warning like the following:
'    Type3.vb(34) : warning BC40026: 'NonZeroCounter' is not CLS-compliant
'    because it derives from 'Counter', which is not CLS-compliant.
'
'    Public Class NonZeroCounter : Inherits Counter
'                 ~~~~~~~~~~~~~~
```

<span data-ttu-id="d6622-376">메서드의 반환 형식 또는 속성 형식을 포함하여 멤버 시그니처에 나타나는 모든 형식은 CLS 규격이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-376">All types that appear in member signatures, including a method's return type or a property type, must be CLS-compliant.</span></span> <span data-ttu-id="d6622-377">또한 제네릭 형식의 경우,</span><span class="sxs-lookup"><span data-stu-id="d6622-377">In addition, for generic types:</span></span>

* <span data-ttu-id="d6622-378">인스턴스화된 제네릭 형식을 구성하는 모든 형식은 CLS 규격이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-378">All types that compose an instantiated generic type must be CLS-compliant.</span></span>

* <span data-ttu-id="d6622-379">제네릭 매개 변수에 대한 제약 조건으로 사용되는 모든 형식은 CLS 규격이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-379">All types used as constraints on generic parameters must be CLS-compliant.</span></span>

<span data-ttu-id="d6622-380">.NET [공용 형식 시스템](common-type-system.md)은 공용 언어 런타임에 의해 직접 지원되고 어셈블리의 메타데이터에서 특수 인코드되는 여러 기본 형식을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-380">The .NET [common type system](common-type-system.md) includes a number of built-in types that are supported directly by the common language runtime and are specially encoded in an assembly's metadata.</span></span> <span data-ttu-id="d6622-381">이러한 내장 형식 중에서 다음 표에 나열된 형식은 CLS 규격입니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-381">Of these intrinsic types, the types listed in the following table are CLS-compliant.</span></span>

<span data-ttu-id="d6622-382">CLS 규격 형식</span><span class="sxs-lookup"><span data-stu-id="d6622-382">CLS-compliant type</span></span> | <span data-ttu-id="d6622-383">설명</span><span class="sxs-lookup"><span data-stu-id="d6622-383">Description</span></span>
------------------ | -----------
[<span data-ttu-id="d6622-384">Byte</span><span class="sxs-lookup"><span data-stu-id="d6622-384">Byte</span></span>](xref:System.Byte) | <span data-ttu-id="d6622-385">8비트 부호 없는 정수</span><span class="sxs-lookup"><span data-stu-id="d6622-385">8-bit unsigned integer</span></span>
[<span data-ttu-id="d6622-386">Int16</span><span class="sxs-lookup"><span data-stu-id="d6622-386">Int16</span></span>](xref:System.Int16) | <span data-ttu-id="d6622-387">16비트 부호 있는 정수</span><span class="sxs-lookup"><span data-stu-id="d6622-387">16-bit signed integer</span></span>
[<span data-ttu-id="d6622-388">Int32</span><span class="sxs-lookup"><span data-stu-id="d6622-388">Int32</span></span>](xref:System.Int32) | <span data-ttu-id="d6622-389">32비트 부호 있는 정수</span><span class="sxs-lookup"><span data-stu-id="d6622-389">32-bit signed integer</span></span>
[<span data-ttu-id="d6622-390">Int64</span><span class="sxs-lookup"><span data-stu-id="d6622-390">Int64</span></span>](xref:System.Int64) | <span data-ttu-id="d6622-391">64비트 부호 있는 정수</span><span class="sxs-lookup"><span data-stu-id="d6622-391">64-bit signed integer</span></span>
[<span data-ttu-id="d6622-392">Single</span><span class="sxs-lookup"><span data-stu-id="d6622-392">Single</span></span>](xref:System.Single) | <span data-ttu-id="d6622-393">단정밀도 부동 소수점 값</span><span class="sxs-lookup"><span data-stu-id="d6622-393">Single-precision floating-point value</span></span>
[<span data-ttu-id="d6622-394">double</span><span class="sxs-lookup"><span data-stu-id="d6622-394">Double</span></span>](xref:System.Double) | <span data-ttu-id="d6622-395">배정밀도 부동 소수점 값</span><span class="sxs-lookup"><span data-stu-id="d6622-395">Double-precision floating-point value</span></span>
[<span data-ttu-id="d6622-396">Boolean</span><span class="sxs-lookup"><span data-stu-id="d6622-396">Boolean</span></span>](xref:System.Boolean) | <span data-ttu-id="d6622-397">true 또는 false 값 형식</span><span class="sxs-lookup"><span data-stu-id="d6622-397">true or false value type</span></span>
[<span data-ttu-id="d6622-398">Char</span><span class="sxs-lookup"><span data-stu-id="d6622-398">Char</span></span>](xref:System.Char) | <span data-ttu-id="d6622-399">UTF-16으로 인코딩된 코드 단위</span><span class="sxs-lookup"><span data-stu-id="d6622-399">UTF-16 encoded code unit</span></span>
[<span data-ttu-id="d6622-400">Decimal</span><span class="sxs-lookup"><span data-stu-id="d6622-400">Decimal</span></span>](xref:System.Decimal) | <span data-ttu-id="d6622-401">비 부동 소수점 10진수</span><span class="sxs-lookup"><span data-stu-id="d6622-401">Non-floating-point decimal number</span></span>
[<span data-ttu-id="d6622-402">IntPtr</span><span class="sxs-lookup"><span data-stu-id="d6622-402">IntPtr</span></span>](xref:System.IntPtr) | <span data-ttu-id="d6622-403">플랫폼 정의 크기의 포인터 또는 핸들</span><span class="sxs-lookup"><span data-stu-id="d6622-403">Pointer or handle of a platform-defined size</span></span>
[<span data-ttu-id="d6622-404">String</span><span class="sxs-lookup"><span data-stu-id="d6622-404">String</span></span>](xref:System.String) | <span data-ttu-id="d6622-405">0개 또는 하나 이상의 Char 개체 컬렉션</span><span class="sxs-lookup"><span data-stu-id="d6622-405">Collection of zero, one, or more Char objects</span></span>

<span data-ttu-id="d6622-406">다음 표에 나열된 내장 형식은 CLS 규격이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-406">The intrinsic types listed in the following table are not CLS-Compliant.</span></span>

<span data-ttu-id="d6622-407">비규격 형식</span><span class="sxs-lookup"><span data-stu-id="d6622-407">Non-compliant type</span></span> | <span data-ttu-id="d6622-408">설명</span><span class="sxs-lookup"><span data-stu-id="d6622-408">Description</span></span> | <span data-ttu-id="d6622-409">CLS 규격 대체 항목</span><span class="sxs-lookup"><span data-stu-id="d6622-409">CLS-compliant alternative</span></span>
------------------ | ----------- | -------------------------
[<span data-ttu-id="d6622-410">SByte</span><span class="sxs-lookup"><span data-stu-id="d6622-410">SByte</span></span>](xref:System.SByte) | <span data-ttu-id="d6622-411">8비트 부호 있는 정수 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="d6622-411">8-bit signed integer data type</span></span> | [<span data-ttu-id="d6622-412">Int16</span><span class="sxs-lookup"><span data-stu-id="d6622-412">Int16</span></span>](xref:System.Int16)
[<span data-ttu-id="d6622-413">UInt16</span><span class="sxs-lookup"><span data-stu-id="d6622-413">UInt16</span></span>](xref:System.UInt16) | <span data-ttu-id="d6622-414">16비트 부호 없는 정수</span><span class="sxs-lookup"><span data-stu-id="d6622-414">16-bit unsigned integer</span></span> | [<span data-ttu-id="d6622-415">Int32</span><span class="sxs-lookup"><span data-stu-id="d6622-415">Int32</span></span>](xref:System.Int32)
[<span data-ttu-id="d6622-416">UInt32</span><span class="sxs-lookup"><span data-stu-id="d6622-416">UInt32</span></span>](xref:System.UInt32) | <span data-ttu-id="d6622-417">32비트 부호 없는 정수</span><span class="sxs-lookup"><span data-stu-id="d6622-417">32-bit unsigned integer</span></span> | [<span data-ttu-id="d6622-418">Int64</span><span class="sxs-lookup"><span data-stu-id="d6622-418">Int64</span></span>](xref:System.Int64)
[<span data-ttu-id="d6622-419">UInt64</span><span class="sxs-lookup"><span data-stu-id="d6622-419">UInt64</span></span>](xref:System.UInt64) | <span data-ttu-id="d6622-420">64비트 부호 없는 정수</span><span class="sxs-lookup"><span data-stu-id="d6622-420">64-bit unsigned integer</span></span> | <span data-ttu-id="d6622-421">[Int64](xref:System.Int64)(오버플로될 수 있음), [BigInteger](xref:System.Numerics.BigInteger) 또는 [Double](xref:System.Double)</span><span class="sxs-lookup"><span data-stu-id="d6622-421">[Int64](xref:System.Int64) (may overflow), [BigInteger](xref:System.Numerics.BigInteger), or [Double](xref:System.Double)</span></span>
[<span data-ttu-id="d6622-422">UIntPtr</span><span class="sxs-lookup"><span data-stu-id="d6622-422">UIntPtr</span></span>](xref:System.UIntPtr) | <span data-ttu-id="d6622-423">부호 없는 포인터 또는 핸들</span><span class="sxs-lookup"><span data-stu-id="d6622-423">Unsigned pointer or handle</span></span> | [<span data-ttu-id="d6622-424">IntPtr</span><span class="sxs-lookup"><span data-stu-id="d6622-424">IntPtr</span></span>](xref:System.IntPtr)

<span data-ttu-id="d6622-425">.NET 클래스 라이브러리 또는 기타 다른 클래스 라이브러리는 다음 예시와 같은 CLS 규격이 아닌 기타 형식을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-425">The .NET Class Library or any other class library may include other types that aren't CLS-compliant; for example:</span></span>

* <span data-ttu-id="d6622-426">boxed 값 형식.</span><span class="sxs-lookup"><span data-stu-id="d6622-426">Boxed value types.</span></span> <span data-ttu-id="d6622-427">다음 C# 예제는 이름이 `int*`인 public 속성 `Value` 형식을 가진 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-427">The following C# example creates a class that has a public property of type `int*` named `Value`.</span></span> <span data-ttu-id="d6622-428">`int*`는 boxed 값 형식이므로 컴파일러에서 CLS 비규격으로 플래그를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-428">Because an `int*` is a boxed value type, the compiler flags it as non-CLS-compliant.</span></span>

```csharp
using System;

[assembly:CLSCompliant(true)]

public unsafe class TestClass
{
   private int* val;

   public TestClass(int number)
   {
      val = (int*) number;
   }

   public int* Value {
      get { return val; }
   }
}
// The compiler generates the following output when compiling this example:
//        warning CS3003: Type of 'TestClass.Value' is not CLS-compliant
```

* <span data-ttu-id="d6622-429">형식화된 참조란 개체에 대한 참조 및 형식에 대한 참조를 포함하는 특수 생성자로서,</span><span class="sxs-lookup"><span data-stu-id="d6622-429">Typed references, which are special constructs that contain a reference to an object and a reference to a type.</span></span>

<span data-ttu-id="d6622-430">형식이 CLS 규격이 아닌 경우 *isCompliant* 매개 변수를 `false` 값으로 지정하여 [CLSCompliantAttribute](xref:System.CLSCompliantAttribute) 특성을 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-430">If a type is not CLS-compliant, you should apply the [CLSCompliantAttribute](xref:System.CLSCompliantAttribute) attribute with an *isCompliant* parameter with a value of `false` to it.</span></span> <span data-ttu-id="d6622-431">자세한 내용은 [CLSCompliantAttribute 특성](#the-clscompliantattribute-attribute) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d6622-431">For more information, see the [CLSCompliantAttribute attribute](#the-clscompliantattribute-attribute) section.</span></span>

<span data-ttu-id="d6622-432">다음 예제에서는 메서드 시그니처와 제네릭 형식 인스턴스화의 CLS 규격 문제를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-432">The following example illustrates the problem of CLS compliance in a method signature and in generic type instantiation.</span></span> <span data-ttu-id="d6622-433">`InvoiceItem` 클래스를 [UInt32](xref:System.UInt32) 형식의 속성, [Nullable(Of UInt32)](xref:System.Nullable%601) 형식의 속성, `UInt32` 및 `Nullable(Of UInt32)` 형식의 매개 변수가 있는 생성자로 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-433">It defines an `InvoiceItem` class with a property of type [UInt32](xref:System.UInt32), a property of type [Nullable(Of UInt32)](xref:System.Nullable%601), and a constructor with parameters of type `UInt32` and `Nullable(Of UInt32)`.</span></span> <span data-ttu-id="d6622-434">이 예제를 컴파일하려고 할 때 4개의 컴파일러 경고가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-434">You get four compiler warnings when you try to compile this example.</span></span>

```csharp
using System;

[assembly: CLSCompliant(true)]

public class InvoiceItem
{
   private uint invId = 0;
   private uint itemId = 0;
   private Nullable<uint> qty;

   public InvoiceItem(uint sku, Nullable<uint> quantity)
   {
      itemId = sku;
      qty = quantity;
   }

   public Nullable<uint> Quantity
   {
      get { return qty; }
      set { qty = value; }
   }

   public uint InvoiceId
   {
      get { return invId; }
      set { invId = value; }
   }
}
// The attempt to compile the example displays the following output:
//    Type1.cs(13,23): warning CS3001: Argument type 'uint' is not CLS-compliant
//    Type1.cs(13,33): warning CS3001: Argument type 'uint?' is not CLS-compliant
//    Type1.cs(19,26): warning CS3003: Type of 'InvoiceItem.Quantity' is not CLS-compliant
//    Type1.cs(25,16): warning CS3003: Type of 'InvoiceItem.InvoiceId' is not CLS-compliant
```

```vb
<Assembly: CLSCompliant(True)>

Public Class InvoiceItem

   Private invId As UInteger = 0
   Private itemId As UInteger = 0
   Private qty AS Nullable(Of UInteger)

   Public Sub New(sku As UInteger, quantity As Nullable(Of UInteger))
      itemId = sku
      qty = quantity
   End Sub

   Public Property Quantity As Nullable(Of UInteger)
      Get
         Return qty
      End Get
      Set
         qty = value
      End Set
   End Property

   Public Property InvoiceId As UInteger
      Get
         Return invId
      End Get
      Set
         invId = value
      End Set
   End Property
End Class
' The attempt to compile the example displays output similar to the following:
'    Type1.vb(13) : warning BC40028: Type of parameter 'sku' is not CLS-compliant.
'
'       Public Sub New(sku As UInteger, quantity As Nullable(Of UInteger))
'                      ~~~
'    Type1.vb(13) : warning BC40041: Type 'UInteger' is not CLS-compliant.
'
'       Public Sub New(sku As UInteger, quantity As Nullable(Of UInteger))
'                                                               ~~~~~~~~
'    Type1.vb(18) : warning BC40041: Type 'UInteger' is not CLS-compliant.
'
'       Public Property Quantity As Nullable(Of UInteger)
'                                               ~~~~~~~~
'    Type1.vb(27) : warning BC40027: Return type of function 'InvoiceId' is not CLS-compliant.
'
'       Public Property InvoiceId As UInteger
```

<span data-ttu-id="d6622-435">컴파일러 경고를 없애려면 `InvoiceItem` 공용 인터페이스의 CLS 규격이 아닌 형식을 CLS 규격 형식으로 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-435">To eliminate the compiler warnings, replace the non-CLS-compliant types in the `InvoiceItem` public interface with compliant types:</span></span>

```csharp
using System;

[assembly: CLSCompliant(true)]

public class InvoiceItem
{
   private uint invId = 0;
   private uint itemId = 0;
   private Nullable<int> qty;

   public InvoiceItem(int sku, Nullable<int> quantity)
   {
      if (sku <= 0)
         throw new ArgumentOutOfRangeException("The item number is zero or negative.");
      itemId = (uint) sku;

      qty = quantity;
   }

   public Nullable<int> Quantity
   {
      get { return qty; }
      set { qty = value; }
   }

   public int InvoiceId
   {
      get { return (int) invId; }
      set {
         if (value <= 0)
            throw new ArgumentOutOfRangeException("The invoice number is zero or negative.");
         invId = (uint) value; }
   }
}
```

```vb
Assembly: CLSCompliant(True)>

Public Class InvoiceItem

   Private invId As UInteger = 0
   Private itemId As UInteger = 0
   Private qty AS Nullable(Of Integer)

   Public Sub New(sku As Integer, quantity As Nullable(Of Integer))
      If sku <= 0 Then
         Throw New ArgumentOutOfRangeException("The item number is zero or negative.")
      End If
      itemId = CUInt(sku)
      qty = quantity
   End Sub

   Public Property Quantity As Nullable(Of Integer)
      Get
         Return qty
      End Get
      Set
         qty = value
      End Set
   End Property

   Public Property InvoiceId As Integer
      Get
         Return CInt(invId)
      End Get
      Set
         invId = CUInt(value)
      End Set
   End Property
End Class
```

<span data-ttu-id="d6622-436">나열된 특정 형식 외에도 일부 형식 범주가 CLS 규격이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-436">In addition to the specific types listed, some categories of types are not CLS compliant.</span></span> <span data-ttu-id="d6622-437">여기에는 관리되지 않는 포인터 형식 및 함수 포인터 형식이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-437">These include unmanaged pointer types and function pointer types.</span></span> <span data-ttu-id="d6622-438">다음 예제에서는 정수에 대한 포인터를 사용하여 정수 배열을 만들기 때문에 컴파일러 경고가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-438">The following example generates a compiler warning because it uses a pointer to an integer to create an array of integers.</span></span>

```csharp
using System;

[assembly: CLSCompliant(true)]

public class ArrayHelper
{
   unsafe public static Array CreateInstance(Type type, int* ptr, int items)
   {
      Array arr = Array.CreateInstance(type, items);
      int* addr = ptr;
      for (int ctr = 0; ctr < items; ctr++) {
          int value = *addr;
          arr.SetValue(value, ctr);
          addr++;
      }
      return arr;
   }
}
// The attempt to compile this example displays the following output:
//    UnmanagedPtr1.cs(8,57): warning CS3001: Argument type 'int*' is not CLS-compliant
```

```csharp
using System;

[assembly: CLSCompliant(true)]

public class ArrayHelper
{
   unsafe public static Array CreateInstance(Type type, int* ptr, int items)
   {
      Array arr = Array.CreateInstance(type, items);
      int* addr = ptr;
      for (int ctr = 0; ctr < items; ctr++) {
          int value = *addr;
          arr.SetValue(value, ctr);
          addr++;
      }
      return arr;
   }
}
// The attempt to compile this example displays the following output:
//    UnmanagedPtr1.cs(8,57): warning CS3001: Argument type 'int*' is not CLS-compliant
```

<span data-ttu-id="d6622-439">CLS 규격인 추상 클래스(C#에서 `abstract`로 표시된 클래스)의 경우 이 클래스의 모든 멤버 역시 CLS 규격이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-439">For CLS-compliant abstract classes (that is, classes marked as `abstract` in C#), all members of the class must also be CLS-compliant.</span></span>

### <a name="naming-conventions"></a><span data-ttu-id="d6622-440">명명 규칙</span><span class="sxs-lookup"><span data-stu-id="d6622-440">Naming conventions</span></span>

<span data-ttu-id="d6622-441">일부 프로그래밍 언어에서는 대/소문자를 구분하기 때문에 식별자(네임스페이스, 형식 및 멤버 이름 등)는 대/소문자 그 이상의 차이가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-441">Because some programming languages are case-insensitive, identifiers (such as the names of namespaces, types, and members) must differ by more than case.</span></span> <span data-ttu-id="d6622-442">소문자 매핑이 같은 두 개의 식별자는 서로 동일한 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-442">Two identifiers are considered equivalent if their lowercase mappings are the same.</span></span> <span data-ttu-id="d6622-443">다음 C# 예제에서는 `Person` 및 `person`이라는 두 가지 공용 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-443">The following C# example defines two public classes, `Person` and `person`.</span></span> <span data-ttu-id="d6622-444">이들 클래스는 대/소문자만 다르므로 C# 컴파일러는 CLS 규격이 아니라는 플래그를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-444">Because they differ only by case, the C# compiler flags them as not CLS-compliant.</span></span>

```csharp
using System;

[assembly: CLSCompliant(true)]

public class Person : person
{

}

public class person
{

}
// Compilation produces a compiler warning like the following:
//    Naming1.cs(11,14): warning CS3005: Identifier 'person' differing
//                       only in case is not CLS-compliant
//    Naming1.cs(6,14): (Location of symbol related to previous warning)
```

<span data-ttu-id="d6622-445">네임스페이스, 형식 및 멤버의 이름과 같은 언어 식별자 프로그래밍은 [유니코드 표준 ](https://unicode.org/reports/tr15/)을 준수해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-445">Programming language identifiers, such as the names of namespaces, types, and members, must conform to the [Unicode Standard](https://unicode.org/reports/tr15/).</span></span> <span data-ttu-id="d6622-446">이는 다음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-446">This means that:</span></span>

* <span data-ttu-id="d6622-447">식별자의 첫 문자로는 유니코드 대문자, 소문자, 제목 대/소문자, 한정자 문자, 기타 문자 또는 문자 숫자가 올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-447">The first character of an identifier can be any Unicode uppercase letter, lowercase letter, title case letter, modifier letter, other letter, or letter number.</span></span> <span data-ttu-id="d6622-448">유니코드 문자 범주에 대한 자세한 내용은 [System.Globalization.UnicodeCategory](xref:System.Globalization.UnicodeCategory) 열거형을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d6622-448">For information on Unicode character categories, see the [System.Globalization.UnicodeCategory](xref:System.Globalization.UnicodeCategory) enumeration.</span></span>

* <span data-ttu-id="d6622-449">연속되는 문자는 첫 번째 문자로서 가능한 모든 범주의 문자가 올 수 있으며 간격 없음 표시, 간격 결합 기호, 10진수, 연결 문장 부호 및 형식 지정 코드를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-449">Subsequent characters can be from any of the categories as the first character, and can also include non-spacing marks, spacing combining marks, decimal numbers, connector punctuation, and formatting codes.</span></span>

<span data-ttu-id="d6622-450">단일 문자를 다중 UTF-16 인코딩 코드 단위로 표시할 수 있으므로 식별자를 비교하기 전에 형식 지정 코드를 필터링하고 식별자를 유니코드 정규화 형식 C로 변환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-450">Before you compare identifiers, you should filter out formatting codes and convert the identifiers to Unicode Normalization Form C, because a single character can be represented by multiple UTF-16-encoded code units.</span></span> <span data-ttu-id="d6622-451">유니코드 정규화 형식 C에서 동일한 코드 단위를 만드는 문자 시퀀스는 CLS 규격이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-451">Character sequences that produce the same code units in Unicode Normalization Form C are not CLS-compliant.</span></span> <span data-ttu-id="d6622-452">다음 예제에서는 ANGSTROM SIGN(U+212B) 문자로 구성된 `Å`이라는 속성과 LATIN CAPITAL LETTER A WITH RING ABOVE(U+00C5) 문자로 구성된 두 번째 `Å`이라는 속성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-452">The following example defines a property named `Å`, which consists of the character ANGSTROM SIGN (U+212B), and a second property named `Å`, which consists of the character LATIN CAPITAL LETTER A WITH RING ABOVE (U+00C5).</span></span> <span data-ttu-id="d6622-453">C# 컴파일러는 소스 코드에 CLS 비규격으로 플래그를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-453">The C# compiler flags the source code as non-CLS-compliant.</span></span>

```csharp
public class Size
{
   private double a1;
   private double a2;

   public double Å
   {
       get { return a1; }
       set { a1 = value; }
   }

   public double Å
   {
       get { return a2; }
       set { a2 = value; }
   }
}
// Compilation produces a compiler warning like the following:
//    Naming2a.cs(16,18): warning CS3005: Identifier 'Size.Å' differing only in case is not
//            CLS-compliant
//    Naming2a.cs(10,18): (Location of symbol related to previous warning)
//    Naming2a.cs(18,8): warning CS3005: Identifier 'Size.Å.get' differing only in case is not
//            CLS-compliant
//    Naming2a.cs(12,8): (Location of symbol related to previous warning)
//    Naming2a.cs(19,8): warning CS3005: Identifier 'Size.Å.set' differing only in case is not
//            CLS-compliant
//    Naming2a.cs(13,8): (Location of symbol related to previous warning)
```

```vb
<Assembly: CLSCompliant(True)>
Public Class Size
   Private a1 As Double
   Private a2 As Double

   Public Property Å As Double
       Get
          Return a1
       End Get
       Set
          a1 = value
       End Set
   End Property

   Public Property Å As Double
       Get
          Return a2
       End Get
       Set
          a2 = value
       End Set
   End Property
End Class
' Compilation produces a compiler warning like the following:
'    Naming1.vb(9) : error BC30269: 'Public Property Å As Double' has multiple definitions
'     with identical signatures.
'
'       Public Property Å As Double
'                       ~
```

<span data-ttu-id="d6622-454">오버로드를 통해 확인되는 이름을 제외한 특정 범위 내의 멤버 이름(예: 어셈블리 내 네임스페이스, 네임스페이스 내 형식 또는 형식 내 멤버)은 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-454">Member names within a particular scope (such as the namespaces within an assembly, the types within a namespace, or the members within a type) must be unique except for names that are resolved through overloading.</span></span> <span data-ttu-id="d6622-455">이 요구 사항은 한 범위 내의 여러 멤버가 다른 종류의 멤버인 경우(예를 들어 하나는 메서드이고 하나는 필드인 경우) 고유한 이름을 사용할 수 있는 공용 형식 시스템의 요구 사항보다 더 엄격합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-455">This requirement is more stringent than that of the common type system, which allows multiple members within a scope to have identical names as long as they are different kinds of members (for example, one is a method and one is a field).</span></span> <span data-ttu-id="d6622-456">특히, 형식 멤버가</span><span class="sxs-lookup"><span data-stu-id="d6622-456">In particular, for type members:</span></span>

* <span data-ttu-id="d6622-457">필드 및 중첩된 형식인 경우 이름으로만 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-457">Fields and nested types are distinguished by name alone.</span></span>

* <span data-ttu-id="d6622-458">이름이 같은 메서드, 속성 및 이벤트인 경우 반환 형식 이외의 차이점이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-458">Methods, properties, and events that have the same name must differ by more than just return type.</span></span>

<span data-ttu-id="d6622-459">다음 예제에서는 멤버 이름이 해당 범위 내에서 고유해야 한다는 요구 사항을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-459">The following example illustrates the requirement that member names must be unique within their scope.</span></span> <span data-ttu-id="d6622-460">`Converter`이라는 4개 멤버를 포함하는 `Conversion`라는 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-460">It defines a class named `Converter` that includes four members named `Conversion`.</span></span> <span data-ttu-id="d6622-461">세 가지는 메서드이고 한 가지는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-461">Three are methods, and one is a property.</span></span> <span data-ttu-id="d6622-462">`Int64` 매개 변수가 포함된 메서드의 이름은 고유하지만, `Int32` 매개 변수가 포함된 두 메서드의 이름은 반환 값이 멤버 시그니처의 일부로 간주되지 않으므로 고유하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-462">The method that includes an `Int64` parameter is uniquely named, but the two methods with an `Int32` parameter are not, because return value is not considered a part of a member's signature.</span></span> <span data-ttu-id="d6622-463">속성은 오버로드된 메서드와 동일한 이름을 가질 수 없으므로 `Conversion` 속성 또한 이 요구 사항을 위반합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-463">The `Conversion` property also violates this requirement, because properties cannot have the same name as overloaded methods.</span></span>

```csharp
using System;

[assembly: CLSCompliant(true)]

public class Converter
{
   public double Conversion(int number)
   {
      return (double) number;
   }

   public float Conversion(int number)
   {
      return (float) number;
   }

   public double Conversion(long number)
   {
      return (double) number;
   }

   public bool Conversion
   {
      get { return true; }
   }
}
// Compilation produces a compiler error like the following:
//    Naming3.cs(13,17): error CS0111: Type 'Converter' already defines a member called
//            'Conversion' with the same parameter types
//    Naming3.cs(8,18): (Location of symbol related to previous error)
//    Naming3.cs(23,16): error CS0102: The type 'Converter' already contains a definition for
//            'Conversion'
//    Naming3.cs(8,18): (Location of symbol related to previous error)
```

```vb
<Assembly: CLSCompliant(True)>

Public Class Converter
   Public Function Conversion(number As Integer) As Double
      Return CDbl(number)
   End Function

   Public Function Conversion(number As Integer) As Single
      Return CSng(number)
   End Function

   Public Function Conversion(number As Long) As Double
      Return CDbl(number)
   End Function

   Public ReadOnly Property Conversion As Boolean
      Get
         Return True
      End Get
   End Property
End Class
' Compilation produces a compiler error like the following:
'    Naming3.vb(8) : error BC30301: 'Public Function Conversion(number As Integer) As Double'
'                    and 'Public Function Conversion(number As Integer) As Single' cannot
'                    overload each other because they differ only by return types.
'
'       Public Function Conversion(number As Integer) As Double
'                       ~~~~~~~~~~
'    Naming3.vb(20) : error BC30260: 'Conversion' is already declared as 'Public Function
'                     Conversion(number As Integer) As Single' in this class.
'
'       Public ReadOnly Property Conversion As Boolean
'                                ~~~~~~~~~~
```

<span data-ttu-id="d6622-464">개별 언어는 고유 키워드를 포함하기 때문에 공용 언어 런타임을 대상으로 하는 언어는 키워드와 일치하는 식별자(예: 형식 이름)를 참조하기 위한 일부 메커니즘도 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-464">Individual languages include unique keywords, so languages that target the common language runtime must also provide some mechanism for referencing identifiers (such as type names) that coincide with keywords.</span></span> <span data-ttu-id="d6622-465">예를 들어, `case`는 C# 및 Visual Basic 모두의 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-465">For example, `case` is a keyword in both C# and Visual Basic.</span></span> <span data-ttu-id="d6622-466">그러나 다음 Visual Basic 예제에서는 열고 닫는 중괄호를 사용하여 `case` 키워드에서 `case`라는 이름의 클래스를 구분할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-466">However, the following Visual Basic example is able to disambiguate a class named `case` from the `case` keyword by using opening and closing braces.</span></span> <span data-ttu-id="d6622-467">중괄호가 없다면 이 예제에서는 "키워드를 식별자로 사용할 수 없습니다."와 같은 오류 메시지가 발생하고 컴파일되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-467">Otherwise, the example would produce the error message, "Keyword is not valid as an identifier," and fail to compile.</span></span>

```vb
Public Class [case]
   Private _id As Guid
   Private name As String

   Public Sub New(name As String)
      _id = Guid.NewGuid()
      Me.name = name
   End Sub

   Public ReadOnly Property ClientName As String
      Get
         Return name
      End Get
   End Property
End Class
```

<span data-ttu-id="d6622-468">다음 C# 예제에서는 @ 기호를 사용하여 언어 키워드에서 식별자를 구분하여 `case` 클래스를 인스턴스화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-468">The following C# example is able to instantiate the `case` class by using the @ symbol to disambiguate the identifier from the language keyword.</span></span> <span data-ttu-id="d6622-469">이 기호가 없으면 C# 컴파일러에서는 "형식이 필요합니다" 및 "식의 'case' 항이 잘못되었습니다"라는 두 개의 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-469">Without it, the C# compiler would display two error messages, "Type expected" and "Invalid expression term 'case'."</span></span>

```csharp
using System;

public class Example
{
   public static void Main()
   {
      @case c = new @case("John");
      Console.WriteLine(c.ClientName);
   }
}
```

### <a name="type-conversion"></a><span data-ttu-id="d6622-470">형식 변환</span><span class="sxs-lookup"><span data-stu-id="d6622-470">Type conversion</span></span>

<span data-ttu-id="d6622-471">공용 언어 사양은 다음과 같은 두 변환 연산자를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-471">The Common Language Specification defines two conversion operators:</span></span>

* <span data-ttu-id="d6622-472">`op_Implicit`는 데이터 또는 정밀도가 손실되지 않는 확대 변환에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-472">`op_Implicit`, which is used for widening conversions that do not result in loss of data or precision.</span></span> <span data-ttu-id="d6622-473">예를 들어 [Decimal](xref:System.Decimal) 구조체에 오버로드된 `op_Implicit` 연산자를 포함하여 정수 형식의 값과 [Char](xref:System.Char) 값을 `Decimal` 값으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-473">For example, the [Decimal](xref:System.Decimal) structure includes an overloaded `op_Implicit` operator to convert values of integral types and [Char](xref:System.Char) values to `Decimal` values.</span></span>

* <span data-ttu-id="d6622-474">`op_Explicit`는 크기 손실(보다 작은 범위의 값으로 변환) 또는 정밀도 손실이 발생할 수 있는 축소 변환에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-474">`op_Explicit`, which is used for narrowing conversions that can result in loss of magnitude (a value is converted to a value that has a smaller range) or precision.</span></span> <span data-ttu-id="d6622-475">예를 들어 `Decimal` 구조체에 오버로드된 `op_Explicit`연산자를 포함하여 [Double](xref:System.Double) 및 [Single](xref:System.Single) 값을 `Decimal` 값으로 변환하고, `Decimal` 값을 정수 값, `Double`, `Single` 및 `Char`로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-475">For example, the `Decimal` structure includes an overloaded `op_Explicit` operator to convert [Double](xref:System.Double) and [Single](xref:System.Single) values to `Decimal` and to convert `Decimal` values to integral values, `Double`, `Single`, and `Char`.</span></span>

<span data-ttu-id="d6622-476">그러나 모든 언어가 연산자 오버로드 또는 사용자 지정 연산자 정의를 지원하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-476">However, not all languages support operator overloading or the definition of custom operators.</span></span> <span data-ttu-id="d6622-477">이러한 변환 연산자를 구현하도록 선택한 경우, 변환을 수행하기 위한 다른 방법도 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-477">If you choose to implement these conversion operators, you should also provide an alternate way to perform the conversion.</span></span> <span data-ttu-id="d6622-478">`From`Xxx 및 `To`Xxx 메서드를 제공하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-478">We recommend that you provide `From`Xxx and `To`Xxx methods.</span></span>

<span data-ttu-id="d6622-479">다음 예제에서는 CLS 규격의 암시적 및 명시적 변환을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-479">The following example defines CLS-compliant implicit and explicit conversions.</span></span> <span data-ttu-id="d6622-480">부호 있는 배정밀도, 부동 소수점 숫자를 나타내는 `UDouble` 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-480">It creates a `UDouble` class that represents a signed double-precision, floating-point number.</span></span> <span data-ttu-id="d6622-481">`UDouble`에서 `Double`로의 암시적 변환 및 `UDouble`에서 `Single`로, `Double`에서 `UDouble`로, `Single`에서 `UDouble`로의 명시적 변환이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-481">It provides for implicit conversions from `UDouble` to `Double` and for explicit conversions from `UDouble` to `Single`, `Double` to `UDouble`, and `Single` to `UDouble`.</span></span> <span data-ttu-id="d6622-482">또한 `ToDouble` 메서드를 암시적 변환 연산자에 대한 대안으로 정의하고 `ToSingle`, `FromDouble` 및 `FromSingle` 메서드를 명시적 변환 연산자에 대한 대안으로 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-482">It also defines a `ToDouble` method as an alternative to the implicit conversion operator and the `ToSingle`, `FromDouble`, and `FromSingle` methods as alternatives to the explicit conversion operators.</span></span>

```csharp
using System;

public struct UDouble
{
   private double number;

   public UDouble(double value)
   {
      if (value < 0)
         throw new InvalidCastException("A negative value cannot be converted to a UDouble.");

      number = value;
   }

   public UDouble(float value)
   {
      if (value < 0)
         throw new InvalidCastException("A negative value cannot be converted to a UDouble.");

      number = value;
   }

   public static readonly UDouble MinValue = (UDouble) 0.0;
   public static readonly UDouble MaxValue = (UDouble) Double.MaxValue;

   public static explicit operator Double(UDouble value)
   {
      return value.number;
   }

   public static implicit operator Single(UDouble value)
   {
      if (value.number > (double) Single.MaxValue)
         throw new InvalidCastException("A UDouble value is out of range of the Single type.");

      return (float) value.number;
   }

   public static explicit operator UDouble(double value)
   {
      if (value < 0)
         throw new InvalidCastException("A negative value cannot be converted to a UDouble.");

      return new UDouble(value);
   }

   public static implicit operator UDouble(float value)
   {
      if (value < 0)
         throw new InvalidCastException("A negative value cannot be converted to a UDouble.");

      return new UDouble(value);
   }

   public static Double ToDouble(UDouble value)
   {
      return (Double) value;
   }

   public static float ToSingle(UDouble value)
   {
      return (float) value;
   }

   public static UDouble FromDouble(double value)
   {
      return new UDouble(value);
   }

   public static UDouble FromSingle(float value)
   {
      return new UDouble(value);
   }
}
```

```vb
Public Structure UDouble
   Private number As Double

   Public Sub New(value As Double)
      If value < 0 Then
         Throw New InvalidCastException("A negative value cannot be converted to a UDouble.")
      End If
      number = value
   End Sub

   Public Sub New(value As Single)
      If value < 0 Then
         Throw New InvalidCastException("A negative value cannot be converted to a UDouble.")
      End If
      number = value
   End Sub

   Public Shared ReadOnly MinValue As UDouble = CType(0.0, UDouble)
   Public Shared ReadOnly MaxValue As UDouble = Double.MaxValue

   Public Shared Widening Operator CType(value As UDouble) As Double
      Return value.number
   End Operator

   Public Shared Narrowing Operator CType(value As UDouble) As Single
      If value.number > CDbl(Single.MaxValue) Then
         Throw New InvalidCastException("A UDouble value is out of range of the Single type.")
      End If
      Return CSng(value.number)
   End Operator

   Public Shared Narrowing Operator CType(value As Double) As UDouble
      If value < 0 Then
         Throw New InvalidCastException("A negative value cannot be converted to a UDouble.")
      End If
      Return New UDouble(value)
   End Operator

   Public Shared Narrowing Operator CType(value As Single) As UDouble
      If value < 0 Then
         Throw New InvalidCastException("A negative value cannot be converted to a UDouble.")
      End If
      Return New UDouble(value)
   End Operator

   Public Shared Function ToDouble(value As UDouble) As Double
      Return CType(value, Double)
   End Function

   Public Shared Function ToSingle(value As UDouble) As Single
      Return CType(value, Single)
   End Function

   Public Shared Function FromDouble(value As Double) As UDouble
      Return New UDouble(value)
   End Function

   Public Shared Function FromSingle(value As Single) As UDouble
      Return New UDouble(value)
   End Function
End Structure
```

### <a name="arrays"></a><span data-ttu-id="d6622-483">배열</span><span class="sxs-lookup"><span data-stu-id="d6622-483">Arrays</span></span>

<span data-ttu-id="d6622-484">CLS 규격 배열은 다음 규칙을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-484">CLS-compliant arrays conform to the following rules:</span></span>

* <span data-ttu-id="d6622-485">배열의 모든 크기는 하한이 0이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-485">All dimensions of an array must have a lower bound of zero.</span></span> <span data-ttu-id="d6622-486">다음 예제에서는 하한이 1인 CLS 비규격 배열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-486">The following example creates a non-CLS-compliant array with a lower bound of one.</span></span> <span data-ttu-id="d6622-487">[CLSCompliantAttribute](xref:System.CLSCompliantAttribute) 특성이 있음에도 불구하고 `Numbers.GetTenPrimes` 메서드에서 반환된 배열이 CLS 규격이 아님을 컴파일러에서 감지하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-487">Despite the presence of the [CLSCompliantAttribute](xref:System.CLSCompliantAttribute) attribute, the compiler does not detect that the array returned by the `Numbers.GetTenPrimes` method is not CLS-compliant.</span></span>

  ```csharp
  [assembly: CLSCompliant(true)]

  public class Numbers
  {
    public static Array GetTenPrimes()
    {
        Array arr = Array.CreateInstance(typeof(Int32), new int[] {10}, new int[] {1});
        arr.SetValue(1, 1);
        arr.SetValue(2, 2);
        arr.SetValue(3, 3);
        arr.SetValue(5, 4);
        arr.SetValue(7, 5);
        arr.SetValue(11, 6);
        arr.SetValue(13, 7);
        arr.SetValue(17, 8);
        arr.SetValue(19, 9);
        arr.SetValue(23, 10);

        return arr;
    }
  }
  ```

  ```vb
  <Assembly: CLSCompliant(True)>

  Public Class Numbers
     Public Shared Function GetTenPrimes() As Array
        Dim arr As Array = Array.CreateInstance(GetType(Int32), {10}, {1})
        arr.SetValue(1, 1)
        arr.SetValue(2, 2)
        arr.SetValue(3, 3)
        arr.SetValue(5, 4)
        arr.SetValue(7, 5)
        arr.SetValue(11, 6)
        arr.SetValue(13, 7)
        arr.SetValue(17, 8)
        arr.SetValue(19, 9)
        arr.SetValue(23, 10)
        Return arr
     End Function
  End Class
  ```

* <span data-ttu-id="d6622-488">모든 배열 요소는 CLS 규격 형식으로 구성되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-488">All array elements must consist of CLS-compliant types.</span></span> <span data-ttu-id="d6622-489">다음 예제에서는 CLS 비규격 배열을 반환하는 두 개의 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-489">The following example defines two methods that return non-CLS-compliant arrays.</span></span> <span data-ttu-id="d6622-490">첫 번째는 [UInt32](xref:System.UInt32) 값의 배열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-490">The first returns an array of [UInt32](xref:System.UInt32) values.</span></span> <span data-ttu-id="d6622-491">두 번째는 [Int32](xref:System.Int32) 및 `UInt32` 값이 포함된 [Object](xref:System.Object) 배열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-491">The second returns an [Object](xref:System.Object) array that includes [Int32](xref:System.Int32) and `UInt32` values.</span></span> <span data-ttu-id="d6622-492">컴파일러는 `UInt32` 형식 때문에 첫 번째 배열을 비규격으로 식별하지만 두 번째 배열이 CLS 비규격 요소를 포함하는지 인식하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-492">Although the compiler identifies the first array as non-compliant because of its `UInt32` type, it fails to recognize that the second array includes non-CLS-compliant elements.</span></span>

  ```csharp
  using System;

  [assembly: CLSCompliant(true)]

  public class Numbers
  {
    public static UInt32[] GetTenPrimes()
    {
        uint[] arr = { 1u, 2u, 3u, 5u, 7u, 11u, 13u, 17u, 19u };
        return arr;
    }

    public static Object[] GetFivePrimes()
    {
        Object[] arr = { 1, 2, 3, 5u, 7u };
        return arr;
    }
  }
  // Compilation produces a compiler warning like the following:
  //    Array2.cs(8,27): warning CS3002: Return type of 'Numbers.GetTenPrimes()' is not
  //            CLS-compliant
  ```

  ```vb
  <Assembly: CLSCompliant(True)>

  Public Class Numbers
     Public Shared Function GetTenPrimes() As UInt32()
        Return { 1ui, 2ui, 3ui, 5ui, 7ui, 11ui, 13ui, 17ui, 19ui }
     End Function
     Public Shared Function GetFivePrimes() As Object()
        Dim arr() As Object = { 1, 2, 3, 5ui, 7ui }
        Return arr
     End Function
  End Class
  ' Compilation produces a compiler warning like the following:
  '    warning BC40027: Return type of function 'GetTenPrimes' is not CLS-compliant.
  ```

* <span data-ttu-id="d6622-493">배열 매개 변수가 있는 메서드에 대한 오버로드 확인은 이들이 배열인지 여부와 해당 요소 형식을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-493">Overload resolution for methods that have array parameters is based on the fact that they are arrays and on their element type.</span></span> <span data-ttu-id="d6622-494">따라서 오버로드된 `GetSquares` 메서드의 다음 정의는 CLS 규격입니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-494">For this reason, the following definition of an overloaded `GetSquares` method is CLS-compliant.</span></span>

  ```csharp
  using System;
  using System.Numerics;

  [assembly: CLSCompliant(true)]

  public class Numbers
  {
    public static byte[] GetSquares(byte[] numbers)
    {
        byte[] numbersOut = new byte[numbers.Length];
        for (int ctr = 0; ctr < numbers.Length; ctr++) {
            int square = ((int) numbers[ctr]) * ((int) numbers[ctr]);
            if (square <= Byte.MaxValue)
                numbersOut[ctr] = (byte) square;
            // If there's an overflow, assign MaxValue to the corresponding
            // element.
            else
                numbersOut[ctr] = Byte.MaxValue;

        }
        return numbersOut;
    }

    public static BigInteger[] GetSquares(BigInteger[] numbers)
  {
        BigInteger[] numbersOut = new BigInteger[numbers.Length];
        for (int ctr = 0; ctr < numbers.Length; ctr++)
            numbersOut[ctr] = numbers[ctr] * numbers[ctr];

       return numbersOut;
    }
  }
  ```

  ```vb
  Imports System.Numerics

  <Assembly: CLSCompliant(True)>

  Public Module Numbers
     Public Function GetSquares(numbers As Byte()) As Byte()
        Dim numbersOut(numbers.Length - 1) As Byte
        For ctr As Integer = 0 To numbers.Length - 1
           Dim square As Integer = (CInt(numbers(ctr)) * CInt(numbers(ctr)))
           If square <= Byte.MaxValue Then
              numbersOut(ctr) = CByte(square)
           ' If there's an overflow, assign MaxValue to the corresponding
           ' element.
           Else
              numbersOut(ctr) = Byte.MaxValue
           End If
        Next
        Return numbersOut
     End Function

     Public Function GetSquares(numbers As BigInteger()) As BigInteger()
         Dim numbersOut(numbers.Length - 1) As BigInteger
         For ctr As Integer = 0 To numbers.Length - 1
            numbersOut(ctr) = numbers(ctr) * numbers(ctr)
         Next
         Return numbersOut
     End Function
  End Module
  ```

### <a name="interfaces"></a><span data-ttu-id="d6622-495">인터페이스</span><span class="sxs-lookup"><span data-stu-id="d6622-495">Interfaces</span></span>

<span data-ttu-id="d6622-496">CLS 규격 인터페이스는 속성, 이벤트 및 가상 메서드를 정의할 수 있습니다(구현이 없는 메서드).</span><span class="sxs-lookup"><span data-stu-id="d6622-496">CLS-compliant interfaces can define properties, events, and virtual methods (methods with no implementation).</span></span> <span data-ttu-id="d6622-497">CLS 규격 인터페이스에는 다음이 포함될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-497">A CLS-compliant interface cannot have any of the following:</span></span>

* <span data-ttu-id="d6622-498">정적 메서드 또는 정적 필드.</span><span class="sxs-lookup"><span data-stu-id="d6622-498">Static methods or static fields.</span></span> <span data-ttu-id="d6622-499">인터페이스에서 정적 멤버를 정의할 경우 C# 컴파일러에서 컴파일러 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-499">The C# compiler generates compiler errors if you define a static member in an interface.</span></span>

* <span data-ttu-id="d6622-500">필드.</span><span class="sxs-lookup"><span data-stu-id="d6622-500">Fields.</span></span> <span data-ttu-id="d6622-501">인터페이스에서 필드를 정의할 경우 C# 컴파일러에서 컴파일러 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-501">The C# a compiler generates compiler errors if you define a field in an interface.</span></span>

* <span data-ttu-id="d6622-502">CLS 규격이 아닌 메서드.</span><span class="sxs-lookup"><span data-stu-id="d6622-502">Methods that are not CLS-compliant.</span></span> <span data-ttu-id="d6622-503">예를 들어 다음 인터페이스 정의에는 CLS 비규격으로 표시된 `INumber.GetUnsigned` 메서드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-503">For example, the following interface definition includes a method, `INumber.GetUnsigned`, that is marked as non-CLS-compliant.</span></span> <span data-ttu-id="d6622-504">이 예제에서는 컴파일러 경고가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-504">This example generates a compiler warning.</span></span>

  ```csharp
  using System;

  [assembly:CLSCompliant(true)]

  public interface INumber
  {
      int Length();
      [CLSCompliant(false)] ulong GetUnsigned();
  }
  // Attempting to compile the example displays output like the following:
  //    Interface2.cs(8,32): warning CS3010: 'INumber.GetUnsigned()': CLS-compliant interfaces
  //            must have only CLS-compliant members
  ```

  ```vb
  <Assembly: CLSCompliant(True)>

  Public Interface INumber
    Function Length As Integer
      <CLSCompliant(False)> Function GetUnsigned As ULong
    End Interface
    ' Attempting to compile the example displays output like the following:
    '    Interface2.vb(9) : warning BC40033: Non CLS-compliant 'function' is not allowed in a
    '    CLS-compliant interface.
    '
    '       <CLSCompliant(False)> Function GetUnsigned As ULong
    '                                      ~~~~~~~~~~~
  ```

  <span data-ttu-id="d6622-505">이 규칙 때문에 CLS 규격이 아닌 멤버를 구현하는 데에는 CLS 규격 형식이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-505">Because of this rule, CLS-compliant types are not required to implement non-CLS-compliant members.</span></span> <span data-ttu-id="d6622-506">CLS 규격 프레임워크에서 CLS 비규격 인터페이스를 구현하는 클래스를 노출하는 경우, 모든 CLS 비규격 멤버의 구체적 구현도 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-506">If a CLS-compliant framework does expose a class that implements a non-CLS compliant interface, it should also provide concrete implementations of all non-CLS-compliant members.</span></span>

<span data-ttu-id="d6622-507">CLS 규격 언어 컴파일러를 사용하면 클래스는 다중 인터페이스에서 동일한 이름과 시그니처를 가진 멤버를 개별적으로 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-507">CLS-compliant language compilers must also allow a class to provide separate implementations of members that have the same name and signature in multiple interfaces.</span></span> <span data-ttu-id="d6622-508">C#에서는 명시적 인터페이스 구현을 지원하여 동일한 이름의 메서드를 다르게 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-508">C# supports explicit interface implementations to provide different implementations of identically named methods.</span></span> <span data-ttu-id="d6622-509">다음 예제에서는 `Temperature` 및 `ICelsius` 인터페이스를 명시적 인터페이스 구현으로 구현하는 `IFahrenheit` 클래스를 정의하여 이 시나리오를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-509">The following example illustrates this scenario by defining a `Temperature` class that implements the `ICelsius` and `IFahrenheit` interfaces as explicit interface implementations.</span></span>

```csharp
using System;

[assembly: CLSCompliant(true)]

public interface IFahrenheit
{
   decimal GetTemperature();
}

public interface ICelsius
{
   decimal GetTemperature();
}

public class Temperature : ICelsius, IFahrenheit
{
   private decimal _value;

   public Temperature(decimal value)
   {
      // We assume that this is the Celsius value.
      _value = value;
   }

   decimal IFahrenheit.GetTemperature()
   {
      return _value * 9 / 5 + 32;
   }

   decimal ICelsius.GetTemperature()
   {
      return _value;
   }
}
public class Example
{
   public static void Main()
   {
      Temperature temp = new Temperature(100.0m);
      ICelsius cTemp = temp;
      IFahrenheit fTemp = temp;
      Console.WriteLine("Temperature in Celsius: {0} degrees",
                        cTemp.GetTemperature());
      Console.WriteLine("Temperature in Fahrenheit: {0} degrees",
                        fTemp.GetTemperature());
   }
}
// The example displays the following output:
//       Temperature in Celsius: 100.0 degrees
//       Temperature in Fahrenheit: 212.0 degrees
```

```vb
Assembly: CLSCompliant(True)>

Public Interface IFahrenheit
   Function GetTemperature() As Decimal
End Interface

Public Interface ICelsius
   Function GetTemperature() As Decimal
End Interface

Public Class Temperature : Implements ICelsius, IFahrenheit
   Private _value As Decimal

   Public Sub New(value As Decimal)
      ' We assume that this is the Celsius value.
      _value = value
   End Sub

   Public Function GetFahrenheit() As Decimal _
          Implements IFahrenheit.GetTemperature
      Return _value * 9 / 5 + 32
   End Function

   Public Function GetCelsius() As Decimal _
          Implements ICelsius.GetTemperature
      Return _value
   End Function
End Class

Module Example
   Public Sub Main()
      Dim temp As New Temperature(100.0d)
      Console.WriteLine("Temperature in Celsius: {0} degrees",
                        temp.GetCelsius())
      Console.WriteLine("Temperature in Fahrenheit: {0} degrees",
                        temp.GetFahrenheit())
   End Sub
End Module
' The example displays the following output:
'       Temperature in Celsius: 100.0 degrees
'       Temperature in Fahrenheit: 212.0 degrees
```

### <a name="enumerations"></a><span data-ttu-id="d6622-510">열거형</span><span class="sxs-lookup"><span data-stu-id="d6622-510">Enumerations</span></span>

<span data-ttu-id="d6622-511">CLS 규격 열거형은 다음 규칙을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-511">CLS-compliant enumerations must follow these rules:</span></span>

* <span data-ttu-id="d6622-512">열거형의 기본 형식은 내장 CLS 규격 정수([Byte](xref:System.Byte), [Int16](xref:System.Int16), [Int32](xref:System.Int32) 또는 [Int64](xref:System.Int64))여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-512">The underlying type of the enumeration must be an intrinsic CLS-compliant integer ([Byte](xref:System.Byte), [Int16](xref:System.Int16), [Int32](xref:System.Int32), or [Int64](xref:System.Int64)).</span></span> <span data-ttu-id="d6622-513">예를 들어 다음 코드에서는 기본 형식이 [UInt32](xref:System.UInt32)이고 컴파일러 경고를 발생시키는 열거형을 정의하려 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-513">For example, the following code tries to define an enumeration whose underlying type is [UInt32](xref:System.UInt32) and generates a compiler warning.</span></span>

    ```csharp
    using System;

    [assembly: CLSCompliant(true)]

    public enum Size : uint {
        Unspecified = 0,
        XSmall = 1,
        Small = 2,
        Medium = 3,
        Large = 4,
        XLarge = 5
    };

    public class Clothing
    {
        public string Name;
        public string Type;
        public string Size;
    }
    // The attempt to compile the example displays a compiler warning like the following:
    //    Enum3.cs(6,13): warning CS3009: 'Size': base type 'uint' is not CLS-compliant
    ```

    ```vb
    <Assembly: CLSCompliant(True)>

    Public Enum Size As UInt32
       Unspecified = 0
       XSmall = 1
       Small = 2
       Medium = 3
       Large = 4
       XLarge = 5
    End Enum

    Public Class Clothing
       Public Name As String
       Public Type As String
       Public Size As Size
    End Class
    ' The attempt to compile the example displays a compiler warning like the following:
    '    Enum3.vb(6) : warning BC40032: Underlying type 'UInt32' of Enum is not CLS-compliant.
    '
    '    Public Enum Size As UInt32
    '                ~~~~
    ```

* <span data-ttu-id="d6622-514">열거형 형식에는 `Value__` 특성으로 표시되는 `FieldAttributes.RTSpecialName`라는 단일 인스턴스 필드가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-514">An enumeration type must have a single instance field named `Value__` that is marked with the `FieldAttributes.RTSpecialName` attribute.</span></span> <span data-ttu-id="d6622-515">이를 통해 필드 값을 암시적으로 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-515">This enables you to reference the field value implicitly.</span></span>

* <span data-ttu-id="d6622-516">열거형에는 형식이 해당 열거형의 형식과 일치하는 리터럴 정적 필드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-516">An enumeration includes literal static fields whose types match the type of the enumeration itself.</span></span> <span data-ttu-id="d6622-517">예를 들어 `State` 및 `State.On`의 값으로 `State.Off` 열거형을 정의하는 경우, `State.On` 및 `State.Off`는 모두 `State` 형식 리터럴 정적 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-517">For example, if you define a `State` enumeration with values of `State.On` and `State.Off`, `State.On` and `State.Off` are both literal static fields whose type is `State`.</span></span>

* <span data-ttu-id="d6622-518">열거형에는 다음 두 가지 종류가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-518">There are two kinds of enumerations:</span></span>

  * <span data-ttu-id="d6622-519">상호 배타적인 명명된 정수 값 집합을 나타내는 열거형.</span><span class="sxs-lookup"><span data-stu-id="d6622-519">An enumeration that represents a set of mutually exclusive, named integer values.</span></span> <span data-ttu-id="d6622-520">이러한 유형의 열거형은 [System.FlagsAttribute](xref:System.FlagsAttribute) 사용자 지정 특성이 없는 것으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-520">This type of enumeration is indicated by the absence of the [System.FlagsAttribute](xref:System.FlagsAttribute) custom attribute.</span></span>

  * <span data-ttu-id="d6622-521">결합하여 명명되지 않은 값을 생성할 수 있는 비트 플래그 집합을 나타내는 열거형.</span><span class="sxs-lookup"><span data-stu-id="d6622-521">An enumeration that represents a set of bit flags that can combine to generate an unnamed value.</span></span> <span data-ttu-id="d6622-522">이러한 유형의 열거형은 [System.FlagsAttribute](xref:System.FlagsAttribute) 사용자 지정 특성이 있는 것으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-522">This type of enumeration is indicated by the presence of the [System.FlagsAttribute](xref:System.FlagsAttribute) custom attribute.</span></span>

<span data-ttu-id="d6622-523">자세한 내용은 [Enum](xref:System.Enum) 구조체에 대한 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d6622-523">For more information, see the documentation for the [Enum](xref:System.Enum) structure.</span></span>

* <span data-ttu-id="d6622-524">열거형의 값은 지정된 값의 범위로 제한되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-524">The value of an enumeration is not limited to the range of its specified values.</span></span> <span data-ttu-id="d6622-525">즉, 열거형의 값 범위는 기본 값의 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-525">In other words, the range of values in an enumeration is the range of its underlying value.</span></span> <span data-ttu-id="d6622-526">`Enum.IsDefined` 메서드를 사용하여 지정된 값이 열거형 멤버인지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-526">You can use the `Enum.IsDefined` method to determine whether a specified value is a member of an enumeration.</span></span>

### <a name="type-members-in-general"></a><span data-ttu-id="d6622-527">형식 멤버 일반 사항</span><span class="sxs-lookup"><span data-stu-id="d6622-527">Type members in general</span></span>

<span data-ttu-id="d6622-528">공용 언어 사양에서는 모든 필드와 메서드가 특정 클래스의 멤버로 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-528">The Common Language Specification requires all fields and methods to be accessed as members of a particular class.</span></span> <span data-ttu-id="d6622-529">따라서 전역 정적 필드와 메서드(즉, 형식과 별도로 정의된 정적 필드 또는 메서드)는 CLS 규격이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-529">Therefore, global static fields and methods (that is, static fields or methods that are defined apart from a type) are not CLS-compliant.</span></span> <span data-ttu-id="d6622-530">소스 코드에 전역 필드 또는 메서드를 포함하려고 하면 C# 컴파일러에서 컴파일러 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-530">If you try to include a global field or method in your source code, the C# compiler generates a compiler error.</span></span>

<span data-ttu-id="d6622-531">공용 언어 사양은 관리되는 표준 호출 규칙만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-531">The Common Language Specification supports only the standard managed calling convention.</span></span> <span data-ttu-id="d6622-532">`varargs` 키워드로 표시된 가변 인수 목록을 사용하여 관리되지 않는 호출 규칙 및 메서드를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-532">It doesn't support unmanaged calling conventions and methods with variable argument lists marked with the `varargs` keyword.</span></span> <span data-ttu-id="d6622-533">관리되는 표준 호출 규칙과 호환되는 가변 인수 목록을 얻으려면 [ParamArrayAttribute](xref:System.ParamArrayAttribute) 특성 또는 C#의 `params` 키워드와 Visual Basic의 `ParamArray` 키워드와 같은 개별 언어의 구현을 이용합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-533">For variable argument lists that are compatible with the standard managed calling convention, use the [ParamArrayAttribute](xref:System.ParamArrayAttribute) attribute or the individual language's implementation, such as the `params` keyword in C# and the `ParamArray` keyword in Visual Basic.</span></span>

### <a name="member-accessibility"></a><span data-ttu-id="d6622-534">멤버 접근성</span><span class="sxs-lookup"><span data-stu-id="d6622-534">Member accessibility</span></span>

<span data-ttu-id="d6622-535">상속된 멤버를 재정의하면 해당 멤버의 액세스 가능성을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-535">Overriding an inherited member cannot change the accessibility of that member.</span></span> <span data-ttu-id="d6622-536">예를 들어 파생된 클래스의 private 메서드가 기본 클래스의 public 메서드를 재정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-536">For example, a public method in a base class cannot be overridden by a private method in a derived class.</span></span> <span data-ttu-id="d6622-537">한 가지 예외는 다른 어셈블리의 형식으로 재정의된 한 어셈블리에 있는 `protected internal`(C#의 경우) 또는 `Protected Friend`(Visual Basic의 경우) 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-537">There is one exception: a `protected internal` (in C#) or `Protected Friend` (in Visual Basic) member in one assembly that is overridden by a type in a different assembly.</span></span>  <span data-ttu-id="d6622-538">이 경우, 재정의에 대한 액세스 가능성은 `Protected`입니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-538">In that case, the accessibility of the override is `Protected`.</span></span>

<span data-ttu-id="d6622-539">다음 예제에서는 [CLSCompliantAttribute](xref:System.CLSCompliantAttribute) 특성이 `true`로 설정되고 `Animal`에서 파생된 `Person` 클래스가 `Species` 속성의 접근성을 public에서 private으로 변경하려고 할 때 생성되는 오류를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-539">The following example illustrates the error that is generated when the [CLSCompliantAttribute](xref:System.CLSCompliantAttribute) attribute is set to `true`, and `Person`, which is a class derived from `Animal`, tries to change the accessibility of the `Species` property from public to private.</span></span> <span data-ttu-id="d6622-540">이 예제는 해당 액세스 가능성이 public으로 변경되는 경우 성공적으로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-540">The example compiles successfully if its accessibility is changed to public.</span></span>

```csharp
using System;

[assembly: CLSCompliant(true)]

public class Animal
{
   private string _species;

   public Animal(string species)
   {
      _species = species;
   }

   public virtual string Species
   {
      get { return _species; }
   }

   public override string ToString()
   {
      return _species;
   }
}

public class Human : Animal
{
   private string _name;

   public Human(string name) : base("Homo Sapiens")
   {
      _name = name;
   }

   public string Name
   {
      get { return _name; }
   }

   private override string Species
   {
      get { return base.Species; }
   }

   public override string ToString()
   {
      return _name;
   }
}

public class Example
{
   public static void Main()
   {
      Human p = new Human("John");
      Console.WriteLine(p.Species);
      Console.WriteLine(p.ToString());
   }
}
// The example displays the following output:
//    error CS0621: 'Human.Species': virtual or abstract members cannot be private
```

```vb
<Assembly: CLSCompliant(True)>

Public Class Animal
   Private _species As String

   Public Sub New(species As String)
      _species = species
   End Sub

   Public Overridable ReadOnly Property Species As String
      Get
         Return _species
      End Get
   End Property

   Public Overrides Function ToString() As String
      Return _species
   End Function
End Class

Public Class Human : Inherits Animal
   Private _name As String

   Public Sub New(name As String)
      MyBase.New("Homo Sapiens")
      _name = name
   End Sub

   Public ReadOnly Property Name As String
      Get
         Return _name
      End Get
   End Property

   Private Overrides ReadOnly Property Species As String
      Get
         Return MyBase.Species
      End Get
   End Property

   Public Overrides Function ToString() As String
      Return _name
   End Function
End Class

Public Module Example
   Public Sub Main()
      Dim p As New Human("John")
      Console.WriteLine(p.Species)
      Console.WriteLine(p.ToString())
   End Sub
End Module
' The example displays the following output:
'     'Private Overrides ReadOnly Property Species As String' cannot override
'     'Public Overridable ReadOnly Property Species As String' because
'      they have different access levels.
'
'         Private Overrides ReadOnly Property Species As String
```

<span data-ttu-id="d6622-541">멤버 시그니처의 형식은 해당 멤버를 액세스할 수 있는 경우 항상 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-541">Types in the signature of a member must be accessible whenever that member is accessible.</span></span> <span data-ttu-id="d6622-542">예를 들어 public 멤버는 형식이 private, protected 또는 internal인 매개 변수를 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-542">For example, this means that a public member cannot include a parameter whose type is private, protected, or internal.</span></span> <span data-ttu-id="d6622-543">다음 예제에서는 `StringWrapper` 클래스 생성자가 문자열 값을 래핑하는 방법을 결정하는 internal `StringOperationType` 열거형 값을 노출할 때 결과로 발생하는 컴파일러 오류를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-543">The following example illustrates the compiler error that results when a `StringWrapper` class constructor exposes an internal `StringOperationType` enumeration value that determines how a string value should be wrapped.</span></span>

```csharp
using System;
using System.Text;

public class StringWrapper
{
   string internalString;
   StringBuilder internalSB = null;
   bool useSB = false;

   public StringWrapper(StringOperationType type)
   {
      if (type == StringOperationType.Normal) {
         useSB = false;
      }
      else {
         useSB = true;
         internalSB = new StringBuilder();
      }
   }

   // The remaining source code...
}

internal enum StringOperationType { Normal, Dynamic }
// The attempt to compile the example displays the following output:
//    error CS0051: Inconsistent accessibility: parameter type
//            'StringOperationType' is less accessible than method
//            'StringWrapper.StringWrapper(StringOperationType)'
```

```vb
Imports System.Text

<Assembly:CLSCompliant(True)>

Public Class StringWrapper

   Dim internalString As String
   Dim internalSB As StringBuilder = Nothing
   Dim useSB As Boolean = False

   Public Sub New(type As StringOperationType)
      If type = StringOperationType.Normal Then
         useSB = False
      Else
         internalSB = New StringBuilder()
         useSB = True
      End If
   End Sub

   ' The remaining source code...
End Class

Friend Enum StringOperationType As Integer
   Normal = 0
   Dynamic = 1
End Enum
' The attempt to compile the example displays the following output:
'    error BC30909: 'type' cannot expose type 'StringOperationType'
'     outside the project through class 'StringWrapper'.
'
'       Public Sub New(type As StringOperationType)
'                              ~~~~~~~~~~~~~~~~~~~
```

### <a name="generic-types-and-members"></a><span data-ttu-id="d6622-544">제네릭 형식 및 멤버</span><span class="sxs-lookup"><span data-stu-id="d6622-544">Generic types and members</span></span>

<span data-ttu-id="d6622-545">중첩 형식에는 적어도 바깥쪽 형식과 같은 수의 제네릭 매개 변수가 항상 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-545">Nested types always have at least as many generic parameters as their enclosing type.</span></span> <span data-ttu-id="d6622-546">이러한 값은 바깥쪽 형식의 제네릭 매개 변수와 위치가 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-546">These correspond by position to the generic parameters in the enclosing type.</span></span> <span data-ttu-id="d6622-547">제네릭 형식은 새 제네릭 매개 변수를 포함할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-547">The generic type can also include new generic parameters.</span></span>

<span data-ttu-id="d6622-548">포함 형식의 제네릭 형식 매개 변수와 중첩 형식 사이의 관계는 개별 언어의 구문에 의해 숨겨질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-548">The relationship between the generic type parameters of a containing type and its nested types may be hidden by the syntax of individual languages.</span></span> <span data-ttu-id="d6622-549">다음 예제에서 제네릭 형식 `Outer<T>`에는 두 개의 중첩된 클래스인 `Inner1A` 및 `Inner1B<U>`가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-549">In the following example, a generic type `Outer<T>` contains two nested classes, `Inner1A` and `Inner1B<U>`.</span></span> <span data-ttu-id="d6622-550">`Object.ToString`에서 각 클래스가 상속받는 `ToString` 메서드 호출은 포함하는 클래스의 형식 매개 변수가 각 중첩 클래스에 포함되는 것을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-550">The calls to the `ToString` method, which each class inherits from `Object.ToString`, show that each nested class includes the type parameters of its containing class.</span></span>

```csharp
using System;

[assembly:CLSCompliant(true)]

public class Outer<T>
{
   T value;

   public Outer(T value)
   {
      this.value = value;
   }

   public class Inner1A : Outer<T>
   {
      public Inner1A(T value) : base(value)
      {  }
   }

   public class Inner1B<U> : Outer<T>
   {
      U value2;

      public Inner1B(T value1, U value2) : base(value1)
      {
         this.value2 = value2;
      }
   }
}

public class Example
{
   public static void Main()
   {
      var inst1 = new Outer<String>("This");
      Console.WriteLine(inst1);

      var inst2 = new Outer<String>.Inner1A("Another");
      Console.WriteLine(inst2);

      var inst3 = new Outer<String>.Inner1B<int>("That", 2);
      Console.WriteLine(inst3);
   }
}
// The example displays the following output:
//       Outer`1[System.String]
//       Outer`1+Inner1A[System.String]
//       Outer`1+Inner1B`1[System.String,System.Int32]
```

```vb
<Assembly:CLSCompliant(True)>

Public Class Outer(Of T)
   Dim value As T

   Public Sub New(value As T)
      Me.value = value
   End Sub

   Public Class Inner1A : Inherits Outer(Of T)
      Public Sub New(value As T)
         MyBase.New(value)
      End Sub
   End Class

   Public Class Inner1B(Of U) : Inherits Outer(Of T)
      Dim value2 As U

      Public Sub New(value1 As T, value2 As U)
         MyBase.New(value1)
         Me.value2 = value2
      End Sub
   End Class
End Class

Public Module Example
   Public Sub Main()
      Dim inst1 As New Outer(Of String)("This")
      Console.WriteLine(inst1)

      Dim inst2 As New Outer(Of String).Inner1A("Another")
      Console.WriteLine(inst2)

      Dim inst3 As New Outer(Of String).Inner1B(Of Integer)("That", 2)
      Console.WriteLine(inst3)
   End Sub
End Module
' The example displays the following output:
'       Outer`1[System.String]
'       Outer`1+Inner1A[System.String]
'       Outer`1+Inner1B`1[System.String,System.Int32]
```

<span data-ttu-id="d6622-551">제네릭 형식 이름을 *name*'*n* 형식으로 인코드합니다. 여기서 *name* 은 형식 이름, *\`* 은 문자 리터럴, *n* 은 이 형식에서 선언된 매개 변수 개수 또는 중첩된 제네릭 형식의 경우 새로 도입된 형식 매개 변수 개수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-551">Generic type names are encoded in the form *name*'*n*, where *name* is the type name, *\`* is a character literal, and *n* is the number of parameters declared on the type, or, for nested generic types, the number of newly introduced type parameters.</span></span> <span data-ttu-id="d6622-552">제네릭 형식 이름의 이러한 인코딩은 라이브러리에서 CLS 규격 제네릭 형식에 액세스하기 위해 리플렉션을 사용하는 개발자들에게 주로 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-552">This encoding of generic type names is primarily of interest to developers who use reflection to access CLS-complaint generic types in a library.</span></span>

<span data-ttu-id="d6622-553">제약 조건이 제네릭 형식에 적용될 경우 제약 조건으로 사용되는 모든 형식도 CLS 규격이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-553">If constraints are applied to a generic type, any types used as constraints must also be CLS-compliant.</span></span> <span data-ttu-id="d6622-554">다음 예제에서는 CLS 규격 및 `BaseClass` 제네릭 클래스가 아닌 이름이 `BaseCollection`인 클래스를 정의합니다. 해당 형식 매개 변수는 `BaseClass`에서 파생되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-554">The following example defines a class named `BaseClass` that is not CLS-compliant and a generic class named `BaseCollection` whose type parameter must derive from `BaseClass`.</span></span> <span data-ttu-id="d6622-555">하지만 `BaseClass`는 CLS 규격이 아니므로 컴파일러에서 경고를 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-555">But because `BaseClass` is not CLS-compliant, the compiler emits a warning.</span></span>

```csharp
using System;

[assembly:CLSCompliant(true)]

[CLSCompliant(false)] public class BaseClass
{}

public class BaseCollection<T> where T : BaseClass
{}
// Attempting to compile the example displays the following output:
//    warning CS3024: Constraint type 'BaseClass' is not CLS-compliant
```

```vb
Assembly: CLSCompliant(True)>

<CLSCompliant(False)> Public Class BaseClass
End Class

Public Class BaseCollection(Of T As BaseClass)
End Class
' Attempting to compile the example displays the following output:
'    warning BC40040: Generic parameter constraint type 'BaseClass' is not
'    CLS-compliant.
'
'    Public Class BaseCollection(Of T As BaseClass)
'                                        ~~~~~~~~~
```

<span data-ttu-id="d6622-556">제네릭 형식이 제네릭 기본 형식에서 파생되는 경우 기본 형식에 대한 제약 조건이 충족됨을 보장할 수 있도록 모든 제약 조건을 다시 선언해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-556">If a generic type is derived from a generic base type, it must redeclare any constraints so that it can guarantee that constraints on the base type are also satisfied.</span></span> <span data-ttu-id="d6622-557">다음 예제에서는 임의의 숫자 형식을 나타낼 수 있는 `Number<T>`를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-557">The following example defines a `Number<T>` that can represent any numeric type.</span></span> <span data-ttu-id="d6622-558">또한 부동 소수점 값을 나타내는 `FloatingPoint<T>` 클래스도 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-558">It also defines a `FloatingPoint<T>` class that represents a floating point value.</span></span> <span data-ttu-id="d6622-559">하지만 이 소스 코드는 `Number<T>`(여기서 T는 값 형식이어야 함)에 대한 제약 조건을 `FloatingPoint<T>`에 적용하지 못하므로 컴파일되지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-559">However, the source code fails to compile, because it does not apply the constraint on `Number<T>` (that T must be a value type) to `FloatingPoint<T>`.</span></span>

```csharp
using System;

[assembly:CLSCompliant(true)]

public class Number<T> where T : struct
{
   // use Double as the underlying type, since its range is a superset of
   // the ranges of all numeric types except BigInteger.
   protected double number;

   public Number(T value)
   {
      try {
         this.number = Convert.ToDouble(value);
      }
      catch (OverflowException e) {
         throw new ArgumentException("value is too large.", e);
      }
      catch (InvalidCastException e) {
         throw new ArgumentException("The value parameter is not numeric.", e);
      }
   }

   public T Add(T value)
   {
      return (T) Convert.ChangeType(number + Convert.ToDouble(value), typeof(T));
   }

   public T Subtract(T value)
   {
      return (T) Convert.ChangeType(number - Convert.ToDouble(value), typeof(T));
   }
}

public class FloatingPoint<T> : Number<T>
{
   public FloatingPoint(T number) : base(number)
   {
      if (typeof(float) == number.GetType() ||
          typeof(double) == number.GetType() ||
          typeof(decimal) == number.GetType())
         this.number = Convert.ToDouble(number);
      else
         throw new ArgumentException("The number parameter is not a floating-point number.");
   }
}
// The attempt to compile the example displays the following output:
//       error CS0453: The type 'T' must be a non-nullable value type in
//               order to use it as parameter 'T' in the generic type or method 'Number<T>'
```

```vb
<Assembly:CLSCompliant(True)>

Public Class Number(Of T As Structure)
   ' Use Double as the underlying type, since its range is a superset of
   ' the ranges of all numeric types except BigInteger.
   Protected number As Double

   Public Sub New(value As T)
      Try
         Me.number = Convert.ToDouble(value)
      Catch e As OverflowException
         Throw New ArgumentException("value is too large.", e)
      Catch e As InvalidCastException
         Throw New ArgumentException("The value parameter is not numeric.", e)
      End Try
   End Sub

   Public Function Add(value As T) As T
      Return CType(Convert.ChangeType(number + Convert.ToDouble(value), GetType(T)), T)
   End Function

   Public Function Subtract(value As T) As T
      Return CType(Convert.ChangeType(number - Convert.ToDouble(value), GetType(T)), T)
   End Function
End Class

Public Class FloatingPoint(Of T) : Inherits Number(Of T)
   Public Sub New(number As T)
      MyBase.New(number)
      If TypeOf number Is Single Or
               TypeOf number Is Double Or
               TypeOf number Is Decimal Then
         Me.number = Convert.ToDouble(number)
      Else
         throw new ArgumentException("The number parameter is not a floating-point number.")
      End If
   End Sub
End Class
' The attempt to compile the example displays the following output:
'    error BC32105: Type argument 'T' does not satisfy the 'Structure'
'    constraint for type parameter 'T'.
'
'    Public Class FloatingPoint(Of T) : Inherits Number(Of T)
'                                                          ~
```

<span data-ttu-id="d6622-560">이 예제는 제약 조건이 `FloatingPoint<T>` 클래스에 추가되는 경우 성공적으로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-560">The example compiles successfully if the constraint is added to the `FloatingPoint<T>` class.</span></span>

```csharp
using System;

[assembly:CLSCompliant(true)]

public class Number<T> where T : struct
{
   // use Double as the underlying type, since its range is a superset of
   // the ranges of all numeric types except BigInteger.
   protected double number;

   public Number(T value)
   {
      try {
         this.number = Convert.ToDouble(value);
      }
      catch (OverflowException e) {
         throw new ArgumentException("value is too large.", e);
      }
      catch (InvalidCastException e) {
         throw new ArgumentException("The value parameter is not numeric.", e);
      }
   }

   public T Add(T value)
   {
      return (T) Convert.ChangeType(number + Convert.ToDouble(value), typeof(T));
   }

   public T Subtract(T value)
   {
      return (T) Convert.ChangeType(number - Convert.ToDouble(value), typeof(T));
   }
}

public class FloatingPoint<T> : Number<T> where T : struct
{
   public FloatingPoint(T number) : base(number)
   {
      if (typeof(float) == number.GetType() ||
          typeof(double) == number.GetType() ||
          typeof(decimal) == number.GetType())
         this.number = Convert.ToDouble(number);
      else
         throw new ArgumentException("The number parameter is not a floating-point number.");
   }
}
```

```vb
<Assembly:CLSCompliant(True)>

Public Class Number(Of T As Structure)
   ' Use Double as the underlying type, since its range is a superset of
   ' the ranges of all numeric types except BigInteger.
   Protected number As Double

   Public Sub New(value As T)
      Try
         Me.number = Convert.ToDouble(value)
      Catch e As OverflowException
         Throw New ArgumentException("value is too large.", e)
      Catch e As InvalidCastException
         Throw New ArgumentException("The value parameter is not numeric.", e)
      End Try
   End Sub

   Public Function Add(value As T) As T
      Return CType(Convert.ChangeType(number + Convert.ToDouble(value), GetType(T)), T)
   End Function

   Public Function Subtract(value As T) As T
      Return CType(Convert.ChangeType(number - Convert.ToDouble(value), GetType(T)), T)
   End Function
End Class

Public Class FloatingPoint(Of T As Structure) : Inherits Number(Of T)
   Public Sub New(number As T)
      MyBase.New(number)
      If TypeOf number Is Single Or
               TypeOf number Is Double Or
               TypeOf number Is Decimal Then
         Me.number = Convert.ToDouble(number)
      Else
         throw new ArgumentException("The number parameter is not a floating-point number.")
      End If
   End Sub
End Class
```

<span data-ttu-id="d6622-561">공용 언어 사양에서는 중첩된 형식 및 protected 멤버에 대해 보수적인 인스턴스화별 모델을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-561">The Common Language Specification imposes a conservative per-instantiation model for nested types and protected members.</span></span> <span data-ttu-id="d6622-562">개방형 제네릭 형식은 protected 중첩 제네릭 형식의 특정 인스턴스화를 포함하는 시그니처로 필드 또는 멤버를 노출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-562">Open generic types cannot expose fields or members with signatures that contain a specific instantiation of a nested, protected generic type.</span></span> <span data-ttu-id="d6622-563">제네릭 기본 클래스나 인터페이스의 특정 인스턴스화를 확장하는 제네릭이 아닌 형식은 protected 중첩 제네릭 형식의 다른 인스턴스화를 포함하는 서명이 있는 필드나 멤버를 노출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-563">Non-generic types that extend a specific instantiation of a generic base class or interface cannot expose fields or members with signatures that contain a different instantiation of a nested, protected generic type.</span></span>

<span data-ttu-id="d6622-564">다음 예제에서는 제네릭 형식 `C1<T>`와 protected 클래스 `C1<T>.N`을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-564">The following example defines a generic type, `C1<T>`, and a protected class, `C1<T>.N`.</span></span> <span data-ttu-id="d6622-565">`C1<T>`에는 `M1` 및 `M2`의 두 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-565">`C1<T>` has two methods, `M1` and `M2`.</span></span> <span data-ttu-id="d6622-566">하지만 `M1`은 `C1<T>`에서 `C1<int>.N` 개체를 반환하려고 하므로 CLS 규격이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-566">However, `M1` is not CLS-compliant because it tries to return a `C1<int>.N` object from `C1<T>`.</span></span> <span data-ttu-id="d6622-567">두 번째 클래스인 `C2`는 `C1<long>`에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-567">A second class, `C2`, is derived from `C1<long>`.</span></span> <span data-ttu-id="d6622-568">여기에는 `M3` 및 `M4`의 두 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-568">It has two methods, `M3` and `M4`.</span></span> <span data-ttu-id="d6622-569">`M3`는 `C1<long>`의 하위 클래스에서 `C1<int>.N` 개체를 반환하려고 하므로 CLS 규격이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-569">`M3` is not CLS-compliant because it tries to return a `C1<int>.N` object from a subclass of `C1<long>`.</span></span> <span data-ttu-id="d6622-570">언어 컴파일러는 훨씬 더 제한적일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-570">Language compilers can be even more restrictive.</span></span> <span data-ttu-id="d6622-571">이 예제에서는 Visual Basic에서 `M4`를 컴파일하려고 하면 오류를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-571">In this example, Visual Basic displays an error when it tries to compile `M4`.</span></span>

```csharp
using System;

[assembly:CLSCompliant(true)]

public class C1<T>
{
   protected class N { }

   protected void M1(C1<int>.N n) { } // Not CLS-compliant - C1<int>.N not
                                      // accessible from within C1<T> in all
                                      // languages
   protected void M2(C1<T>.N n) { }   // CLS-compliant – C1<T>.N accessible
                                      // inside C1<T>
}

public class C2 : C1<long>
{
   protected void M3(C1<int>.N n) { }  // Not CLS-compliant – C1<int>.N is not
                                       // accessible in C2 (extends C1<long>)

   protected void M4(C1<long>.N n) { } // CLS-compliant, C1<long>.N is
                                       // accessible in C2 (extends C1<long>)
}
// Attempting to compile the example displays output like the following:
//       Generics4.cs(9,22): warning CS3001: Argument type 'C1<int>.N' is not CLS-compliant
//       Generics4.cs(18,22): warning CS3001: Argument type 'C1<int>.N' is not CLS-compliant
```

```vb
<Assembly:CLSCompliant(True)>

Public Class C1(Of T)
   Protected Class N
   End Class

   Protected Sub M1(n As C1(Of Integer).N)   ' Not CLS-compliant - C1<int>.N not
                                             ' accessible from within C1(Of T) in all
   End Sub                                   ' languages

   Protected Sub M2(n As C1(Of T).N)     ' CLS-compliant – C1(Of T).N accessible
   End Sub                               ' inside C1(Of T)
End Class

Public Class C2 : Inherits C1(Of Long)
   Protected Sub M3(n As C1(Of Integer).N)   ' Not CLS-compliant – C1(Of Integer).N is not
   End Sub                                   ' accessible in C2 (extends C1(Of Long))

   Protected Sub M4(n As C1(Of Long).N)
   End Sub
End Class
' Attempting to compile the example displays output like the following:
'    error BC30508: 'n' cannot expose type 'C1(Of Integer).N' in namespace
'    '<Default>' through class 'C1'.
'
'       Protected Sub M1(n As C1(Of Integer).N)   ' Not CLS-compliant - C1<int>.N not
'                             ~~~~~~~~~~~~~~~~
'    error BC30389: 'C1(Of T).N' is not accessible in this context because
'    it is 'Protected'.
'
'       Protected Sub M3(n As C1(Of Integer).N)   ' Not CLS-compliant - C1(Of Integer).N is not
'
'                             ~~~~~~~~~~~~~~~~
'
'    error BC30389: 'C1(Of T).N' is not accessible in this context because it is 'Protected'.
'
'       Protected Sub M4(n As C1(Of Long).N)
'                             ~~~~~~~~~~~~~
```

### <a name="constructors"></a><span data-ttu-id="d6622-572">생성자</span><span class="sxs-lookup"><span data-stu-id="d6622-572">Constructors</span></span>

<span data-ttu-id="d6622-573">CLS 규격 클래스의 생성자와 구조체는 다음 규칙을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-573">Constructors in CLS-compliant classes and structures must follow these rules:</span></span>

* <span data-ttu-id="d6622-574">파생된 클래스의 생성자는 상속된 인스턴스 데이터에 액세스하기 전에 기본 클래스의 인스턴스 생성자를 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-574">A constructor of a derived class must call the instance constructor of its base class before it accesses inherited instance data.</span></span> <span data-ttu-id="d6622-575">이 요구 사항은 파생된 클래스에서 기본 클래스 생성자가 상속되지 않기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-575">This requirement is due to the fact that base class constructors are not inherited by their derived classes.</span></span> <span data-ttu-id="d6622-576">이 규칙은 직접 상속을 지원하지 않는 구조체에는 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-576">This rule does not apply to structures, which do not support direct inheritance.</span></span>

  <span data-ttu-id="d6622-577">일반적으로 컴파일러는 다음 예제에서처럼 CLS 규격 여부와는 독립적으로 이 규칙을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-577">Typically, compilers enforce this rule independently of CLS compliance, as the following example shows.</span></span> <span data-ttu-id="d6622-578">이 예제에서는 `Doctor` 클래스에서 파생되는 `Person` 클래스를 만들지만 `Doctor` 클래스는 `Person` 클래스 생성자를 호출하여 상속된 인스턴스 필드를 초기화하는 데 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-578">It creates a `Doctor` class that is derived from a `Person` class, but the `Doctor` class fails to call the `Person` class constructor to initialize inherited instance fields.</span></span>

    ```csharp
    using System;

    [assembly: CLSCompliant(true)]

    public class Person
    {
    private string fName, lName, _id;

    public Person(string firstName, string lastName, string id)
    {
        if (String.IsNullOrEmpty(firstName + lastName))
            throw new ArgumentNullException("Either a first name or a last name must be provided.");

        fName = firstName;
        lName = lastName;
        _id = id;
    }

    public string FirstName
    {
        get { return fName; }
    }

    public string LastName
    {
        get { return lName; }
    }

    public string Id
    {
        get { return _id; }
    }

    public override string ToString()
    {
        return String.Format("{0}{1}{2}", fName,
                            String.IsNullOrEmpty(fName) ?  "" : " ",
                            lName);
    }
    }

    public class Doctor : Person
    {
    public Doctor(string firstName, string lastName, string id)
    {
    }

    public override string ToString()
    {
        return "Dr. " + base.ToString();
    }
    }
    // Attempting to compile the example displays output like the following:
    //    ctor1.cs(45,11): error CS1729: 'Person' does not contain a constructor that takes 0
    //            arguments
    //    ctor1.cs(10,11): (Location of symbol related to previous error)
    ```

    ```vb
    <Assembly: CLSCompliant(True)>

    Public Class Person
       Private fName, lName, _id As String

       Public Sub New(firstName As String, lastName As String, id As String)
          If String.IsNullOrEmpty(firstName + lastName) Then
             Throw New ArgumentNullException("Either a first name or a last name must be provided.")
          End If

          fName = firstName
          lName = lastName
          _id = id
       End Sub

       Public ReadOnly Property FirstName As String
          Get
             Return fName
          End Get
       End Property

       Public ReadOnly Property LastName As String
          Get
             Return lName
          End Get
       End Property

       Public ReadOnly Property Id As String
          Get
             Return _id
          End Get
       End Property

       Public Overrides Function ToString() As String
          Return String.Format("{0}{1}{2}", fName,
                               If(String.IsNullOrEmpty(fName), "", " "),
                               lName)
       End Function
    End Class

    Public Class Doctor : Inherits Person
       Public Sub New(firstName As String, lastName As String, id As String)
       End Sub

       Public Overrides Function ToString() As String
          Return "Dr. " + MyBase.ToString()
       End Function
    End Class
    ' Attempting to compile the example displays output like the following:
    '    Ctor1.vb(46) : error BC30148: First statement of this 'Sub New' must be a call
    '    to 'MyBase.New' or 'MyClass.New' because base class 'Person' of 'Doctor' does
    '    not have an accessible 'Sub New' that can be called with no arguments.
    '
    '       Public Sub New()
    '                  ~~~
    ````

* <span data-ttu-id="d6622-579">개체 생성자는 개체를 만드는 경우를 제외하고는 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-579">An object constructor cannot be called except to create an object.</span></span> <span data-ttu-id="d6622-580">또한 개체는 두 번 초기화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-580">In addition, an object cannot be initialized twice.</span></span> <span data-ttu-id="d6622-581">예를 들어 `Object.MemberwiseClone`은 생성자를 호출해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-581">For example, this means that `Object.MemberwiseClone` must not call constructors.</span></span>

### <a name="properties"></a><span data-ttu-id="d6622-582">속성</span><span class="sxs-lookup"><span data-stu-id="d6622-582">Properties</span></span>

<span data-ttu-id="d6622-583">CLS 규격 형식의 속성은 다음 규칙을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-583">Properties in CLS-compliant types must follow these rules:</span></span>

* <span data-ttu-id="d6622-584">속성에는 setter, getter 또는 둘 모두가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-584">A property must have a setter, a getter, or both.</span></span> <span data-ttu-id="d6622-585">어셈블리에서 이러한 메서드는 특수한 메서드로 구현됩니다. 즉, 어셈블리의 메타데이터에 `SpecialName`으로 표시되는 별도 메서드(getter의 이름은 `get`\_*propertyname* 이고, setter의 이름은 `set`\_*propertyname* 임)로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-585">In an assembly, these are implemented as special methods, which means that they will appear as separate methods (the getter is named `get`\_*propertyname* and the setter is `set`\_*propertyname*) marked as `SpecialName` in the assembly's metadata.</span></span> <span data-ttu-id="d6622-586">C# 컴파일러에서는 <xref:System.CLSCompliantAttribute> 특성을 적용할 필요 없이 자동으로 이 규칙을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-586">The C# compiler enforces this rule automatically without the need to apply the <xref:System.CLSCompliantAttribute> attribute.</span></span>

* <span data-ttu-id="d6622-587">속성의 형식은 속성 getter의 반환 형식이며 setter의 마지막 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-587">A property's type is the return type of the property getter and the last argument of the setter.</span></span> <span data-ttu-id="d6622-588">이러한 형식은 CLS 규격이어야 하며 인수는 참조로 속성에 할당할 수 없습니다. 즉, 관리되는 포인터일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-588">These types must be CLS compliant, and arguments cannot be assigned to the property by reference (that is, they cannot be managed pointers).</span></span>

* <span data-ttu-id="d6622-589">속성에 getter와 setter가 모두 있는 경우, 둘 다 virtual이거나 static이거나 instance여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-589">If a property has both a getter and a setter, they must both be virtual, both static, or both instance.</span></span> <span data-ttu-id="d6622-590">C# 컴파일러에서는 속성 정의 구문을 통해 이 규칙을 자동으로 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-590">The C# compiler automatically enforces this rule through property definition syntax.</span></span>

### <a name="events"></a><span data-ttu-id="d6622-591">이벤트</span><span class="sxs-lookup"><span data-stu-id="d6622-591">Events</span></span>

<span data-ttu-id="d6622-592">이벤트는 이름 및 해당 형식으로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-592">An event is defined by its name and its type.</span></span> <span data-ttu-id="d6622-593">이벤트 유형은 이벤트를 나타내는 데 사용되는 대리자입니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-593">The event type is a delegate that is used to indicate the event.</span></span> <span data-ttu-id="d6622-594">예를 들어 `DbConnection.StateChange` 이벤트는 `StateChangeEventHandler` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-594">For example, the `DbConnection.StateChange` event is of type `StateChangeEventHandler`.</span></span> <span data-ttu-id="d6622-595">해당 이벤트에 추가로 이 이벤트 이름을 기반으로 한 이름의 다음 세 가지 메서드가 이벤트를 구현하고 어셈블리의 메타데이터에 `SpecialName`으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-595">In addition to the event itself, three methods with names based on the event name provide the event's implementation and are marked as `SpecialName` in the assembly's metadata:</span></span>

* <span data-ttu-id="d6622-596">이벤트 처리기를 추가하는 `add`_ *EventName* 메서드.</span><span class="sxs-lookup"><span data-stu-id="d6622-596">A method for adding an event handler, named `add`_ *EventName*.</span></span> <span data-ttu-id="d6622-597">예를 들어 `DbConnection.StateChange` 이벤트의 이벤트 구독 메서드 이름은 `add_StateChange`입니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-597">For example, the event subscription method for the `DbConnection.StateChange` event is named `add_StateChange`.</span></span>

* <span data-ttu-id="d6622-598">이벤트 처리기를 제거하는 `remove`_ *EventName* 메서드.</span><span class="sxs-lookup"><span data-stu-id="d6622-598">A method for removing an event handler, named `remove`_ *EventName*.</span></span> <span data-ttu-id="d6622-599">예를 들어 `DbConnection.StateChange` 이벤트의 제거 메서드 이름은 `remove_StateChange`입니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-599">For example, the removal method for the `DbConnection.StateChange` event is named `remove_StateChange`.</span></span>

* <span data-ttu-id="d6622-600">이벤트가 발생했음을 나타내는 `raise`\_*EventName* 메서드.</span><span class="sxs-lookup"><span data-stu-id="d6622-600">A method for indicating that the event has occurred, named `raise`\_*EventName*.</span></span>

> [!NOTE]
> <span data-ttu-id="d6622-601">이벤트에 관련된 대부분의 공용 언어 사양 규칙은 언어 컴파일러에서 구현되며 구성 요소 개발자에게 투명하게 공개됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-601">Most of the Common Language Specification's rules regarding events are implemented by language compilers and are transparent to component developers.</span></span>

<span data-ttu-id="d6622-602">이벤트를 추가, 제거 또는 발생시키는 메서드의 액세스 가능성은 모두 동일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-602">The methods for adding, removing, and raising the event must have the same accessibility.</span></span> <span data-ttu-id="d6622-603">또한 모두 동일하게 static, instance 또는 virtual이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-603">They must also all be static, instance, or virtual.</span></span> <span data-ttu-id="d6622-604">이벤트를 추가하고 제거하는 메서드에는 이벤트 대리자 형식의 매개 변수가 하나 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-604">The methods for adding and removing an event have one parameter whose type is the event delegate type.</span></span> <span data-ttu-id="d6622-605">추가 메서드와 제거 메서드는 모두 있거나 모두 없어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-605">The add and remove methods must both be present or both be absent.</span></span>

<span data-ttu-id="d6622-606">다음 예제에서는 두 계측값 사이의 온도 변화가 임계값과 같거나 이를 넘어설 때 `Temperature` 이벤트를 발생시키는 CLS 규격 클래스 `TemperatureChanged`를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-606">The following example defines a CLS-compliant class named `Temperature` that raises a `TemperatureChanged` event if the change in temperature between two readings equals or exceeds a threshold value.</span></span> <span data-ttu-id="d6622-607">`Temperature` 클래스는 이벤트 처리기를 선택적으로 실행할 수 있도록 `raise_TemperatureChanged` 메서드를 명시적으로 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-607">The `Temperature` class explicitly defines a `raise_TemperatureChanged` method so that it can selectively execute event handlers.</span></span>

```csharp
using System;
using System.Collections;
using System.Collections.Generic;

[assembly: CLSCompliant(true)]

public class TemperatureChangedEventArgs : EventArgs
{
   private Decimal originalTemp;
   private Decimal newTemp;
   private DateTimeOffset when;

   public TemperatureChangedEventArgs(Decimal original, Decimal @new, DateTimeOffset time)
   {
      originalTemp = original;
      newTemp = @new;
      when = time;
   }

   public Decimal OldTemperature
   {
      get { return originalTemp; }
   }

   public Decimal CurrentTemperature
   {
      get { return newTemp; }
   }

   public DateTimeOffset Time
   {
      get { return when; }
   }
}

public delegate void TemperatureChanged(Object sender, TemperatureChangedEventArgs e);

public class Temperature
{
   private struct TemperatureInfo
   {
      public Decimal Temperature;
      public DateTimeOffset Recorded;
   }

   public event TemperatureChanged TemperatureChanged;

   private Decimal previous;
   private Decimal current;
   private Decimal tolerance;
   private List<TemperatureInfo> tis = new List<TemperatureInfo>();

   public Temperature(Decimal temperature, Decimal tolerance)
   {
      current = temperature;
      TemperatureInfo ti = new TemperatureInfo();
      ti.Temperature = temperature;
      tis.Add(ti);
      ti.Recorded = DateTimeOffset.UtcNow;
      this.tolerance = tolerance;
   }

   public Decimal CurrentTemperature
   {
      get { return current; }
      set {
         TemperatureInfo ti = new TemperatureInfo();
         ti.Temperature = value;
         ti.Recorded = DateTimeOffset.UtcNow;
         previous = current;
         current = value;
         if (Math.Abs(current - previous) >= tolerance)
            raise_TemperatureChanged(new TemperatureChangedEventArgs(previous, current, ti.Recorded));
      }
   }

   public void raise_TemperatureChanged(TemperatureChangedEventArgs eventArgs)
   {
      if (TemperatureChanged == null)
         return;

      foreach (TemperatureChanged d in TemperatureChanged.GetInvocationList()) {
         if (d.Method.Name.Contains("Duplicate"))
            Console.WriteLine("Duplicate event handler; event handler not executed.");
         else
            d.Invoke(this, eventArgs);
      }
   }
}

public class Example
{
   public Temperature temp;

   public static void Main()
   {
      Example ex = new Example();
   }

   public Example()
   {
      temp = new Temperature(65, 3);
      temp.TemperatureChanged += this.TemperatureNotification;
      RecordTemperatures();
      Example ex = new Example(temp);
      ex.RecordTemperatures();
   }

   public Example(Temperature t)
   {
      temp = t;
      RecordTemperatures();
   }

   public void RecordTemperatures()
   {
      temp.TemperatureChanged += this.DuplicateTemperatureNotification;
      temp.CurrentTemperature = 66;
      temp.CurrentTemperature = 63;
   }

   internal void TemperatureNotification(Object sender, TemperatureChangedEventArgs e)
   {
      Console.WriteLine("Notification 1: The temperature changed from {0} to {1}", e.OldTemperature, e.CurrentTemperature);
   }

   public void DuplicateTemperatureNotification(Object sender, TemperatureChangedEventArgs e)
   {
      Console.WriteLine("Notification 2: The temperature changed from {0} to {1}", e.OldTemperature, e.CurrentTemperature);
   }
}
```

```vb
Imports System.Collections
Imports System.Collections.Generic

<Assembly: CLSCompliant(True)>

Public Class TemperatureChangedEventArgs   : Inherits EventArgs
   Private originalTemp As Decimal
   Private newTemp As Decimal
   Private [when] As DateTimeOffset

   Public Sub New(original As Decimal, [new] As Decimal, [time] As DateTimeOffset)
      originalTemp = original
      newTemp = [new]
      [when] = [time]
   End Sub

   Public ReadOnly Property OldTemperature As Decimal
      Get
         Return originalTemp
      End Get
   End Property

   Public ReadOnly Property CurrentTemperature As Decimal
      Get
         Return newTemp
      End Get
   End Property

   Public ReadOnly Property [Time] As DateTimeOffset
      Get
         Return [when]
      End Get
   End Property
End Class

Public Delegate Sub TemperatureChanged(sender As Object, e As TemperatureChangedEventArgs)

Public Class Temperature
   Private Structure TemperatureInfo
      Dim Temperature As Decimal
      Dim Recorded As DateTimeOffset
   End Structure

   Public Event TemperatureChanged As TemperatureChanged

   Private previous As Decimal
   Private current As Decimal
   Private tolerance As Decimal
   Private tis As New List(Of TemperatureInfo)

   Public Sub New(temperature As Decimal, tolerance As Decimal)
      current = temperature
      Dim ti As New TemperatureInfo()
      ti.Temperature = temperature
      ti.Recorded = DateTimeOffset.UtcNow
      tis.Add(ti)
      Me.tolerance = tolerance
   End Sub

   Public Property CurrentTemperature As Decimal
      Get
         Return current
      End Get
      Set
         Dim ti As New TemperatureInfo
         ti.Temperature = value
         ti.Recorded = DateTimeOffset.UtcNow
         previous = current
         current = value
         If Math.Abs(current - previous) >= tolerance Then
            raise_TemperatureChanged(New TemperatureChangedEventArgs(previous, current, ti.Recorded))
         End If
      End Set
   End Property

   Public Sub raise_TemperatureChanged(eventArgs As TemperatureChangedEventArgs)
      If TemperatureChangedEvent Is Nothing Then Exit Sub

      Dim ListenerList() As System.Delegate = TemperatureChangedEvent.GetInvocationList()
      For Each d As TemperatureChanged In TemperatureChangedEvent.GetInvocationList()
         If d.Method.Name.Contains("Duplicate") Then
            Console.WriteLine("Duplicate event handler; event handler not executed.")
         Else
            d.Invoke(Me, eventArgs)
         End If
      Next
   End Sub
End Class

Public Class Example
   Public WithEvents temp As Temperature

   Public Shared Sub Main()
      Dim ex As New Example()
   End Sub

   Public Sub New()
      temp = New Temperature(65, 3)
      RecordTemperatures()
      Dim ex As New Example(temp)
      ex.RecordTemperatures()
   End Sub

   Public Sub New(t As Temperature)
      temp = t
      RecordTemperatures()
   End Sub

   Public Sub RecordTemperatures()
      temp.CurrentTemperature = 66
      temp.CurrentTemperature = 63

   End Sub

   Friend Shared Sub TemperatureNotification(sender As Object, e As TemperatureChangedEventArgs) _
          Handles temp.TemperatureChanged
      Console.WriteLine("Notification 1: The temperature changed from {0} to {1}", e.OldTemperature, e.CurrentTemperature)
   End Sub

   Friend Shared Sub DuplicateTemperatureNotification(sender As Object, e As TemperatureChangedEventArgs) _
          Handles temp.TemperatureChanged
      Console.WriteLine("Notification 2: The temperature changed from {0} to {1}", e.OldTemperature, e.CurrentTemperature)
   End Sub
End Class
```

### <a name="overloads"></a><span data-ttu-id="d6622-608">Overloads</span><span class="sxs-lookup"><span data-stu-id="d6622-608">Overloads</span></span>

<span data-ttu-id="d6622-609">공용 언어 사양에서는 오버로드된 멤버에 대해 다음과 같은 요구 사항을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-609">The Common Language Specification imposes the following requirements on overloaded members:</span></span>

* <span data-ttu-id="d6622-610">매개 변수 개수와 매개 변수 형식에 따라 멤버를 오버로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-610">Members can be overloaded based on the number of parameters and the type of any parameter.</span></span> <span data-ttu-id="d6622-611">호출 규칙, 반환 형식, 사용자 지정 한정자는 메서드 또는 해당 매개 변수에 적용되며, 오버로드 간에 구별하는 경우 매개 변수가 값으로 전달되는지 또는 참조로 전달되는지 여부는 고려되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-611">Calling convention, return type, custom modifiers applied to the method or its parameter, and whether parameters are passed by value or by reference are not considered when differentiating between overloads.</span></span> <span data-ttu-id="d6622-612">예를 들어 이름이 [명명 규칙](#naming-conventions) 섹션의 적용 범위 내에서 고유해야 한다는 요구 사항에 대한 코드를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d6622-612">For an example, see the code for the requirement that names must be unique within a scope in the [Naming conventions](#naming-conventions) section.</span></span>

* <span data-ttu-id="d6622-613">속성 및 메서드만 오버로드될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-613">Only properties and methods can be overloaded.</span></span> <span data-ttu-id="d6622-614">필드 및 이벤트는 오버로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-614">Fields and events cannot be overloaded.</span></span>

* <span data-ttu-id="d6622-615">제네릭 메서드는 제네릭 매개 변수의 개수에 따라 오버로드될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-615">Generic methods can be overloaded based on the number of their generic parameters.</span></span>

> [!NOTE]
> <span data-ttu-id="d6622-616">`op_Explicit` 연산자와 `op_Implicit` 연산자는 반환 값은 오버로드 확인을 위한 메서드 시그니처의 일부로 고려되지 않는다는 규칙의 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-616">The `op_Explicit` and `op_Implicit` operators are exceptions to the rule that return value is not considered part of a method signature for overload resolution.</span></span> <span data-ttu-id="d6622-617">이러한 두 연산자는 매개 변수 및 해당 반환 값에 따라 오버로드될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-617">These two operators can be overloaded based on both their parameters and their return value.</span></span>

### <a name="exceptions"></a><span data-ttu-id="d6622-618">예외</span><span class="sxs-lookup"><span data-stu-id="d6622-618">Exceptions</span></span>

<span data-ttu-id="d6622-619">예외 개체는 [System.Exception](xref:System.Exception)에서 파생되거나 `System.Exception`에서 파생된 또 다른 형식에서 파생되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-619">Exception objects must derive from [System.Exception](xref:System.Exception) or from another type derived from `System.Exception`.</span></span> <span data-ttu-id="d6622-620">다음 예제에서는 사용자 지정 클래스 `ErrorClass`가 예외 처리에 사용될 때 결과로 발생하는 컴파일러 오류를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-620">The following example illustrates the compiler error that results when a custom class named `ErrorClass` is used for exception handling.</span></span>

```csharp
using System;

[assembly: CLSCompliant(true)]

public class ErrorClass
{
   string msg;

   public ErrorClass(string errorMessage)
   {
      msg = errorMessage;
   }

   public string Message
   {
      get { return msg; }
   }
}

public static class StringUtilities
{
   public static string[] SplitString(this string value, int index)
   {
      if (index < 0 | index > value.Length) {
         ErrorClass badIndex = new ErrorClass("The index is not within the string.");
         throw badIndex;
      }
      string[] retVal = { value.Substring(0, index - 1),
                          value.Substring(index) };
      return retVal;
   }
}
// Compilation produces a compiler error like the following:
//    Exceptions1.cs(26,16): error CS0155: The type caught or thrown must be derived from
//            System.Exception
```

```vb
Imports System.Runtime.CompilerServices

<Assembly: CLSCompliant(True)>

Public Class ErrorClass
   Dim msg As String

   Public Sub New(errorMessage As String)
      msg = errorMessage
   End Sub

   Public ReadOnly Property Message As String
      Get
         Return msg
      End Get
   End Property
End Class

Public Module StringUtilities
   <Extension()> Public Function SplitString(value As String, index As Integer) As String()
      If index < 0 Or index > value.Length Then
         Dim BadIndex As New ErrorClass("The index is not within the string.")
         Throw BadIndex
      End If
      Dim retVal() As String = { value.Substring(0, index - 1),
                                 value.Substring(index) }
      Return retVal
   End Function
End Module
' Compilation produces a compiler error like the following:
'    Exceptions1.vb(27) : error BC30665: 'Throw' operand must derive from 'System.Exception'.
'
'             Throw BadIndex
'             ~~~~~~~~~~~~~~
```

<span data-ttu-id="d6622-621">이 오류를 수정하려면 `ErrorClass` 클래스는 `System.Exception`에서 상속해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-621">To correct this error, the `ErrorClass` class must inherit from `System.Exception`.</span></span> <span data-ttu-id="d6622-622">또한 Message 속성을 재정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-622">In addition, the Message property must be overridden.</span></span> <span data-ttu-id="d6622-623">다음 예제에서는 이러한 오류를 해결하여 CLS 규격 `ErrorClass` 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-623">The following example corrects these errors to define an `ErrorClass` class that is CLS-compliant.</span></span>

```csharp
using System;

[assembly: CLSCompliant(true)]

public class ErrorClass : Exception
{
   string msg;

   public ErrorClass(string errorMessage)
   {
      msg = errorMessage;
   }

   public override string Message
   {
      get { return msg; }
   }
}

public static class StringUtilities
{
   public static string[] SplitString(this string value, int index)
   {
      if (index < 0 | index > value.Length) {
         ErrorClass badIndex = new ErrorClass("The index is not within the string.");
         throw badIndex;
      }
      string[] retVal = { value.Substring(0, index - 1),
                          value.Substring(index) };
      return retVal;
   }
}
```

```vb
Imports System.Runtime.CompilerServices

<Assembly: CLSCompliant(True)>

Public Class ErrorClass : Inherits Exception
   Dim msg As String

   Public Sub New(errorMessage As String)
      msg = errorMessage
   End Sub

   Public Overrides ReadOnly Property Message As String
      Get
         Return msg
      End Get
   End Property
End Class

Public Module StringUtilities
   <Extension()> Public Function SplitString(value As String, index As Integer) As String()
      If index < 0 Or index > value.Length Then
         Dim BadIndex As New ErrorClass("The index is not within the string.")
         Throw BadIndex
      End If
      Dim retVal() As String = { value.Substring(0, index - 1),
                                 value.Substring(index) }
      Return retVal
   End Function
End Module
```

### <a name="attributes"></a><span data-ttu-id="d6622-624">특성</span><span class="sxs-lookup"><span data-stu-id="d6622-624">Attributes</span></span>

<span data-ttu-id="d6622-625">.NET 어셈블리에서 사용자 지정 특성은 확장 가능한 메커니즘을 제공하여 사용자 지정 특성을 저장하고 어셈블리, 형식, 멤버, 메서드 매개 변수 등의 개체 프로그래밍에 대한 메타데이터를 검색할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-625">In .NET assemblies, custom attributes provide an extensible mechanism for storing custom attributes and retrieving metadata about programming objects, such as assemblies, types, members, and method parameters.</span></span> <span data-ttu-id="d6622-626">사용자 지정 특성은 [System.Attribute](xref:System.Attribute)에서 파생되거나 `System.Attribute`에서 파생된 형식에서 파생되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-626">Custom attributes must derive from [System.Attribute](xref:System.Attribute) or from a type derived from `System.Attribute`.</span></span>

<span data-ttu-id="d6622-627">다음은 이 규칙을 위반하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-627">The following example violates this rule.</span></span> <span data-ttu-id="d6622-628">이 예제에서는 `NumericAttribute`에서 파생되지 않은 `System.Attribute` 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-628">It defines a `NumericAttribute` class that does not derive from `System.Attribute`.</span></span> <span data-ttu-id="d6622-629">컴파일러 오류는 클래스를 정의하지 않은 경우가 아닌 CLS 규격이 아닌 특성이 적용되는 경우에만 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-629">A compiler error results only when the non-CLS-compliant attribute is applied, not when the class is defined.</span></span>

```csharp
using System;

[assembly: CLSCompliant(true)]

[AttributeUsageAttribute(AttributeTargets.Class | AttributeTargets.Struct)]
public class NumericAttribute
{
   private bool _isNumeric;

   public NumericAttribute(bool isNumeric)
   {
      _isNumeric = isNumeric;
   }

   public bool IsNumeric
   {
      get { return _isNumeric; }
   }
}

[Numeric(true)] public struct UDouble
{
   double Value;
}
// Compilation produces a compiler error like the following:
//    Attribute1.cs(22,2): error CS0616: 'NumericAttribute' is not an attribute class
//    Attribute1.cs(7,14): (Location of symbol related to previous error)
```

```vb
<Assembly: CLSCompliant(True)>

<AttributeUsageAttribute(AttributeTargets.Class Or AttributeTargets.Struct)> _
Public Class NumericAttribute
   Private _isNumeric As Boolean

   Public Sub New(isNumeric As Boolean)
      _isNumeric = isNumeric
   End Sub

   Public ReadOnly Property IsNumeric As Boolean
      Get
         Return _isNumeric
      End Get
   End Property
End Class

<Numeric(True)> Public Structure UDouble
   Dim Value As Double
End Structure
' Compilation produces a compiler error like the following:
'    error BC31504: 'NumericAttribute' cannot be used as an attribute because it
'    does not inherit from 'System.Attribute'.
'
'    <Numeric(True)> Public Structure UDouble
'     ~~~~~~~~~~~~~
```

<span data-ttu-id="d6622-630">CLS 규격 특성의 속성 또는 생성자는 다음과 같은 형식만 노출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-630">The constructor or the properties of a CLS-compliant attribute can expose only the following types:</span></span>

* [<span data-ttu-id="d6622-631">Boolean</span><span class="sxs-lookup"><span data-stu-id="d6622-631">Boolean</span></span>](xref:System.Boolean)

* [<span data-ttu-id="d6622-632">Byte</span><span class="sxs-lookup"><span data-stu-id="d6622-632">Byte</span></span>](xref:System.Byte)

* [<span data-ttu-id="d6622-633">Char</span><span class="sxs-lookup"><span data-stu-id="d6622-633">Char</span></span>](xref:System.Char)

* [<span data-ttu-id="d6622-634">double</span><span class="sxs-lookup"><span data-stu-id="d6622-634">Double</span></span>](xref:System.Double)

* [<span data-ttu-id="d6622-635">Int16</span><span class="sxs-lookup"><span data-stu-id="d6622-635">Int16</span></span>](xref:System.Int16)

* [<span data-ttu-id="d6622-636">Int32</span><span class="sxs-lookup"><span data-stu-id="d6622-636">Int32</span></span>](xref:System.Int32)

* [<span data-ttu-id="d6622-637">Int64</span><span class="sxs-lookup"><span data-stu-id="d6622-637">Int64</span></span>](xref:System.Int64)

* [<span data-ttu-id="d6622-638">Single</span><span class="sxs-lookup"><span data-stu-id="d6622-638">Single</span></span>](xref:System.Single)

* [<span data-ttu-id="d6622-639">String</span><span class="sxs-lookup"><span data-stu-id="d6622-639">String</span></span>](xref:System.String)

* [<span data-ttu-id="d6622-640">Type</span><span class="sxs-lookup"><span data-stu-id="d6622-640">Type</span></span>](xref:System.Type)

* <span data-ttu-id="d6622-641">기본 형식이 `Byte`, `Int16`, `Int32` 또는 `Int64`인 열거형 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-641">Any enumeration type whose underlying type is `Byte`, `Int16`, `Int32`, or `Int64`.</span></span>

<span data-ttu-id="d6622-642">다음 예제에서는 [Attribute](xref:System.Attribute)에서 파생된 `DescriptionAttribute` 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-642">The following example defines a `DescriptionAttribute` class that derives from [Attribute](xref:System.Attribute).</span></span> <span data-ttu-id="d6622-643">클래스 생성자에 `Descriptor` 형식의 매개 변수가 있으므로 이 클래스는 CLS 규격이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-643">The class constructor has a parameter of type `Descriptor`, so the class is not CLS-compliant.</span></span> <span data-ttu-id="d6622-644">C# 컴파일러에서 경고를 표시하지만 성공적으로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-644">The C# compiler emits a warning but compiles successfully.</span></span>

```csharp
using System;

[assembly:CLSCompliantAttribute(true)]

public enum DescriptorType { type, member };

public class Descriptor
{
   public DescriptorType Type;
   public String Description;
}

[AttributeUsage(AttributeTargets.All)]
public class DescriptionAttribute : Attribute
{
   private Descriptor desc;

   public DescriptionAttribute(Descriptor d)
   {
      desc = d;
   }

   public Descriptor Descriptor
   { get { return desc; } }
}
// Attempting to compile the example displays output like the following:
//       warning CS3015: 'DescriptionAttribute' has no accessible
//               constructors which use only CLS-compliant types
```

```vb
<Assembly:CLSCompliantAttribute(True)>

Public Enum DescriptorType As Integer
   Type = 0
   Member = 1
End Enum

Public Class Descriptor
   Public Type As DescriptorType
   Public Description As String
End Class

<AttributeUsage(AttributeTargets.All)> _
Public Class DescriptionAttribute : Inherits Attribute
   Private desc As Descriptor

   Public Sub New(d As Descriptor)
      desc = d
   End Sub

   Public ReadOnly Property Descriptor As Descriptor
      Get
         Return desc
      End Get
   End Property
End Class
```

## <a name="the-clscompliantattribute-attribute"></a><span data-ttu-id="d6622-645">CLSCompliantAttribute 특성</span><span class="sxs-lookup"><span data-stu-id="d6622-645">The CLSCompliantAttribute attribute</span></span>

<span data-ttu-id="d6622-646">[CLSCompliantAttribute](xref:System.CLSCompliantAttribute) 특성은 프로그램 요소가 공용 언어 사양을 준수하는지 여부를 나타내는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-646">The [CLSCompliantAttribute](xref:System.CLSCompliantAttribute) attribute is used to indicate whether a program element complies with the Common Language Specification.</span></span> <span data-ttu-id="d6622-647">`CLSCompliantAttribute.CLSCompliantAttribute(Boolean)` 생성자에는 프로그램 요소가 CLS 규격인지 여부를 나타내는 단일 필수 매개 변수 *isCompliant* 가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-647">The `CLSCompliantAttribute.CLSCompliantAttribute(Boolean)` constructor includes a single required parameter, *isCompliant*, that indicates whether the program element is CLS-compliant.</span></span>

<span data-ttu-id="d6622-648">컴파일 타임에 컴파일러는 CLS 규격으로 우선 간주되었던 비규격 요소를 검색하고 경고를 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-648">At compile time, the compiler detects non-compliant elements that are presumed to be CLS-compliant and emits a warning.</span></span> <span data-ttu-id="d6622-649">컴파일러는 비규격으로 명시적 선언된 형식 또는 멤버에 대해서는 경고를 발생시키지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-649">The compiler does not emit warnings for types or members that are explicitly declared to be non-compliant.</span></span>

<span data-ttu-id="d6622-650">구성 요소 개발자는 다음 두 가지 방식으로 `CLSCompliantAttribute` 특성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-650">Component developers can use the `CLSCompliantAttribute` attribute in two ways:</span></span>

* <span data-ttu-id="d6622-651">CLS 규격인 구성 요소에서 노출된 공용 인터페이스 부분과 CLS 규격이 아닌 부분을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-651">To define the parts of the public interface exposed by a component that are CLS-compliant and the parts that are not CLS-compliant.</span></span> <span data-ttu-id="d6622-652">특정 프로그램 요소를 CLS 규격으로 표시하도록 특성을 사용하면, 해당 요소는 .NET을 대상으로 하는 모든 언어 및 도구에서 액세스 가능성이 보장됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-652">When the attribute is used to mark particular program elements as CLS-compliant, its use guarantees that those elements are accessible from all languages and tools that target .NET.</span></span>

* <span data-ttu-id="d6622-653">구성 요소 라이브러리의 공용 인터페이스에서 CLS 규격인 프로그램 요소만을 노출시키도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-653">To ensure that the component library's public interface exposes only program elements that are CLS-compliant.</span></span> <span data-ttu-id="d6622-654">요소가 CLS 규격이 아닌 경우, 일반적으로 컴파일러에서 경고가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-654">If elements are not CLS-compliant, compilers will generally issue a warning.</span></span>

> [!WARNING]
> <span data-ttu-id="d6622-655">경우에 따라 언어 컴파일러는 `CLSCompliantAttribute` 특성 사용 여부에 관계없이 CLS 규격 규칙을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-655">In some cases, language compilers enforce CLS-compliant rules regardless of whether the `CLSCompliantAttribute` attribute is used.</span></span> <span data-ttu-id="d6622-656">예를 들어 인터페이스에서 `*static` 멤버를 정의하면 CLS 규칙에 위반됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-656">For example, defining a `*static` member in an interface violates a CLS rule.</span></span> <span data-ttu-id="d6622-657">하지만 인터페이스에서 `*static` 멤버를 정의하는 경우 C# 컴파일러에서 오류 메시지가 표시되고 응용 프로그램이 컴파일되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-657">However, if you define a `*static` member in an interface, the C# compiler displays an error message and fails to compile the app.</span></span>

<span data-ttu-id="d6622-658">`CLSCompliantAttribute` 특성은 값이 `AttributeTargets.All`인 [AttributeUsageAttribute](xref:System.AttributeUsageAttribute) 특성으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-658">The `CLSCompliantAttribute` attribute is marked with an [AttributeUsageAttribute](xref:System.AttributeUsageAttribute) attribute that has a value of `AttributeTargets.All`.</span></span> <span data-ttu-id="d6622-659">이 값을 사용하면 `CLSCompliantAttribute` 특성을 어셈블리, 모듈, 형식(클래스, 구조체, 열거형, 인터페이스 및 대리자), 형식 멤버(생성자, 메서드, 속성, 필드 및 이벤트), 매개 변수, 제네릭 매개 변수 및 반환 값 등 어떤 프로그램 요소에도 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-659">This value allows you to apply the `CLSCompliantAttribute` attribute to any program element, including assemblies, modules, types (classes, structures, enumerations, interfaces, and delegates), type members (constructors, methods, properties, fields, and events), parameters, generic parameters, and return values.</span></span> <span data-ttu-id="d6622-660">그러나 실제로는 어셈블리, 형식 및 형식 멤버에만 이 특성을 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-660">However, in practice, you should apply the attribute only to assemblies, types, and type members.</span></span> <span data-ttu-id="d6622-661">그러지 않으면 컴파일러는 특성을 무시하고 라이브러리의 공용 인터페이스에서 비규격 매개 변수, 제네릭 매개 변수 또는 반환 값이 발생할 때마다 컴파일러 경고를 계속해서 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-661">Otherwise, compilers ignore the attribute and continue to generate compiler warnings whenever they encounter a non-compliant parameter, generic parameter, or return value in your library's public interface.</span></span>

<span data-ttu-id="d6622-662">`CLSCompliantAttribute` 특성의 값은 포함된 프로그램 요소에 의해 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-662">The value of the `CLSCompliantAttribute` attribute is inherited by contained program elements.</span></span> <span data-ttu-id="d6622-663">예를 들어, 어셈블리가 CLS 규격으로 표시되어 있으면 해당 형식도 CLS 규격입니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-663">For example, if an assembly is marked as CLS-compliant, its types are also CLS-compliant.</span></span> <span data-ttu-id="d6622-664">또한 형식이 CLS 규격으로 표시되어 있으면 해당 중첩 형식 및 멤버도 CLS 규격입니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-664">If a type is marked as CLS-compliant, its nested types and members are also CLS-compliant.</span></span>

<span data-ttu-id="d6622-665">포함된 프로그램 요소에 `CLSCompliantAttribute` 특성을 적용하여 상속된 규격을 명시적으로 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-665">You can explicitly override the inherited compliance by applying the `CLSCompliantAttribute` attribute to a contained program element.</span></span> <span data-ttu-id="d6622-666">예를 들어 *isCompliant* 값을 `false`로 지정하여 `CLSCompliantAttribute` 특성을 사용하면 규격 어셈블리에서 비규격 형식을 정의할 수 있고, *isCompliant* 값을 `true`로 지정하여 해당 특성을 사용하면 비규격 어셈블리에서 규격 형식을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-666">For example, you can use the `CLSCompliantAttribute` attribute with an *isCompliant* value of `false` to define a non-compliant type in a compliant assembly, and you can use the attribute with an *isCompliant* value of `true` to define a compliant type in a non-compliant assembly.</span></span> <span data-ttu-id="d6622-667">또한 규격 형식으로 비규격 멤버를 정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-667">You can also define non-compliant members in a compliant type.</span></span> <span data-ttu-id="d6622-668">하지만 비규격 형식은 규격 멤버를 가질 수 없기 때문에 비규격 형식의 상속을 재정의하기 위해 *isCompliant* 값을 `true`로 지정해서 이 특성을 사용할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-668">However, a non-compliant type cannot have compliant members, so you cannot use the attribute with an *isCompliant* value of `true` to override inheritance from a non-compliant type.</span></span>

<span data-ttu-id="d6622-669">구성 요소를 개발하는 경우 어셈블리 및 해당 형식과 멤버가 CLS 규격인지 여부를 나타내는 `CLSCompliantAttribute` 특성을 반드시 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-669">When you are developing components, you should always use the `CLSCompliantAttribute` attribute to indicate whether your assembly, its types, and its members are CLS-compliant.</span></span>

<span data-ttu-id="d6622-670">CLS 규격 구성 요소를 만들려면</span><span class="sxs-lookup"><span data-stu-id="d6622-670">To create CLS-compliant components:</span></span>

1. <span data-ttu-id="d6622-671">`CLSCompliantAttribute`를 사용하여 어셈블리를 CLS 규격으로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-671">Use the `CLSCompliantAttribute` to mark you assembly as CLS-compliant.</span></span>

2. <span data-ttu-id="d6622-672">CLS 규격이 아닌 어셈블리의 공개적으로 노출되는 모든 형식을 비규격으로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-672">Mark any publicly exposed types in the assembly that are not CLS-compliant as non-compliant.</span></span>

3. <span data-ttu-id="d6622-673">CLS 규격 형식의 공개적으로 노출되는 모든 멤버를 비규격으로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-673">Mark any publicly exposed members in CLS-compliant types as non-compliant.</span></span>

4. <span data-ttu-id="d6622-674">CLS 규격이 아닌 멤버에 대해 CLS 규격 대체 멤버를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-674">Provide a CLS-compliant alternative for non-CLS-compliant members.</span></span>

<span data-ttu-id="d6622-675">모든 비규격 형식 및 멤버를 성공적으로 표시한 경우 컴파일러에서 미준수 경고가 발생하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-675">If you've successfully marked all your non-compliant types and members, your compiler should not emit any non-compliance warnings.</span></span> <span data-ttu-id="d6622-676">그러나 제품 설명서에 CLS 규격이 아닌 멤버를 표시하고 이들의 CLS 규격 대체 멤버를 명시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-676">However, you should indicate which members are not CLS-compliant and list their CLS-compliant alternatives in your product documentation.</span></span>

<span data-ttu-id="d6622-677">다음 예제에서는 `CLSCompliantAttribute` 특성을 사용하여 CLS 규격 어셈블리와 CLS 규격이 아닌 멤버 두 개가 포함된 `CharacterUtilities` 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-677">The following example uses the `CLSCompliantAttribute` attribute to define a CLS-compliant assembly and a type, `CharacterUtilities`, that has two non-CLS-compliant members.</span></span> <span data-ttu-id="d6622-678">두 멤버 모두 `CLSCompliant(false)` 특성으로 태그가 지정되어 있으므로 컴파일러에서 경고를 생성하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-678">Because both members are tagged with the `CLSCompliant(false)` attribute, the compiler produces no warnings.</span></span> <span data-ttu-id="d6622-679">또한 이 클래스는 두 메서드 모두에 대해 CLS 규격 대체 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-679">The class also provides a CLS-compliant alternative for both methods.</span></span> <span data-ttu-id="d6622-680">일반적으로 두 오버로드를 `ToUTF16` 메서드에 추가하여 CLS 규격 대체 메서드를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-680">Ordinarily, we would just add two overloads to the `ToUTF16` method to provide CLS-compliant alternatives.</span></span> <span data-ttu-id="d6622-681">하지만 메서드는 반환 값을 기반으로 오버로드될 수 없기 때문에, CLS 규격 메서드의 이름은 비규격 메서드의 이름과는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-681">However, because methods cannot be overloaded based on return value, the names of the CLS-compliant methods are different from the names of the non-compliant methods.</span></span>

```csharp
using System;
using System.Text;

[assembly:CLSCompliant(true)]

public class CharacterUtilities
{
   [CLSCompliant(false)] public static ushort ToUTF16(String s)
   {
      s = s.Normalize(NormalizationForm.FormC);
      return Convert.ToUInt16(s[0]);
   }

   [CLSCompliant(false)] public static ushort ToUTF16(Char ch)
   {
      return Convert.ToUInt16(ch);
   }

   // CLS-compliant alternative for ToUTF16(String).
   public static int ToUTF16CodeUnit(String s)
   {
      s = s.Normalize(NormalizationForm.FormC);
      return (int) Convert.ToUInt16(s[0]);
   }

   // CLS-compliant alternative for ToUTF16(Char).
   public static int ToUTF16CodeUnit(Char ch)
   {
      return Convert.ToInt32(ch);
   }

   public bool HasMultipleRepresentations(String s)
   {
      String s1 = s.Normalize(NormalizationForm.FormC);
      return s.Equals(s1);
   }

   public int GetUnicodeCodePoint(Char ch)
   {
      if (Char.IsSurrogate(ch))
         throw new ArgumentException("ch cannot be a high or low surrogate.");

      return Char.ConvertToUtf32(ch.ToString(), 0);
   }

   public int GetUnicodeCodePoint(Char[] chars)
   {
      if (chars.Length > 2)
         throw new ArgumentException("The array has too many characters.");

      if (chars.Length == 2) {
         if (! Char.IsSurrogatePair(chars[0], chars[1]))
            throw new ArgumentException("The array must contain a low and a high surrogate.");
         else
            return Char.ConvertToUtf32(chars[0], chars[1]);
      }
      else {
         return Char.ConvertToUtf32(chars.ToString(), 0);
      }
   }
}
```

```vb
Imports System.Text

<Assembly:CLSCompliant(True)>

Public Class CharacterUtilities
   <CLSCompliant(False)> Public Shared Function ToUTF16(s As String) As UShort
      s = s.Normalize(NormalizationForm.FormC)
      Return Convert.ToUInt16(s(0))
   End Function

   <CLSCompliant(False)> Public Shared Function ToUTF16(ch As Char) As UShort
      Return Convert.ToUInt16(ch)
   End Function

   ' CLS-compliant alternative for ToUTF16(String).
   Public Shared Function ToUTF16CodeUnit(s As String) As Integer
      s = s.Normalize(NormalizationForm.FormC)
      Return CInt(Convert.ToInt16(s(0)))
   End Function

   ' CLS-compliant alternative for ToUTF16(Char).
   Public Shared Function ToUTF16CodeUnit(ch As Char) As Integer
      Return Convert.ToInt32(ch)
   End Function

   Public Function HasMultipleRepresentations(s As String) As Boolean
      Dim s1 As String = s.Normalize(NormalizationForm.FormC)
      Return s.Equals(s1)
   End Function

   Public Function GetUnicodeCodePoint(ch As Char) As Integer
      If Char.IsSurrogate(ch) Then
         Throw New ArgumentException("ch cannot be a high or low surrogate.")
      End If
      Return Char.ConvertToUtf32(ch.ToString(), 0)
   End Function

   Public Function GetUnicodeCodePoint(chars() As Char) As Integer
      If chars.Length > 2 Then
         Throw New ArgumentException("The array has too many characters.")
      End If
      If chars.Length = 2 Then
         If Not Char.IsSurrogatePair(chars(0), chars(1)) Then
            Throw New ArgumentException("The array must contain a low and a high surrogate.")
         Else
            Return Char.ConvertToUtf32(chars(0), chars(1))
         End If
      Else
         Return Char.ConvertToUtf32(chars.ToString(), 0)
      End If
   End Function
End Class
```

<span data-ttu-id="d6622-682">라이브러리가 아닌 응용 프로그램을 개발하는 경우(다른 응용 프로그램 개발자가 사용할 수 있는 형식 또는 멤버를 노출하지 않으려는 경우) 응용 프로그램이 사용하는 프로그램 요소의 CLS 규격은 해당 언어가 지원하지 않는 경우에만 관련됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-682">If you are developing an app rather than a library (that is, if you aren't exposing types or members that can be consumed by other app developers), the CLS compliance of the program elements that your app consumes are of interest only if your language does not support them.</span></span> <span data-ttu-id="d6622-683">이 경우에 CLS 규격이 아닌 요소를 사용하려고 하면 언어 컴파일러에서 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-683">In that case, your language compiler will generate an error when you try to use a non-CLS-compliant element.</span></span>

## <a name="cross-language-interoperability"></a><span data-ttu-id="d6622-684">언어 간 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="d6622-684">Cross-language interoperability</span></span>

<span data-ttu-id="d6622-685">언어 독립성은 여러 가지 의미를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-685">Language independence has a number of possible meanings.</span></span> <span data-ttu-id="d6622-686">한 가지 의미는 한 언어로 작성된 형식을 다른 언어로 작성된 앱에서 원활하게 사용할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-686">One meaning involves seamlessly consuming types written in one language from an app written in another language.</span></span> <span data-ttu-id="d6622-687">이 문서의 핵심이기도 한 두 번째 의미는 여러 언어로 작성된 코드를 단일 .NET 어셈블리로 결합하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-687">A second meaning, which is the focus of this article, involves combining code written in multiple languages into a single .NET assembly.</span></span>

<span data-ttu-id="d6622-688">다음 예제에서는 두 클래스 `NumericLib` 및 `StringLib`를 포함하는 Utilities.dll이라는 클래스 라이브러리를 만들어 언어 간 상호 운용성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-688">The following example illustrates cross-language interoperability by creating a class library named Utilities.dll that includes two classes, `NumericLib` and `StringLib`.</span></span> <span data-ttu-id="d6622-689">`NumericLib` 클래스는 C#으로 작성되었고 `StringLib` 클래스는 Visual Basic으로 작성되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-689">The `NumericLib` class is written in C#, and the `StringLib` class is written in Visual Basic.</span></span> <span data-ttu-id="d6622-690">다음은 단일 멤버 `ToTitleCase`를 해당 `StringLib` 클래스에 포함하는 `StringUtil.vb`용 소스 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-690">Here's the source code for `StringUtil.vb`, which includes a single member, `ToTitleCase`, in its `StringLib` class.</span></span>

```vb
Imports System.Collections.Generic
Imports System.Runtime.CompilerServices

Public Module StringLib
   Private exclusions As List(Of String)

   Sub New()
      Dim words() As String = { "a", "an", "and", "of", "the" }
      exclusions = New List(Of String)
      exclusions.AddRange(words)
   End Sub

   <Extension()> _
   Public Function ToTitleCase(title As String) As String
      Dim words() As String = title.Split()
      Dim result As String = String.Empty

      For ctr As Integer = 0 To words.Length - 1
         Dim word As String = words(ctr)
         If ctr = 0 OrElse Not exclusions.Contains(word.ToLower()) Then
            result += word.Substring(0, 1).ToUpper() + _
                      word.Substring(1).ToLower()
         Else
            result += word.ToLower()
         End If
         If ctr <= words.Length - 1 Then
            result += " "
         End If
      Next
      Return result
   End Function
End Module
```

<span data-ttu-id="d6622-691">다음은 `NumericLib` 및 `IsEven`라는 두 가지 멤버를 가진 `NearZero` 클래스를 정의하는 NumberUtil.cs용 소스 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-691">Here's the source code for NumberUtil.cs, which defines a `NumericLib` class that has two members, `IsEven` and `NearZero`.</span></span>

```csharp
using System;

public static class NumericLib
{
   public static bool IsEven(this IConvertible number)
   {
      if (number is Byte ||
          number is SByte ||
          number is Int16 ||
          number is UInt16 ||
          number is Int32 ||
          number is UInt32 ||
          number is Int64)
         return ((long) number) % 2 == 0;
      else if (number is UInt64)
         return ((ulong) number) %2 == 0;
      else
         throw new NotSupportedException("IsEven called for a non-integer value.");
   }

   public static bool NearZero(double number)
   {
      return number < .00001;
   }
}
```

<span data-ttu-id="d6622-692">두 클래스를 단일 어셈블리로 패키징하려면 모듈로 컴파일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-692">To package the two classes in a single assembly, you must compile them into modules.</span></span> <span data-ttu-id="d6622-693">Visual Basic 소스 코드 파일을 모듈로 컴파일하려면 다음 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-693">To compile the Visual Basic source code file into a module, use this command:</span></span>

```console
vbc /t:module StringUtil.vb
```

<span data-ttu-id="d6622-694">C# 소스 코드 파일을 모듈로 컴파일하려면 다음 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-694">To compile the C# source code file into a module, use this command:</span></span>

```console
csc /t:module NumberUtil.cs
```

<span data-ttu-id="d6622-695">그런 다음 링크 도구(Link.exe)를 사용하여 두 모듈을 하나의 어셈블리로 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-695">You then use the Link tool (Link.exe) to compile the two modules into an assembly:</span></span>

```console
link numberutil.netmodule stringutil.netmodule /out:UtilityLib.dll /dll
```

<span data-ttu-id="d6622-696">다음 예제에서는 `NumericLib.NearZero` 및 `StringLib.ToTitleCase` 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-696">The following example then calls the `NumericLib.NearZero` and `StringLib.ToTitleCase` methods.</span></span> <span data-ttu-id="d6622-697">Visual Basic 코드와 C# 코드 둘 다 두 클래스의 메서드에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-697">Both the Visual Basic code and the C# code are able to access the methods in both classes.</span></span>

```csharp
using System;

public class Example
{
   public static void Main()
   {
      Double dbl = 0.0 - Double.Epsilon;
      Console.WriteLine(NumericLib.NearZero(dbl));

      string s = "war and peace";
      Console.WriteLine(s.ToTitleCase());
   }
}
// The example displays the following output:
//       True
//       War and Peace
```

```vb
Module Example
   Public Sub Main()
      Dim dbl As Double = 0.0 - Double.Epsilon
      Console.WriteLine(NumericLib.NearZero(dbl))

      Dim s As String = "war and peace"
      Console.WriteLine(s.ToTitleCase())
   End Sub
End Module
' The example displays the following output:
'       True
'       War and Peace
```

<span data-ttu-id="d6622-698">Visual Basic 코드를 컴파일하려면 다음 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-698">To compile the Visual Basic code, use this command:</span></span>

```console
vbc example.vb /r:UtilityLib.dll
```

<span data-ttu-id="d6622-699">C#으로 컴파일하려면 vbc에서 csc로 컴파일러의 이름을 변경하고 .vb에서 .cs로 파일 확장명을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="d6622-699">To compile with C#, change the name of the compiler from vbc to csc, and change the file extension from .vb to .cs:</span></span>

```console
csc example.cs /r:UtilityLib.dll
```
