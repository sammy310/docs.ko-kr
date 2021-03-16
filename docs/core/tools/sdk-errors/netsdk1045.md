---
title: 'NETSDK1045: 현재 .NET SDK는 대상으로 ‘최신 버전’을 지원하지 않습니다.'
description: 빌드 도구가 요청된 .NET SDK 버전을 찾을 수 없을 때 발생하는 .NET SDK 오류 NETSDK1045에 관해 알아봅니다.
ms.topic: error-reference
ms.date: 02/12/2021
f1_keywords:
- NETSDK1045
ms.openlocfilehash: 7f21270fdc7c2db862a49302a302bf8121fc86a5
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102104104"
---
# <a name="netsdk1045-the-current-net-sdk-does-not-support-newer-version-as-a-target"></a>NETSDK1045: 현재 .NET SDK는 대상으로 ‘최신 버전’을 지원하지 않습니다.

**이 문서의 적용 대상:** ✔️ .NET Core 2.1.100 SDK 이상 버전

이 오류는 빌드 도구가 프로젝트를 빌드하는 데 필요한 .NET SDK 버전을 찾을 수 없을 때 발생합니다. 이는 일반적으로 .NET Core SDK 설치 또는 구성 문제로 인해 발생합니다. 전체 오류 메시지는 다음 예제와 유사하게 표시됩니다.

> NETSDK1045: 현재 .NET SDK는 대상으로 ‘최신 버전’을 지원하지 않습니다. ‘이전 버전’ 이하를 대상으로 하거나 ‘최신 버전’을 지원하는 .NET SDK 버전을 사용합니다.

다음 섹션에서는 이 오류의 가능한 몇 가지 원인을 설명합니다. 각 원인을 확인하고 어떤 원인이 적용되는지 알아봅니다. 환경 또는 구성 파일을 변경할 때 변경 내용을 적용하려면 명령 창을 다시 시작하거나, Visual Studio를 다시 시작하거나, 머신을 다시 부팅해야 할 수 있습니다.

## <a name="net-sdk-version"></a>.NET SDK 버전

프로젝트 파일(.csproj, .vbproj 또는 .fsproj)을 열고 대상 프레임워크를 확인합니다. 앱에서 사용하려는 프레임워크의 버전입니다.

```xml
<TargetFramework>netcoreapp3.0</TargetFramework>
```

나열된 .NET 버전이 머신에 설치되어 있는지 확인합니다. 다음 명령을 사용하여 설치된 버전을 나열할 수 있습니다(개발자 명령 프롬프트를 열고 이 명령을 실행).

```dotnetcli
dotnet --list-sdks
```

### <a name="x86-or-x64-architecture"></a>x86 또는 x64 아키텍처

각 버전의 .NET SDK는 x86 및 x64 아키텍처에서 사용할 수 있습니다. 프로젝트가 잘못된 아키텍처용 .NET SDK를 찾으려고 하거나 프로젝트에 필요한 아키텍처용 .NET SDK가 설치되지 않을 수 있습니다. 필요한 아키텍처의 설치 폴더를 확인합니다. 예를 들어 Windows에서 x86 버전의 .NET SDK는 *C:\Program Files (x86)\dotnet* 에 설치되고 x64 버전은 *C:\Program Files\dotnet* 에 설치됩니다. [.NET이 이미 설치되어 있는지 확인하는 방법](../../install/how-to-detect-installed-versions.md)을 참조하고 운영 체제를 선택하여 머신에 설치된 항목을 검색하는 방법을 알아보세요.

필요한 버전이 설치되어 있지 않으면 [.NET 다운로드](https://dotnet.microsoft.com/download/dotnet) 페이지에서 필요한 버전을 찾습니다.

## <a name="preview-not-enabled"></a>미리 보기가 사용되지 않음

요청된 .NET SDK 버전의 미리 보기를 설치한 경우 Visual Studio에서 미리 보기를 사용하도록 설정하는 옵션도 설정해야 합니다. **도구** > **옵션** > **환경** > **미리 보기 기능** 으로 이동하고 **.NET Core SDK의 미리 보기 사용** 이 선택되어 있는지 확인합니다.

## <a name="visual-studio-version"></a>Visual Studio 버전

예를 들어 .NET Core 3.0 이상에는 Visual Studio 2019가 필요합니다. 프로젝트를 빌드하려면 [Visual Studio 2019 버전 16.3](https://visualstudio.microsoft.com/downloads) 이상으로 업그레이드합니다.

## <a name="path-environment-variable"></a>PATH 환경 변수

빌드 도구는 PATH 환경 변수를 사용하여 .NET 빌드 도구의 적합한 버전을 찾습니다. PATH 환경 변수에 이전 빌드 도구의 직접 경로가 포함된 경우 이 오류 메시지가 표시될 수 있습니다. PATH 환경 변수에서 .NET 도구의 유일한 경로가 최상위 *dotnet* 폴더(예: *C:\Program Files\dotnet*)에 있는지 확인합니다. *C:\Program Files\dotnet\2.1.0\sdks* 같은 경로는 잘못된 PATH의 예입니다.

## <a name="msbuildsdkpath-environment-variable"></a>MSBuildSDKPath 환경 변수

MSBuildSDKPath 환경 변수를 확인합니다. 이 선택적 환경 변수는 MSBuild에서 인식되며 설정된 경우 기본값을 재정의합니다. 특정 이전 버전의 .NET SDK로 설정될 수 있습니다. 설정된 경우 환경 변수를 삭제하고 프로젝트를 다시 빌드해 봅니다.

## <a name="globaljson-file"></a>global.json 파일

프로젝트의 루트 폴더에 있는 *global.json* 파일을 확인하고 파일이 폴더 구조의 어디에나 있을 수 있으므로 디렉터리 위로 볼륨의 루트에 연결합니다. SDK 버전을 포함하는 경우 `sdk` 노드와 모든 자식을 삭제하거나 원하는 최신 .NET Core 버전으로 업데이트합니다.

```json
{
  "sdk": {
    "version": "2.1.0"
  }
}
```

*global.json* 파일은 필요하지 않으므로 `sdk` 노드 이외의 항목을 포함하지 않는 경우 전체 파일을 삭제할 수 있습니다.

## <a name="directorybuildprops-file"></a>Directory.build.props 파일

*Directory.build.props* 파일은 전역 속성을 설정할 수 있는 선택적 MSBuild 파일입니다. 솔루션 폴더에 있는 해당 파일을 확인하고 파일이 폴더 구조의 어디에나 있을 수 있으므로 디렉터리 위로 볼륨의 루트에 연결합니다. 원하는 설정을 재정의할 수 있는 `MSBuildSDKPath`의 설정 또는 `TargetFramework` 요소를 찾습니다.

## <a name="see-also"></a>참조

- [현재 .NET SDK가 .NET Core 3.0을 지원하지 않음 – 수정](https://www.ryadel.com/current-net-sdk-not-support-net-core-3-0-fix/)
