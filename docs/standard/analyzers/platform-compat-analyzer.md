---
title: 플랫폼 호환성 분석기
description: 플랫폼 간 앱 및 라이브러리에서 플랫폼 호환성 문제를 감지하는 데 도움이 되는 Roslyn 분석기입니다.
author: buyaa-n
ms.date: 09/17/2020
ms.openlocfilehash: 4e842e5bbe90dd5006d9b27d0365f908b6441997
ms.sourcegitcommit: 1274a1a4a4c7e2eaf56b38da76ef7cec789726ef
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/28/2020
ms.locfileid: "91406590"
---
# <a name="platform-compatibility-analyzer"></a>플랫폼 호환성 분석기

"One .NET": 모든 유형의 애플리케이션을 빌드하기 위한 단일 통합 플랫폼이라는 모토를 들어 보셨을 것입니다. .NET 5.0 SDK에는 ASP.NET Core, Entity Framework Core, WinForms, WPF, Xamarin 및 ML.NET가 포함되어 있으며, 향후 더 많은 플랫폼에 대한 지원이 추가될 예정입니다. .NET 5.0은 .NET의 다양한 플랫폼을 일일이 고려하지 않아도 없는 환경을 제공하기 위해 노력하고 있지만, 기본 OS(운영 체제)를 완전히 추상화하려고 하지는 않습니다. 플랫폼별 API(예: P/Invoke, WinRT 또는 iOS 및 Android용 Xamarin 바인딩)를 계속해서 호출할 수 있습니다.

그러나 한 구성 요소에서 플랫폼별 API를 사용하면 코드는 더 이상 모든 플랫폼에서 작동하지 않을 것입니다. 개발자가 플랫폼별 API를 실수로 사용하는 경우 진단을 받을 수 있도록 디자인 타임에 이를 감지하는 방법이 필요했습니다. 이러한 목표를 달성하기 위해 .NET 5.0에서 개발자가 적절한 플랫폼별 API를 식별하고 사용하는 데 도움이 되는 [플랫폼 호환성 분석기](/visualstudio/code-quality/ca1416) 및 보완 API를 도입했습니다.
새 API의 구성 내용:

