---
title: 'C# 예약된 특성: Conditional, Obsolete, AttributeUsage'
ms.date: 04/09/2020
description: 컴파일러에서 생성된 코드에 영향을 주기 위해 컴파일러가 이 특성을 해석합니다.
ms.openlocfilehash: c6d697dd08233ffc88900949998047137ee170a9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/29/2020
ms.locfileid: "82021771"
---
# <a name="reserved-attributes-conditionalattribute-obsoleteattribute-attributeusageattribute"></a><span data-ttu-id="40bb1-103">예약된 특성: ConditionalAttribute, ObsoleteAttribute, AttributeUsageAttribute</span><span class="sxs-lookup"><span data-stu-id="40bb1-103">Reserved attributes: ConditionalAttribute, ObsoleteAttribute, AttributeUsageAttribute</span></span>

<span data-ttu-id="40bb1-104">이 특성은 코드의 요소에 적용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40bb1-104">These attributes can be applied to elements in your code.</span></span> <span data-ttu-id="40bb1-105">해당 요소에 의미 체계 의미를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="40bb1-105">They add semantic meaning to those elements.</span></span> <span data-ttu-id="40bb1-106">컴파일러는 해당 의미 체계 의미를 사용하여 출력을 변경하고 코드를 사용하여 개발자의 가능한 실수를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="40bb1-106">The compiler uses those semantic meanings to alter its output and report possible mistakes by developers using your code.</span></span>

## <a name="conditional-attribute"></a><span data-ttu-id="40bb1-107">`Conditional` 특성</span><span class="sxs-lookup"><span data-stu-id="40bb1-107">`Conditional` attribute</span></span>

<span data-ttu-id="40bb1-108">`Conditional` 특성을 사용하면 메서드 실행이 전처리 식별자에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="40bb1-108">The `Conditional` attribute makes the execution of a method dependent on a preprocessing identifier.</span></span> <span data-ttu-id="40bb1-109">`Conditional` 특성은 <xref:System.Diagnostics.ConditionalAttribute>의 별칭이고 메서드 또는 특성 클래스에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40bb1-109">The `Conditional` attribute is an alias for <xref:System.Diagnostics.ConditionalAttribute>, and can be applied to a method or an attribute class.</span></span>

<span data-ttu-id="40bb1-110">다음 예제에서 `Conditional`은 프로그램 관련 진단 정보 표시를 사용하거나 사용하지 않도록 설정하는 메서드에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="40bb1-110">In the following example, `Conditional` is applied to a method to enable or disable the display of program-specific diagnostic information:</span></span>

:::code language="csharp" source="snippets/trace.cs" interactive="try-dotnet" :::

<span data-ttu-id="40bb1-111">`TRACE_ON` 식별자가 정의되지 않으면 추적 출력이 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="40bb1-111">If the `TRACE_ON` identifier isn't defined, the trace output isn't displayed.</span></span> <span data-ttu-id="40bb1-112">대화형 창에서 직접 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="40bb1-112">Explore for yourself in the interactive window.</span></span>

<span data-ttu-id="40bb1-113">`Conditional` 특성은 보통 `DEBUG` 식별자와 함께 사용하여 다음 예제에 표시된 대로 릴리스 빌드가 아닌 디버그 빌드의 추적 및 로깅 기능을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="40bb1-113">The `Conditional` attribute is often used with the `DEBUG` identifier to enable trace and logging features for debug builds but not in release builds, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/ConditionalExamples.cs" id="SnippetConditional" :::

<span data-ttu-id="40bb1-114">조건부로 표시된 메서드를 호출하면 지정된 전처리 기호가 있는지 여부에 따라 호출을 포함 또는 생략할지 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="40bb1-114">When a method marked conditional is called, the presence or absence of the specified preprocessing symbol determines whether the call is included or omitted.</span></span> <span data-ttu-id="40bb1-115">기호가 정의되면 호출이 포함되고, 정의되지 않으면 호출이 생략됩니다.</span><span class="sxs-lookup"><span data-stu-id="40bb1-115">If the symbol is defined, the call is included; otherwise, the call is omitted.</span></span> <span data-ttu-id="40bb1-116">조건부 메서드는 클래스 또는 구조체 선언의 메서드여야 하며 `void` 반환 형식을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="40bb1-116">A conditional method must be a method in a class or struct declaration and must have a `void` return type.</span></span> <span data-ttu-id="40bb1-117">메서드를 `#if…#endif` 블록 내부에 포함하는 것보다 `Conditional`을 사용하는 것이 더 분명하고 더 정교하며 오류 가능성이 더 작습니다.</span><span class="sxs-lookup"><span data-stu-id="40bb1-117">Using `Conditional` is cleaner, more elegant, and less error-prone than enclosing methods inside `#if…#endif` blocks.</span></span>

