---
title: 세계화 및 ICU
ms.date: 05/21/2020
helpviewer_keywords:
- globalization [.NET], about globalization
- global applications, globalization
- international applications [.NET], globalization
- world-ready applications, globalization
- application development [.NET], globalization
- culture, globalization
- icu, icu on windows, ms-icu
ms.openlocfilehash: d0361ba41b3a10d6a316341fcdacb869e7a35d26
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94827115"
---
# <a name="net-globalization-and-icu"></a><span data-ttu-id="83445-102">.NET 세계화 및 ICU</span><span class="sxs-lookup"><span data-stu-id="83445-102">.NET globalization and ICU</span></span>

<span data-ttu-id="83445-103">과거에 .NET 세계화 API는 플랫폼마다 다른 기본 라이브러리를 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="83445-103">In the past, the .NET globalization APIs used different underlying libraries on different platforms.</span></span> <span data-ttu-id="83445-104">Unix에서는 [ICU(International Components for Unicode)](http://site.icu-project.org/home)를 사용했고, Windows에서는 [NLS(National Language Support)](/windows/win32/intl/national-language-support)를 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="83445-104">On Unix, the APIs used [International Components for Unicode (ICU)](http://site.icu-project.org/home), and on Windows, they used [National Language Support (NLS)](/windows/win32/intl/national-language-support).</span></span> <span data-ttu-id="83445-105">이로 인해 서로 다른 플랫폼에서 애플리케이션을 실행할 때 일부 세계화 API의 동작이 약간 달랐습니다.</span><span class="sxs-lookup"><span data-stu-id="83445-105">This resulted in some behavioral differences in a handful of globalization APIs when running applications on different platforms.</span></span> <span data-ttu-id="83445-106">다음 영역에서는 동작이 확실히 달랐습니다.</span><span class="sxs-lookup"><span data-stu-id="83445-106">Behavior differences were evident in these areas:</span></span>

- <span data-ttu-id="83445-107">문화권 및 문화권 데이터</span><span class="sxs-lookup"><span data-stu-id="83445-107">Cultures and culture data</span></span>
- <span data-ttu-id="83445-108">문자열 대/소문자 구분</span><span class="sxs-lookup"><span data-stu-id="83445-108">String casing</span></span>
- <span data-ttu-id="83445-109">문자열 정렬 및 검색</span><span class="sxs-lookup"><span data-stu-id="83445-109">String sorting and searching</span></span>
- <span data-ttu-id="83445-110">정렬 키</span><span class="sxs-lookup"><span data-stu-id="83445-110">Sort keys</span></span>
- <span data-ttu-id="83445-111">문자열 정규화</span><span class="sxs-lookup"><span data-stu-id="83445-111">String normalization</span></span>
- <span data-ttu-id="83445-112">IDN(다국어 도메인 이름) 지원</span><span class="sxs-lookup"><span data-stu-id="83445-112">Internationalized Domain Names (IDN) support</span></span>
- <span data-ttu-id="83445-113">Linux의 표준 시간대 표시 이름</span><span class="sxs-lookup"><span data-stu-id="83445-113">Time zone display name on Linux</span></span>

<span data-ttu-id="83445-114">.NET 5.0부터는 사용되는 기본 라이브러리에 대한 개발자의 제어가 향상되면서 애플리케이션의 플랫폼 간 차이를 방지할 수 있게 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="83445-114">Starting with .NET 5.0, developers have more control over which underlying library is used, enabling applications to avoid differences across platforms.</span></span>

## <a name="icu-on-windows"></a><span data-ttu-id="83445-115">Windows의 ICU</span><span class="sxs-lookup"><span data-stu-id="83445-115">ICU on Windows</span></span>

<span data-ttu-id="83445-116">Windows 10 2019년 5월 업데이트 이상 버전에는 OS의 일부로 [icu.dll](/windows/win32/intl/international-components-for-unicode--icu-)이 포함되어 있으며, .NET 5.0 이상 버전에서는 기본적으로 ICU를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="83445-116">Windows 10 May 2019 Update and later versions include [icu.dll](/windows/win32/intl/international-components-for-unicode--icu-) as part of the OS, and .NET 5.0 and later versions use ICU by default.</span></span> <span data-ttu-id="83445-117">Windows에서 실행하는 경우 .NET 5.0 이상 버전은 `icu.dll`을 로드하려 시도하고, 사용 가능하면 세계화 구현에 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="83445-117">When running on Windows, .NET 5.0 and later versions try to load `icu.dll` and, if it's available, use it for the globalization implementation.</span></span> <span data-ttu-id="83445-118">이전 버전의 Windows에서 실행하는 경우처럼 ICU 라이브러리를 찾을 수 없거나 로드할 수 없다면 .NET 5.0 이상 버전은 NLS 기반 구현으로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="83445-118">If the ICU library can't be found or loaded, such as when running on older versions of Windows, .NET 5.0 and later versions fall back to the NLS-based implementation.</span></span>

> [!NOTE]
> <span data-ttu-id="83445-119">ICU를 사용하는 경우에도 `CurrentCulture`, `CurrentUICulture`, `CurrentRegion` 멤버는 여전히 Windows 운영 체제 API를 사용하여 사용자 설정을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="83445-119">Even when using ICU, the `CurrentCulture`, `CurrentUICulture`, and `CurrentRegion` members still use Windows operating system APIs to honor user settings.</span></span>

### <a name="behavioral-differences"></a><span data-ttu-id="83445-120">동작의 차이</span><span class="sxs-lookup"><span data-stu-id="83445-120">Behavioral differences</span></span>

<span data-ttu-id="83445-121">앱을 업그레이드하여 .NET 5를 대상으로 지정하면 세계화 기능을 사용 중임을 인식하지 못하는 경우에도 앱에 변경 내용이 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83445-121">If you upgrade your app to target .NET 5, you might see changes in your app even if you don't realize you're using globalization facilities.</span></span> <span data-ttu-id="83445-122">이 섹션에는 표시될 수 있는 동작 변경 중 하나가 나열되어 있지만 다른 변경도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83445-122">This section lists one of the behavioral changes you might see, but there are others too.</span></span>

##### <a name="stringindexof"></a><span data-ttu-id="83445-123">String.IndexOf</span><span class="sxs-lookup"><span data-stu-id="83445-123">String.IndexOf</span></span>

<span data-ttu-id="83445-124"><xref:System.String.IndexOf(System.String)?displayProperty=nameWithType>을 호출하여 문자열에서 줄 바꿈 문자의 인덱스를 찾는 다음 코드를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="83445-124">Consider the following code that calls <xref:System.String.IndexOf(System.String)?displayProperty=nameWithType> to find the index of the newline character in a string.</span></span>

```csharp
string s = "Hello\r\nworld!";
int idx = s.IndexOf("\n");
Console.WriteLine(idx);
```

- <span data-ttu-id="83445-125">Windows의 .NET 이전 버전에서는 코드 조각이 `6`을 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="83445-125">In previous versions of .NET on Windows, the snippet prints `6`.</span></span>
- <span data-ttu-id="83445-126">Windows 10 2019년 5월 업데이트 이상 버전의 .NET 5.0 이상 버전에서는 코드 조각이 `-1`을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="83445-126">In .NET 5.0 and later versions on Windows 10 May 2019 Update and later versions, the snippet prints `-1`.</span></span>

<span data-ttu-id="83445-127">문화권을 구분하는 검색 대신 서수 검색을 수행하여 이 코드를 수정하려면 <xref:System.String.IndexOf(System.String,System.StringComparison)> 오버로드를 호출하고 <xref:System.StringComparison.Ordinal?displayProperty=nameWithType>을 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="83445-127">To fix this code by conducting an ordinal search instead of a culture-sensitive search, call the <xref:System.String.IndexOf(System.String,System.StringComparison)> overload and pass in <xref:System.StringComparison.Ordinal?displayProperty=nameWithType> as an argument.</span></span>

<span data-ttu-id="83445-128">코드 분석 규칙 [CA1307: 명확성을 위해 StringComparison 지정](../../../docs/fundamentals/code-analysis/quality-rules/ca1307.md) 및 [CA1309: 서수 StringComparison 사용](../../../docs/fundamentals/code-analysis/quality-rules/ca1309.md)을 실행하여 코드에서 이러한 호출 사이트를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83445-128">You can run code analysis rules [CA1307: Specify StringComparison for clarity](../../../docs/fundamentals/code-analysis/quality-rules/ca1307.md) and [CA1309: Use ordinal StringComparison](../../../docs/fundamentals/code-analysis/quality-rules/ca1309.md) to find these call sites in your code.</span></span>

<span data-ttu-id="83445-129">자세한 내용은 [.NET 5+에서 문자열 비교 시 동작 변경](../base-types/string-comparison-net-5-plus.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="83445-129">For more information, see [Behavior changes when comparing strings on .NET 5+](../base-types/string-comparison-net-5-plus.md).</span></span>

### <a name="use-nls-instead-of-icu"></a><span data-ttu-id="83445-130">ICU 대신 NLS 사용</span><span class="sxs-lookup"><span data-stu-id="83445-130">Use NLS instead of ICU</span></span>

<span data-ttu-id="83445-131">NLS 대신 ICU를 사용하면 일부 세계화 관련 작업에서 동작 차이가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83445-131">Using ICU instead of NLS may result in behavioral differences with some globalization-related operations.</span></span> <span data-ttu-id="83445-132">개발자는 NLS 사용으로 되돌리기 위해 ICU 구현을 옵트아웃할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83445-132">To revert back to using NLS, a developer can opt out of the ICU implementation.</span></span> <span data-ttu-id="83445-133">애플리케이션은 다음 방법으로 NLS 모드를 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83445-133">Applications can enable NLS mode in any of the following ways:</span></span>

- <span data-ttu-id="83445-134">프로젝트 파일에서:</span><span class="sxs-lookup"><span data-stu-id="83445-134">In the project file:</span></span>

  ```xml
  <ItemGroup>
    <RuntimeHostConfigurationOption Include="System.Globalization.UseNls" Value="true" />
  </ItemGroup>
  ```

- <span data-ttu-id="83445-135">파일 `runtimeconfig.json`에서:</span><span class="sxs-lookup"><span data-stu-id="83445-135">In the `runtimeconfig.json` file:</span></span>

  ```json
  {
    "runtimeOptions": {
       "configProperties": {
         "System.Globalization.UseNls": true
        }
    }
  }
  ```

- <span data-ttu-id="83445-136">환경 변수 `DOTNET_SYSTEM_GLOBALIZATION_USENLS`를 `true` 또는 `1`으로 설정.</span><span class="sxs-lookup"><span data-stu-id="83445-136">By setting the environment variable `DOTNET_SYSTEM_GLOBALIZATION_USENLS` to the value `true` or `1`.</span></span>

> [!NOTE]
> <span data-ttu-id="83445-137">프로젝트 또는 `runtimeconfig.json` 파일에 설정된 값은 환경 변수보다 우선적으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="83445-137">A value set in the project or in the `runtimeconfig.json` file takes precedence over the environment variable.</span></span>

<span data-ttu-id="83445-138">자세한 내용은 [런타임 구성 설정](../../core/run-time-config/globalization.md#nls)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="83445-138">For more information, see [Run-time config settings](../../core/run-time-config/globalization.md#nls).</span></span>

## <a name="app-local-icu"></a><span data-ttu-id="83445-139">앱 로컬 ICU</span><span class="sxs-lookup"><span data-stu-id="83445-139">App-local ICU</span></span>

<span data-ttu-id="83445-140">각 ICU 릴리스는 버그 수정뿐 아니라 세계 언어를 설명하는 업데이트된 CLDR(Common Locale Data Repository) 데이터를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83445-140">Each release of ICU may bring with it bug fixes as well as updated Common Locale Data Repository (CLDR) data that describes the world's languages.</span></span> <span data-ttu-id="83445-141">ICU 버전 간 이동은 세계화 관련 작업과 관련하여 앱 동작에 미묘한 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83445-141">Moving between versions of ICU can subtly impact app behavior when it comes to globalization-related operations.</span></span> <span data-ttu-id="83445-142">애플리케이션 개발자가 모든 배포에서 일관성을 유지할 수 있도록 .NET 5.0 이상 버전에서는 Windows 및 Unix의 앱이 자체 ICU 복사본을 갖고 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83445-142">To help application developers ensure consistency across all deployments, .NET 5.0 and later versions enable apps on both Windows and Unix to carry and use their own copy of ICU.</span></span>

<span data-ttu-id="83445-143">애플리케이션은 다음 방법으로 앱 로컬 ICU 구현 모드를 옵트인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83445-143">Applications can opt in to an app-local ICU implementation mode in any of the following ways:</span></span>

- <span data-ttu-id="83445-144">프로젝트 파일에서:</span><span class="sxs-lookup"><span data-stu-id="83445-144">In  the project file:</span></span>

  ```xml
  <ItemGroup>
    <RuntimeHostConfigurationOption Include="System.Globalization.AppLocalIcu" Value="<suffix>:<version> or <version>" />
  </ItemGroup>
  ```

- <span data-ttu-id="83445-145">파일 `runtimeconfig.json`에서:</span><span class="sxs-lookup"><span data-stu-id="83445-145">In the `runtimeconfig.json` file:</span></span>

  ```json
  {
    "runtimeOptions": {
       "configProperties": {
         "System.Globalization.AppLocalIcu": "<suffix>:<version> or <version>"
       }
    }
  }
  ```

- <span data-ttu-id="83445-146">환경 변수 `DOTNET_SYSTEM_GLOBALIZATION_APPLOCALICU`를 `<suffix>:<version>` 또는 `<version>`으로 설정.</span><span class="sxs-lookup"><span data-stu-id="83445-146">By setting the environment variable `DOTNET_SYSTEM_GLOBALIZATION_APPLOCALICU` to the value `<suffix>:<version>` or `<version>`.</span></span>

  <span data-ttu-id="83445-147">`<suffix>`: 공용 ICU 패키징 규칙에 따라 길이가 36자 미만인 선택적 접미사입니다.</span><span class="sxs-lookup"><span data-stu-id="83445-147">`<suffix>`: Optional suffix of fewer than 36 characters in length, following the public ICU packaging conventions.</span></span> <span data-ttu-id="83445-148">사용자 지정 ICU를 빌드할 때 lib 이름을 생성하고 내보낸 기호 이름이 접미사를 포함하도록(예: `libicuucmyapp`, 여기서 `myapp`은 접미사) 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83445-148">When building a custom ICU, you can customize it to produce the lib names and exported symbol names to contain a suffix, for example, `libicuucmyapp`, where `myapp` is the suffix.</span></span>

  <span data-ttu-id="83445-149">`<version>`: 유효한 ICU 버전입니다(예: 67.1).</span><span class="sxs-lookup"><span data-stu-id="83445-149">`<version>`: A valid ICU version, for example, 67.1.</span></span> <span data-ttu-id="83445-150">이 버전은 이진 파일을 로드하고 내보낸 기호를 가져오는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="83445-150">This version is used to load the binaries and to get the exported symbols.</span></span>

<span data-ttu-id="83445-151">앱 로컬 스위치가 설정된 경우 ICU를 로드하기 위해 .NET은 여러 경로를 검색하는 <xref:System.Runtime.InteropServices.NativeLibrary.TryLoad%2A?displayProperty=nameWithType> 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="83445-151">To load ICU when the app-local switch is set, .NET uses the <xref:System.Runtime.InteropServices.NativeLibrary.TryLoad%2A?displayProperty=nameWithType> method, which probes multiple paths.</span></span> <span data-ttu-id="83445-152">메서드는 먼저 `NATIVE_DLL_SEARCH_DIRECTORIES` 속성에서 라이브러리를 찾으려고 시도합니다. 이 라이브러리는 앱의 `deps.json` 파일에 기반한 dotnet 호스트에서 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="83445-152">The method first tries to find the library in the `NATIVE_DLL_SEARCH_DIRECTORIES` property, which is created by the dotnet host based on the `deps.json` file for the app.</span></span> <span data-ttu-id="83445-153">자세한 내용은 [기본 검색](../../core/dependency-loading/default-probing.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="83445-153">For more information, see [Default probing](../../core/dependency-loading/default-probing.md).</span></span>

<span data-ttu-id="83445-154">자체 포함 앱의 경우 ICU가 앱 디렉터리에 있는지 확인하는 것 외에 특별한 작업이 필요하지 않습니다(자체 포함 앱의 경우 작업 디렉터리의 기본값은 `NATIVE_DLL_SEARCH_DIRECTORIES`).</span><span class="sxs-lookup"><span data-stu-id="83445-154">For self-contained apps, no special action is required by the user, other than making sure ICU is in the app directory (for self-contained apps, the working directory defaults to `NATIVE_DLL_SEARCH_DIRECTORIES`).</span></span>

<span data-ttu-id="83445-155">NuGet 패키지를 통해 사용하는 ICU는 프레임워크 종속 애플리케이션에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="83445-155">If you're consuming ICU via a NuGet package, this works in framework-dependent applications.</span></span> <span data-ttu-id="83445-156">NuGet은 네이티브 자산을 확인하여 `deps.json` 파일 및 `runtimes` 디렉터리 아래에 있는 애플리케이션의 출력 디렉터리에 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="83445-156">NuGet resolves the native assets and includes them in the `deps.json` file and in the output directory for the application under the `runtimes` directory.</span></span> <span data-ttu-id="83445-157">.NET은 여기에서 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="83445-157">.NET loads it from there.</span></span>

<span data-ttu-id="83445-158">ICU가 로컬 빌드에서 사용되는 프레임워크 종속 앱(자체 포함 앱 아님)의 경우 추가 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83445-158">For framework-dependent apps (not self contained) where ICU is consumed from a local build, you must take additional steps.</span></span> <span data-ttu-id="83445-159">.NET SDK에는 "느슨한" 네이티브 이진 파일을 `deps.json`에 통합하는 기능이 아직 없습니다([이 SDK 문제](https://github.com/dotnet/sdk/issues/11373) 참조).</span><span class="sxs-lookup"><span data-stu-id="83445-159">The .NET SDK doesn't yet have a feature for "loose" native binaries to be incorporated into `deps.json` (see [this SDK issue](https://github.com/dotnet/sdk/issues/11373)).</span></span> <span data-ttu-id="83445-160">대신 애플리케이션의 프로젝트 파일에 추가 정보를 추가하여 이 기능을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83445-160">Instead, you can enable this by adding additional information into the application's project file.</span></span> <span data-ttu-id="83445-161">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="83445-161">For example:</span></span>

```xml
<ItemGroup>
  <IcuAssemblies Include="icu\*.so*" />
  <RuntimeTargetsCopyLocalItems Include="@(IcuAssemblies)" AssetType="native" CopyLocal="true" DestinationSubDirectory="runtimes/linux-x64/native/" DestinationSubPath="%(FileName)%(Extension)" RuntimeIdentifier="linux-x64" NuGetPackageId="System.Private.Runtime.UnicodeData" />
</ItemGroup>
```

<span data-ttu-id="83445-162">지원되는 런타임의 모든 ICU 이진 파일에 이 작업을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83445-162">This must be done for all the ICU binaries for the supported runtimes.</span></span> <span data-ttu-id="83445-163">또한 `RuntimeTargetsCopyLocalItems` 항목 그룹의 `NuGetPackageId` 메타데이터는 프로젝트가 실제로 참조하는 NuGet 패키지와 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83445-163">Also, the `NuGetPackageId` metadata in the `RuntimeTargetsCopyLocalItems` item group needs to match a NuGet package that the project actually references.</span></span>

### <a name="macos-behavior"></a><span data-ttu-id="83445-164">macOS 동작</span><span class="sxs-lookup"><span data-stu-id="83445-164">macOS behavior</span></span>

<span data-ttu-id="83445-165">`macOS`에는 Linux 로더와는 다른, `match-o` 파일에 지정된 load 명령에서 종속 동적 라이브러리를 확인하는 동작이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83445-165">`macOS` has a different behavior for resolving dependent dynamic libraries from the load commands specified in the `match-o` file than the Linux loader.</span></span> <span data-ttu-id="83445-166">Linux 로더에서 .NET은 ICU 종속성 그래프를 충족하기 위해 `libicudata`, `libicuuc`, `libicui18n`을 (이 순서로) 시도할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83445-166">In the Linux loader, .NET can try `libicudata`, `libicuuc`, and `libicui18n` (in that order) to satisfy ICU dependency graph.</span></span> <span data-ttu-id="83445-167">하지만 macOS에서는 이것이 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="83445-167">However, on macOS, this doesn't work.</span></span> <span data-ttu-id="83445-168">macOS에서 ICU를 빌드하는 경우 기본적으로 `libicuuc`에서 이러한 load 명령을 사용하여 동적 라이브러리를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="83445-168">When building ICU on macOS, you, by default, get a dynamic library with these load commands in `libicuuc`.</span></span> <span data-ttu-id="83445-169">다음 코드 조각은 예제를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="83445-169">The following snippet shows an example.</span></span>

```sh
~/ % otool -L /Users/santifdezm/repos/icu-build/icu/install/lib/libicuuc.67.1.dylib
/Users/santifdezm/repos/icu-build/icu/install/lib/libicuuc.67.1.dylib:
 libicuuc.67.dylib (compatibility version 67.0.0, current version 67.1.0)
 libicudata.67.dylib (compatibility version 67.0.0, current version 67.1.0)
 /usr/lib/libSystem.B.dylib (compatibility version 1.0.0, current version 1281.100.1)
 /usr/lib/libc++.1.dylib (compatibility version 1.0.0, current version 902.1.0)
```

<span data-ttu-id="83445-170">이러한 명령은 ICU의 다른 구성 요소에 대한 종속 라이브러리의 이름을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="83445-170">These commands just reference the name of the dependent libraries for the other components of ICU.</span></span> <span data-ttu-id="83445-171">로더는 `dlopen` 규칙에 따라 검색을 수행합니다. 그러려면 시스템 디렉터리에 이러한 라이브러리가 있거나 `LD_LIBRARY_PATH` 환경 변수를 설정하거나 앱 수준 디렉터리에 ICU가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83445-171">The loader performs the search following the `dlopen` conventions, which involves having these libraries in the system directories or setting the `LD_LIBRARY_PATH` env vars, or having ICU at the app-level directory.</span></span> <span data-ttu-id="83445-172">`LD_LIBRARY_PATH`를 설정할 수 없거나 ICU 바이너리가 앱 수준 디렉터리에 있는지 확인할 수 없다면 몇 가지 추가 작업을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83445-172">If you can't set `LD_LIBRARY_PATH` or ensure that ICU binaries are at the app-level directory, you will need to do some extra work.</span></span>

<span data-ttu-id="83445-173">`@loader_path`와 같이 해당 load 명령을 사용하여 이진 파일과 동일한 디렉터리에서 해당 종속성을 검색하도록 로더에게 지시하는 로더를 위한 몇 가지 지시문이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83445-173">There are some directives for the loader, like `@loader_path`, which tell the loader to search for that dependency in the same directory as the binary with that load command.</span></span> <span data-ttu-id="83445-174">두 가지 방법으로 이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83445-174">There are two ways to achieve this:</span></span>

- `install_name_tool -change`

  <span data-ttu-id="83445-175">다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="83445-175">Run the following commands:</span></span>

  ```bash
  install_name_tool -change "libicudata.67.dylib" "@loader_path/libicudata.67.dylib" /path/to/libicuuc.67.1.dylib
  install_name_tool -change "libicudata.67.dylib" "@loader_path/libicudata.67.dylib" /path/to/libicui18n.67.1.dylib
  install_name_tool -change "libicuuc.67.dylib" "@loader_path/libicuuc.67.dylib" /path/to/libicui18n.67.1.dylib
  ```

- <span data-ttu-id="83445-176">`@loader_path`로 설치 이름을 생성하도록 ICU 패치</span><span class="sxs-lookup"><span data-stu-id="83445-176">Patch ICU to produce the install names with `@loader_path`</span></span>

  <span data-ttu-id="83445-177">autoconf(`./runConfigureICU`)를 실행하기 전에 [이 줄](https://github.com/unicode-org/icu/blob/ef91cc3673d69a5e00407cda94f39fcda3131451/icu4c/source/config/mh-darwin#L32-L37)을 다음으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="83445-177">Before running autoconf (`./runConfigureICU`), change [these lines](https://github.com/unicode-org/icu/blob/ef91cc3673d69a5e00407cda94f39fcda3131451/icu4c/source/config/mh-darwin#L32-L37) to:</span></span>

  ```
  LD_SONAME = -Wl,-compatibility_version -Wl,$(SO_TARGET_VERSION_MAJOR) -Wl,-current_version -Wl,$(SO_TARGET_VERSION) -install_name @loader_path/$(notdir $(MIDDLE_SO_TARGET))
  ```

## <a name="icu-on-webassembly"></a><span data-ttu-id="83445-178">WebAssembly의 ICU</span><span class="sxs-lookup"><span data-stu-id="83445-178">ICU on WebAssembly</span></span>

<span data-ttu-id="83445-179">WebAssembly 워크로드 전용인 ICU 버전을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83445-179">A version of ICU is available that's specifically for WebAssembly workloads.</span></span> <span data-ttu-id="83445-180">이 버전은 데스크톱 프로필과의 세계화 호환성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="83445-180">This version provides globalization compatibility with desktop profiles.</span></span> <span data-ttu-id="83445-181">ICU 데이터 파일 크기를 24MB에서 1.4MB(또는 Brotli로 압축된 경우 0.3MB 이하)로 줄이기 위해 이 워크로드에는 몇 가지 제한 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83445-181">To reduce the ICU data file size from 24 MB to 1.4 MB (or ~0.3 MB if compressed with Brotli), this workload has a handful of limitations.</span></span>

<span data-ttu-id="83445-182">다음 API는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="83445-182">The following APIs are not supported:</span></span>

- <xref:System.Globalization.CultureInfo.EnglishName?displayProperty=nameWithType>
- <xref:System.Globalization.CultureInfo.NativeName?displayProperty=nameWithType>
- <xref:System.Globalization.DateTimeFormatInfo.NativeCalendarName?displayProperty=nameWithType>
- <xref:System.Globalization.RegionInfo.NativeName?displayProperty=nameWithType>

<span data-ttu-id="83445-183">다음 API는 제한적으로 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="83445-183">The following APIs are supported with limitations:</span></span>

- <span data-ttu-id="83445-184"><xref:System.String.Normalize(System.Text.NormalizationForm)?displayProperty=nameWithType> 및 <xref:System.String.IsNormalized(System.Text.NormalizationForm)?displayProperty=nameWithType>는 거의 사용되지 않는 <xref:System.Text.NormalizationForm.FormKC> 및 <xref:System.Text.NormalizationForm.FormKD> 형식을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="83445-184"><xref:System.String.Normalize(System.Text.NormalizationForm)?displayProperty=nameWithType> and <xref:System.String.IsNormalized(System.Text.NormalizationForm)?displayProperty=nameWithType> don't support the rarely used <xref:System.Text.NormalizationForm.FormKC> and <xref:System.Text.NormalizationForm.FormKD> forms.</span></span>
- <span data-ttu-id="83445-185"><xref:System.Globalization.RegionInfo.CurrencyNativeName?displayProperty=nameWithType>는 <xref:System.Globalization.RegionInfo.CurrencyEnglishName?displayProperty=nameWithType>와 동일한 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="83445-185"><xref:System.Globalization.RegionInfo.CurrencyNativeName?displayProperty=nameWithType> returns the same value as <xref:System.Globalization.RegionInfo.CurrencyEnglishName?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="83445-186">또한 [dotnet/icu repo](https://github.com/dotnet/icu/blob/0f49268ddfd3331ca090f1c51d2baa2f75f6c6c0/icu-filters/optimal.json#L6-L54)에서 지원되는 로캘 목록을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83445-186">In addition, a list of supported locales can be found on the [dotnet/icu repo](https://github.com/dotnet/icu/blob/0f49268ddfd3331ca090f1c51d2baa2f75f6c6c0/icu-filters/optimal.json#L6-L54).</span></span>
