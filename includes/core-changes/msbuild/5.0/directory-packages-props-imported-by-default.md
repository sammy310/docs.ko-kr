---
ms.openlocfilehash: 4a916a4178535763712ebd58fde1a81e456da0d1
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90538823"
---
### <a name="directorypackagesprops-files-is-imported-by-default"></a>기본적으로 Directory.Packages.props 파일을 가져옴

NuGet의 *.props* 파일은 *Directory.Packages.props*라는 파일이 프로젝트 폴더나 상위 항목에 있는 경우 해당 파일을 자동으로 가져옵니다.

#### <a name="version-introduced"></a>도입된 버전

5.0 미리 보기 8

#### <a name="change-description"></a>변경 내용 설명

이전 .NET 버전의 경우 *Directory.Packages.props*라는 파일이 프로젝트 파일에 있을 수 있으며, 빌드 시 NuGet의 *.props* 파일이 해당 파일을 자동으로 가져오지 않습니다.

.NET 5.0부터는 해당 파일이 프로젝트 폴더나 상위 항목에 있는 경우 파일을 자동으로 ‘가져옵니다’. 프로젝트 폴더에 이 이름을 가진 파일이 있는 경우에는 이러한 자동 가져오기로 인해 빌드의 동작이 변경될 수 있습니다. 예를 들어 파일을 가져오게 되지만 이전에는 가져오지 않았을 수 있습니다. 또는 구체적으로 가져올 때 파일을 가져온 순서가 변경될 수 있습니다.

#### <a name="reason-for-change"></a>변경 이유

NuGet에 대한 [중앙 패키지 버전 관리](https://github.com/NuGet/Home/wiki/Centrally-managing-NuGet-package-versions)를 지원하기 위해 이렇게 변경했습니다.

#### <a name="recommended-action"></a>권장 조치

기존 *Directory.Packages.props* 파일을 자동으로 가져와서는 안 되는 경우 파일의 이름을 바꿉니다.

#### <a name="category"></a>범주

MSBuild

#### <a name="affected-apis"></a>영향을 받는 API

N/A

<!--

#### Affected APIs

Not detectable via API analysis.

-->
