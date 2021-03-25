---
title: SDK 스타일 프로젝트의 대상 프레임워크 - .NET
description: .NET 앱 및 라이브러리의 대상 프레임워크에 대해 알아봅니다.
ms.date: 03/03/2021
ms.prod: dotnet
ms.custom: updateeachrelease
ms.technology: dotnet-standard
ms.openlocfilehash: 9e831726a87493b109578a3546a8f29b7b71cb6c
ms.sourcegitcommit: 46cfed35d79d70e08c313b9c664c7e76babab39e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/10/2021
ms.locfileid: "102604608"
---
# <a name="target-frameworks-in-sdk-style-projects"></a>SDK 스타일 프로젝트의 대상 프레임워크

앱 또는 라이브러리에서 프레임워크를 대상으로 지정하면 앱 또는 라이브러리에서 사용할 수 있도록 하려는 API 집합을 지정하는 것입니다. TFM(대상 프레임워크 모니커)을 사용하여 프로젝트 파일에서 대상 프레임워크를 지정합니다.

앱 또는 라이브러리는 [.NET Standard](net-standard.md) 버전을 대상으로 지정할 수 있습니다. .NET Standard 버전은 모든 .NET 구현체에서 사용할 수 있는 표준화된 API 집합을 나타냅니다. 예를 들어 .NET Standard 1.6을 대상으로 하는 라이브러리는 동일한 코드 기반의 .NET Core 및 .NET Framework에서 동작하는 API에 액세스할 수 있습니다.

앱 또는 라이브러리는 특정 .NET 구현체을 대상으로 지정하여 구현체 관련 API에 액세스할 수도 있습니다. 예를 들어 Xamarin.iOS(예: `Xamarin.iOS10`)를 대상으로 하는 앱은 Xamarin에서 제공하는 iOS 10용 iOS API 래퍼에 액세스하고, UWP(유니버설 Windows 플랫폼, `uap10.0`)를 대상으로 하는 앱은 Windows 10이 실행되는 디바이스용으로 컴파일하는 API에 액세스할 수 있습니다.

일부 대상 프레임워크(예: .NET Framework)에서 API는 프레임워크에서 시스템에 설치하는 어셈블리에 의해 정의되고 애플리케이션 프레임워크 API(예: ASP.NET)를 포함할 수 있습니다.

패키지 기반 대상 프레임워크(예: .NET 5, .NET Core, .NET Standard)에서 API는 앱이나 라이브러리에 포함된 NuGet 패키지에 의해 정의됩니다.

## <a name="latest-versions"></a>최신 버전

다음 표에서는 가장 일반적인 대상 프레임워크, 프레임워크가 참조되는 방법 및 프레임워크에서 구현하는 [.NET Standard](net-standard.md)의 버전을 정의합니다. 이러한 대상 프레임워크 버전은 안정적인 최신 버전입니다. 시험판 버전은 표시되지 않습니다. TFM(대상 프레임워크 모니커)은 .NET 앱 또는 라이브러리의 대상 프레임워크를 지정하기 위해 표준화된 토큰 형식입니다.

| 대상 프레임워크      | 최신 <br/> 안정적인 버전 | TFM(대상 프레임워크 모니커) | 구현된 <br/> .NET Standard 버전 |
| :-: | :-: | :-: | :-: |
| .NET 5                | 5.0                         | net5.0                         | 해당 없음                                     |
| .NET Standard         | 2.1                         | netstandard2.1                 | 해당 없음                                     |
| .NET Core             | 3.1                         | netcoreapp3.1                  | 2.1                                     |
| .NET Framework        | 4.8                         | net48                          | 2.0                                     |

## <a name="supported-target-frameworks"></a>지원되는 대상 프레임워크

대상 프레임워크는 일반적으로 TFM에서 참조됩니다. 다음 표에서는 .NET SDK 및 NuGet 클라이언트에서 지원되는 대상 프레임워크를 보여 줍니다. 동일한 항목은 대괄호 내에 표시됩니다. 예를 들어 `win81`은 `netcore451`과 동일한 TFM입니다.

