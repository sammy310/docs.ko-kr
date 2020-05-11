---
title: 위성 어셈블리 로드 알고리즘 - .NET Core
description: .NET Core에서 위성 어셈블리 로드 알고리즘의 세부 정보 설명
ms.date: 08/09/2019
author: sdmaclea
ms.author: stmaclea
ms.openlocfilehash: 17f29a9aca79019daa91736e586bf1b6b753a9ec
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2020
ms.locfileid: "82859522"
---
# <a name="satellite-assembly-loading-algorithm"></a>위성 어셈블리 로드 알고리즘

위성 어셈블리는 언어 및 문화권에 맞게 사용자 지정된 지역화된 리소스를 저장하는 데 사용됩니다.

위성 어셈블리는 일반적인 관리 어셈블리와 다른 로드 알고리즘을 사용합니다.

## <a name="when-are-satellite-assemblies-loaded"></a>위성 어셈블리는 언제 로드되나요?

위성 어셈블리는 지역화된 리소스를 로드할 때 로드됩니다.

지역화된 리소스를 로드하는 기본 API는 <xref:System.Resources.ResourceManager?displayProperty=fullName> 클래스입니다. 궁극적으로 <xref:System.Resources.ResourceManager> 클래스는 각 <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType>에 대해 <xref:System.Reflection.Assembly.GetSatelliteAssembly%2A> 메서드를 호출합니다.

상위 수준 API는 하위 수준 API를 추상화할 수 있습니다.

## <a name="algorithm"></a>알고리즘

.NET Core 리소스 대체 프로세스에는 다음 단계가 포함됩니다.

1. `active` <xref:System.Runtime.Loader.AssemblyLoadContext> 인스턴스를 확인합니다. 모든 경우에 `active` 인스턴스는 실행 중인 어셈블리의 <xref:System.Runtime.Loader.AssemblyLoadContext>입니다.

2. `active` 인스턴스는 요청된 문화권에 대한 위성 어셈블리를 우선순위에 따라 다음과 같이 로드하려고 시도합니다.
    - 해당 캐시를 확인하는 중입니다.
    - 요청된 <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType>(예:`es-MX`)과 일치하는 하위 디렉터리에 대해 현재 실행 중인 어셈블리의 디렉터리를 확인합니다.

        > [!NOTE]
        > 이 기능은 3.0 이전의 .NET Core에서 구현되지 않았습니다.
        >
        > [!NOTE]
        > Linux 및 macOS에서 하위 디렉터리는 대/소문자를 구분하며 다음 중 하나를 수행해야 합니다.
        >
        > - 대/소문자 구분이 정확히 일치합니다.
        > - 소문자여야 합니다.

    - `active`가 <xref:System.Runtime.Loader.AssemblyLoadContext.Default?displayProperty=nameWithType> 인스턴스인 경우 [기본 위성(리소스) 어셈블리 검색](default-probing.md#satellite-resource-assembly-probing) 논리를 실행합니다.

    - <xref:System.Runtime.Loader.AssemblyLoadContext.Load%2A?displayProperty=nameWithType> 함수를 호출 중입니다.

    - <xref:System.Runtime.Loader.AssemblyLoadContext.Resolving?displayProperty=nameWithType> 이벤트가 발생 중입니다.

    - <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> 이벤트가 발생 중입니다.

3. 위성 어셈블리가 로드된 경우:
   - <xref:System.AppDomain.AssemblyLoad?displayProperty=nameWithType> 이벤트가 발생합니다.
   - 어셈블리에서 요청된 리소스를 검색합니다. 런타임이 어셈블리에서 리소스를 찾으면 해당 리소스가 사용됩니다. 리소스를 찾지 못하면 검색을 계속합니다.

    > [!NOTE]
    > 위성 어셈블리 내의 리소스를 찾기 위해 런타임은 <xref:System.Resources.ResourceManager>에서 현재 <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType>에 대해 요청한 리소스 파일을 검색합니다. 리소스 파일 내에서 요청된 리소스 이름을 검색합니다. 둘 중 하나라도 찾지 못하면 리소스가 찾을 수 없는 것으로 처리됩니다.

4. 런타임은 다음에 여러 잠재적인 수준에서 부모 문화권 어셈블리를 검색하며 매번 2-3단계를 반복합니다.

    각 문화권에는 <xref:System.Globalization.CultureInfo.Parent%2A?displayProperty=nameWithType> 속성으로 정의되는 하나의 부모만 있습니다.

    문화권의 <xref:System.Globalization.CultureInfo.Parent%2A> 속성이 <xref:System.Globalization.CultureInfo.InvariantCulture?displayProperty=nameWithType>이면 부모 문화권 검색이 중지됩니다.

    <xref:System.Globalization.CultureInfo.InvariantCulture>의 경우 2-3 단계로 돌아가지 않고 5단계로 계속 진행합니다.

5. 여전히 리소스를 찾을 수 없는 경우 기본(대체) 문화권에 대한 리소스가 사용됩니다.

   일반적으로 기본 문화권의 리소스는 주 애플리케이션 어셈블리에 포함되어 있습니다. 그러나 <xref:System.Resources.NeutralResourcesLanguageAttribute.Location?displayProperty=nameWithType> 속성에 대해 <xref:System.Resources.UltimateResourceFallbackLocation.Satellite?displayProperty=nameWithType>을 지정할 수 있습니다. 이 값은 리소스의 최종 대체 위치가 주 어셈블리가 아닌 위성 어셈블리임을 나타냅니다.

    > [!NOTE]
    > 기본 문화권이 최종 대체(fallback)입니다. 따라서 기본 리소스 파일에 완전한 리소스 세트를 항상 포함하는 것이 좋습니다. 이렇게 하면 예외가 throw되지 않도록 방지하는 데 도움이 됩니다. 전체 집합을 통해 모든 리소스에 대한 대체를 제공하고 사용자에게 항상 리소스가 하나 이상 제공되도록 합니다.

6. 마지막으로
   - 런타임이 기본(대체) 문화권에 대한 리소스 파일을 찾지 못하면 <xref:System.Resources.MissingManifestResourceException> 또는 <xref:System.Resources.MissingSatelliteAssemblyException> 예외가 throw됩니다.
   - 리소스 파일이 있지만 요청된 리소스가 없는 경우 요청에서 `null`을 반환합니다.
