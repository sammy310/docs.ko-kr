---
ms.openlocfilehash: 975e331ad3e7bd7e0e8f49b62795c6acc7031ca9
ms.sourcegitcommit: 1e8382d0ce8b5515864f8fbb178b9fd692a7503f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2020
ms.locfileid: "89656346"
---
### <a name="winforms-and-wpf-apps-use-microsoftnetsdk"></a>WinForms 및 WPF 앱이 Microsoft.NET.Sdk를 사용함

Windows Forms 앱과 WPF(Windows Presentation Framework) 앱은 이제 .NET Core WinForms 및 WPF SDK(`Microsoft.NET.Sdk.WindowsDesktop`) 대신 .NET SDK(`Microsoft.NET.Sdk`)를 사용합니다.

#### <a name="change-description"></a>변경 내용 설명

이전 .NET Core 버전에서는 WinForms 앱과 WPF 앱이 별도의 [프로젝트 SDK](../../../../docs/core/project-sdk/overview.md)(`Microsoft.NET.Sdk.WindowsDesktop`)를 사용했습니다. .NET 5.0부터 WinForms 및 WPF SDK는 .NET SDK(`Microsoft.NET.Sdk`)와 통합되었습니다. 또한 .NET 5에서 새 [TFM(대상 프레임워크 모니커)](../../../../docs/standard/frameworks.md)이 `netcoreapp` 및 `netstandard`를 대체합니다. 다음 예제에서는 .NET 5.0 이상으로 대상을 변경할 때 WPF 프로젝트 파일에 수행해야 하는 변경을 보여 줍니다.

이전 .NET Core 버전:

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.1</TargetFramework>
    <UseWPF>true</UseWPF>
  </PropertyGroup>

</Project>
```

.NET 5.0 이상 버전:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>net5.0-windows</TargetFramework>
    <UseWPF>true</UseWPF>
  </PropertyGroup>

</Project>
```

#### <a name="version-introduced"></a>도입된 버전

.NET 5.0 미리 보기 8

#### <a name="recommended-action"></a>권장 조치

WPF 또는 Windows Forms 프로젝트 파일에서 다음을 수행합니다.

- `Sdk` 특성을 `Microsoft.NET.Sdk`로 업데이트합니다.
- `TargetFramework` 속성을 `net5.0-windows`로 업데이트합니다.

#### <a name="category"></a>범주

- Windows Forms
- WPF(Windows Presentation Framework)

#### <a name="affected-apis"></a>영향을 받는 API

API 분석을 통해 검색할 수 없습니다.

<!-- 

#### Affected APIs

Not detectable via API analysis.

-->
