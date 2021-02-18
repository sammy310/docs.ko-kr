---
title: Microsoft.NET.Sdk.Desktop의 MSBuild 속성
description: WPF 및 WinForms가 포함된 .NET 데스크톱 SDK에서 이해하는 MSBuild 속성 및 항목의 참조입니다.
ms.date: 02/04/2021
ms.topic: reference
author: adegeo
ms.author: adegeo
ms.custom: updateeachrelease
no-loc:
- App.xaml
- Application.xaml
- ApplicationDefinition
- Page
- EmbeddedResource
- Compile
- None
ms.openlocfilehash: 6d1903558dd03776a72eb6ee56ddae09fb66615b
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100488248"
---
# <a name="msbuild-reference-for-net-desktop-sdk-projects"></a>.NET 데스크톱 SDK 프로젝트의 MSBuild 참조

이 페이지는 .NET 데스크톱 SDK를 사용하여 WinForms(Windows Forms) 및 WPF(Windows Presentation Foundation) 프로젝트를 구성하는 데 사용하는 MSBuild 속성 및 항목의 참조입니다.

> [!NOTE]
> 이 문서에서는 데스크톱 앱과 관련된 .NET SDK의 MSBuild 속성 하위 집합을 설명합니다. 일반적인 .NET SDK 관련 MSBuild 속성 목록은 [.NET SDK 프로젝트의 MSBuild 참조](msbuild-props.md)를 참조하세요. 일반적인 MSBuild 속성의 목록을 보려면 [일반 MSBuild 속성](/visualstudio/msbuild/common-msbuild-project-properties)을 참조하세요.

## <a name="enable-net-desktop-sdk"></a>.NET 데스크톱 SDK 사용

WinForms 또는 WPF를 사용하려면 프로젝트 파일을 구성합니다.

### <a name="net-50"></a>.NET 5.0

WinForms 또는 WPF 프로젝트의 프로젝트 파일에서 다음 설정을 지정합니다.

