---
title: .NET 프레임워크와 .NET 코어의 차이점
description: WPF(Windows 프레젠테이션 파운데이션)의 .NET 프레임워크 구현과 .NET 코어 WPF 간의 차이점에 대해 설명합니다. 앱을 마이그레이션할 때 이러한 비호환성을 고려해야 합니다.
author: thraka
ms.date: 09/21/2019
ms.author: adegeo
ms.openlocfilehash: 341e576f17c522fbcbb9c417176e9d4a13ab1b18
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021838"
---
# <a name="differences-in-wpf"></a>WPF의 차이

이 문서에서는 .NET 코어와 .NET 프레임워크에서 WPF(Windows 프레젠테이션 파운데이션)의 차이점에 대해 설명합니다. .NET 코어용 WPF는 .NET Framework 소스 코드에 대한 원래 WPF에서 포크된 [오픈 소스](https://github.com/dotnet/wpf) 프레임워크입니다.

.NET Core에서 지원하지 않는 몇 가지 기능이 있습니다. 지원되지 않는 기술에 대한 자세한 내용은 [.NET Core에서 사용할 수 없는 .NET Framework 기술을](../../core/porting/net-framework-tech-unavailable.md)참조하십시오.

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="sdk-style-projects"></a>SDK 스타일 프로젝트

.NET Core는 SDK 스타일 프로젝트 파일을 사용합니다. 이러한 프로젝트 파일은 Visual Studio에서 관리하는 기존 .NET Framework 프로젝트 파일과 다릅니다. .NET 프레임워크 WPF 앱을 .NET Core로 마이그레이션하려면 프로젝트를 변환해야 합니다. 자세한 내용은 [WPF 앱을 .NET Core 3.0으로 마이그레이션을](convert-project-from-net-framework.md)참조하십시오.

## <a name="nuget-package-references"></a>NuGet 패키지 참조

.NET Framework 앱이 *packages.config* 파일에 NuGet 종속성을 나열하는 경우 [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) 다음 형식으로 마이그레이션합니다.

1. 시각적 스튜디오에서 솔루션 **탐색기** 창을 엽니다.
1. WPF 프로젝트에서 패키지 를 마우스 오른쪽 단추로 **클릭합니다.config** > **는 packageReference.**

![패키지참조로 업그레이드](media/differences-from-net-framework/package-reference-migration.png)

계산된 최상위 NuGet 종속성을 표시하고 상위 수준으로 승격해야 하는 다른 NuGet 패키지를 묻는 대화 상자가 나타납니다. **확인을** 선택하면 *packages.config* 파일이 프로젝트에서 제거되고 `<PackageReference>` 요소가 프로젝트 파일에 추가됩니다.

프로젝트에서 를 `<PackageReference>`사용하면 패키지가 *패키지* 폴더에 로컬로 저장되지 않고 전역적으로 저장됩니다. 프로젝트 파일을 열고 패키지 `<Analyzer>` 폴더를 참조하는 요소를 *제거합니다.* 이러한 분석기는 NuGet 패키지 참조에 자동으로 포함됩니다.

## <a name="code-access-security"></a>코드 액세스 보안

CAS(코드 액세스 보안)는 .NET 코어 또는 .NET 코어에 대한 WPF에서 지원되지 않습니다. 모든 CAS 관련 기능은 완전 신뢰의 가정하에 처리됩니다. .NET 코어용 WPF는 CAS 관련 코드를 제거합니다. 이러한 형식에 대한 호출이 성공할 수 있도록 이러한 형식의 공용 API 표시면이 여전히 존재합니다.

공개적으로 정의된 CAS 관련 형식은 WPF 어셈블리에서 Core .NET 라이브러리 어셈블리로 이동되었습니다. WPF 어셈블리에는 이동된 형식의 새 위치로 형식 전달 설정이 있습니다.

| 소스 어셈블리 | 대상 어셈블리 | Type                |
| --------------- | --------------- | ------------------- |
| *WindowsBase.dll* | *시스템.보안.권한.dll* | <xref:System.Security.Permissions.MediaPermission> <br /> <xref:System.Security.Permissions.MediaPermissionAttribute> <br /> <xref:System.Security.Permissions.MediaPermissionAudio> <br /> <xref:System.Security.Permissions.MediaPermissionImage> <br /> <xref:System.Security.Permissions.MediaPermissionVideo> <br /> <xref:System.Security.Permissions.WebBrowserPermission> <br /> <xref:System.Security.Permissions.WebBrowserPermissionAttribute> <br /> <xref:System.Security.Permissions.WebBrowserPermissionLevel> |
| *System.Xaml.dll* | *시스템.보안.권한.dll* | <xref:System.Xaml.Permissions.XamlLoadPermission> |
| *System.Xaml.dll* | *시스템.윈도우.확장.dll*    | <xref:System.Xaml.Permissions.XamlAccessLevel><br/> |

> [!NOTE]
> 포팅 마찰을 최소화하기 위해 다음 속성과 관련된 정보를 저장하고 검색하는 `XamlAccessLevel` 기능이 형식에 유지되었습니다.
>
> - `PrivateAccessToTypeName`
> - `AssemblyNameString`

## <a name="next-steps"></a>다음 단계

- [.NET 프레임워크 WPF 앱을 .NET Core로 포팅하는 방법을 알아봅니다.](convert-project-from-net-framework.md)
