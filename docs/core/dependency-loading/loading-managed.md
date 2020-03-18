---
title: 관리 어셈블리 로드 알고리즘 - .NET Core
description: .NET Core에서 관리 어셈블리 로드 알고리즘의 세부 정보 설명
ms.date: 08/09/2019
author: sdmaclea
ms.author: stmaclea
ms.openlocfilehash: 312a320676be6eb453697e0704ab771a6707618b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "73973504"
---
# <a name="managed-assembly-loading-algorithm"></a>관리 어셈블리 로드 알고리즘

관리 어셈블리는 다양한 단계를 포함하는 알고리즘으로 배치되고 로드됩니다.

위성 어셈블리 및 `WinRT` 어셈블리를 제외한 모든 관리 어셈블리는 동일한 알고리즘을 사용합니다.

## <a name="when-are-managed-assemblies-loaded"></a>관리 어셈블리는 언제 로드되나요?

관리 어셈블리 로드를 트리거하는 가장 일반적인 메커니즘은 정적 어셈블리 참조입니다. 이러한 참조는 코드에서 다른 어셈블리에 정의된 형식을 사용할 때마다 컴파일러에 의해 삽입됩니다. 이러한 어셈블리는 런타임에 필요한 대로 로드됩니다(`load-by-name`).

특정 API를 직접 사용하면 로드도 트리거됩니다.

