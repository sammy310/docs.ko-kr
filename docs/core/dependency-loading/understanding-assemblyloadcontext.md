---
title: AssemblyLoadContext 이해 - .NET Core
description: .NET Core에서 AssemblyLoadContext의 용도와 동작을 이해하기 위한 핵심 개념입니다.
ms.date: 08/09/2019
author: sdmaclea
ms.author: stmaclea
ms.openlocfilehash: 8a73a432bf8cc72cced77cf6c62a785b72032913
ms.sourcegitcommit: 9c3a4f2d3babca8919a1e490a159c1500ba7a844
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2019
ms.locfileid: "72303709"
---
# <a name="understanding-systemruntimeloaderassemblyloadcontext"></a>System.Runtime.Loader.AssemblyLoadContext 이해

<xref:System.Runtime.Loader.AssemblyLoadContext> 클래스는 .NET Core에만 있습니다. 이 문서는 <xref:System.Runtime.Loader.AssemblyLoadContext> API 설명서를 개념 정보로 보완하기 위한 것입니다.

이 문서는 동적 로딩을 구현하는 개발자, 특히 동적 로딩 프레임워크 개발자와 관련이 있습니다.

## <a name="what-is-the-assemblyloadcontext"></a>AssemblyLoadContext란?

모든 .NET Core 애플리케이션은 <xref:System.Runtime.Loader.AssemblyLoadContext>를 암시적으로 사용합니다.
종속성을 찾고 로드하는 런타임 공급자입니다. 종속성이 로드될 때마다 <xref:System.Runtime.Loader.AssemblyLoadContext> 인스턴스가 호출되어 해당 종속성을 찾습니다.

- 관리형 어셈블리 및 기타 종속성을 검색, 로드 및 캐시하는 서비스를 제공합니다.

- 동적 코드 로드 및 언로드를 지원하기 위해 자체 <xref:System.Runtime.Loader.AssemblyLoadContext> 인스턴스에 코드와 해당 종속성을 로드하기 위한 격리된 컨텍스트를 만듭니다.

## <a name="when-do-you-need-multiple-assemblyloadcontext-instances"></a>여러 AssemblyLoadContext 인스턴스가 필요한 경우는 언제인가요?

단일 <xref:System.Runtime.Loader.AssemblyLoadContext> 인스턴스는 단순 어셈블리 이름(<xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType>)당 정확히 하나의 <xref:System.Reflection.Assembly> 버전을 로드하는 것으로 제한됩니다.

이 제한은 코드 모듈을 동적으로 로드할 때 문제가 될 수 있습니다. 각 모듈은 독립적으로 컴파일되며 <xref:System.Reflection.Assembly>의 다른 버전에 따라 달라질 수 있습니다. 이 문제는 일반적으로 여러 모듈이 일반적으로 사용되는 라이브러리의 서로 다른 버전에 따라 달라지는 경우에 발생합니다.

동적으로 코드를 로드하도록 지원하기 위해 <xref:System.Runtime.Loader.AssemblyLoadContext> API는 동일한 애플리케이션에서 충돌하는 버전의 <xref:System.Reflection.Assembly>를 로드하는 기능을 제공합니다. 각 <xref:System.Runtime.Loader.AssemblyLoadContext> 인스턴스는 각 <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType>을 특정 <xref:System.Reflection.Assembly> 인스턴스에 매핑하는 고유한 사전을 제공합니다.

또한 나중에 언로드하기 위해 코드 모듈과 관련된 종속성을 그룹화하는 편리한 메커니즘도 제공합니다.

## <a name="what-is-special-about-the-assemblyloadcontextdefault-instance"></a>AssemblyLoadContext.Default 인스턴스에 대한 특별한 사항은 무엇인가요?

<xref:System.Runtime.Loader.AssemblyLoadContext.Default?displayProperty=nameWithType> 인스턴스는 시작 시 런타임에서 자동으로 채웁니다.  [기본 프로빙](default-probing.md)을 사용하여 모든 정적 종속성을 찾습니다.

가장 일반적인 종속성 로드 시나리오를 해결합니다.

## <a name="how-does-assemblyloadcontext-support-dynamic-dependencies"></a>AssemblyLoadContext에서 동적 종속성을 어떻게 지원하나요?

<xref:System.Runtime.Loader.AssemblyLoadContext>에는 재정의할 수 있는 다양한 이벤트와 가상 함수가 있습니다.

