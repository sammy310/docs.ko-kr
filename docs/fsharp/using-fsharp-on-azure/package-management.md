---
title: 패키지 관리를 사용 하 여 F# Azure에 대 한
description: Paket 또는 Nuget 관리를 사용 하 여 F# Azure 종속성
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: fd9c4a15ab0741d44d6d5cf909b7219d310affb0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756535"
---
# <a name="package-management-for-f-azure-dependencies"></a>F# Azure 종속성에 대한 패키지 관리

패키지 관리자를 사용 하는 경우 Azure 개발에 대 한 패키지를 가져오기 하는 것은 쉽습니다. 두 옵션은 [Paket](https://fsprojects.github.io/Paket/) 하 고 [NuGet](https://www.nuget.org/)합니다.

## <a name="using-paket"></a>Paket를 사용 하 여

사용 중인 경우 [Paket](https://fsprojects.github.io/Paket/) 종속성 관리자를 사용할 수 있습니다는 `paket.exe` Azure 종속성을 추가 하는 도구입니다. 예를 들어:

    > paket add nuget WindowsAzure.Storage

사용 중인 경우 또는 [Mono](https://www.mono-project.com/) 플랫폼 간.NET 개발용:

    > mono paket.exe add nuget WindowsAzure.Storage

이렇게 하면 추가 됩니다 `WindowsAzure.Storage` 현재 디렉터리에 있는 프로젝트에 대 한 패키지 종속성 집합을 수정 합니다 `paket.dependencies` 파일과 패키지를 다운로드 합니다. 종속성을 이전에 설정한 위치 종속성 설치를 다른 개발자가 프로젝트를 사용 하 여 작업 중인 경우 해결 하 고 다음과 같은 로컬 종속성을 설치할 수 있습니다.

    > paket install

또는 Mono 개발용:

    > mono paket.exe install

모든 패키지 종속성이 같은 최신 버전으로 업데이트할 수 있습니다.

    > paket update

또는 Mono 개발용:

    > mono paket.exe update

## <a name="using-nuget"></a>Nuget을 사용 하 여

사용 중인 경우 [NuGet](https://www.nuget.org/) 종속성 관리자를 사용할 수 있습니다는 `nuget.exe` Azure 종속성을 추가 하는 도구입니다. 예를 들어:

    > nuget install WindowsAzure.Storage -ExcludeVersion

또는 Mono 개발용:

    > mono nuget.exe install WindowsAzure.Storage -ExcludeVersion

이렇게 하면 추가 됩니다 `WindowsAzure.Storage` 현재 디렉터리에 다운로드 패키지를 프로젝트에 대 한 패키지 종속성 집합에 있습니다. 종속성을 이전에 설정한 위치 종속성 설치를 다른 개발자가 프로젝트를 사용 하 여 작업 중인 경우 해결 하 고 다음과 같은 로컬 종속성을 설치할 수 있습니다.

    > nuget restore 

또는 Mono 개발용:

    > mono nuget.exe restore

모든 패키지 종속성이 같은 최신 버전으로 업데이트할 수 있습니다.

    > nuget update

또는 Mono 개발용:

    > mono nuget.exe update

## <a name="referencing-assemblies"></a>어셈블리 참조

하 여 패키지를 사용 하려면 프로그램 F# 를 사용 하 여 패키지에 포함 된 어셈블리를 참조 해야 하는 스크립트를 `#r` 지시문입니다. 예를 들어:

    > #r "packages/WindowsAzure.Storage/lib/net40/Microsoft.WindowsAzure.Storage.dll"

알 수 있듯이 DLL 및 되지 않을 수 있습니다 정확 하 게 패키지 이름과 전체 DLL 이름으로, 상대 경로 지정 해야 합니다. 경로 프레임 워크 버전 및 패키지 버전 번호가 포함 됩니다. 설치 된 모든 어셈블리를 찾으려면 Windows 명령줄에서 다음과 같이 사용할 수 있습니다.

    > cd packages/WindowsAzure.Storage
    > dir /s/b *.dll

또는 Unix 셸에서 비슷하게이:

    > find packages/WindowsAzure.Storage -name "*.dll"

이렇게 하면 경로는 설치 된 어셈블리에 있습니다. 여기에서 프레임 워크 버전에 대 한 올바른 경로 선택할 수 있습니다.