| 대상 프레임워크           | TFM |
| -------------------------- | --- |
| .NET 5 이상(및 .NET Core)    | netcoreapp1.0<br>netcoreapp1.1<br>netcoreapp2.0<br>netcoreapp2.1<br>netcoreapp2.2<br>netcoreapp3.0<br>netcoreapp3.1<br>net5.0 *<br>net6.0* |
| .NET 표준              | netstandard1.0<br>netstandard1.1<br>netstandard1.2<br>netstandard1.3<br>netstandard1.4<br>netstandard1.5<br>netstandard1.6<br>netstandard2.0<br>netstandard2.1 |
| .NET Framework             | net11<br>net20<br>net35<br>net40<br>net403<br>net45<br>net451<br>net452<br>net46<br>net461<br>net462<br>net47<br>net471<br>net472<br>net48 |
| Windows 스토어              | netcore [netcore45]<br>netcore45 [win] [win8]<br>netcore451 [win81] |
| .NET Micro Framework       | netmf |
| Silverlight                | sl4<br>sl5 |
| Windows Phone              | wp [wp7]<br>wp7<br>wp75<br>wp8<br>wp81<br>wpa81 |
| 유니버설 Windows 플랫폼 | uap [uap10.0]<br>uap10.0 [win10] [netcore50] |