<xref:System.Runtime.Loader.AssemblyLoadContext.Default?displayProperty=nameWithType> 인스턴스는 이벤트 재정의만 지원합니다.

[관리형 어셈블리 로드 알고리즘](loading-managed.md), [위성 어셈블리 로드 알고리즘](loading-resources.md) 및 [비관리형(네이티브) 라이브러리 로드 알고리즘](loading-unmanaged.md) 문서에서는 사용 가능한 모든 이벤트와 가상 함수를 참조합니다.  이 문서에는 로드 알고리즘에서 각 이벤트와 함수의 상대적 위치가 나와 있습니다. 여기서는 해당 정보를 재현하지 않습니다.

이 섹션에서는 관련 이벤트 및 함수에 대한 일반 원칙에 대해 설명합니다.

- **반복할 수 있습니다**. 특정 종속성에 대한 쿼리는 항상 동일한 응답을 생성해야 합니다. 로드된 동일한 종속성 인스턴스를 반환해야 합니다. 이 요구 사항은 캐시 일관성을 위한 기본 사항입니다. 특히 관리형 어셈블리의 경우 <xref:System.Reflection.Assembly> 캐시를 만듭니다. 캐시 키는 단순 어셈블리 이름(<xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType>)입니다.
- **일반적으로 throw하지 않습니다**.  요청된 종속성을 찾을 수 없는 경우 이러한 함수는 덤프 대신 `null`을 반환해야 합니다. throw하면 검색을 조기에 종료하고 예외를 호출자에 전파합니다. throw는 손상된 어셈블리 또는 메모리 부족 상태와 같은 예기치 않은 오류로 제한해야 합니다.
- **재귀를 사용하지 않습니다**. 이러한 함수와 처리기는 종속성을 찾기 위한 로드 규칙을 구현합니다. 구현에서 재귀를 트리거하는 API를 호출하지 않아야 합니다. 코드는 일반적으로 특정 경로 또는 메모리 참조 인수가 필요한 **AssemblyLoadContext** 로드 함수를 호출해야 합니다.
- **올바른 AssemblyLoadContext에 로드합니다**. 로드 종속성을 로드할 위치를 선택하는 것은 애플리케이션마다 다릅니다.  선택은 이러한 이벤트와 함수를 통해 구현됩니다. 코드에서 **AssemblyLoadContext** load-by-path(경로별 로드) 함수를 호출하면 코드를 로드하려는 인스턴스에서 이 함수를 호출합니다. 때로는 `null`을 반환하고 <xref:System.Runtime.Loader.AssemblyLoadContext.Default?displayProperty=nameWithType>에서 로드를 처리할 수 있도록 하는 것이 가장 간단한 옵션일 수 있습니다.
- **스레드 경합에 주의합니다**. 로딩은 여러 스레드에서 트리거할 수 있습니다. AssemblyLoadContext는 어셈블리를 원자 단위로 캐시에 추가하여 스레드 경합을 처리합니다. 경합 실패자의 인스턴스가 삭제됩니다. 구현 논리에서는 여러 스레드를 올바르게 처리하지 않는 추가 논리를 추가하지 않습니다.

## <a name="how-are-dynamic-dependencies-isolated"></a>동적 종속성은 어떻게 격리되나요?

각 <xref:System.Runtime.Loader.AssemblyLoadContext> 인스턴스는 <xref:System.Reflection.Assembly> 인스턴스와 <xref:System.Type> 정의의 고유 범위를 나타냅니다.

이러한 종속성 간에는 이진 격리가 없습니다. 이름으로 서로를 찾지 못하여 격리될 뿐입니다.

각각의 <xref:System.Runtime.Loader.AssemblyLoadContext>에서 다음을 수행할 수 있습니다.

- <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType>은 다른 <xref:System.Reflection.Assembly> 인스턴스를 참조할 수 있습니다.
- <xref:System.Type.GetType%2A?displayProperty=nameWithType>은 동일한 `name` 형식에 대해 다른 형식 인스턴스를 반환할 수 있습니다.

## <a name="how-are-dependencies-shared"></a>종속성은 어떻게 공유되나요?

