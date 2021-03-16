---
title: '호환성이 손상되는 변경: 기본적으로 Directory.Packages.props 파일을 가져옴'
description: Directory.Packages.props라는 파일이 프로젝트 폴더에 있는 경우 NuGet의 .props 파일이 해당 파일을 자동으로 가져오는 .NET 5의 호환성이 손상되는 변경에 관해 알아봅니다.
ms.date: 09/17/2020
ms.openlocfilehash: a031d9b2bd832be06dedb20495c24075d1239b02
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256584"
---
# <a name="directorypackagesprops-files-is-imported-by-default"></a>기본적으로 Directory.Packages.props 파일을 가져옴

NuGet의 *.props* 파일은 *Directory.Packages.props* 라는 파일이 프로젝트 폴더나 상위 항목에 있는 경우 해당 파일을 자동으로 가져옵니다.

## <a name="version-introduced"></a>도입된 버전

5.0

## <a name="change-description"></a>변경 내용 설명

이전 .NET 버전의 경우 *Directory.Packages.props* 라는 파일이 프로젝트 파일에 있을 수 있으며, 빌드 시 NuGet의 *.props* 파일이 해당 파일을 자동으로 가져오지 않습니다.

.NET 5부터는 해당 파일이 프로젝트 폴더나 상위 항목에 있는 경우 파일을 자동으로 ‘가져옵니다’. 프로젝트 폴더에 이 이름을 가진 파일이 있는 경우에는 이러한 자동 가져오기로 인해 빌드의 동작이 변경될 수 있습니다. 예를 들어 파일을 가져오게 되지만 이전에는 가져오지 않았을 수 있습니다. 또는 구체적으로 가져올 때 파일을 가져온 순서가 변경될 수 있습니다.

## <a name="reason-for-change"></a>변경 이유

NuGet에 대한 [중앙 패키지 버전 관리](https://github.com/NuGet/Home/wiki/Centrally-managing-NuGet-package-versions)를 지원하기 위해 이렇게 변경했습니다.

## <a name="recommended-action"></a>권장 조치

기존 *Directory.Packages.props* 파일을 자동으로 가져와서는 안 되는 경우 파일의 이름을 바꿉니다.

## <a name="affected-apis"></a>영향을 받는 API

N/A

<!--

### Affected APIs

Not detectable via API analysis.

### Category

MSBuild

-->
