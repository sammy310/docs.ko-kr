---
title: .NET Framework와 .NET Core 간의 차이점
description: WPF(Windows Presentation Foundation)의 .NET Framework 구현과 .NET Core WPF 간의 차이점을 설명합니다. 앱을 마이그레이션할 때 이러한 비호환성을 고려해야 합니다.
author: thraka
ms.date: 09/21/2019
ms.author: adegeo
ms.openlocfilehash: 341e576f17c522fbcbb9c417176e9d4a13ab1b18
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021838"
---
# <a name="differences-in-wpf"></a>WPF 차이점

이 문서에서는 .NET Core 및 .NET Framework에서 WPF(Windows Presentation Foundation)의 차이점을 설명합니다. .NET Core용 WPF는 원래 .NET Framework용 WPF 소스 코드에서 분기된 [오픈 소스 프레임워크](https://github.com/dotnet/wpf)입니다.

.NET Framework 기능 중에 .NET Core에서 지원하지 않는 것이 몇 가지 있습니다. 지원되지 않는 기술에 대한 자세한 내용은 [.NET Core에서 사용할 수 없는 .NET Framework 기술](../../core/porting/net-framework-tech-unavailable.md)을 참조하세요.

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="sdk-style-projects"></a>SDK 스타일 프로젝트

.NET Core는 SDK 스타일 프로젝트 파일을 사용합니다. 이러한 프로젝트 파일은 Visual Studio가 관리하는 기존 .NET Framework 프로젝트 파일과 다릅니다. .NET Framework WPF 앱을 .NET Core로 마이그레이션하려면 프로젝트를 변환해야 합니다. 자세한 내용은 [WPF 앱을 .NET Core 3.0으로 마이그레이션](convert-project-from-net-framework.md)을 참조하세요.

## <a name="nuget-package-references"></a>NuGet 패키지 참조

.NET Framework 앱이 *packages.config* 파일에서 NuGet 종속성을 나열하는 경우 다음과 같이 [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) 형식으로 마이그레이션합니다.

1. Visual Studio에서 **솔루션 탐색기** 창을 엽니다.
1. WPF 프로젝트에서 **packages.config** > 를 마우스 오른쪽 단추로 클릭하고 **packages.config를 PackageReference로 마이그레이션**을 선택합니다.

![PackageReference로 업그레이드](media/differences-from-net-framework/package-reference-migration.png)

계산된 최상위 NuGet 종속성을 보여주는 대화 상자가 나타나고, 다른 어떤 NuGet 패키지를 최상위 수준으로 승격해야 하는지 묻는 메시지가 표시됩니다. **확인**을 선택하면 *packages.config* 파일이 프로젝트에서 제거되고 `<PackageReference>` 요소가 프로젝트 파일에 추가됩니다.

프로젝트에서 `<PackageReference>`를 사용하는 경우 패키지는 *Packages* 폴더에 로컬로 저장되지 않고 전역적으로 저장됩니다. 프로젝트 파일을 열고 *Packages* 폴더를 참조하는 모든 `<Analyzer>` 요소를 제거합니다. 이러한 분석기는 NuGet 패키지 참조에 자동으로 포함됩니다.

## <a name="code-access-security"></a>코드 액세스 보안

CAS(코드 액세스 보안)는 .NET Core 또는 .NET Core 용 WPF에서 지원되지 않습니다. 모든 CAS 관련 기능은 완전 신뢰를 가정하여 처리됩니다. .NET Core 용 WPF는 CAS 관련 코드를 제거합니다. 이러한 형식의 공용 API 노출 영역은 이러한 형식에 대한 호출이 성공하도록 하기 위해 여전히 존재합니다.

공개적으로 정의된 CAS 관련 형식이 WPF 어셈블리에서 Core .NET 라이브러리 어셈블리로 이동되었습니다. WPF 어셈블리에는 이동된 형식의 새 위치로 설정된 형식 전달이 있습니다.

| 소스 어셈블리 | 대상 어셈블리 | 형식                |
| --------------- | --------------- | ------------------- |
| *WindowsBase.dll* | *System.Security.Permissions.dll* | <xref:System.Security.Permissions.MediaPermission> <br /> <xref:System.Security.Permissions.MediaPermissionAttribute> <br /> <xref:System.Security.Permissions.MediaPermissionAudio> <br /> <xref:System.Security.Permissions.MediaPermissionImage> <br /> <xref:System.Security.Permissions.MediaPermissionVideo> <br /> <xref:System.Security.Permissions.WebBrowserPermission> <br /> <xref:System.Security.Permissions.WebBrowserPermissionAttribute> <br /> <xref:System.Security.Permissions.WebBrowserPermissionLevel> |
| *System.Xaml.dll* | *System.Security.Permissions.dll* | <xref:System.Xaml.Permissions.XamlLoadPermission> |
| *System.Xaml.dll* | *System.Windows.Extension.dll*    | <xref:System.Xaml.Permissions.XamlAccessLevel><br/> |

> [!NOTE]
> 포팅 마찰을 최소화하기 위해 다음 속성과 관련된 정보를 저장하고 검색하는 기능은 `XamlAccessLevel` 형식으로 유지됩니다.
>
> - `PrivateAccessToTypeName`
> - `AssemblyNameString`

## <a name="next-steps"></a>다음 단계

- [.NET Framework WPF 앱을 .NET Core로 이식하는 방법을 알아봅니다.](convert-project-from-net-framework.md)
