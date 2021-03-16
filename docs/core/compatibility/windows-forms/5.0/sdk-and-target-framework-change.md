---
title: '호환성이 손상되는 변경: WinForms 및 WPF 앱이 Microsoft.NET.Sdk를 사용함'
description: Windows Forms 및 Windows Presentation Framework 앱이 .NET Core WinForms 및 WPF SDK 대신 .NET SDK를 사용하는 .NET 5의 호환성이 손상되는 변경에 관해 알아봅니다.
ms.date: 09/18/2020
ms.openlocfilehash: 408233f6f8801fb3d4e53beab28c26a777a4a3e1
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256207"
---
# <a name="winforms-and-wpf-apps-use-microsoftnetsdk"></a>WinForms 및 WPF 앱이 Microsoft.NET.Sdk를 사용함

Windows Forms 앱과 WPF(Windows Presentation Framework) 앱은 이제 .NET Core WinForms 및 WPF SDK(`Microsoft.NET.Sdk.WindowsDesktop`) 대신 .NET SDK(`Microsoft.NET.Sdk`)를 사용합니다.

## <a name="change-description"></a>변경 내용 설명

이전 .NET Core 버전에서는 WinForms 앱과 WPF 앱이 별도의 [프로젝트 SDK](../../../project-sdk/overview.md)(`Microsoft.NET.Sdk.WindowsDesktop`)를 사용했습니다. .NET 5부터 WinForms 및 WPF SDK는 .NET SDK(`Microsoft.NET.Sdk`)와 통합되었습니다. 또한 .NET 5에서 새 [TFM(대상 프레임워크 모니커)](../../../../standard/frameworks.md)이 `netcoreapp` 및 `netstandard`를 대체합니다. 다음 예제에서는 .NET 5 이상으로 대상을 변경할 때 WPF 프로젝트 파일에서 변경할 내용을 보여 줍니다.

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

.NET 5 이상 버전:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>net5.0-windows</TargetFramework>
    <UseWPF>true</UseWPF>
  </PropertyGroup>

</Project>
```

## <a name="version-introduced"></a>도입된 버전

.NET SDK 5.0.100

## <a name="recommended-action"></a>권장 조치

WPF 또는 Windows Forms 프로젝트 파일에서 다음을 수행합니다.

- `Sdk` 특성을 `Microsoft.NET.Sdk`로 업데이트합니다.
- `TargetFramework` 속성을 `net5.0-windows`로 업데이트합니다.

## <a name="affected-apis"></a>영향을 받는 API

API 분석을 통해 검색할 수 없습니다.

<!--

### Affected APIs

Not detectable via API analysis.

### Category

- Windows Forms
- Windows Presentation Framework (WPF)

-->