|API  |설명  |`Active` <xref:System.Runtime.Loader.AssemblyLoadContext> |
|---------|---------|---------|
|<xref:System.Runtime.Loader.AssemblyLoadContext.LoadFromAssemblyName%2A?displayProperty=nameWithType>|`Load-by-name`|[이](../../csharp/language-reference/keywords/this.md) 인스턴스입니다.|
|<xref:System.Runtime.Loader.AssemblyLoadContext.LoadFromAssemblyPath%2A?displayProperty=nameWithType><p><xref:System.Runtime.Loader.AssemblyLoadContext.LoadFromNativeImagePath%2A?displayProperty=nameWithType>|경로에서 로드합니다.|[이](../../csharp/language-reference/keywords/this.md) 인스턴스입니다.|
<xref:System.Runtime.Loader.AssemblyLoadContext.LoadFromStream%2A?displayProperty=nameWithType>|개체에서 로드합니다.|[이](../../csharp/language-reference/keywords/this.md) 인스턴스입니다.|
|<xref:System.Reflection.Assembly.LoadFile%2A?displayProperty=nameWithType>|새 <xref:System.Runtime.Loader.AssemblyLoadContext> 인스턴스의 경로에서 로드|새 <xref:System.Runtime.Loader.AssemblyLoadContext> 인스턴스입니다.|
<xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>|<xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> 인스턴스의 경로에서 로드합니다.<p><xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType>에 <xref:System.Runtime.Loader.AssemblyLoadContext.Resolving> 처리기를 추가합니다. 처리기는 해당 디렉터리에서 어셈블리의 종속성을 로드합니다.|<xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> 인스턴스입니다.|
|<xref:System.Reflection.Assembly.Load(System.Reflection.AssemblyName)?displayProperty=nameWithType><p><xref:System.Reflection.Assembly.Load(System.String)?displayProperty=nameWithType><p><xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=nameWithType>|`Load-by-name`.|호출자에서 유추됩니다.<p><xref:System.Runtime.Loader.AssemblyLoadContext> 메서드를 선택합니다.|
|<xref:System.Reflection.Assembly.Load(System.Byte[])?displayProperty=nameWithType><p><xref:System.Reflection.Assembly.Load(System.Byte[],System.Byte[])?displayProperty=nameWithType>|새 <xref:System.Runtime.Loader.AssemblyLoadContext> 인스턴스에서 개체를 로드합니다.|새 <xref:System.Runtime.Loader.AssemblyLoadContext> 인스턴스입니다.|
<xref:System.Type.GetType(System.String)?displayProperty=nameWithType><p><xref:System.Type.GetType(System.String,System.Boolean)?displayProperty=nameWithType><p><xref:System.Type.GetType(System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType>|`Load-by-name`.|호출자에서 유추됩니다.<p>`assemblyResolver` 인수를 사용하여 <xref:System.Type.GetType%2A?displayProperty=nameWithType> 메서드를 선택합니다.|
<xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType>|형식 `name`에서 어셈블리의 정규화된 제네릭 형식을 설명하는 경우 `Load-by-name`을 트리거합니다.|호출자에서 유추됩니다.<p>어셈블리의 정규화된 형식 이름을 사용할 때는 <xref:System.Type.GetType%2A?displayProperty=nameWithType>을 선택합니다.|
<xref:System.Activator.CreateInstance(System.String,System.String)?displayProperty=nameWithType><p><xref:System.Activator.CreateInstance(System.String,System.String,System.Object[])?displayProperty=nameWithType><p><xref:System.Activator.CreateInstance(System.String,System.String,System.Boolean,System.Reflection.BindingFlags,System.Reflection.Binder,System.Object[],System.Globalization.CultureInfo,System.Object[])?displayProperty=nameWithType>|`Load-by-name`.|호출자에서 유추됩니다.<p><xref:System.Type> 인수를 사용하는 <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> 메서드를 선택합니다.|

## <a name="algorithm"></a>알고리즘

다음 알고리즘은 런타임에서 관리 어셈블리를 로드하는 방법을 설명합니다.

1. `active` <xref:System.Runtime.Loader.AssemblyLoadContext>를 확인합니다.

    - 정적 어셈블리 참조의 경우 `active` <xref:System.Runtime.Loader.AssemblyLoadContext>는 참조하는 어셈블리를 로드한 인스턴스입니다.
    - 기본 API는 `active` <xref:System.Runtime.Loader.AssemblyLoadContext>를 명시적으로 만듭니다.
    - 다른 API는 `active` <xref:System.Runtime.Loader.AssemblyLoadContext>를 유추합니다. 이러한 API의 경우 <xref:System.Runtime.Loader.AssemblyLoadContext.CurrentContextualReflectionContext?displayProperty=nameWithType> 속성이 사용됩니다. 해당 값이 `null`이면 유추된 <xref:System.Runtime.Loader.AssemblyLoadContext> 인스턴스가 사용됩니다.
    - 위의 표를 참조하세요.

2. `Load-by-name` 메서드의 경우 활성 <xref:System.Runtime.Loader.AssemblyLoadContext>가 어셈블리를 로드합니다. 우선 순위에 따라 정렬:
    - 해당 `cache-by-name`을 확인 중입니다.

    - <xref:System.Runtime.Loader.AssemblyLoadContext.Load%2A?displayProperty=nameWithType> 함수를 호출 중입니다.

    - <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> 인스턴스의 캐시를 확인하고 [관리 어셈블리 기본 검색](default-probing.md#managed-assembly-default-probing) 논리를 실행합니다.

    - 활성 AssemblyLoadContext에 대한 <xref:System.Runtime.Loader.AssemblyLoadContext.Resolving?displayProperty=nameWithType> 이벤트를 발생시킵니다.

    - <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> 이벤트가 발생 중입니다.

3. 다른 유형의 로드의 경우 `active` <xref:System.Runtime.Loader.AssemblyLoadContext>가 어셈블리를 로드합니다. 우선 순위에 따라 정렬:
    - 해당 `cache-by-name`을 확인 중입니다.

    - 지정된 경로 또는 원시 어셈블리 개체에서 로드하는 중입니다.

4. 두 경우 모두 어셈블리가 새로 로드되면 다음을 수행합니다.
   - <xref:System.AppDomain.AssemblyLoad?displayProperty=nameWithType> 이벤트가 발생합니다.
   - 참조가 어셈블리의 <xref:System.Runtime.Loader.AssemblyLoadContext> 인스턴스의 `cache-by-name`에 추가됩니다.

5. 어셈블리가 있는 경우 필요에 따라 `active` <xref:System.Runtime.Loader.AssemblyLoadContext> 인스턴스의 `cache-by-name`에 참조가 추가됩니다.
