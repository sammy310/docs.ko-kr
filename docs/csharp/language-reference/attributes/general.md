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
# <a name="reserved-attributes-conditionalattribute-obsoleteattribute-attributeusageattribute"></a>예약된 특성: ConditionalAttribute, ObsoleteAttribute, AttributeUsageAttribute

이 특성은 코드의 요소에 적용될 수 있습니다. 해당 요소에 의미 체계 의미를 추가합니다. 컴파일러는 해당 의미 체계 의미를 사용하여 출력을 변경하고 코드를 사용하여 개발자의 가능한 실수를 보고합니다.

## <a name="conditional-attribute"></a>`Conditional` 특성

`Conditional` 특성을 사용하면 메서드 실행이 전처리 식별자에 따라 달라집니다. `Conditional` 특성은 <xref:System.Diagnostics.ConditionalAttribute>의 별칭이고 메서드 또는 특성 클래스에 적용할 수 있습니다.

다음 예제에서 `Conditional`은 프로그램 관련 진단 정보 표시를 사용하거나 사용하지 않도록 설정하는 메서드에 적용됩니다.

:::code language="csharp" source="snippets/trace.cs" interactive="try-dotnet" :::

`TRACE_ON` 식별자가 정의되지 않으면 추적 출력이 표시되지 않습니다. 대화형 창에서 직접 살펴보세요.

`Conditional` 특성은 보통 `DEBUG` 식별자와 함께 사용하여 다음 예제에 표시된 대로 릴리스 빌드가 아닌 디버그 빌드의 추적 및 로깅 기능을 사용하도록 설정합니다.

:::code language="csharp" source="snippets/ConditionalExamples.cs" id="SnippetConditional" :::

조건부로 표시된 메서드를 호출하면 지정된 전처리 기호가 있는지 여부에 따라 호출을 포함 또는 생략할지 결정됩니다. 기호가 정의되면 호출이 포함되고, 정의되지 않으면 호출이 생략됩니다. 조건부 메서드는 클래스 또는 구조체 선언의 메서드여야 하며 `void` 반환 형식을 포함해야 합니다. 메서드를 `#if…#endif` 블록 내부에 포함하는 것보다 `Conditional`을 사용하는 것이 더 분명하고 더 정교하며 오류 가능성이 더 작습니다.

한 메서드에 여러 `Conditional` 특성이 있을 경우 하나 이상의 조건부 기호가 정의되면(기호가 OR 연산자를 통해 논리적으로 함께 연결되면) 메서드 호출이 포함됩니다. 다음 예제에서는 `A` 또는 `B`가 있으면 메서드 호출이 발생합니다.

:::code language="csharp" source="snippets/ConditionalExamples.cs" id="SnippetMultipleConditions" :::

### <a name="using-conditional-with-attribute-classes"></a>특성 클래스와 함께 `Conditional` 사용

`Conditional` 특성을 특성 클래스 정의에 적용할 수도 있습니다. 다음 예제에서 사용자 지정 특성 `Documentation`은 `DEBUG`가 정의된 경우에만 메타데이터에 정보를 추가합니다.

:::code language="csharp" source="snippets/ConditionalExamples.cs" id="SnippetConditionalConditionalAttribute" :::

## <a name="obsolete-attribute"></a>`Obsolete` 특성

`Obsolete` 특성은 코드 요소를 더 이상 사용이 권장되지 않는 항목으로 표시합니다. 사용되지 않음으로 표시된 엔터티를 사용하면 경고나 오류가 생성됩니다. `Obsolete` 특성은 단일 사용 특성이고 특성을 허용하는 모든 엔터티에 적용할 수 있습니다. `Obsolete`는 <xref:System.ObsoleteAttribute>의 별칭입니다.

다음 예제에서는 `Obsolete` 특성이 `A` 클래스 및 `B.OldMethod` 메서드에 적용됩니다. `B.OldMethod`에 적용된 특성 생성자의 두 번째 인수가 `true`로 설정되므로 이 메서드는 컴파일러 오류를 일으키지만, `A` 클래스를 사용하면 경고가 생성됩니다. 그러나 `B.NewMethod`를 호출하면 경고나 오류가 생성되지 않습니다. 예를 들어 이전 정의와 함께 사용할 경우 다음 코드에서는 두 개의 경고 및 하나의 오류가 생성됩니다.

