---
title: MSBuild 호환성이 손상되는 변경 사항
description: .NET Core용 MSBuild의 호환성이 손상되는 변경 사항을 나열합니다.
ms.date: 02/10/2020
ms.openlocfilehash: 7493516dff68b8bd45740c9877ebf21886e667ff
ms.sourcegitcommit: aa6d8a90a4f5d8fe0f6e967980b8c98433f05a44
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/16/2020
ms.locfileid: "90679331"
---
# <a name="msbuild-breaking-changes"></a>MSBuild 호환성이 손상되는 변경 사항

이 페이지에는 다음과 같은 주요 변경 사항이 설명되어 있습니다.

| 주요 변경 내용 | 도입된 버전 |
| - | - |
| [PublishDepsFilePath 동작 변경](#publishdepsfilepath-behavior-change) | 5.0 |
| [기본적으로 Directory.Packages.props 파일을 가져옴](#directorypackagesprops-files-is-imported-by-default) | 5.0 |
| [리소스 매니페스트 파일 이름 변경](#resource-manifest-file-name-change) | 3.0 |

## <a name="net-50"></a>.NET 5.0

[!INCLUDE [publishdepsfilepath-behavior-change](../../../includes/core-changes/msbuild/5.0/publishdepsfilepath-behavior-change.md)]

***

[!INCLUDE [directory-packages-props-imported-by-default](../../../includes/core-changes/msbuild/5.0/directory-packages-props-imported-by-default.md)]

***

## <a name="net-core-30"></a>.NET Core 3.0

[!INCLUDE[Resource file names](~/includes/core-changes/msbuild/3.0/resource-manifest-name.md)]

***