<span data-ttu-id="40bb1-118">한 메서드에 여러 `Conditional` 특성이 있을 경우 하나 이상의 조건부 기호가 정의되면(기호가 OR 연산자를 통해 논리적으로 함께 연결되면) 메서드 호출이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="40bb1-118">If a method has multiple `Conditional` attributes, a call to the method is included if at one or more conditional symbols is defined (the symbols are logically linked together by using the OR operator).</span></span> <span data-ttu-id="40bb1-119">다음 예제에서는 `A` 또는 `B`가 있으면 메서드 호출이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="40bb1-119">In the following example, the presence of either `A` or `B` results in a method call:</span></span>

:::code language="csharp" source="snippets/ConditionalExamples.cs" id="SnippetMultipleConditions" :::

### <a name="using-conditional-with-attribute-classes"></a><span data-ttu-id="40bb1-120">특성 클래스와 함께 `Conditional` 사용</span><span class="sxs-lookup"><span data-stu-id="40bb1-120">Using `Conditional` with attribute classes</span></span>

<span data-ttu-id="40bb1-121">`Conditional` 특성을 특성 클래스 정의에 적용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40bb1-121">The `Conditional` attribute can also be applied to an attribute class definition.</span></span> <span data-ttu-id="40bb1-122">다음 예제에서 사용자 지정 특성 `Documentation`은 `DEBUG`가 정의된 경우에만 메타데이터에 정보를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="40bb1-122">In the following example, the custom attribute `Documentation` will only add information to the metadata if `DEBUG` is defined.</span></span>

:::code language="csharp" source="snippets/ConditionalExamples.cs" id="SnippetConditionalConditionalAttribute" :::

## <a name="obsolete-attribute"></a><span data-ttu-id="40bb1-123">`Obsolete` 특성</span><span class="sxs-lookup"><span data-stu-id="40bb1-123">`Obsolete` attribute</span></span>

<span data-ttu-id="40bb1-124">`Obsolete` 특성은 코드 요소를 더 이상 사용이 권장되지 않는 항목으로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="40bb1-124">The `Obsolete` attribute marks a code element as no longer recommended for use.</span></span> <span data-ttu-id="40bb1-125">사용되지 않음으로 표시된 엔터티를 사용하면 경고나 오류가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="40bb1-125">Use of an entity marked obsolete generates a warning or an error.</span></span> <span data-ttu-id="40bb1-126">`Obsolete` 특성은 단일 사용 특성이고 특성을 허용하는 모든 엔터티에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40bb1-126">The `Obsolete` attribute is a single-use attribute and can be applied to any entity that allows attributes.</span></span> <span data-ttu-id="40bb1-127">`Obsolete`는 <xref:System.ObsoleteAttribute>의 별칭입니다.</span><span class="sxs-lookup"><span data-stu-id="40bb1-127">`Obsolete` is an alias for <xref:System.ObsoleteAttribute>.</span></span>

<span data-ttu-id="40bb1-128">다음 예제에서는 `Obsolete` 특성이 `A` 클래스 및 `B.OldMethod` 메서드에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="40bb1-128">In the following example the `Obsolete` attribute is applied to class `A` and to method `B.OldMethod`.</span></span> <span data-ttu-id="40bb1-129">`B.OldMethod`에 적용된 특성 생성자의 두 번째 인수가 `true`로 설정되므로 이 메서드는 컴파일러 오류를 일으키지만, `A` 클래스를 사용하면 경고가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="40bb1-129">Because the second argument of the attribute constructor applied to `B.OldMethod` is set to `true`, this method will cause a compiler error, whereas using class `A` will just produce a warning.</span></span> <span data-ttu-id="40bb1-130">그러나 `B.NewMethod`를 호출하면 경고나 오류가 생성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="40bb1-130">Calling `B.NewMethod`, however, produces no warning or error.</span></span> <span data-ttu-id="40bb1-131">예를 들어 이전 정의와 함께 사용할 경우 다음 코드에서는 두 개의 경고 및 하나의 오류가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="40bb1-131">For example, when you use it with the previous definitions, the following code generates two warnings and one error:</span></span>

:::code language="csharp" source="snippets/ObsoleteExample.cs" interactive="try-dotnet" :::