:::code language="csharp" source="snippets/ObsoleteExample.cs" interactive="try-dotnet" :::

특성 생성자에 첫 번째 인수로 제공된 문자열은 경고 또는 오류의 일부로 표시됩니다. `A` 클래스에 대한 두 개의 경고가 각각 클래스 참조 선언 및 클래스 생성자에 대해 생성됩니다. `Obsolete` 특성은 인수 없이 사용할 수 있지만 대신 사용이 권장되는 항목에 대한 설명을 포함합니다.

## <a name="attributeusage-attribute"></a>`AttributeUsage` 특성

`AttributeUsage` 특성은 사용자 지정 특성 클래스를 사용하는 방법을 결정합니다. <xref:System.AttributeUsageAttribute>는 사용자 지정 특성 정의에 적용되는 특성입니다. `AttributeUsage` 특성을 사용하면 다음을 제어할 수 있습니다.

- 적용할 수 있는 프로그램 요소 특성 사용을 제한하지 않는 한, 다음과 같은 프로그램 요소 중 하나에 특성을 적용할 수 있습니다.
  - 어셈블리(assembly)
  - 모듈(module)
  - 필드(field)
  - event
  - 메서드(method)
  - 매개변수(param)
  - 속성(property)
  - 반환값(return)
  - 형식(type)
- 특성을 단일 프로그램 요소에 여러 번 적용할 수 있는지 여부
- 특성이 파생 클래스에게 상속되는지 여부

기본 설정을 명시적으로 적용할 경우 다음 예제와 같이 작성합니다.

:::code language="csharp" source="snippets/NewAttribute.cs" id="SnippetUsageFirst" :::

이 예제에서 `NewAttribute` 클래스는 모든 지원되는 프로그램 요소에 적용할 수 있습니다. 하지만 각 엔터티에 한 번만 적용할 수 있습니다. 이 특성은 기본 클래스에 적용될 때 파생 클래스에게 상속됩니다.

<xref:System.AttributeUsageAttribute.AllowMultiple> 및 <xref:System.AttributeUsageAttribute.Inherited> 인수는 선택 사항이므로 다음 코드는 동일한 효과를 가집니다.

:::code language="csharp" source="snippets/NewAttribute.cs" id="SnippetUsageSecond" :::

첫 번째 <xref:System.AttributeUsageAttribute> 인수는 <xref:System.AttributeTargets> 열거형의 요소가 하나 이상이어야 합니다. 다음 예제와 같이 OR 연산자를 사용하여 여러 대상 형식을 함께 연결할 수 있습니다.

:::code language="csharp" source="snippets/NewPropertyOrFieldAttribute.cs" id="SnippetDefinePropertyAttribute" :::

C# 7.3부터 특성은 속성 또는 자동 구현 속성의 지원 필드에 적용할 수 있습니다. 특성에 `field` 지정자를 지정하지 않는 한 특성이 속성에 적용됩니다. 두 경우 모두 다음 예제에서 표시됩니다.

:::code language="csharp" source="snippets/NewPropertyOrFieldAttribute.cs" id="SnippetUsePropertyAttribute" :::

<xref:System.AttributeUsageAttribute.AllowMultiple> 인수가 `true`인 경우 다음 예제와 같이 결과 특성을 단일 엔터티에 두 번 이상 적용할 수 있습니다.

:::code language="csharp" source="snippets/MultiUseAttribute.cs" id="SnippetMultiUse" :::

이 경우 `AllowMultiple`이 `true`로 설정되므로 `MultiUseAttribute`를 반복적으로 적용할 수 있습니다. 여러 특성을 적용하기 위해 표시된 두 형식이 모두 유효합니다.

<xref:System.AttributeUsageAttribute.Inherited>이 `false`인 경우 특성은 특성 클래스에서 파생된 클래스에서 상속하지 않습니다. 예를 들어:

:::code language="csharp" source="snippets/NonInheritedAttribute.cs" id="SnippetNonInherited" :::

이 경우에 `NonInheritedAttribute`은 상속을 통해 `DClass`에 적용되지 않습니다.

## <a name="see-also"></a>참조

- <xref:System.Attribute>
- <xref:System.Reflection>
- [특성](../../../standard/attributes/index.md)
- [리플렉션](../../programming-guide/concepts/reflection.md)