종속성은 <xref:System.Runtime.Loader.AssemblyLoadContext> 인스턴스 간에 쉽게 공유할 수 있습니다. 일반 모델은 하나의 <xref:System.Runtime.Loader.AssemblyLoadContext>에서 종속성을 로드하는 데 사용할 수 있습니다.  다른 하나는 로드된 어셈블리에 대한 참조를 사용하여 종속성을 공유합니다.

이 공유는 런타임 어셈블리에 필요합니다. 이러한 어셈블리는 <xref:System.Runtime.Loader.AssemblyLoadContext.Default?displayProperty=nameWithType>에만 로드할 수 있습니다. `ASP.NET`, `WPF` 또는 `WinForms`와 같은 프레임워크에도 동일하게 필요합니다.

공유 종속성을 <xref:System.Runtime.Loader.AssemblyLoadContext.Default?displayProperty=nameWithType>에 로드하는 것이 좋습니다. 이 공유는 일반적인 디자인 패턴입니다.

공유는 사용자 지정 <xref:System.Runtime.Loader.AssemblyLoadContext> 인스턴스의 코딩에서 구현됩니다. <xref:System.Runtime.Loader.AssemblyLoadContext>에는 재정의할 수 있는 다양한 이벤트와 가상 함수가 있습니다. 이러한 함수 중 하나에서 다른 <xref:System.Runtime.Loader.AssemblyLoadContext> 인스턴스에 로드된 <xref:System.Reflection.Assembly> 인스턴스에 대한 참조를 반환하면 <xref:System.Reflection.Assembly> 인스턴스가 공유됩니다. 표준 로드 알고리즘은 일반 공유 패턴을 간소화하기 위해 <xref:System.Runtime.Loader.AssemblyLoadContext.Default?displayProperty=nameWithType>의 로드를 지연시킵니다.  [관리형 어셈블리 로드 알고리즘](loading-managed.md)을 참조하세요.

## <a name="complications"></a>컴플리케이션

### <a name="type-conversion-issues"></a>형식 변환 문제

두 <xref:System.Runtime.Loader.AssemblyLoadContext> 인스턴스에 동일한 `name`의 형식 정의가 포함되는 경우 동일한 형식이 아닙니다. 이러한 형식은 동일한 <xref:System.Reflection.Assembly> 인스턴스에서 온 경우에만 동일합니다.

복잡한 문제에서 이러한 일치하지 않는 형식에 대한 예외 메시지는 혼동될 수 있습니다. 형식은 예외 메시지에서 단순 형식 이름으로 참조됩니다. 이 경우 일반적인 예외 메시지는 다음과 같은 형식입니다.

> 'IsolatedType' 형식의 개체를 'IsolatedType' 형식으로 변환할 수 없습니다.

### <a name="debugging-type-conversion-issues"></a>형식 변환 문제 디버깅

일치하지 않는 형식 쌍을 지정하는 경우 다음 사항도 알고 있어야 합니다.

- 각 형식의 <xref:System.Type.Assembly?displayProperty=nameWithType>
- 각 형식의 <xref:System.Runtime.Loader.AssemblyLoadContext> - <xref:System.Runtime.Loader.AssemblyLoadContext.GetLoadContext(System.Reflection.Assembly)?displayProperty=nameWithType> 함수를 통해 가져올 수 있습니다.

`a` 및 `b`의 두 개체를 지정하는 경우 디버거에서 다음을 평가하는 것이 좋습니다.

```csharp
// In debugger look at each assembly's instance, Location, and FullName
a.GetType().Assembly
b.GetType().Assembly
// In debugger look at each AssemblyLoadContext's instance and name
System.Runtime.AssemblyLoadContext.GetLoadContext(a.GetType().Assembly)
System.Runtime.AssemblyLoadContext.GetLoadContext(b.GetType().Assembly)
```

### <a name="resolving-type-conversion-issues"></a>형식 변환 문제 해결

이러한 형식 변환 문제를 해결하기 위한 두 가지 디자인 패턴이 있습니다.

1. 공용 공유 형식을 사용합니다. 이 공유 형식은 기본 런타임 형식이거나 새 공유 형식을 공유 어셈블리에 만들 수 있습니다.  공유 형식은 애플리케이션 어셈블리에 정의된 [인터페이스](../../csharp/language-reference/keywords/interface.md)인 경우가 많습니다. 참고 항목: [종속성은 어떻게 공유되나요?](#how-are-dependencies-shared)

2. 마샬링 기술을 사용하여 한 형식에서 다른 형식으로 변환합니다.
