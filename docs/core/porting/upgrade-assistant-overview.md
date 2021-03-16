---
title: .NET 업그레이드 도우미 개요
description: .NET Framework에서 마이그레이션하는 데 도움이 되고 프로젝트를 .NET 5로 업그레이드하는 .NET 업그레이드 도우미 도구를 소개합니다.
author: ardalis
ms.date: 02/25/2021
ms.openlocfilehash: bd1c904586d170d93b76ae058914adb334289f89
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102108287"
---
# <a name="overview-of-the-net-upgrade-assistant"></a>.NET 업그레이드 도우미 개요

현재 .NET Framework에서 실행되는 앱을 .NET 5로 이동해야 하는 경우가 있습니다. .NET 업그레이드 도우미 도구가 해당 프로세스를 지원할 수 있습니다. 이 문서에서는 다음을 제공합니다.

* .NET 업그레이드 도우미의 개요
* .NET 업그레이드 도우미를 설치하는 방법

## <a name="what-is-the-net-upgrade-assistant"></a>.NET 업그레이드 도우미란?

.NET 업그레이드 도우미는 다양한 종류의 .NET Framework 앱에서 실행할 수 있는 명령줄 도구입니다. 해당 도구는 .NET Framework 앱을 .NET 5로 업그레이드하는 데 도움이 되도록 설계되었습니다. 도구를 실행한 후 **대부분의 경우 앱에서는 마이그레이션을 완료하는 데 더 많은 작업이 필요** 합니다. 도구는 마이그레이션을 완료하는 데 도움이 될 수 있는 분석기 설치를 포함합니다.

현재 해당 도구는 다음 .NET Framework 앱 유형을 지원합니다.

- .NET Framework Windows Forms 앱
- .NET Framework WPF 앱
- .NET Framework ASP.NET MVC 앱
- .NET Framework 콘솔 앱
- .NET Framework 클래스 라이브러리

.NET 업그레이드 도우미는 현재 시험판이며 빈번한 업데이트를 받고 있습니다. 도구를 사용하여 문제를 발견하는 경우 도구의 [GitHub 리포지토리](https://github.com/dotnet/upgrade-assistant)에서 문제를 신고하세요.

## <a name="how-to-install-the-net-upgrade-assistant"></a>.NET 업그레이드 도우미를 설치하는 방법

[시작 자습서](https://aka.ms/dotnet-upgrade-assistant-install)에서는 .NET 업그레이드 도우미를 설치하고 사용하는 방법을 안내합니다.

### <a name="prerequisites"></a>사전 요구 사항

1. 해당 도구는 MSBuild를 사용하여 프로젝트 파일 작업을 수행합니다. 최신 버전의 MSBuild가 설치되어 있는지 확인합니다. 해당 작업을 손쉽게 수행하려면 [Visual Studio 2019를 설치](https://visualstudio.microsoft.com/downloads/)합니다.
1. 해당 도구는 [try-convert](https://github.com/dotnet/try-convert)를 사용합니다. 도구를 올바르게 실행하려면 프로젝트 파일을 새 SDK 스타일로 변환하기 위한 try-convert 도구를 설치해야 합니다. 이미 **try-convert** 가 설치되어 있는 경우 대신 업데이트해야 할 수 있습니다(**upgrade-assistant** 가 _0.7.212201_ 이상 버전을 사용하기 때문).
    1. try-convert를 설치하려면: `dotnet tool install -g try-convert`
    1. try-convert를 업데이트하려면: `dotnet tool update -g try-convert`

### <a name="installation-steps"></a>설치 단계

도구는 `dotnet tool install -g upgrade-assistant --add-source https://pkgs.dev.azure.com/dnceng/public/_packaging/dotnet-tools/nuget/v3/index.json`을 실행하여 .NET CLI 도구로 설치할 수 있습니다.

마찬가지로 .NET 업그레이드 도우미가 .NET CLI 도구로 설치되기 때문에 `https://pkgs.dev.azure.com/dnceng/public/_packaging/dotnet-tools/nuget/v3/index.json`을 실행하여 쉽게 업데이트할 수 있습니다.

자세한 설치 지침은 프로젝트의 [추가 정보](https://github.com/dotnet/upgrade-assistant)를 참조하세요.

## <a name="see-also"></a>참고 항목

- [.NET 업그레이드 도우미를 사용하여 WPF 앱을 .NET 5로 업그레이드](upgrade-assistant-wpf-framework.md)
- [.NET 업그레이드 도우미를 사용하여 Windows Forms 앱을 .NET 5로 업그레이드](upgrade-assistant-winforms-framework.md)
- [.NET 업그레이드 도우미를 사용하여 ASP.NET MVC 앱을 .NET 5로 업그레이드](upgrade-assistant-aspnetmvc.md)
- [.NET 업그레이드 도우미 GitHub 리포지토리](https://github.com/dotnet/upgrade-assistant)
