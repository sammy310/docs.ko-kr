---
ms.openlocfilehash: f24a29a00a1bff34a452c43716d76bf72ef277b5
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83206223"
---
### <a name="resource-manifest-file-name-change"></a>리소스 매니페스트 파일 이름 변경

.NET Core 3.0부터 기본 사례에서 MSBuild는 리소스 파일에 대해 다른 매니페스트 파일 이름을 생성합니다.

#### <a name="version-introduced"></a>도입된 버전

3.0

#### <a name="change-description"></a>변경 내용 설명

.NET Core 3.0보다 이전 버전에서는 프로젝트 파일의 `EmbeddedResource` 항목에 대해 `LogicalName`, `ManifestResourceName` 또는 `DependentUpon` 메타데이터가 지정되지 않은 경우 MSBuild는 `<RootNamespace>.<ResourceFilePathFromProjectRoot>.resources` 패턴으로 매니페스트 파일 이름을 생성했습니다. 프로젝트 파일에 `RootNamespace`가 정의되어 있지 않은 경우 기본적으로 프로젝트 이름으로 설정됩니다. 예를 들어, 루트 프로젝트 디렉터리의 *Form1.resx*라는 리소스 파일에 대해 생성된 매니페스트 이름은 *MyProject.Form1.resources*였습니다.

.NET Core 3.0부터 리소스 파일이 동일한 이름의 소스 파일과 공동 배치되는 경우(예: *Form1.resx*와 *Form1.cs*) MSBuild는 소스 파일의 형식 정보를 사용하여 `<Namespace>.<ClassName>.resources` 패턴으로 매니페스트 파일 이름을 생성합니다. 네임스페이스 및 클래스 이름은 공동 배치된 소스 파일의 첫 번째 형식에서 추출됩니다. 예를 들어 *Form1.cs*라는 소스 파일과 공동 배치된 *Form1.resx*라는 리소스 파일에 대해 생성된 매니페스트 이름은 *MyNamespace.Form1.resources*입니다. 중요한 점은 파일 이름의 첫 부분이 이전 버전의 .NET Core와 다르다는 것입니다(*MyProject*가 아니라 *MyNamespace*).

> [!NOTE]
> 프로젝트 파일의 `EmbeddedResource` 항목에 `LogicalName`, `ManifestResourceName` 또는 `DependentUpon` 메타데이터가 지정되어 있는 경우 이 변경 내용은 해당 리소스 파일에 영향을 주지 않습니다.

이 주요 변경 내용은 .NET Core 프로젝트에 `EmbeddedResourceUseDependentUponConvention` 속성을 추가하여 도입되었습니다. 기본적으로 리소스 파일은 .NET Core 프로젝트 파일에 명시적으로 나열되지 않으므로 생성된 *.resources* 파일의 이름을 지정하는 방법을 지정하는 `DependentUpon` 메타데이터가 없습니다. `EmbeddedResourceUseDependentUponConvention`이 기본값 `true`로 설정된 경우 MSBuild는 공동 배치된 소스 파일을 찾아 해당 파일에서 네임스페이스 및 클래스 이름을 추출합니다. `EmbeddedResourceUseDependentUponConvention`을 `false`로 설정하면 MSBuild는 이전 동작에 따라, 즉 `RootNamespace`와 상대 파일 경로를 결합하여 매니페스트 이름을 생성합니다.

#### <a name="recommended-action"></a>권장 조치

대부분의 경우 개발자에게는 아무 작업도 필요하지 않으며 앱은 계속 작동할 것입니다. 그러나 이 변경으로 앱이 중단되는 경우 다음 중 하나를 수행할 수 있습니다.

- 새 매니페스트 이름을 예상하도록 코드를 변경합니다.

- 프로젝트 파일에서 `EmbeddedResourceUseDependentUponConvention`을 `false`로 설정하여 새 명명 규칙을 옵트아웃합니다.

  ```xml
  <PropertyGroup>
    <EmbeddedResourceUseDependentUponConvention>false</EmbeddedResourceUseDependentUponConvention>
  </PropertyGroup>
  ```

#### <a name="category"></a>범주

MSBuild

#### <a name="affected-apis"></a>영향을 받는 API

N/A
