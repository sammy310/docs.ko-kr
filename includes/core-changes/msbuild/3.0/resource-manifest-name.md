---
ms.openlocfilehash: f24a29a00a1bff34a452c43716d76bf72ef277b5
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83206223"
---
### <a name="resource-manifest-file-name-change"></a><span data-ttu-id="42838-101">리소스 매니페스트 파일 이름 변경</span><span class="sxs-lookup"><span data-stu-id="42838-101">Resource manifest file name change</span></span>

<span data-ttu-id="42838-102">.NET Core 3.0부터 기본 사례에서 MSBuild는 리소스 파일에 대해 다른 매니페스트 파일 이름을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="42838-102">Starting in .NET Core 3.0, in the default case, MSBuild generates a different manifest file name for resource files.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="42838-103">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="42838-103">Version introduced</span></span>

<span data-ttu-id="42838-104">3.0</span><span class="sxs-lookup"><span data-stu-id="42838-104">3.0</span></span>

#### <a name="change-description"></a><span data-ttu-id="42838-105">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="42838-105">Change description</span></span>

<span data-ttu-id="42838-106">.NET Core 3.0보다 이전 버전에서는 프로젝트 파일의 `EmbeddedResource` 항목에 대해 `LogicalName`, `ManifestResourceName` 또는 `DependentUpon` 메타데이터가 지정되지 않은 경우 MSBuild는 `<RootNamespace>.<ResourceFilePathFromProjectRoot>.resources` 패턴으로 매니페스트 파일 이름을 생성했습니다.</span><span class="sxs-lookup"><span data-stu-id="42838-106">Prior to .NET Core 3.0, if no `LogicalName`, `ManifestResourceName`, or `DependentUpon` metadata was specified for an `EmbeddedResource` item in the project file, MSBuild generated a manifest file name in the pattern `<RootNamespace>.<ResourceFilePathFromProjectRoot>.resources`.</span></span> <span data-ttu-id="42838-107">프로젝트 파일에 `RootNamespace`가 정의되어 있지 않은 경우 기본적으로 프로젝트 이름으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="42838-107">If `RootNamespace` is not defined in the project file, it defaults to the project name.</span></span> <span data-ttu-id="42838-108">예를 들어, 루트 프로젝트 디렉터리의 *Form1.resx*라는 리소스 파일에 대해 생성된 매니페스트 이름은 *MyProject.Form1.resources*였습니다.</span><span class="sxs-lookup"><span data-stu-id="42838-108">For example, the generated manifest name for a resource file named *Form1.resx* in the root project directory was *MyProject.Form1.resources*.</span></span>

<span data-ttu-id="42838-109">.NET Core 3.0부터 리소스 파일이 동일한 이름의 소스 파일과 공동 배치되는 경우(예: *Form1.resx*와 *Form1.cs*) MSBuild는 소스 파일의 형식 정보를 사용하여 `<Namespace>.<ClassName>.resources` 패턴으로 매니페스트 파일 이름을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="42838-109">Starting in .NET Core 3.0, if a resource file is colocated with a source file of the same name (for example, *Form1.resx* and *Form1.cs*), MSBuild uses type information from the source file to generate the manifest file name in the pattern `<Namespace>.<ClassName>.resources`.</span></span> <span data-ttu-id="42838-110">네임스페이스 및 클래스 이름은 공동 배치된 소스 파일의 첫 번째 형식에서 추출됩니다.</span><span class="sxs-lookup"><span data-stu-id="42838-110">The namespace and class name are extracted from the first type in the colocated source file.</span></span> <span data-ttu-id="42838-111">예를 들어 *Form1.cs*라는 소스 파일과 공동 배치된 *Form1.resx*라는 리소스 파일에 대해 생성된 매니페스트 이름은 *MyNamespace.Form1.resources*입니다.</span><span class="sxs-lookup"><span data-stu-id="42838-111">For example, the generated manifest name for a resource file named *Form1.resx* that's colocated with a source file named *Form1.cs* is *MyNamespace.Form1.resources*.</span></span> <span data-ttu-id="42838-112">중요한 점은 파일 이름의 첫 부분이 이전 버전의 .NET Core와 다르다는 것입니다(*MyProject*가 아니라 *MyNamespace*).</span><span class="sxs-lookup"><span data-stu-id="42838-112">The key thing to note is that the first part of the file name is different to prior versions of .NET Core (*MyNamespace* instead of *MyProject*).</span></span>

