---
title: MSBuild 호환성이 손상되는 변경 사항
description: .NET Core 2.1~3.1용 MSBuild의 호환성이 손상되는 변경을 나열합니다.
ms.date: 02/22/2021
ms.openlocfilehash: 03fcd9807a83c4f679dc659b009c857e351b9b2d
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102105645"
---
# <a name="msbuild-breaking-changes-in-net-core-21---31"></a>.NET Core 2.1~3.1의 MSBuild 호환성이 손상되는 변경

이 페이지에는 다음과 같은 주요 변경 사항이 설명되어 있습니다.

| 주요 변경 내용 | 도입된 버전 |
| - | - |
| [디자인 타임 빌드는 최상위 패키지 참조만 반환](#design-time-builds-only-return-top-level-package-references) | 3.1 |
| [리소스 매니페스트 파일 이름 변경](#resource-manifest-file-name-change) | 3.0 |
| [이제 프로젝트 도구가 SDK에 포함됨](#project-tools-now-included-in-sdk) | 2.1 |

## <a name="net-core-31"></a>.NET Core 3.1

[!INCLUDE [design-time-builds-return-top-level-package-refs](../../../includes/core-changes/msbuild/3.1/design-time-builds-return-top-level-package-refs.md)]

***

## <a name="net-core-30"></a>.NET Core 3.0

[!INCLUDE[Resource file names](../../../includes/core-changes/msbuild/3.0/resource-manifest-name.md)]

***

## <a name="net-core-21"></a>.NET Core 2.1

[!INCLUDE [DotNetCliToolReference project elements removed for bundled tools](../../../includes/core-changes/msbuild/2.1/dotnetclitoolreference.md)]

***