- .NET SDK `Microsoft.NET.Sdk`를 대상으로 지정합니다. 자세한 내용은 [프로젝트 파일](overview.md#project-files)을 참조하세요.
- [`TargetFramework`](msbuild-props.md#targetframework)를 `net5.0-windows`로 설정합니다.
- UI 프레임워크 속성(또는 필요한 경우 둘 다)을 추가합니다.
  - [`UseWPF`](#usewpf)를 `true`로 설정하여 WPF를 가져오고 사용합니다.
  - [`UseWindowsForms`](#usewindowsforms)를 `true`로 설정하여 WinForms를 가져오고 사용합니다.
- (선택 사항) `OutputType`을 `WinExe`로 설정합니다. 이렇게 하면 라이브러리가 아닌 앱이 생성됩니다. 라이브러리를 생성하려면 해당 속성을 생략합니다.

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>net5.0-windows</TargetFramework>

    <UseWPF>true</UseWPF>
    <!-- and/or -->
    <UseWindowsForms>true</UseWindowsForms>
  </PropertyGroup>

</Project>
```

### <a name="net-core-31"></a>.NET Core 3.1

WinForms 또는 WPF 프로젝트의 프로젝트 파일에서 다음 설정을 지정합니다.

- .NET SDK `Microsoft.NET.Sdk.WindowsDesktop`을 대상으로 지정합니다. 자세한 내용은 [프로젝트 파일](overview.md#project-files)을 참조하세요.
- [`TargetFramework`](msbuild-props.md#targetframework)를 `netcoreapp3.1`로 설정합니다.
- UI 프레임워크 속성(또는 필요한 경우 둘 다)을 추가합니다.
  - [`UseWPF`](#usewpf)를 `true`로 설정하여 WPF를 가져오고 사용합니다.
  - [`UseWindowsForms`](#usewindowsforms)를 `true`로 설정하여 WinForms를 가져오고 사용합니다.
- (선택 사항) `OutputType`을 `WinExe`로 설정합니다. 이렇게 하면 라이브러리가 아닌 앱이 생성됩니다. 라이브러리를 생성하려면 해당 속성을 생략합니다.

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.1</TargetFramework>

    <UseWPF>true</UseWPF>
    <!-- and/or -->
    <UseWindowsForms>true</UseWindowsForms>
  </PropertyGroup>

</Project>
```

## <a name="wpf-default-includes-and-excludes"></a>WPF 기본 포함 및 제외

SDK 프로젝트는 프로젝트의 파일을 암시적으로 포함하거나 제외하는 규칙 세트를 정의합니다. 해당 규칙은 파일의 빌드 작업도 자동으로 설정합니다. 이는 기본 포함 또는 제외 규칙이 없는 이전 비 SDK .NET Framework 프로젝트와 다릅니다. .NET Framework 프로젝트에서는 프로젝트에 포함할 파일을 명시적으로 선언해야 합니다.

.NET 프로젝트 파일에는 파일을 자동으로 처리하는 [표준 규칙 세트](overview.md#default-includes-and-excludes)가 포함됩니다. WPF 프로젝트는 다른 규칙을 추가합니다.

다음 표에서는 [`UseWPF`](#usewpf) 프로젝트 속성이 `true`로 설정된 경우 .NET 데스크톱 SDK에서 포함되거나 제외되는 요소 및 [GLOB](https://en.wikipedia.org/wiki/Glob_(programming))를 보여 줍니다.

| 요소               | GLOB 포함                 | GLOB 제외                                                                                           | GLOB 제거  |
|-----------------------|------------------------------|--------------------------------------------------------------------|--------------|
| ApplicationDefinition | App.xaml 또는 Application.xaml | N/A                                                                | N/A          |
| Page                  | \*\*/\*.xaml                 | \*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc<br>*ApplicationDefinition* 에서 정의된 모든 XAML | N/A          |
| None                  | N/A                          | N/A                                                                | \*\*/\*.xaml |

모든 프로젝트 형식의 기본 포함 및 제외 설정은 다음과 같습니다. 자세한 내용은 [기본 포함 및 제외](overview.md#default-includes-and-excludes)를 참조하세요.

| 요소           | GLOB 포함                              | GLOB 제외                                                  | GLOB 제거              |
|-------------------|-------------------------------------------|---------------------------------------------------------------|--------------------------|
| Compile           | \*\*/\*.cs, \*\*/\*.vb(또는 기타 언어 확장) | \*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc  | N/A          |
| EmbeddedResource  | \*\*/\*.resx                              | \*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc     | N/A                      |
| None              | \*\*/\*                                   | \*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc     | \*\*/\*.cs; \*\*/\*.resx |

### <a name="errors-related-to-duplicate-items"></a>“중복” 항목 관련 오류

프로젝트에 파일을 명시적으로 추가했거나 XAML GLOB가 프로젝트에 파일을 자동으로 포함하도록 하려면 다음 오류 중 하나가 발생할 수 있습니다.

* 중복 ‘ApplicationDefinition’ 항목이 포함되었습니다.
* 중복 ‘Page’ 항목이 포함되었습니다.

해당 오류는 설정과 충돌하는 암시적 *Include* GLOB의 결과입니다. 이 문제를 해결하려면 [`EnableDefaultApplicationDefinition`](#enabledefaultapplicationdefinition) 또는 [`EnableDefaultPageItems`](#enabledefaultpageitems)를 `false`로 설정합니다. 해당 값을 `false`로 설정하면 프로젝트에서 기본 GLOB를 명시적으로 정의하거나 프로젝트에 포함할 파일을 명시적으로 정의해야 했던 이전 SDK의 동작으로 되돌아갑니다.

[`EnableDefaultItems` 속성](msbuild-props.md#enabledefaultitems)을 `false`로 설정하여 모든 암시적 포함을 완전히 사용하지 않도록 설정할 수 있습니다.

## <a name="wpf-settings"></a>WPF 설정

- [UseWPF](#usewpf)
- [EnableDefaultApplicationDefinition](#enabledefaultapplicationdefinition)
- [EnableDefaultPageItems](#enabledefaultpageitems)

비 WPF 관련 프로젝트 설정에 관한 자세한 내용은 [.NET SDK 프로젝트의 MSBuild 참조](msbuild-props.md)를 참조하세요.

### <a name="usewpf"></a>UseWPF

`UseWPF` 속성은 WPF 라이브러리에 대한 참조를 포함할지 여부를 제어합니다. 또한 MSBuild 파이프라인을 변경하여 WPF 프로젝트 및 관련 파일을 올바르게 처리합니다. 기본값은 `false`입니다. `UseWPF` 속성을 `true`로 설정하여 WPF 지원을 사용하도록 설정합니다. 해당 속성을 사용하는 경우 Windows 플랫폼만 대상으로 지정할 수 있습니다.

```xml
<PropertyGroup>
  <UseWPF>true</UseWPF>
</PropertyGroup>
```

해당 속성을 `true`로 설정하면 .NET 5.0 이상 프로젝트는 [.NET 데스크톱 SDK](#enable-net-desktop-sdk)를 자동으로 가져옵니다.

.NET Core 3.1 프로젝트는 해당 속성을 사용하려면 명시적으로 [.NET 데스크톱 SDK](#enable-net-desktop-sdk)를 대상으로 지정해야 합니다.

### <a name="enabledefaultapplicationdefinition"></a>EnableDefaultApplicationDefinition

`EnableDefaultApplicationDefinition` 속성은 `ApplicationDefinition` 항목을 프로젝트에 암시적으로 포함할지 여부를 제어합니다. 기본값은 `true`입니다. `EnableDefaultApplicationDefinition` 속성을 `false`로 설정하여 암시적 파일 포함을 사용하지 않도록 설정합니다.

```xml
<PropertyGroup>
  <EnableDefaultApplicationDefinition>false</EnableDefaultApplicationDefinition>
</PropertyGroup>
```

해당 속성을 사용하려면 [`EnableDefaultItems` 속성](msbuild-props.md#enabledefaultitems)을 기본 설정인 `true`로 설정해야 합니다.

### <a name="enabledefaultpageitems"></a>EnableDefaultPageItems

`EnableDefaultPageItems` 속성은 _.xaml_ 파일인 `Page` 항목이 프로젝트에 암시적으로 포함되는지 여부를 제어합니다. 기본값은 `true`입니다. `EnableDefaultPageItems` 속성을 `false`로 설정하여 암시적 파일 포함을 사용하지 않도록 설정합니다.

```xml
<PropertyGroup>
  <EnableDefaultPageItems>false</EnableDefaultPageItems>
</PropertyGroup>
```

해당 속성을 사용하려면 [`EnableDefaultItems` 속성](msbuild-props.md#enabledefaultitems)을 기본 설정인 `true`로 설정해야 합니다.

## <a name="windows-forms-settings"></a>Windows Forms 설정

- [UseWindowsForms](#usewindowsforms)

비 WinForms 관련 프로젝트 속성에 관한 자세한 내용은 [.NET SDK 프로젝트의 MSBuild 참조](msbuild-props.md)를 참조하세요.

### <a name="usewindowsforms"></a>UseWindowsForms

`UseWindowsForms` 속성은 애플리케이션이 Windows Forms를 대상으로 하도록 빌드되는지 여부를 제어합니다. 해당 속성은 MSBuild 파이프라인을 변경하여 Windows Forms 프로젝트 및 관련 파일을 올바르게 처리합니다. 기본값은 `false`입니다. `UseWindowsForms` 속성을 `true`로 설정하여 Windows Forms 지원을 사용하도록 설정합니다. 해당 설정을 사용하는 경우 Windows 플랫폼만 대상으로 지정할 수 있습니다.

```xml
<PropertyGroup>
  <UseWindowsForms>true</UseWindowsForms>
</PropertyGroup>
```

해당 속성을 `true`로 설정하면 .NET 5.0 이상 프로젝트는 [.NET 데스크톱 SDK](#enable-net-desktop-sdk)를 자동으로 가져옵니다.

.NET Core 3.1 프로젝트는 해당 속성을 사용하려면 명시적으로 [.NET 데스크톱 SDK](#enable-net-desktop-sdk)를 대상으로 지정해야 합니다.

## <a name="shared-settings"></a>공유 설정

- [DisableWinExeOutputInference](#disablewinexeoutputinference)

### <a name="disablewinexeoutputinference"></a>DisableWinExeOutputInference

.NET 5.0 SDK 이상에 적용됩니다.

앱에서 `OutputType` 속성에 `Exe` 값이 설정되어 있을 때 앱이 콘솔에서 실행되고 있지 않으면 콘솔 창이 만들어집니다. 이는 일반적으로 Windows 데스크톱 앱의 필요한 동작이 아닙니다. `WinExe` 값을 사용하면 콘솔 창이 생성되지 않습니다. .NET 5.0 SDK부터는 `Exe` 값이 `WinExe`로 자동으로 변환됩니다.

`DisableWinExeOutputInference` 속성은 `Exe`를 `WinExe`로 처리하는 동작을 되돌립니다. 해당 값을 `true`로 설정하여 `Exe`의 `OutputType` 속성 값 동작을 복원합니다. 기본값은 `false`입니다.

```xml
<PropertyGroup>
  <DisableWinExeOutputInference>true</DisableWinExeOutputInference>
</PropertyGroup>
```

## <a name="see-also"></a>참조

- [.NET 프로젝트 SDK](overview.md)
- [.NET SDK 프로젝트용 MSBuild 참조](msbuild-props.md)
- [MSBuild 스키마 참조](/visualstudio/msbuild/msbuild-project-file-schema-reference)
- [일반 MSBuild 속성](/visualstudio/msbuild/common-msbuild-project-properties)
- [빌드 사용자 지정](/visualstudio/msbuild/customize-your-build)