> [!NOTE]
> <span data-ttu-id="42838-113">프로젝트 파일의 `EmbeddedResource` 항목에 `LogicalName`, `ManifestResourceName` 또는 `DependentUpon` 메타데이터가 지정되어 있는 경우 이 변경 내용은 해당 리소스 파일에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="42838-113">If you have `LogicalName`, `ManifestResourceName`, or `DependentUpon` metadata specified on an `EmbeddedResource` item in the project file, then this change does not affect that resource file.</span></span>

<span data-ttu-id="42838-114">이 주요 변경 내용은 .NET Core 프로젝트에 `EmbeddedResourceUseDependentUponConvention` 속성을 추가하여 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="42838-114">This breaking change was introduced with the addition of the `EmbeddedResourceUseDependentUponConvention` property to .NET Core projects.</span></span> <span data-ttu-id="42838-115">기본적으로 리소스 파일은 .NET Core 프로젝트 파일에 명시적으로 나열되지 않으므로 생성된 *.resources* 파일의 이름을 지정하는 방법을 지정하는 `DependentUpon` 메타데이터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="42838-115">By default, resource files aren't explicitly listed in a .NET Core project file, so they have no `DependentUpon` metadata to specify how to name the generated *.resources* file.</span></span> <span data-ttu-id="42838-116">`EmbeddedResourceUseDependentUponConvention`이 기본값 `true`로 설정된 경우 MSBuild는 공동 배치된 소스 파일을 찾아 해당 파일에서 네임스페이스 및 클래스 이름을 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="42838-116">When `EmbeddedResourceUseDependentUponConvention` is set to `true`, which is the default, MSBuild looks for a colocated source file and extracts a namespace and class name from that file.</span></span> <span data-ttu-id="42838-117">`EmbeddedResourceUseDependentUponConvention`을 `false`로 설정하면 MSBuild는 이전 동작에 따라, 즉 `RootNamespace`와 상대 파일 경로를 결합하여 매니페스트 이름을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="42838-117">If you set `EmbeddedResourceUseDependentUponConvention` to `false`, MSBuild generates the manifest name according to the previous behavior, which combines `RootNamespace` and the relative file path.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="42838-118">권장 조치</span><span class="sxs-lookup"><span data-stu-id="42838-118">Recommended action</span></span>

<span data-ttu-id="42838-119">대부분의 경우 개발자에게는 아무 작업도 필요하지 않으며 앱은 계속 작동할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="42838-119">In most cases, no action is required on the part of the developer, and your app should continue to work.</span></span> <span data-ttu-id="42838-120">그러나 이 변경으로 앱이 중단되는 경우 다음 중 하나를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42838-120">However, if this change breaks your app, you can either:</span></span>

- <span data-ttu-id="42838-121">새 매니페스트 이름을 예상하도록 코드를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="42838-121">Change your code to expect the new manifest name.</span></span>

- <span data-ttu-id="42838-122">프로젝트 파일에서 `EmbeddedResourceUseDependentUponConvention`을 `false`로 설정하여 새 명명 규칙을 옵트아웃합니다.</span><span class="sxs-lookup"><span data-stu-id="42838-122">Opt out of the new naming convention by setting `EmbeddedResourceUseDependentUponConvention` to `false` in your project file.</span></span>

  ```xml
  <PropertyGroup>
    <EmbeddedResourceUseDependentUponConvention>false</EmbeddedResourceUseDependentUponConvention>
  </PropertyGroup>
  ```

#### <a name="category"></a><span data-ttu-id="42838-123">범주</span><span class="sxs-lookup"><span data-stu-id="42838-123">Category</span></span>

<span data-ttu-id="42838-124">MSBuild</span><span class="sxs-lookup"><span data-stu-id="42838-124">MSBuild</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="42838-125">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="42838-125">Affected APIs</span></span>

<span data-ttu-id="42838-126">N/A</span><span class="sxs-lookup"><span data-stu-id="42838-126">N/A</span></span>