<span data-ttu-id="40bb1-132">특성 생성자에 첫 번째 인수로 제공된 문자열은 경고 또는 오류의 일부로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="40bb1-132">The string provided as the first argument to the attribute constructor will be displayed as part of the warning or error.</span></span> <span data-ttu-id="40bb1-133">`A` 클래스에 대한 두 개의 경고가 각각 클래스 참조 선언 및 클래스 생성자에 대해 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="40bb1-133">Two warnings for class `A` are generated: one for the declaration of the class reference, and one for the class constructor.</span></span> <span data-ttu-id="40bb1-134">`Obsolete` 특성은 인수 없이 사용할 수 있지만 대신 사용이 권장되는 항목에 대한 설명을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="40bb1-134">The `Obsolete` attribute can be used without arguments, but including an explanation what to use instead is recommended.</span></span>

## <a name="attributeusage-attribute"></a><span data-ttu-id="40bb1-135">`AttributeUsage` 특성</span><span class="sxs-lookup"><span data-stu-id="40bb1-135">`AttributeUsage` attribute</span></span>

<span data-ttu-id="40bb1-136">`AttributeUsage` 특성은 사용자 지정 특성 클래스를 사용하는 방법을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="40bb1-136">The `AttributeUsage` attribute determines how a custom attribute class can be used.</span></span> <span data-ttu-id="40bb1-137"><xref:System.AttributeUsageAttribute>는 사용자 지정 특성 정의에 적용되는 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="40bb1-137"><xref:System.AttributeUsageAttribute> is an attribute you apply to custom attribute definitions.</span></span> <span data-ttu-id="40bb1-138">`AttributeUsage` 특성을 사용하면 다음을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40bb1-138">The `AttributeUsage` attribute enables you to control:</span></span>

- <span data-ttu-id="40bb1-139">적용할 수 있는 프로그램 요소 특성</span><span class="sxs-lookup"><span data-stu-id="40bb1-139">Which program elements attribute may be applied to.</span></span> <span data-ttu-id="40bb1-140">사용을 제한하지 않는 한, 다음과 같은 프로그램 요소 중 하나에 특성을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40bb1-140">Unless you restrict its usage, an attribute may be applied to any of the following program elements:</span></span>
  - <span data-ttu-id="40bb1-141">어셈블리(assembly)</span><span class="sxs-lookup"><span data-stu-id="40bb1-141">assembly</span></span>
  - <span data-ttu-id="40bb1-142">모듈(module)</span><span class="sxs-lookup"><span data-stu-id="40bb1-142">module</span></span>
  - <span data-ttu-id="40bb1-143">필드(field)</span><span class="sxs-lookup"><span data-stu-id="40bb1-143">field</span></span>
  - <span data-ttu-id="40bb1-144">event</span><span class="sxs-lookup"><span data-stu-id="40bb1-144">event</span></span>
  - <span data-ttu-id="40bb1-145">메서드(method)</span><span class="sxs-lookup"><span data-stu-id="40bb1-145">method</span></span>
  - <span data-ttu-id="40bb1-146">매개변수(param)</span><span class="sxs-lookup"><span data-stu-id="40bb1-146">param</span></span>
  - <span data-ttu-id="40bb1-147">속성(property)</span><span class="sxs-lookup"><span data-stu-id="40bb1-147">property</span></span>
  - <span data-ttu-id="40bb1-148">반환값(return)</span><span class="sxs-lookup"><span data-stu-id="40bb1-148">return</span></span>
  - <span data-ttu-id="40bb1-149">형식(type)</span><span class="sxs-lookup"><span data-stu-id="40bb1-149">type</span></span>
- <span data-ttu-id="40bb1-150">특성을 단일 프로그램 요소에 여러 번 적용할 수 있는지 여부</span><span class="sxs-lookup"><span data-stu-id="40bb1-150">Whether an attribute can be applied to a single program element multiple times.</span></span>
- <span data-ttu-id="40bb1-151">특성이 파생 클래스에게 상속되는지 여부</span><span class="sxs-lookup"><span data-stu-id="40bb1-151">Whether attributes are inherited by derived classes.</span></span>

<span data-ttu-id="40bb1-152">기본 설정을 명시적으로 적용할 경우 다음 예제와 같이 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="40bb1-152">The default settings look like the following example when applied explicitly:</span></span>

:::code language="csharp" source="snippets/NewAttribute.cs" id="SnippetUsageFirst" :::

<span data-ttu-id="40bb1-153">이 예제에서 `NewAttribute` 클래스는 모든 지원되는 프로그램 요소에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40bb1-153">In this example, the `NewAttribute` class can be applied to any supported program element.</span></span> <span data-ttu-id="40bb1-154">하지만 각 엔터티에 한 번만 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40bb1-154">But it can be applied only once to each entity.</span></span> <span data-ttu-id="40bb1-155">이 특성은 기본 클래스에 적용될 때 파생 클래스에게 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="40bb1-155">The attribute is inherited by derived classes when applied to a base class.</span></span>

