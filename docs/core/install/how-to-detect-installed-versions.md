---
title: Windows, Linux, macOS에 설치된 .NET 버전 확인 - .NET
description: 컴퓨터에 설치된 .NET 버전을 확인하는 방법을 알아봅니다. 여기에는 .NET 런타임 및 SDK가 포함됩니다.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 2fc12c8c398b1a74d623e53884df666f4d4b85f1
ms.sourcegitcommit: 45c7148f2483db2501c1aa696ab6ed2ed8cb71b2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/08/2020
ms.locfileid: "96851616"
---
# <a name="how-to-check-that-net-is-already-installed"></a>.NET이 설치되어 있는지 확인하는 방법

이 문서에서는 컴퓨터에 설치된 .NET 런타임 및 SDK의 버전을 확인하는 방법을 알아봅니다. Visual Studio 또는 Mac용 Visual Studio와 같은 통합 개발 환경을 사용하는 경우 .NET이 이미 설치되어 있을 수 있습니다.

SDK를 설치하면 그에 해당하는 런타임도 설치됩니다.

이 문서에서 안내하는 명령이 작동하지 않는다면 런타임 또는 SDK가 설치되지 않은 것입니다. 자세한 내용은 [Windows](windows.md), [macOS](macos.md) 또는 [Linux](linux.md)에 대한 설치 문서를 참조하세요.

## <a name="check-sdk-versions"></a>SDK 버전 확인

터미널을 사용하여 현재 설치된 .NET SDK의 버전을 확인할 수 있습니다. 터미널을 열고 다음 명령을 실행합니다.

```dotnetcli
dotnet --list-sdks
```

그러면 다음과 같은 출력이 표시됩니다.

::: zone pivot="os-windows"

```console
2.1.500 [C:\program files\dotnet\sdk]
2.1.502 [C:\program files\dotnet\sdk]
2.1.504 [C:\program files\dotnet\sdk]
2.1.600 [C:\program files\dotnet\sdk]
2.1.602 [C:\program files\dotnet\sdk]
3.1.100 [C:\program files\dotnet\sdk]
5.0.100 [C:\program files\dotnet\sdk]
```

::: zone-end

::: zone pivot="os-linux"

```bash
2.1.500 [/home/user/dotnet/sdk]
2.1.502 [/home/user/dotnet/sdk]
2.1.504 [/home/user/dotnet/sdk]
2.1.600 [/home/user/dotnet/sdk]
2.1.602 [/home/user/dotnet/sdk]
3.1.100 [/home/user/dotnet/sdk]
5.0.100 [/home/user/dotnet/sdk]
```

::: zone-end

::: zone pivot="os-macos"

```bash
2.1.500 [/usr/local/share/dotnet/sdk]
2.1.502 [/usr/local/share/dotnet/sdk]
2.1.504 [/usr/local/share/dotnet/sdk]
2.1.600 [/usr/local/share/dotnet/sdk]
2.1.602 [/usr/local/share/dotnet/sdk]
3.1.100 [/usr/local/share/dotnet/sdk]
5.0.100 [/usr/local/share/dotnet/sdk]
```

::: zone-end

## <a name="check-runtime-versions"></a>런타임 버전 확인

다음 명령을 사용하여 현재 설치된 .NET 런타임의 버전을 확인할 수 있습니다.

```dotnetcli
dotnet --list-runtimes
```

그러면 다음과 같은 출력이 표시됩니다.

::: zone pivot="os-windows"

```console
Microsoft.AspNetCore.All 2.1.7 [c:\program files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.13 [c:\program files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.App 2.1.7 [c:\program files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.13 [c:\program files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 3.1.0 [c:\program files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 5.0.0 [c:\program files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.NETCore.App 2.1.7 [c:\program files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.13 [c:\program files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 3.1.0 [c:\program files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 5.0.0 [c:\program files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.WindowsDesktop.App 3.0.0 [c:\program files\dotnet\shared\Microsoft.WindowsDesktop.App]
Microsoft.WindowsDesktop.App 3.1.0 [c:\program files\dotnet\shared\Microsoft.WindowsDesktop.App]
Microsoft.WindowsDesktop.App 5.0.0 [c:\program files\dotnet\shared\Microsoft.WindowsDesktop.App]
```

::: zone-end

::: zone pivot="os-linux"

```bash
Microsoft.AspNetCore.All 2.1.7 [/home/user/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.13 [/home/user/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.App 2.1.7 [/home/user/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.13 [/home/user/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 3.1.0 [/home/user/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 5.0.0 [/home/user/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.NETCore.App 2.1.7 [/home/user/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.13 [/home/user/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 3.1.0 [/home/user/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 5.0.0 [/home/user/dotnet/shared/Microsoft.NETCore.App]
```

::: zone-end

::: zone pivot="os-macos"

```bash
Microsoft.AspNetCore.All 2.1.7 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.13 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.App 2.1.7 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.13 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 3.1.0 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 5.0.0 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.NETCore.App 2.1.7 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.13 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 3.1.0 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 5.0.0 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
```

::: zone-end

## <a name="check-for-install-folders"></a>설치 폴더 확인

.NET이 설치되어 있지만 운영 체제 또는 사용자 프로필의 `PATH` 변수에 추가되지 않았을 수 있습니다. 이 경우 이전 섹션의 명령이 작동하지 않을 수 있습니다. 또는 .NET 설치 폴더가 있는지 확인할 수 있습니다.

설치 관리자 또는 스크립트에서 .NET을 설치하면 표준 폴더에 설치됩니다. 대부분의 경우 .NET을 설치하는 데 사용하는 설치 관리자나 스크립트는 다른 폴더에 설치할 수 있는 옵션을 제공합니다. 다른 폴더에 설치하도록 선택한 경우 폴더 경로의 시작을 조정합니다.

::: zone pivot="os-windows"

- **dotnet 실행 파일**\
_C:\\program files\\dotnet\\dotnet.exe_

- **.NET SDK**\
_C:\\program files\\dotnet\\sdk\\{version}\\_

- **.NET 런타임**\
_C:\\program files\\dotnet\\shared\\{runtime-type}\\{version}\\_

::: zone-end

::: zone pivot="os-linux"

- **dotnet 실행 파일**\
_/home/user/share/dotnet/dotnet_

- **.NET SDK**\
_/home/user/share/dotnet/sdk/{version}/_

- **.NET 런타임**\
_/home/user/share/dotnet/shared/{runtime-type}/{version}/_

::: zone-end

::: zone pivot="os-macos"

- **dotnet 실행 파일**\
_/usr/local/share/dotnet/dotnet_

- **.NET SDK**\
_/usr/local/share/dotnet/sdk/{version}/_

- **.NET 런타임**\
_/usr/local/share/dotnet/shared/{runtime-type}/{version}/_

::: zone-end

## <a name="more-information"></a>추가 정보

`dotnet --info` 명령을 사용하여 SDK의 버전과 런타임의 버전을 모두 확인할 수 있습니다. 그 밖에도 운영 체제 버전, 런타임 식별자(RID)와 같은 다른 환경 관련 정보도 확인할 수 있습니다.

## <a name="next-steps"></a>다음 단계

- [Windows용 .NET 런타임 및 SDK 설치](windows.md).
- [macOS용 .NET 런타임 및 SDK 설치](macos.md).
- [Linux용 .NET 런타임 SDK 설치](linux.md).

## <a name="see-also"></a>참조

- [설치된 .NET Framework 버전 확인](../../framework/migration-guide/how-to-determine-which-versions-are-installed.md)
