---
ms.openlocfilehash: 16ee73bfc0ab33b04ea3e2fa6d0eec521a9b8634
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "78967886"
---
### <a name="resource-manifest-file-names"></a><span data-ttu-id="fb109-101">리소스 매니페스트 파일 이름</span><span class="sxs-lookup"><span data-stu-id="fb109-101">Resource manifest file names</span></span>

<span data-ttu-id="fb109-102">.NET Core 3.0부터 생성된 리소스 매니페스트 파일 이름이 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fb109-102">Starting in .NET Core 3.0, the generated resource manifest file name has changed.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="fb109-103">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="fb109-103">Version introduced</span></span>

<span data-ttu-id="fb109-104">3.0</span><span class="sxs-lookup"><span data-stu-id="fb109-104">3.0</span></span>

#### <a name="change-description"></a><span data-ttu-id="fb109-105">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="fb109-105">Change description</span></span>

<span data-ttu-id="fb109-106">.NET Core 3.0 이전에는MSBuild 프로젝트 파일의 리소스( *.resx*) 파일에 [DependentUpon](/visualstudio/msbuild/common-msbuild-project-items#compile) 메타데이터가 설정된 경우 생성된 매니페스트 이름이 *Namespace.Classname.resources*였습니다.</span><span class="sxs-lookup"><span data-stu-id="fb109-106">Prior to .NET Core 3.0, when [DependentUpon](/visualstudio/msbuild/common-msbuild-project-items#compile) metadata was set for a resource (*.resx*) file in the MSBuild project file, the generated manifest name was *Namespace.Classname.resources*.</span></span> <span data-ttu-id="fb109-107">[DependentUpon](/visualstudio/msbuild/common-msbuild-project-items#compile)이 설정되지 않은 경우 생성된 매니페스트 이름은 *Namespace.Classname.FolderPathRelativeToRoot.Culture.resources*였습니다.</span><span class="sxs-lookup"><span data-stu-id="fb109-107">When [DependentUpon](/visualstudio/msbuild/common-msbuild-project-items#compile) was not set, the generated manifest name was *Namespace.Classname.FolderPathRelativeToRoot.Culture.resources*.</span></span>

<span data-ttu-id="fb109-108">.NET Core 3.0부터 *.resx* 파일이 동일한 이름의 소스 파일과 공동 배치된 경우(예: Windows Forms 앱) 소스 파일에 있는 첫 번째 형식의 전체 이름에서 리소스 매니페스트 이름이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb109-108">Starting in .NET Core 3.0, when a *.resx* file is colocated with a source file of the same name, for example, in Windows Forms apps, the resource manifest name is generated from the full name of the first type in the source file.</span></span> <span data-ttu-id="fb109-109">예를 들어 *Type.cs*가 *Type.resx*와 공동 배치된 경우 생성된 매니페스트 이름은 *Namespace.Classname.resources*입니다.</span><span class="sxs-lookup"><span data-stu-id="fb109-109">For example, if *Type.cs* is colocated with *Type.resx*, the generated manifest name is *Namespace.Classname.resources*.</span></span> <span data-ttu-id="fb109-110">그러나 *.resx* 파일의 `EmbeddedResource` 속성에서 특성을 수정하는 경우 생성된 매니페스트 파일 이름은 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb109-110">However, if you modify any of the attributes on the `EmbeddedResource` property for the *.resx* file, the generated manifest file name may be different:</span></span>

- <span data-ttu-id="fb109-111">`EmbeddedResource` 속성의 `LogicalName` 특성이 설정되어 있으면 해당 값이 리소스 매니페스트 파일 이름으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb109-111">If the `LogicalName` attribute on the `EmbeddedResource` property is set, that value is used as the resource manifest file name.</span></span>

  <span data-ttu-id="fb109-112">예:</span><span class="sxs-lookup"><span data-stu-id="fb109-112">Examples:</span></span>

  ```xml
  <EmbeddedResource Include="X.resx" LogicalName="SomeName.resources" />
  -or-
  <EmbeddedResource Include="X.fr-FR.resx" LogicalName="SomeName.resources" />
  ```

  <span data-ttu-id="fb109-113">**생성된 리소스 매니페스트 파일 이름**: *SomeName.resources*( *.resx* 파일 이름 또는 문화권 또는 기타 메타데이터와 관계 없음).</span><span class="sxs-lookup"><span data-stu-id="fb109-113">**Generated resource manifest file name**: *SomeName.resources* (regardless of the *.resx* file name or culture or any other metadata).</span></span>

- <span data-ttu-id="fb109-114">`LogicalName`이 설정되지 않았지만 `EmbeddedResource` 속성의 `ManifestResourceName` 특성이 설정된 경우 해당 값이 파일 확장명 *.resources*와 함께 리소스 매니페스트 파일 이름으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb109-114">If `LogicalName` is not set, but the `ManifestResourceName` attribute on the `EmbeddedResource` property is set, its value, combined with the file extension *.resources*, is used as the resource manifest file name.</span></span>

  <span data-ttu-id="fb109-115">예:</span><span class="sxs-lookup"><span data-stu-id="fb109-115">Examples:</span></span>

  ```xml
  <EmbeddedResource Include="X.resx" ManifestResourceName="SomeName" />
  -or-
  <EmbeddedResource Include="X.fr-FR.resx" ManifestResourceName="SomeName.fr-FR" />
  ```

  <span data-ttu-id="fb109-116">**생성된 리소스 매니페스트 파일 이름**: *SomeName.resources* 또는 *SomeName.fr-FR.resources*.</span><span class="sxs-lookup"><span data-stu-id="fb109-116">**Generated resource manifest file name**: *SomeName.resources* or *SomeName.fr-FR.resources*.</span></span>

- <span data-ttu-id="fb109-117">이전 규칙이 적용되지 않고 `EmbeddedResource` 요소의 `DependentUpon` 특성이 소스 파일로 설정된 경우 소스 파일의 첫 번째 클래스의 형식 이름이 리소스 매니페스트 파일 이름에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb109-117">If the previous rules don't apply, and the `DependentUpon` attribute on the `EmbeddedResource` element is set to a source file, the type name of the first class in the source file is used in the resource manifest file name.</span></span> <span data-ttu-id="fb109-118">구체적으로 말하면 생성된 파일 이름은 *Namespace.Classname\[.Culture].resources*입니다.</span><span class="sxs-lookup"><span data-stu-id="fb109-118">More specifically, the generated file name is *Namespace.Classname\[.Culture].resources*.</span></span>

  <span data-ttu-id="fb109-119">예:</span><span class="sxs-lookup"><span data-stu-id="fb109-119">Examples:</span></span>

  ```xml
  <EmbeddedResource Include="X.resx" DependentUpon="MyTypes.cs">
  -or-
  <EmbeddedResource Include="X.fr-FR.resx" DependentUpon="MyTypes.cs">
  ```

  <span data-ttu-id="fb109-120">**생성된 리소스 매니페스트 파일 이름**: *Namespace.Classname.resources* 또는 *Namespace.Classname.fr-FR.resources*(여기서 `Namespace.Classname`은 *MyTypes.cs*의 첫 번째 클래스 이름).</span><span class="sxs-lookup"><span data-stu-id="fb109-120">**Generated resource manifest file name**: *Namespace.Classname.resources* or *Namespace.Classname.fr-FR.resources* (where `Namespace.Classname` is the name of the first class in *MyTypes.cs*).</span></span>

- <span data-ttu-id="fb109-121">이전 규칙이 적용되지 않고, `EmbeddedResourceUseDependentUponConvention`이 `true`(.NET Core 기본값)이고, 기본 파일 이름이 동일한 *.resx* 파일과 공동 배치된 소스 파일이 있는 경우 *.resx* 파일은 일치하는 소스 파일에 따라 달라지며 생성된 이름은 이전 규칙과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="fb109-121">If the previous rules don't apply, `EmbeddedResourceUseDependentUponConvention` is `true` (the default for .NET Core), and there's a source file colocated with a *.resx* file that has the same base file name, the *.resx* file is made dependent upon the matching source file, and the generated name is the same as in the previous rule.</span></span> <span data-ttu-id="fb109-122">이는 .NET Core 프로젝트의 "기본 설정" 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="fb109-122">This is the "default settings" rule for .NET Core projects.</span></span>
  
  <span data-ttu-id="fb109-123">예:</span><span class="sxs-lookup"><span data-stu-id="fb109-123">Examples:</span></span>
  
  <span data-ttu-id="fb109-124">*MyTypes.cs* 및 *MyTypes.resx* 또는 *MyTypes.fr-FR.resx* 파일이 동일한 폴더에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb109-124">Files *MyTypes.cs* and *MyTypes.resx* or *MyTypes.fr-FR.resx* exist in the same folder.</span></span>
  
  <span data-ttu-id="fb109-125">**생성된 리소스 매니페스트 파일 이름**: *Namespace.Classname.resources* 또는 *Namespace.Classname.fr-FR.resources*(여기서 `Namespace.Classname`은 *MyTypes.cs*의 첫 번째 클래스 이름).</span><span class="sxs-lookup"><span data-stu-id="fb109-125">**Generated resource manifest file name**: *Namespace.Classname.resources* or *Namespace.Classname.fr-FR.resources* (where `Namespace.Classname` is the name of the first class in *MyTypes.cs*).</span></span>

- <span data-ttu-id="fb109-126">위 규칙이 모두 적용되지 않는 경우 생성된 리소스 매니페스트 파일 이름은 *RootNamespace.RelativePathWithDotsForSlashes.\[Culture.]resources*입니다.</span><span class="sxs-lookup"><span data-stu-id="fb109-126">If none of the previous rules apply, the generated resource manifest file name is *RootNamespace.RelativePathWithDotsForSlashes.\[Culture.]resources*.</span></span> <span data-ttu-id="fb109-127">상대 경로는 설정된 경우 `EmbeddedResource` 요소의 `Link` 특성 값입니다.</span><span class="sxs-lookup"><span data-stu-id="fb109-127">The relative path is the value of the `Link` attribute of the `EmbeddedResource` element if it's set.</span></span> <span data-ttu-id="fb109-128">그렇지 않으면 상대 경로는 `EmbeddedResource` 요소의 `Identity` 특성 값입니다.</span><span class="sxs-lookup"><span data-stu-id="fb109-128">Otherwise, the relative path is the value of the `Identity` attribute of the `EmbeddedResource` element.</span></span> <span data-ttu-id="fb109-129">Visual Studio에서 이 경로는 프로젝트 루트에서 솔루션 탐색기 내 파일까지의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="fb109-129">In Visual Studio, this is the path from the project root to the file in Solution Explorer.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="fb109-130">권장 조치</span><span class="sxs-lookup"><span data-stu-id="fb109-130">Recommended action</span></span>

<span data-ttu-id="fb109-131">생성된 매니페스트 이름에 만족하지 않는다면 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb109-131">If you're unsatisfied with the generated manifest names, you can:</span></span>

- <span data-ttu-id="fb109-132">앞서 설명한 명명 규칙 중 하나에 따라 리소스 파일 메타데이터를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="fb109-132">Modify your resource file metadata according to one of the previously described naming rules.</span></span>

- <span data-ttu-id="fb109-133">프로젝트 파일에서 `EmbeddedResourceUseDependentUponConvention`을 `false`로 설정하여 새 규칙을 완전히 옵트아웃합니다.</span><span class="sxs-lookup"><span data-stu-id="fb109-133">Set `EmbeddedResourceUseDependentUponConvention` to `false` in your project file to opt out of the new convention entirely:</span></span>

   ```xml
   <EmbeddedResourceUseDependentUponConvention>false</EmbeddedResourceUseDependentUponConvention>
   ```

   > [!NOTE]
   > <span data-ttu-id="fb109-134">`LogicalName` 또는 `ManifestResourceName` 특성이 있으면 생성된 파일 이름에도 해당 값이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb109-134">If the `LogicalName` or `ManifestResourceName` attributes are present, their values will still be used for the generated file name.</span></span>

#### <a name="category"></a><span data-ttu-id="fb109-135">범주</span><span class="sxs-lookup"><span data-stu-id="fb109-135">Category</span></span>

<span data-ttu-id="fb109-136">MSBuild</span><span class="sxs-lookup"><span data-stu-id="fb109-136">MSBuild</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="fb109-137">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="fb109-137">Affected APIs</span></span>

<span data-ttu-id="fb109-138">N/A</span><span class="sxs-lookup"><span data-stu-id="fb109-138">N/A</span></span>