<span data-ttu-id="40bb1-156"><xref:System.AttributeUsageAttribute.AllowMultiple> 및 <xref:System.AttributeUsageAttribute.Inherited> 인수는 선택 사항이므로 다음 코드는 동일한 효과를 가집니다.</span><span class="sxs-lookup"><span data-stu-id="40bb1-156">The <xref:System.AttributeUsageAttribute.AllowMultiple> and <xref:System.AttributeUsageAttribute.Inherited> arguments are optional, so the following code has the same effect:</span></span>

:::code language="csharp" source="snippets/NewAttribute.cs" id="SnippetUsageSecond" :::

<span data-ttu-id="40bb1-157">첫 번째 <xref:System.AttributeUsageAttribute> 인수는 <xref:System.AttributeTargets> 열거형의 요소가 하나 이상이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="40bb1-157">The first <xref:System.AttributeUsageAttribute> argument must be one or more elements of the <xref:System.AttributeTargets> enumeration.</span></span> <span data-ttu-id="40bb1-158">다음 예제와 같이 OR 연산자를 사용하여 여러 대상 형식을 함께 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40bb1-158">Multiple target types can be linked together with the OR operator, like the following example shows:</span></span>

:::code language="csharp" source="snippets/NewPropertyOrFieldAttribute.cs" id="SnippetDefinePropertyAttribute" :::

<span data-ttu-id="40bb1-159">C# 7.3부터 특성은 속성 또는 자동 구현 속성의 지원 필드에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40bb1-159">Beginning in C# 7.3, attributes can be applied to either the property or the backing field for an auto-implemented property.</span></span> <span data-ttu-id="40bb1-160">특성에 `field` 지정자를 지정하지 않는 한 특성이 속성에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="40bb1-160">The attribute applies to the property, unless you specify the `field` specifier on the attribute.</span></span> <span data-ttu-id="40bb1-161">두 경우 모두 다음 예제에서 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="40bb1-161">Both are shown in the following example:</span></span>

:::code language="csharp" source="snippets/NewPropertyOrFieldAttribute.cs" id="SnippetUsePropertyAttribute" :::

<span data-ttu-id="40bb1-162"><xref:System.AttributeUsageAttribute.AllowMultiple> 인수가 `true`인 경우 다음 예제와 같이 결과 특성을 단일 엔터티에 두 번 이상 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40bb1-162">If the <xref:System.AttributeUsageAttribute.AllowMultiple> argument is `true`, then the resulting attribute can be applied more than once to a single entity, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/MultiUseAttribute.cs" id="SnippetMultiUse" :::

<span data-ttu-id="40bb1-163">이 경우 `AllowMultiple`이 `true`로 설정되므로 `MultiUseAttribute`를 반복적으로 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40bb1-163">In this case, `MultiUseAttribute` can be applied repeatedly because `AllowMultiple` is set to `true`.</span></span> <span data-ttu-id="40bb1-164">여러 특성을 적용하기 위해 표시된 두 형식이 모두 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="40bb1-164">Both formats shown for applying multiple attributes are valid.</span></span>

<span data-ttu-id="40bb1-165"><xref:System.AttributeUsageAttribute.Inherited>이 `false`인 경우 특성은 특성 클래스에서 파생된 클래스에서 상속하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="40bb1-165">If <xref:System.AttributeUsageAttribute.Inherited> is `false`, then the attribute isn't inherited by classes derived from an attributed class.</span></span> <span data-ttu-id="40bb1-166">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="40bb1-166">For example:</span></span>

:::code language="csharp" source="snippets/NonInheritedAttribute.cs" id="SnippetNonInherited" :::

<span data-ttu-id="40bb1-167">이 경우에 `NonInheritedAttribute`은 상속을 통해 `DClass`에 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="40bb1-167">In this case `NonInheritedAttribute` isn't applied to `DClass` via inheritance.</span></span>

## <a name="see-also"></a><span data-ttu-id="40bb1-168">참조</span><span class="sxs-lookup"><span data-stu-id="40bb1-168">See also</span></span>

- <xref:System.Attribute>
- <xref:System.Reflection>
- [<span data-ttu-id="40bb1-169">특성</span><span class="sxs-lookup"><span data-stu-id="40bb1-169">Attributes</span></span>](../../../standard/attributes/index.md)
- [<span data-ttu-id="40bb1-170">리플렉션</span><span class="sxs-lookup"><span data-stu-id="40bb1-170">Reflection</span></span>](../../programming-guide/concepts/reflection.md)