\* .NET 5 이상 TFM에는 일부 운영 체제별 변형이 포함됩니다. 자세한 내용은 [.NET 5+ OS별 TFM](#net-5-os-specific-tfms) 섹션을 참조하세요.

### <a name="net-5-os-specific-tfms"></a>.NET 5+ OS별 TFM

`net5.0` 및 `net6.0` TFM에는 다양한 플랫폼에서 작동하는 기술이 포함되어 있습니다. *OS별 TFM* 을 지정하면 운영 체제와 관련된 API를 앱에서 사용할 수 있도록 합니다(예: Windows Forms 또는 iOS 바인딩). OS별 TFM은 해당 기본 TFM(예: `net5.0` TFM)에 사용할 수 있는 모든 API도 상속합니다.

.NET 5에는 WinForms, WPF 및 UWP API에 대한 Windows 관련 바인딩을 포함하는 `net5.0-windows` OS별 TFM이 도입되었습니다. .NET 6에는 추가 OS별 TFM이 도입되었습니다.

다음 표에서는 .NET 5+ TFM의 호환성을 보여줍니다.

| TFM                | 호환 가능                                                                                                         |
|--------------------|-------------------------------------------------------------------------------------------------------------------------|
| net5.0             | net1..4(NU1701 경고 포함)<br />netcoreapp1..3.1(WinForms 또는 WPF가 참조되는 경우 경고)<br />netstandard1..2.1 |
| net5.0-windows     | netcoreapp1..3.1(`net5.0`에서 상속되는 다른 모든 항목 포함)                                                         |
| net6.0             | (`net5.0`의 후속 버전)                                                                                        |
| net6.0-android     | `xamarin.android`(+`net6.0`에서 상속된 다른 모든 항목)                                                            |
| net6.0-ios         | `xamarin.ios`(+`net6.0`에서 상속된 다른 모든 항목)                                                                |
| net6.0-macos       | `xamarin.mac`(+`net6.0`에서 상속된 다른 모든 항목)                                                                |
| net6.0-maccatalyst | `xamarin.ios`(+`net6.0`에서 상속된 다른 모든 항목)                                                                |
| net6.0-tvos        | `xamarin.tvos`(+`net6.0`에서 상속된 다른 모든 항목)                                                               |
| net6.0-windows     | (`net5.0-windows`의 후속 버전)                                                                                |

여러 플랫폼에서 앱을 이식 가능하게 만들면서 OS별 API에 액세스할 수 있도록 하려면 여러 OS별 TFM을 대상으로 지정하고 `#if` 전처리기 지시문을 사용하여 OS별 API 호출을 기준으로 플랫폼 가드를 추가할 수 있습니다.

#### <a name="suggested-targets"></a>제안된 대상

다음 지침을 사용하여 앱에서 사용할 TFM을 결정합니다.

- 여러 플랫폼으로 이식할 수 있는 앱은 기본 TFM(예: `net5.0`)을 대상으로 해야 합니다. 여기에는 대부분의 라이브러리가 포함되며 ASP.NET Core 및 Entity Framework도 포함됩니다.

- 플랫폼별 라이브러리는 플랫폼별 버전을 대상으로 지정해야 합니다. 예를 들어 WinForms 및 WPF 프로젝트는 `net5.0-windows` 또는 `net6.0-windows`를 대상으로 지정해야 합니다.

- 플랫폼 간 애플리케이션 모델(Xamarin Forms, ASP.NET Core) 및 브리지 팩(Xamarin Essentials)은 최소한 기본 TFM(예: `net6.0`)을 대상으로 지정해야 하지만 추가 플랫폼별 버전을 대상으로 지정하여 더 많은 API 또는 기능을 강화할 수도 있습니다.

#### <a name="os-version-in-tfms"></a>TFM의 OS 버전

TFM의 끝 부분에 선택적 OS 버전을 지정(예: `net6.0-ios13.0`)하여 앱에서 사용 가능한 API를 나타낼 수도 있습니다. (해당 .NET SDK는 릴리스되는 최신 OS 버전에 대한 지원을 포함하도록 업데이트됩니다.) 새로 릴리스된 API에 대한 액세스 권한을 얻으려면 TFM에서 OS 버전을 증가시킵니다. 프로젝트 파일에 `SupportedOSPlatformVersion` 요소를 추가하여 앱이 이전 OS 버전과 계속 호환되도록 하고 이후 버전 API에 대한 호출을 기준으로 가드를 추가할 수 있습니다. `SupportedOSPlatformVersion` 요소는 앱을 실행하는 데 필요한 최소 OS 버전을 나타냅니다.

예를 들어 다음 프로젝트 파일 예제에서는 iOS 14 API를 앱에서 사용할 수 있도록 지정하지만 iOS 13 이상 머신에서 실행할 수 있습니다.

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFramework>net6.0-ios14.0</TargetFramework>
    <SupportedOSPlatformVersion>13.0</SupportedOSPlatformVersion> (minimum os platform version)
  </PropertyGroup>

  ...

</Project>
```

## <a name="how-to-specify-a-target-framework"></a>대상 프레임워크를 지정하는 방법

대상 프레임워크는 프로젝트 파일에서 지정합니다. 단일 대상 프레임워크를 지정하는 경우 [TargetFramework 요소](../core/project-sdk/msbuild-props.md#targetframework)를 사용합니다. 다음 콘솔 앱 프로젝트 파일에서는 .NET 5.0을 대상 프레임워크로 지정하는 방법을 보여 줍니다.

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>net5.0</TargetFramework>
  </PropertyGroup>

</Project>
```

여러 대상 프레임워크를 지정하는 경우 각 대상 프레임워크에 대한 어셈블리를 조건에 따라 참조할 수 있습니다. 코드에서는 *if-then-else* 로직에 전처리기 기호를 사용하여 해당 어셈블리를 조건에 따라 컴파일할 수 있습니다.

다음 라이브러리 프로젝트는 .NET Standard(`netstandard1.4`)의 API 및 .NET Framework(`net40` 및 `net45`)의 API를 대상으로 합니다. 다중 대상 프레임워크에는 복수형 [TargetFrameworks 요소](../core/project-sdk/msbuild-props.md#targetframeworks)를 사용합니다. 라이브러리가 두 개의 .NET Framework TFM에 대해 컴파일되면 `Condition` 특성에 구현 관련 패키지가 포함됩니다.

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFrameworks>netstandard1.4;net40;net45</TargetFrameworks>
  </PropertyGroup>

  <!-- Conditionally obtain references for the .NET Framework 4.0 target -->
  <ItemGroup Condition=" '$(TargetFramework)' == 'net40' ">
    <Reference Include="System.Net" />
  </ItemGroup>

  <!-- Conditionally obtain references for the .NET Framework 4.5 target -->
  <ItemGroup Condition=" '$(TargetFramework)' == 'net45' ">
    <Reference Include="System.Net.Http" />
    <Reference Include="System.Threading.Tasks" />
  </ItemGroup>

</Project>
```

라이브러리나 앱에서 [전처리기 지시문](../csharp/language-reference/preprocessor-directives/preprocessor-if.md)으로 조건 코드를 작성하여 각 대상 프레임워크에 대해 컴파일합니다.

```csharp
public class MyClass
{
    static void Main()
    {
#if NET40
        Console.WriteLine("Target framework: .NET Framework 4.0");
#elif NET45
        Console.WriteLine("Target framework: .NET Framework 4.5");
#else
        Console.WriteLine("Target framework: .NET Standard 1.4");
#endif
    }
}
```

빌드 시스템은 SDK 스타일 프로젝트를 사용할 때 [지원되는 대상 프레임워크 버전](#supported-target-frameworks) 표에 표시된 대상 프레임워크를 나타내는 전처리기 기호를 인식합니다. .NET Standard, .NET Core 또는 .NET 5 TFM을 나타내는 기호를 사용할 경우 밑줄로 바꾸고 소문자를 대문자로 변경합니다. 예를 들어 `netstandard1.4`에 대한 기호는 `NETSTANDARD1_4`입니다.

다음은 .NET 대상 프레임워크에 대한 전체 전처리기 기호 목록입니다.

[!INCLUDE [Preprocessor symbols](../../includes/preprocessor-symbols.md)]

## <a name="deprecated-target-frameworks"></a>사용되지 않는 대상 프레임워크

다음 대상 프레임워크는 사용되지 않습니다. 이러한 대상 프레임워크를 대상으로 하는 패키지는 지정된 대체 항목으로 마이그레이션되어야 합니다.

| 사용되지 않는 TFM                                                                             | Replacement |
| ------------------------------------------------------------------------------------------ | ----------- |
| aspnet50<br>aspnetcore50<br>dnxcore50<br>dnx<br>dnx45<br>dnx451<br>dnx452                  | netcoreapp  |
| dotnet<br>dotnet50<br>dotnet51<br>dotnet52<br>dotnet53<br>dotnet54<br>dotnet55<br>dotnet56 | netstandard |
| netcore50                                                                                  | uap10.0     |
| win                                                                                        | netcore45   |
| win8                                                                                       | netcore45   |
| win81                                                                                      | netcore451  |
| win10                                                                                      | uap10.0     |
| winrt                                                                                      | netcore45   |

## <a name="see-also"></a>참고 항목

- [.NET 5의 대상 프레임워크 이름](https://github.com/dotnet/designs/blob/master/accepted/2020/net5/net5.md)
- [데스크톱 앱에서 Windows 런타임 API 호출](/windows/apps/desktop/modernize/desktop-to-uwp-enhance)
- [여러 플랫폼에서 사용할 수 있는 도구로 라이브러리 개발](../core/tutorials/libraries.md)
- [.NET Standard](net-standard.md)
- [.NET Core 버전 관리](../core/versions/index.md)
- [dotnet/standard GitHub repository](https://github.com/dotnet/standard)(dotnet/표준 GitHub 리포지토리)
- [NuGet Tools GitHub Repository](https://github.com/joelverhagen/NuGetTools)(NuGet 도구 GitHub 리포지토리)
- [Framework Profiles in .NET](https://blog.stephencleary.com/2012/05/framework-profiles-in-net.html)(.NET의 프레임워크 프로필)
- [플랫폼 호환성 분석기](analyzers/platform-compat-analyzer.md)
