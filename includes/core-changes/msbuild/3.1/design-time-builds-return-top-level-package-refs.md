---
ms.openlocfilehash: 53840ddd59ae3463bae2930fd0151ab2cd2d65cb
ms.sourcegitcommit: e301979e3049ce412d19b094c60ed95b316a8f8c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/16/2020
ms.locfileid: "97593329"
---
### <a name="design-time-builds-only-return-top-level-package-references"></a>디자인 타임 빌드는 최상위 패키지 참조만 반환

.NET Core SDK 3.1.400부터 `RunResolvePackageDependencies` 대상에서는 최상위 패키지 참조만 반환합니다.

#### <a name="version-introduced"></a>도입된 버전

.NET Core SDK 3.1.400

#### <a name="change-description"></a>변경 내용 설명

이전 버전의 .NET Core SDK에서는 `RunResolvePackageDependencies` 대상이 NuGet 자산 파일의 정보를 포함하는 다음 MSBuild 항목을 만들었습니다.

- `PackageDefinitions`
- `PackageDependencies`
- `TargetDefinitions`
- `FileDefinitions`
- `FileDependencies`

이 데이터는 Visual Studio에서 솔루션 탐색기의 종속성 노드를 채우는 데 사용됩니다. 그러나 데이터양이 많을 수 있고 종속성 노드를 확장하지 않는 경우 해당 데이터가 필요하지 않습니다.

.NET Core SDK 버전 3.1.400부터 이러한 항목은 대부분 기본적으로 생성되지 않습니다. `Package` 형식의 항목만 반환됩니다. Visual Studio에서 종속성 노드를 채울 항목이 필요한 경우 자산 파일에서 직접 정보를 읽습니다.

#### <a name="reason-for-change"></a>변경 이유

이 변경 사항은 Visual Studio 내에서 솔루션 로드 성능을 개선하기 위해 도입되었습니다. 이전에는 모든 패키지 참조를 로드했고 따라서 대부분의 사용자가 보지 않는 많은 참조가 로드되었습니다.

#### <a name="recommended-action"></a>권장 조치

이러한 항목을 사용하는 MSBuild 논리를 만드는 경우 프로젝트 파일에서 `EmitLegacyAssetsFileItems` 속성을 `true`로 설정합니다. 이렇게 설정하면 모든 항목이 만들어지는 이전 동작이 사용됩니다.

#### <a name="category"></a>범주

MSBuild

#### <a name="affected-apis"></a>영향을 받는 API

N/A
