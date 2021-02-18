---
title: 'NETSDK1064: 패키지를 찾을 수 없음'
description: 패키지를 찾을 수 없을 때 발생하는 .NET SDK 오류 NETSDK1064에 관해 알아봅니다.
ms.topic: error-reference
ms.date: 02/10/2021
f1_keywords:
- NETSDK1064
ms.openlocfilehash: 1a155db1aacbceb9878401dbcac61ece5f1f9824
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100488220"
---
# <a name="netsdk1064-package-not-found"></a>NETSDK1064: 패키지를 찾을 수 없음

**이 문서의 적용 대상:** ✔️ .NET Core 2.1.100 SDK 이상 버전

이 오류는 빌드 도구가 프로젝트를 빌드하는 데 필요한 NuGet 패키지를 찾을 수 없을 때 발생합니다. 이 오류는 일반적으로 패키지 복원 문제로 인해 발생합니다. 전체 오류 메시지는 다음 예제와 유사하게 표시됩니다.

> NETSDK1064: 패키지 ‘PackageName’ 버전 x.x.x를 찾을 수 없습니다. NuGet 복원 이후 삭제되었을 수 있습니다. 그러지 않으면 NuGet 복원이 부분적으로만 완료되었을 수 있으며 최대 경로 길이 제한으로 인해 발생했을 수 있습니다.

이 오류를 해결하기 위해 수행할 수 있는 몇 가지 작업은 다음과 같습니다.

* `/restore` 옵션을 *MSBuild.exe* 명령에 추가합니다. 미묘한 버그가 발생할 수 있으므로 `/t:Restore;Build`를 사용하지 마세요. 대안은 패키지 복원을 자동으로 수행하므로 `dotnet build` 명령을 사용하는 것입니다.
* Visual Studio 2019 또는 *MSBuild.exe* 를 사용하여 패키지 복원을 실행하는 경우 최대 경로 길이 제한으로 인해 오류가 발생할 수 있습니다. 자세한 내용은 [긴 경로 지원(NuGet CLI)](/nuget/reference/cli-reference/cli-ref-long-path) 및 [NuGet/Home 이슈 #3324](https://github.com/NuGet/Home/issues/3324)를 참조하세요.
* x86 *nuget.exe* 를 사용하여 복원하고 x64 *MSBuild.exe* 를 사용하여 빌드하는 경우 일치하지 않는 비트 수로 인해 이 오류가 발생할 수 있습니다. *project.assets.json* 의 경로가 다른 비트 수의 프로세스에서 작동하지 않기 때문에 해당 빌드는 복원이 획득된 것으로 클레임하는 패키지를 찾을 수 없습니다. 오류를 해결하려면 복원 및 빌드에 동일한 비트 수의 도구를 사용하거나, x86과 x64 간에 가상화되지 않는 폴더에 패키지를 복원하도록 NuGet을 구성합니다. 자세한 내용은 [dotnet/core 이슈 #4332](https://github.com/dotnet/core/issues/4332)를 참조하세요.
* Docker 이미지를 빌드하는 경우 *.dockerignore* 파일이 *bin* 및 *obj* 디렉터리를 무시하는지 확인합니다. 자세한 내용은 [NETSDK1064: 패키지 DnsClient 1.2.0을 찾을 수 없음](https://stackoverflow.com/questions/61167032/error-netsdk1064-package-dnsclient-1-2-0-was-not-found)을 참조하세요.