- API에 플랫폼별 주석을 달기 위한 <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute>와 API에 특정 OS에서 지원되지 않음 주석을 달기 위한 <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute>. 이러한 특성은 선택적으로 버전 번호를 포함할 수 있으며 핵심 .NET 라이브러리의 일부 플랫폼별 API에 이미 적용되어 있습니다.
- 플랫폼별 API를 안전하게 호출하기 위한 <xref:System.OperatingSystem?displayProperty=nameWithType> 클래스의 `Is<Platform>()` 및 `Is<Platform>VersionAtLeast(int major, int minor = 0, int build = 0, int revision = 0)` 정적 메서드. 예를 들어 <xref:System.OperatingSystem.IsWindows?displayProperty=nameWithType>를 사용하여 Windows 관련 API에 대한 호출을 보호할 수 있으며, <xref:System.OperatingSystem.IsWindowsVersionAtLeast%2A?displayProperty=nameWithType>()를 사용하여 버전이 지정된 Windows 관련 API 호출을 보호할 수 있습니다. 이러한 메서드를 플랫폼별 API 참조의 가드로 사용할 수 있는 방법에 대해서는 [예제](#guard-platform-specific-apis-with-guard-methods)를 참조하세요.

> [!TIP]
> 플랫폼 호환성 분석기는 [.NET API 분석기](../../standard/analyzers/api-analyzer.md)의 [플랫폼 간 문제 검색](../../standard/analyzers/api-analyzer.md#discover-cross-platform-issues) 기능을 업그레이드하고 대체합니다.

## <a name="prerequisites"></a>사전 요구 사항

플랫폼 호환성 분석기는 Roslyn 코드 품질 분석기 중 하나입니다. .NET 5.0부터 이러한 분석기는 [.NET SDK](../../fundamentals/productivity/code-analysis.md)에 포함되어 있습니다. 플랫폼 호환성 분석기는 `net5.0` 이상 버전을 대상으로 하는 프로젝트에서만 기본으로 사용됩니다. 그러나 다른 프레임워크를 대상으로 하는 프로젝트에도 [사용](/visualstudio/code-quality/ca1416.md#configurability)할 수 있습니다.

## <a name="how-the-analyzer-determines-platform-dependency"></a>분석기에서 플랫폼 종속성을 확인하는 방법

- **특성이 지정되지 않은 API**는 **모든 OS 플랫폼**에서 작동하는 것으로 간주됩니다.
- `[SupportedOSPlatform("platform")]`으로 표시된 API는 지정된 OS `platform`에만 이식할 수 있는 것으로 간주됩니다.
  - 이 특성을 여러 번 적용하여 **다중 플랫폼 지원**(`[SupportedOSPlatform("windows"), SupportedOSPlatform("Android6.0")]`)을 나타낼 수 있습니다.
  - 적절한 **플랫폼 컨텍스트** 없이 플랫폼별 API를 참조하는 경우 분석기가 **경고**를 생성합니다.
    - 프로젝트가 지원되는 플랫폼을 대상으로 하지 않는 경우(예: 프로젝트가 `<TargetFramework>net5.0-ios14.0</TargetFramework>`를 대상으로 할 때 Windows 관련 API를 호출) **경고합니다**.
    - 프로젝트가 다중 대상으로 지정된 경우(`<TargetFramework>net5.0</TargetFramework>`) **경고합니다**.
    - **지정된 플랫폼**을 대상으로 하는 프로젝트 내에서 플랫폼별 API를 참조하는 경우(예: 프로젝트가 `<TargetFramework>net5.0-windows</TargetFramework>`를 대상으로 할 때 Windows 관련 API를 호출) **경고하지 않습니다**.
    - 플랫폼별 API 호출이 해당하는 플랫폼 검사 메서드(예: `if(OperatingSystem.IsWindows())`)로 보호되는 경우 **경고하지 않습니다**.
    - 플랫폼별 API가 동일한 플랫폼별 컨텍스트에서 참조되는 경우(**호출 사이트에도 `[SupportedOSPlatform("platform")` 특성이 지정됨**) **경고하지 않습니다**.
- `[UnsupportedOSPlatform("platform")]`으로 표시된 API는 지정된 OS `platform`에서만 지원되지 않고 다른 모든 플랫폼에서는 지원되는 것으로 간주됩니다.
  - 이 특성은 서로 다른 플랫폼에서 여러 번 적용될 수 있습니다(예: `[UnsupportedOSPlatform("iOS"), UnsupportedOSPlatform("Android6.0")]`).
  - 분석기는 `platform`이 호출 사이트에 유효한 경우에만 **경고**를 생성합니다.
    - 프로젝트가 지원되지 않는 것으로 지정된 플랫폼을 대상으로 하는 경우(예: 호출 사이트가 `<TargetFramework>net5.0-windows</TargetFramework>`를 대상으로 할 때 API에 `[UnsupportedOSPlatform("windows")]` 특성이 지정됨) **경고합니다**.
    - 프로젝트가 다중 대상으로 지정되고 `platform`이 기본 [MSBuild `<SupportedPlatform>`](https://github.com/dotnet/sdk/blob/master/src/Tasks/Microsoft.NET.Build.Tasks/targets/Microsoft.NET.SupportedPlatforms.props) 항목 그룹에 포함되거나 `platform`이 수동으로 `MSBuild` \<SupportedPlatform> 항목 그룹에 포함된 경우 **경고합니다**.

      ```XML
      <ItemGroup>
          <SupportedPlatform Include="platform" />
      </ItemGroup>
      ```

    - 지원되지 않는 플랫폼을 대상으로 하지 않거나 다중 대상으로 지정된 앱을 빌드하고 플랫폼이 기본 [MSBuild `<SupportedPlatform>`](https://github.com/dotnet/sdk/blob/master/src/Tasks/Microsoft.NET.Build.Tasks/targets/Microsoft.NET.SupportedPlatforms.props) 항목 그룹에 포함되지 않은 경우 **경고하지 않습니다**.
- 두 특성 모두 플랫폼 이름의 일부로 버전 번호를 사용하거나 사용하지 않고 인스턴스화할 수 있습니다.
  - 버전 번호는 `major.minor[.build[.revision]]` 형식입니다. `major.minor`는 필수 항목이고 `build` 및 `revision` 부분은 선택 사항입니다. 예를 들어 "Windows 7.0"은 Windows 버전 7.0을 나타내지만 "Windows"는 Windows 0.0으로 해석됩니다.

자세한 내용은 [특성 작동 방식 및 관련 진단 예제](#examples-of-how-the-attributes-work-and-what-diagnostics-they-produce)를 참조하세요.

### <a name="advanced-scenarios-for-combining-attributes"></a>특성 결합을 위한 고급 시나리오

- `[SupportedOSPlatform]` 및 `[UnsupportedOSPlatform]` 특성의 조합이 있는 경우 모든 특성은 OS 플랫폼 식별자로 그룹화됩니다.
  - **지원 목록**. 각 OS 플랫폼의 가장 낮은 버전이 `[SupportedOSPlatform]` 특성인 경우 API는 나열된 플랫폼에서만 지원되고 다른 모든 플랫폼에서는 지원되지 않는 것으로 간주됩니다. 각 플랫폼에 대한 선택적 `[UnsupportedOSPlatform]` 특성은 지원되는 최소 버전보다 상위 버전에만 적용될 수 있으며, 이는 지정된 버전부터 API가 제거됨을 나타냅니다.

    ```csharp
    // The API only supported on Windows 8.0 and later, not supported for all other.
    // The API is removed/unsupported from version 10.0.19041.0.
    [SupportedOSPlatform("windows8.0")]
    [UnsupportedOSPlatform("windows10.0.19041.0")]
    public void ApiSupportedFromWindows80SupportFromCertainVersion();
    ```

  - **미지원 목록**. 각 OS 플랫폼의 가장 낮은 버전이 `[UnsupportedOSPlatform]` 특성인 경우 API는 나열된 플랫폼에서만 지원되지 않고 다른 모든 플랫폼에서는 지원되는 것으로 간주됩니다. 이 목록에는 동일한 플랫폼의 상위 버전에 `[SupportedOSPlatform]` 특성이 지정될 수 있습니다. 이는 해당 버전부터 API가 지원됨을 나타냅니다.
  
    ```csharp
    // The API was unsupported on Windows until version 10.0.19041.0.
    // The API is considered supported everywhere else without constraints.
    [UnsupportedOSPlatform("windows")]
    [SupportedOSPlatform("windows10.0.19041.0")]
    public void ApiSupportedFromWindows8UnsupportFromWindows10();
    ```

  - **불일치 목록**. 일부 플랫폼의 가장 낮은 버전이 `[SupportedOSPlatform]`이고 다른 플랫폼에 대해서 `[UnsupportedOSPlatform]`인 경우 불일치로 간주됩니다(분석기에 대해 지원되지 않음).
  - `[SupportedOSPlatform]` 및 `[UnsupportedOSPlatform]` 특성의 가장 낮은 버전이 동일한 경우 분석기는 해당 플랫폼을 **지원 목록**의 일부로 간주합니다.
- 플랫폼 특성은 다양한 플랫폼 이름 및/또는 버전을 사용하는 형식, 멤버(메서드, 필드, 속성 및 이벤트) 및 어셈블리에 적용할 수 있습니다.
  - 최상위 수준 `target`에서 적용된 특성은 모든 멤버 및 형식에 영향을 미칩니다.
  - 자식 수준 특성은 "자식 주석은 플랫폼 지원 범위를 축소할 수 있지만 확장할 수 없음" 규칙을 준수하는 경우에만 적용됩니다.
    - 부모에 **지원** 목록만 지정된 경우 자식 멤버 특성은 새 플랫폼 지원을 추가할 수 없습니다(부모 지원 범위를 확장하기 때문). 새 플랫폼 지원은 부모 자체에만 추가할 수 있습니다. 그러나 동일한 플랫폼의 상위 버전에 `Supported` 특성이 지정될 수 있으며 이 경우 지원 범위가 축소됩니다. 동일한 플랫폼에 `Unsupported` 특성도 지정될 수 있고 이러한 경우에도 부모 지원 범위가 축소됩니다.
    - 부모에 **미지원** 목록이 지정된 경우 자식 멤버 특성은 새 플랫폼 지원을 추가할 수 있지만(부모 지원 범위를 축소하기 때문), 부모와 동일한 플랫폼에 `Supported` 특성이 지정될 수는 없습니다(부모 지원 범위를 확장하기 때문). 동일한 플랫폼에 대한 지원은 원래 `Unsupported` 특성이 적용된 부모 수준에만 추가할 수 있습니다.
  - 동일한 `platform` 이름의 API에 `[SupportedOSPlatform("platformVersion")]`를 두 번 이상 적용한 경우 분석기는 최소 버전을 사용하는 API만 고려합니다.
  - 동일한 `platform` 이름의 API에 `[UnsupportedOSPlatform("platformVersion")]`을 세 번 이상 적용한 경우 분석기는 최소 버전을 사용하는 API 두 개만 고려합니다.
  
  > [!NOTE]
  > 처음에는 지원되었지만 상위 버전에서 지원되지 않는(제거된) API는 이후 버전에서도 다시 지원되지 않습니다.

### <a name="examples-of-how-the-attributes-work-and-what-diagnostics-they-produce"></a>특성 작동 방식 및 관련 진단 예제

  ```csharp
  // An API supported only on Windows.
  [SupportedOSPlatform("Windows")]
  public void WindowsOnlyApi() { }

  // an API supported on Windows and Linux.
  [SupportedOSPlatform("Windows")]
  [SupportedOSPlatform("Linux")]
  public void SupportedOnWindowsAndLinuxOnly() { }

  // an API only supported on Windows 8.0 and later, not supported for all other.
  // an API is removed/unsupported from version 10.0.19041.0.
  [SupportedOSPlatform("windows8.0")]
  [UnsupportedOSPlatform("windows10.0.19041.0")]
  public void ApiSupportedFromWindows8UnsupportFromWindows10() { }

  // an Assembly supported on Windows, the API added from version 10.0.19041.0.
  [assembly: SupportedOSPlatform("Windows")]
  [SupportedOSPlatform("windows10.0.19041.0")]
  public void AssemblySupportedOnWindowsApiSupportedFromWindows10() { }

  public void Caller()
  {
      WindowsOnlyApi(); // warns: 'WindowsOnlyApi' is supported on 'windows'

      // warns: 'SupportedOnWindowsAndLinuxOnly' is supported on 'Windows'
      // warns: 'SupportedOnWindowsAndLinuxOnly' is supported on 'Linux'
      SupportedOnWindowsAndLinuxOnly();

      // warns: 'ApiSupportedFromWindows8UnsupportFromWindows10' is supported on 'windows' 8.0 and later  
      // warns: 'ApiSupportedFromWindows8UnsupportFromWindows10' is unsupported on 'windows' 10.0.19041.0 and later
      ApiSupportedFromWindows8UnsupportFromWindows10();

      // warns: 'ApiSupportedFromWindows8UnsupportFromWindows10' is supported on 'windows' 10.0.19041.0 and later
      // for same platform analyzer only warn for the latest version.
      AssemblySupportedOnWindowsApiSupportedFromWindows10();
  }

  // an API not supported on android but supported on all other.
  [UnsupportedOSPlatform("android")]  
  public void DoesNotWorkOnAndroid() { }

  // an API was unsupported on Windows until version 8.0.
  // The API is considered supported everywhere else without constraints.
  [UnsupportedOSPlatform("windows")]
  [SupportedOSPlatform("windows8.0")]
  public void StartedWindowsSupportFromVersion8() { }

  // an API was unsupported on Windows until version8.0.
  // Then the API is removed (unsupported) from version 10.0.19041.0.
  // The API is considered supported everywhere else without constraints.
  [UnsupportedOSPlatform("windows")]
  [SupportedOSPlatform("windows8.0")]
  [UnsupportedOSPlatform("windows10.0.19041.0")]
  public void StartedWindowsSupportFrom8UnsupportedFrom10() { }

  public void Caller2()
  {
      DoesNotWorkOnAndroid(); // warns 'DoesNotWorkOnAndroid' is unsupported on 'android'

      // warns:'StartedWindowsSupportFromVersion8' is unsupported on 'windows'  
      // warns:'StartedWindowsSupportFromVersion8' is supported on 'windows' 8.0 and later
      StartedWindowsSupportFromVersion8();

      // warns:'StartedWindowsSupportFrom8UnsupportedFrom10' is unsupported on 'windows'  
      // warns:'StartedWindowsSupportFrom8UnsupportedFrom10' is supported on 'windows' 8.0 and later
      // even there were 3 diagnostics found analyzer warn only for the first 2.
      StartedWindowsSupportFrom8UnsupportedFrom10();
  }
  ```

## <a name="handle-reported-warnings"></a>보고된 경고 처리

이러한 진단을 처리하는 권장 방법은 적절한 플랫폼에서 실행되는 경우에만 플랫폼별 API를 호출하는 것입니다. 다음은 경고를 해결하는 데 사용할 수 있는 옵션입니다. 상황에 가장 적합한 것을 선택하세요.

- **호출를 보호합니다**. 런타임에 코드를 조건부로 호출하여 이를 달성할 수 있습니다. 플랫폼 검사 방법 중 하나(예: `OperatingSystem.Is<Platform>()` 또는 `OperatingSystem.Is<Platform>VersionAtLeast(int major, int minor = 0, int build = 0, int revision = 0)`)를 사용하여 원하는 `Platform`에서 실행하고 있는지 확인합니다.

- **호출 사이트를 플랫폼별로 표시합니다**. 사용자 고유의 API를 플랫폼별로 표시하여 요구 사항을 효과적으로 호출자에게 전달할 수도 있습니다. 참조되는 플랫폼 종속 호출과 동일한 특성을 사용하여 포함하는 메서드나 형식 또는 전체 어셈블리를 표시합니다. [예제](#mark-call-site-as-platform-specific).

- **플랫폼 검사를 사용하여 호출 사이트를 어설션합니다**. 런타임에 추가 `if` 문의 오버헤드를 원친 않는 경우 대신 <xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType>를 사용합니다. [예제](#assert-the-call-site-with-platform-check).

- **코드를 삭제합니다**. Windows 사용자가 코드를 사용할 때 충실도가 상실되다는 의미이므로 일반적으로 개발자가 원하는 옵션은 아닙니다. 플랫폼 간 대안이 있는 경우 플랫폼별 API를 통해 사용하는 것이 더 좋을 수 있습니다.

- **경고를 표시하지 않습니다**. editor.config 또는 `#pragma warning disable ca1416`를 통해 경고를 표시하지 않을 수도 있습니다. 그러나 플랫폼별 API를 사용하는 경우 이 옵션은 마지막 수단이어야 합니다.

### <a name="guard-platform-specific-apis-with-guard-methods"></a>가드 메서드를 사용하여 플랫폼별 API를 보호

가드 메서드의 플랫폼 이름은 호출하는 플랫폼 종속 API 플랫폼 이름과 일치해야 합니다. 호출하는 API의 플랫폼 문자열에 버전이 포함되는 경우

- `[SupportedOSPlatform("platformVersion")]` 특성의 경우 가드 메서드 플랫폼 `version`이 호출하는 플랫폼의 `Version`보다 크거나 같아야 합니다.
- `[UnsupportedOSPlatform("platformVersion")]` 특성의 경우 가드 메서드 플랫폼 `version`이 호출하는 플랫폼의 `Version`보다 작거나 같아야 합니다.

  ```csharp
  public void CallingSupportedOnlyApis() // Allow list calls
  {
      if (OperatingSystem.IsWindows())
      {
          WindowsOnlyApi(); // will not warn
      }

      if (OperatingSystem.IsLinux())
      {
          SupportedOnWindowsAndLinuxOnly(); // will not warn, within one of the supported context
      }

      // Can use &&, || logical operators to guard combined attributes
      if (OperatingSystem.IsWindowsVersionAtLeast(8) && !OperatingSystem.IsWindowsVersionAtLeast(10.0.19041)))
      {
          ApiSupportedFromWindows8UnsupportFromWindows10();
      }

      if (OperatingSystem.IsWindowsVersionAtLeast(10, 0, 1903))
      {
          AssemblySupportedOnWindowsApiSupportedFromWindows10(); // Only need to check latest supported version
      }
  }

  public void CallingUnsupportedApis()
  {
      if (!OperatingSystem.IsAndroid())
      {
          DoesNotWorkOnAndroid(); // will not warn
      }

      if (!OperatingSystem.IsWindows() || OperatingSystem.IsWindowsVersionAtLeast(8))
      {
          StartedWindowsSupportFromVersion8(); // will not warn
      }

      if (!OperatingSystem.IsWindows() || // supported all other platforms
         (OperatingSystem.IsWindowsVersionAtLeast(8) && !OperatingSystem.IsWindowsVersionAtLeast(10, 0, 1903)))
      {
          StartedWindowsSupportFrom8UnsupportedFrom10(); // will not warn
      }
  }
  ```

- 새 <xref:System.OperatingSystem> API를 사용할 수 없는 netstandard.또는 netcoreapp을 대상으로 하는 코드를 보호해야 하는 경우 <xref:System.Runtime.InteropServices.RuntimeInformation.IsOSPlatform%2A?displayProperty=nameWithType> API를 사용할 수 있으며 분석기에서 이 API가 적용합니다. 하지만 <xref:System.OperatingSystem>에 추가된 새 API만큼 최적화되지는 않았습니다. <xref:System.Runtime.InteropServices.OSPlatform> 구조체에서 플랫폼이 지원되지 않는 경우 <xref:System.Runtime.InteropServices.OSPlatform.Create%2A?displayProperty=nameWithType>("platform")을 사용할 수 있습니다(분석기에서도 적용됨).

  ```csharp
  public void CallingSupportedOnlyApis()
  {
      if (RuntimeInformation.IsOSPlatform(OSPlatform.Windows))
      {
          SupportedOnWindowsAndLinuxOnly(); // will not warn
      }

      if (RuntimeInformation.IsOSPlatform(OSPlatform.Create("browser")))
      {
          ApiOnlySupportedOnBrowser(); // call of browser specific API
      }
  }
  ```

### <a name="mark-call-site-as-platform-specific"></a>호출 사이트를 플랫폼별로 표시

플랫폼 이름은 호출하는 플랫폼 종속 API와 일치해야 합니다. 플랫폼 문자열에 버전이 포함되는 경우

- `[SupportedOSPlatform("platformVersion")]` 특성의 경우 호출 사이트 플랫폼 `version`이 호출하는 플랫폼의 `Version`보다 크거나 같아야 합니다.
- `[UnsupportedOSPlatform("platformVersion")]` 특성의 경우 호출 사이트 플랫폼 `version`이 호출하는 플랫폼의 `Version`보다 작거나 같아야 합니다.

  ```csharp
  // an API supported only on Windows.
  [SupportedOSPlatform("windows")]
  public void WindowsOnlyApi() { }

  // an API supported on Windows and Linux.
  [SupportedOSPlatform("Windows")]
  [SupportedOSPlatform("Linux")]
  public void SupportedOnWindowsAndLinuxOnly() { }

  // an API only supported on Windows 8.0 and later, not supported for all other.
  // an API is removed/unsupported from version 10.0.19041.0.
  [SupportedOSPlatform("windows8.0")]
  [UnsupportedOSPlatform("windows10.0.19041.0")]
  public void ApiSupportedFromWindows8UnsupportFromWindows10() { }

  // an Assembly supported on Windows, the API added from version 10.0.19041.0.
  [assembly: SupportedOSPlatform("Windows")]
  [SupportedOSPlatform("windows10.0.19041.0")]
  public void AssemblySupportedOnWindowsApiSupportedFromWindows10() { }

  [SupportedOSPlatform("windows8.0")] // call site attributed Windows 8.0 or above.
  public void Caller()
  {
      WindowsOnlyApi(); // will not warn as call site is for Windows.

      // will not warn as call site is for Windows.
      SupportedOnWindowsAndLinuxOnly();

      // will not warn for the API's [SupportedOSPlatform("windows8.0")] attribute.
      // Warns: 'ApiSupportedFromWindows8UnsupportFromWindows10' is unsupported on 'windows' 10.0.19041.0 and later
      ApiSupportedFromWindows8UnsupportFromWindows10();

      // warns: 'ApiSupportedFromWindows8UnsupportFromWindows10' is supported on 'windows' 10.0.19041.0 and later
      // as the call site version is lower than calling version.
      AssemblySupportedOnWindowsApiSupportedFromWindows10();
  }

  [SupportedOSPlatform("windows11.0")] // call site attributed with windows 11.0 or above.
  public void Caller2()
  {
      // Warns: 'ApiSupportedFromWindows8UnsupportFromWindows10' is unsupported on 'windows' 10.0.19041.0 and later
      ApiSupportedFromWindows8UnsupportFromWindows10();

      // will not warn as call site version higher than calling API.
      AssemblySupportedOnWindowsApiSupportedFromWindows10();
  }

  [SupportedOSPlatform("windows8.0")]
  [UnsupportedOSPlatform("windows10.0.19041.0")] // call site supports Windows from version 8.0 to 10.0.19041.0.
  public void Caller3()
  {
      // will not warn as caller has exact same attributes.
      ApiSupportedFromWindows8UnsupportFromWindows10();

      // Warns: 'ApiSupportedFromWindows8UnsupportFromWindows10' is supported on 'windows' 10.0.19041.0 and later
      // As call site stopped support from that version.
      AssemblySupportedOnWindowsApiSupportedFromWindows10();
  }

  // an API not supported on Android but supported on all other.
  [UnsupportedOSPlatform("android")]  
  public void DoesNotWorkOnAndroid() { }

  // an API was unsupported on Windows until version 8.0.
  // The API is considered supported everywhere else without constraints.
  [UnsupportedOSPlatform("windows")]
  [SupportedOSPlatform("windows8.0")]
  public void StartedWindowsSupportFromVersion8() { }

  // an API was unsupported on Windows until version8.0.
  // Then the API is removed (unsupported) from version 10.0.19041.0.
  // The API is considered supported everywhere else without constraints.
  [UnsupportedOSPlatform("windows")]
  [SupportedOSPlatform("windows8.0")]
  [UnsupportedOSPlatform("windows10.0.19041.0")]
  public void StartedWindowsSupportFrom8UnsupportedFrom10() { }

  [UnsupportedOSPlatform("windows")] // Caller no support Windows for any version.
  public void Caller4()
  {
      DoesNotWorkOnAndroid(); // warns 'DoesNotWorkOnAndroid' is unsupported on 'Android'.

      // will not warns as the call site not support Windows at all, but supports all other.
      StartedWindowsSupportFromVersion8();

      // same, will not warns as the call site not support Windows at all, but supports all other.
      StartedWindowsSupportFrom8UnsupportedFrom10();
  }

  [UnsupportedOSPlatform("windows")]
  [UnsupportedOSPlatform("android")] // Caller not support Windows and Android for any version.
  public void Caller4()
  {
      DoesNotWorkOnAndroid(); // will not warn as call site not supports Android.

      // will not warns as the call site not support Windows at all, but supports all other.
      StartedWindowsSupportFromVersion8();

      // same, will not warns as the call site not support Windows at all, but supports all other.
      StartedWindowsSupportFrom8UnsupportedFrom10();
  }
  ```

### <a name="assert-the-call-site-with-platform-check"></a>플랫폼 검사를 사용하여 호출 사이트를 어설션

[플랫폼 가드 예제](#guard-platform-specific-apis-with-guard-methods)에서 사용되는 모든 조건부 검사는 <xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType>에 대한 조건으로 사용할 수도 있습니다.

  ```csharp
  // An API supported only on Linux.
  [SupportedOSPlatform("linux")]
  public void LinuxOnlyApi() { }

  public void Caller()
  {
      Debug.Assert(OperatingSystem.IsLinux());

      LinuxOnlyApi(); // will not warn
  }
  ```

## <a name="see-also"></a>참고 항목

- [.NET 5의 대상 프레임워크 이름](https://github.com/dotnet/designs/blob/master/accepted/2020/net5/net5.md)
- [API에 플랫폼별 주석 달기 및 사용 검색](https://github.com/dotnet/designs/blob/master/accepted/2020/platform-checks/platform-checks.md)
- [API에 특정 플랫폼에서 지원되지 않음 주석 달기](https://github.com/dotnet/designs/blob/master/accepted/2020/platform-exclusion/platform-exclusion.md)
- [CA1416 플랫폼 호환성 분석기](/visualstudio/code-quality/ca1416)
- [.NET API 분석기](../../standard/analyzers/api-analyzer.md)
