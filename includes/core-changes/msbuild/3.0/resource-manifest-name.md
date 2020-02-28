---
ms.openlocfilehash: 276268d31670b5e7dcd0ae9c0b7a61c3c38ca663
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "77451895"
---
### <a name="resource-manifest-file-names"></a>리소스 매니페스트 파일 이름

.NET Core 3.0부터 생성된 리소스 매니페스트 파일 이름이 변경되었습니다.

#### <a name="version-introduced"></a>도입된 버전

3.0

#### <a name="change-description"></a>변경 내용 설명

.NET Core 3.0 이전에는MSBuild 프로젝트 파일의 리소스( *.resx*) 파일에 [DependentUpon](/visualstudio/msbuild/common-msbuild-project-items#compile) 메타데이터가 설정된 경우 생성된 매니페스트 이름이 *Namespace.Classname.resources*였습니다. [DependentUpon](/visualstudio/msbuild/common-msbuild-project-items#compile)이 설정되지 않은 경우 생성된 매니페스트 이름은 *Namespace.Classname.FolderPathRelativeToRoot.Culture.resources*였습니다.

.NET Core 3.0부터 *.resx* 파일이 동일한 이름의 소스 파일과 공동 배치된 경우(예: Windows Forms 앱) 소스 파일에 있는 첫 번째 형식의 전체 이름에서 리소스 매니페스트 이름이 생성됩니다. 예를 들어 *Type.cs*가 *Type.resx*와 공동 배치된 경우 생성된 매니페스트 이름은 *Namespace.Classname.resources*입니다. 그러나 *.resx* 파일의 `EmbeddedResource` 속성에서 특성을 수정하는 경우 생성된 매니페스트 파일 이름은 다를 수 있습니다.

- `EmbeddedResource` 속성의 `LogicalName` 특성이 설정되어 있으면 해당 값이 리소스 매니페스트 파일 이름으로 사용됩니다.

  예:

  ```xml
  <EmbeddedResource Include="X.resx" LogicalName="SomeName.resources" />
  -or-
  <EmbeddedResource Include="X.fr-FR.resx" LogicalName="SomeName.resources" />
  ```

  **생성된 리소스 매니페스트 파일 이름**: *SomeName.resources*( *.resx* 파일 이름 또는 문화권 또는 기타 메타데이터와 관계 없음).

- `LogicalName`이 설정되지 않았지만 `EmbeddedResource` 속성의 `ManifestResourceName` 특성이 설정된 경우 해당 값이 파일 확장명 *.resources*와 함께 리소스 매니페스트 파일 이름으로 사용됩니다.

  예:

  ```xml
  <EmbeddedResource Include="X.resx" ManifestResourceName="SomeName" />
  -or-
  <EmbeddedResource Include="X.fr-FR.resx" ManifestResourceName="SomeName.fr-FR" />
  ```

  **생성된 리소스 매니페스트 파일 이름**: *SomeName.resources* 또는 *SomeName.fr-FR.resources*.

- 이전 규칙이 적용되지 않고 `EmbeddedResource` 요소의 `DependentUpon` 특성이 소스 파일로 설정된 경우 소스 파일의 첫 번째 클래스의 형식 이름이 리소스 매니페스트 파일 이름에 사용됩니다. 구체적으로 말하면 생성된 파일 이름은 *Namespace.Classname\[.Culture].resources*입니다.

  예:

  ```xml
  <EmbeddedResource Include="X.resx" DependentUpon="MyTypes.cs">
  -or-
  <EmbeddedResource Include="X.fr-FR.resx" DependentUpon="MyTypes.cs">
  ```

  **생성된 리소스 매니페스트 파일 이름**: *Namespace.Classname.resources* 또는 *Namespace.Classname.fr-FR.resources*(여기서 `Namespace.Classname`은 *MyTypes.cs*의 첫 번째 클래스 이름).

- 이전 규칙이 적용되지 않고, `EmbeddedResourceUseDependentUponConvention`이 `true`(.NET Core 기본값)이고, 기본 파일 이름이 동일한 *.resx* 파일과 공동 배치된 소스 파일이 있는 경우 *.resx* 파일은 일치하는 소스 파일에 따라 달라지며 생성된 이름은 이전 규칙과 동일합니다. 이는 .NET Core 프로젝트의 "기본 설정" 규칙입니다.
  
  예:
  
  *MyTypes.cs* 및 *MyTypes.resx* 또는 *MyTypes.fr-FR.resx* 파일이 동일한 폴더에 있습니다.
  
  **생성된 리소스 매니페스트 파일 이름**: *Namespace.Classname.resources* 또는 *Namespace.Classname.fr-FR.resources*(여기서 `Namespace.Classname`은 *MyTypes.cs*의 첫 번째 클래스 이름).
    
- 위 규칙이 모두 적용되지 않는 경우 생성된 리소스 매니페스트 파일 이름은 *RootNamespace.RelativePathWithDotsForSlashes.\[Culture.]resources*입니다. 상대 경로는 설정된 경우 `EmbeddedResource` 요소의 `Link` 특성 값입니다. 그렇지 않으면 상대 경로는 `EmbeddedResource` 요소의 `Identity` 특성 값입니다. Visual Studio에서 이 경로는 프로젝트 루트에서 솔루션 탐색기 내 파일까지의 경로입니다.

#### <a name="recommended-action"></a>권장 조치

생성된 매니페스트 이름에 만족하지 않는다면 다음을 수행할 수 있습니다.

- 앞서 설명한 명명 규칙 중 하나에 따라 리소스 파일 메타데이터를 수정합니다.

- 프로젝트 파일에서 `EmbeddedResourceUseDependentUponConvention`을 `false`로 설정하여 새 규칙을 완전히 옵트아웃합니다.

   ```xml
   <EmbeddedResourceUseDependentUponConvention>false</EmbeddedResourceUseDependentUponConvention>
   ```

   > [!NOTE]
   > `LogicalName` 또는 `ManifestResourceName` 특성이 있으면 생성된 파일 이름에도 해당 값이 사용됩니다.

#### <a name="category"></a>범주

MSBuild

#### <a name="affected-apis"></a>영향을 받는 API

N/A
