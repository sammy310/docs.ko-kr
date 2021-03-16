---
title: 'NETSDK1004: 자산 파일을 찾을 수 없음'
description: project.assets.json 파일을 찾을 수 없는 경우 발생하는 .NET SDK 오류 NETSDK1004에 대해 알아봅니다.
ms.topic: error-reference
ms.date: 01/29/2021
f1_keywords:
- NETSDK1004
ms.openlocfilehash: aa01ff657143faac96baa5ae1133493516edfb1c
ms.sourcegitcommit: bdbf6472de867a0a11aaa5b9384a2506c24f27d2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2021
ms.locfileid: "102206715"
---
# <a name="netsdk1004-assets-file-not-found"></a>NETSDK1004: 자산 파일을 찾을 수 없음

**이 문서의 적용 대상:** ✔️ .NET Core 2.1.100 SDK 이상 버전

NuGet은 *obj* 폴더에 *project.assets.json* 이라는 파일을 작성하고 .NET SDK는 해당 파일을 사용하여 패키지 정보를 컴파일러에 전달합니다. 이 오류는 빌드하는 동안 자산 파일 *project.assets.json* 을 찾을 수 없는 경우에 발생합니다. 전체 오류 메시지는 다음 예제와 유사하게 표시됩니다.

**NETSDK1004: 자산 파일 ‘C:\path\to\project.assets.json’을 찾을 수 없습니다. NuGet 패키지 복원을 실행하여 이 파일을 생성하세요.**

오류의 몇 가지 가능한 원인은 다음과 같습니다.

* `%` 문자를 포함하는 디렉터리 경로에서 `dotnet build` 명령을 실행하고 있습니다. 오류를 해결하려면 폴더 이름에서 `%`를 제거하고 `dotnet build`를 다시 실행합니다.
* 프로젝트 파일의 변경 내용이 프로젝트 시스템에서 자동으로 검색되고 복원되지 않았습니다. 오류를 해결하려면 명령 프롬프트를 열고 프로젝트에서 `dotnet restore`를 실행합니다.
* 프로젝트가 이전 버전의 Nuget.exe에서 별도로 복원되었습니다. 오류를 해결하려면 명령 프롬프트를 열고 프로젝트에서 `dotnet restore`를 실행합니다.
* NETSDK1045(사용 중인 SDK의 버전이 프로젝트의 대상 프레임워크를 지원하지 않음)와 같은 이전 오류가 발생하면 NuGet에서 프로젝트 자산 파일을 만들 수 없습니다. NETSDK1004 오류를 해결하려면 이전 오류를 해결하고 프로젝트에서 `dotnet restore`를 실행합니다.
* App Center CI가 NuGet에 없는 외부 어셈블리를 포함하는 프로젝트를 빌드하고 있습니다. 오류를 해결하려면 어셈블리에 대한 NuGet 패키지를 사용합니다.
* 마침표로 시작하는 이름을 사용하여 Visual Studio에서 솔루션 폴더를 추가했습니다. 오류를 해결하려면 폴더 이름에서 선행 마침표를 제거합니다.
