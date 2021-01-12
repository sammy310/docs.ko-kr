---
title: 'NETSDK1005 및 NETSDK1047: 자산 파일에 대상이 없음'
description: 자산 파일에 대상이 없는 문제를 해결하는 방법입니다.
author: sfoslund
ms.topic: error-reference
ms.date: 12/17/2020
f1_keywords:
- NETSDK1005
- NETSDK1047
ms.openlocfilehash: e3e7389adf6a9a715d44661a5f7cbae5efe299e4
ms.sourcegitcommit: 4b79862c5b41fbd86cf38f926f6a49516059f6f2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/18/2020
ms.locfileid: "97678164"
---
# <a name="netsdk1005-and-netsdk1047-asset-file-is-missing-target"></a>NETSDK1005 및 NETSDK1047: 자산 파일에 대상이 없음

**이 문서의 적용 대상:** ✔️ .NET Core 2.1.100 SDK 이상 버전

.NET SDK가 NETSDK1005 또는 NETSDK1047 오류를 실행하는 경우 프로젝트의 자산 파일에 대상 프레임워크 중 하나의 정보가 누락된 것입니다. NuGet은 *obj* 폴더에 *project.assets.json* 이라는 파일을 작성하고 .NET SDK는 해당 파일을 사용하여 패키지 정보를 컴파일러에 전달합니다. .NET 5에서 NuGet에 `TargetFrameworkAlias`라는 새 필드가 추가되었으므로 이전 버전의 MSBuild 또는 NuGet은 새 필드 없이 자산 파일을 생성합니다. 자세한 내용은 [error NETSDK1005](https://developercommunity.visualstudio.com/content/problem/1248649/error-netsdk1005-assets-file-projectassetsjson-doe.html)(오류 NETSDK1005)를 참조하세요.

다음의 몇 가지 작업을 통해 오류를 해결할 수 있습니다.

* MSBuild 버전 16.8 이상과 NuGet 버전 5.8 이상을 사용 중인지 확인하고 도구를 업데이트한 후 프로젝트를 복원합니다. NuGet 버전 5.8 이상을 사용 중인 경우 Visual Studio 2019 버전 16.8 이상, MSBuild 버전 16.8 이상, .NET 5.0 SDK 이상을 사용해야 합니다.

* Visual Studio 2019에서 버전 16.8을 설치한 후나 프로젝트의 대상 프레임워크를 변경한 후 처음으로 프로젝트를 빌드하는 동안 오류가 발생하는 경우 프로젝트를 두 번째로 빌드합니다.

* 프로젝트를 빌드하기 전에 *obj* 폴더를 삭제합니다.

* 누락된 대상 값이 프로젝트의 `TargetFrameworks` 속성에 포함되어 있는지 확인합니다.
