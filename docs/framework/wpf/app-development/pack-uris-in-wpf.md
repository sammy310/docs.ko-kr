---
title: Pack Uri
description: Uri (uniform resource identifier)를 사용 하 여 Windows Presentation Foundation (WPF)에서 파일을 식별 하 고 로드 하는 여러 가지 방법에 대해 알아봅니다.
ms.date: 03/30/2017
helpviewer_keywords:
- pack URI scheme [WPF]
- loading embedded resources [WPF]
- URIs (Uniform Resource Identifiers)
- Uniform Resource Identifiers (URIs)
- loading non-resource files
- application management [WPF]
ms.assetid: 43adb517-21a7-4df3-98e8-09e9cdf764c4
ms.openlocfilehash: 1d19dec0d846659f8de6ed518a7f98d224354a82
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621693"
---
# <a name="pack-uris-in-wpf"></a><span data-ttu-id="2afa5-103">WPF의 Pack URI</span><span class="sxs-lookup"><span data-stu-id="2afa5-103">Pack URIs in WPF</span></span>

<span data-ttu-id="2afa5-104">WPF (Windows Presentation Foundation)에서 Uri (uniform resource identifier)는 다음을 비롯 한 여러 가지 방법으로 파일을 식별 하 고 로드 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-104">In Windows Presentation Foundation (WPF), uniform resource identifiers (URIs) are used to identify and load files in many ways, including the following:</span></span>

- <span data-ttu-id="2afa5-105">[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]응용 프로그램을 처음 시작할 때 표시할를 지정 하는입니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-105">Specifying the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] to show when an application first starts.</span></span>

- <span data-ttu-id="2afa5-106">이미지 로드</span><span class="sxs-lookup"><span data-stu-id="2afa5-106">Loading images.</span></span>

- <span data-ttu-id="2afa5-107">페이지 탐색</span><span class="sxs-lookup"><span data-stu-id="2afa5-107">Navigating to pages.</span></span>

- <span data-ttu-id="2afa5-108">비실행 데이터 파일 로드</span><span class="sxs-lookup"><span data-stu-id="2afa5-108">Loading non-executable data files.</span></span>

<span data-ttu-id="2afa5-109">또한 Uri는 다음을 포함 하 여 다양 한 위치에서 파일을 식별 하 고 로드 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-109">Furthermore, URIs can be used to identify and load files from a variety of locations, including the following:</span></span>

- <span data-ttu-id="2afa5-110">현재 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-110">The current assembly.</span></span>

- <span data-ttu-id="2afa5-111">참조된 어셈블리</span><span class="sxs-lookup"><span data-stu-id="2afa5-111">A referenced assembly.</span></span>

- <span data-ttu-id="2afa5-112">어셈블리에 상대적인 위치</span><span class="sxs-lookup"><span data-stu-id="2afa5-112">A location relative to an assembly.</span></span>

- <span data-ttu-id="2afa5-113">애플리케이션의 원본 사이트</span><span class="sxs-lookup"><span data-stu-id="2afa5-113">The application's site of origin.</span></span>

<span data-ttu-id="2afa5-114">이러한 위치에서 이러한 형식의 파일을 식별 하 고 로드 하기 위한 일관 된 메커니즘을 제공 하기 위해 WPF는 *PACK URI 체계*의 확장성을 활용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-114">To provide a consistent mechanism for identifying and loading these types of files from these locations, WPF leverages the extensibility of the *pack URI scheme*.</span></span> <span data-ttu-id="2afa5-115">이 항목에서는 태그와 코드의 pack Uri를 사용 하는 방법을 보여 주기 위해 다양 한 시나리오에 대 한 pack Uri를 생성 하는 방법에 대해 설명 하 고, 다양 한 시나리오에 대 한 pack Uri를 생성 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-115">This topic provides an overview of the scheme, covers how to construct pack URIs for a variety of scenarios, discusses absolute and relative URIs and URI resolution, before showing how to use pack URIs from both markup and code.</span></span>

<a name="The_Pack_URI_Scheme"></a>

## <a name="the-pack-uri-scheme"></a><span data-ttu-id="2afa5-116">Pack URI 체계</span><span class="sxs-lookup"><span data-stu-id="2afa5-116">The Pack URI Scheme</span></span>

<span data-ttu-id="2afa5-117">Pack URI 체계는 콘텐츠를 구성 하 고 식별 하기 위한 모델을 설명 하는 OPC ( [Open 패키징 규칙](https://www.ecma-international.org/publications/standards/Ecma-376.htm) ) 사양에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-117">The pack URI scheme is used by the [Open Packaging Conventions](https://www.ecma-international.org/publications/standards/Ecma-376.htm) (OPC) specification, which describes a model for organizing and identifying content.</span></span> <span data-ttu-id="2afa5-118">이 모델의 핵심 요소는 패키지 및 파트입니다. 여기서 *패키지* 는 하나 이상의 논리적 *파트*에 대 한 논리적 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-118">The key elements of this model are packages and parts, where a *package* is a logical container for one or more logical *parts*.</span></span> <span data-ttu-id="2afa5-119">다음 그림에서는 이 개념을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-119">The following figure illustrates this concept.</span></span>

![패키지 및 파트 다이어그램](./media/pack-uris-in-wpf/wpf-package-parts-diagram.png)

<span data-ttu-id="2afa5-121">파트를 식별 하기 위해 OPC 사양은 RFC 2396 (URI (Uniform Resource Identifier): Generic 구문)의 확장성을 활용 하 여 pack URI 체계를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-121">To identify parts, the OPC specification leverages the extensibility of RFC 2396 (Uniform Resource Identifiers (URI): Generic Syntax) to define the pack URI scheme.</span></span>

<span data-ttu-id="2afa5-122">URI로 지정 된 체계는 접두사에 의해 정의 됩니다. http, ftp 및 파일은 잘 알려진 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-122">The scheme that is specified by a URI is defined by its prefix; http, ftp, and file are well-known examples.</span></span> <span data-ttu-id="2afa5-123">Pack URI 체계는 "pack"을 체계로 사용 하 고 두 구성 요소인 authority와 path를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-123">The pack URI scheme uses "pack" as its scheme, and contains two components: authority and path.</span></span> <span data-ttu-id="2afa5-124">다음은 pack URI에 대 한 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-124">The following is the format for a pack URI.</span></span>

<span data-ttu-id="2afa5-125">pack://*authority* / *경로*</span><span class="sxs-lookup"><span data-stu-id="2afa5-125">pack://*authority*/*path*</span></span>

<span data-ttu-id="2afa5-126">*기관은* 파트에 포함 된 패키지 유형을 지정 하는 반면 *경로* 는 패키지 내 파트의 위치를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-126">The *authority* specifies the type of package that a part is contained by, while the *path* specifies the location of a part within a package.</span></span>

<span data-ttu-id="2afa5-127">다음 그림에서는 이 개념을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-127">This concept is illustrated by the following figure:</span></span>

![패키지, 권한 및 경로의 관계](./media/pack-uris-in-wpf/wpf-relationship-diagram.png)

<span data-ttu-id="2afa5-129">패키지와 파트는 애플리케이션 및 파일과 유사합니다. 즉, 애플리케이션(패키지)은 다음을 비롯한 하나 이상의 파일(파트)을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-129">Packages and parts are analogous to applications and files, where an application (package) can include one or more files (parts), including:</span></span>

- <span data-ttu-id="2afa5-130">로컬 어셈블리로 컴파일되는 리소스 파일</span><span class="sxs-lookup"><span data-stu-id="2afa5-130">Resource files that are compiled into the local assembly.</span></span>

- <span data-ttu-id="2afa5-131">참조된 어셈블리로 컴파일되는 리소스 파일</span><span class="sxs-lookup"><span data-stu-id="2afa5-131">Resource files that are compiled into a referenced assembly.</span></span>

- <span data-ttu-id="2afa5-132">참조하는 어셈블리로 컴파일되는 리소스 파일</span><span class="sxs-lookup"><span data-stu-id="2afa5-132">Resource files that are compiled into a referencing assembly.</span></span>

- <span data-ttu-id="2afa5-133">콘텐츠 파일</span><span class="sxs-lookup"><span data-stu-id="2afa5-133">Content files.</span></span>

- <span data-ttu-id="2afa5-134">원본 사이트 파일</span><span class="sxs-lookup"><span data-stu-id="2afa5-134">Site of origin files.</span></span>

<span data-ttu-id="2afa5-135">WPF는 이러한 파일 형식에 액세스 하기 위해 application:///및 siteoforigin:///의 두 가지 기관을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-135">To access these types of files, WPF supports two authorities: application:/// and siteoforigin:///.</span></span> <span data-ttu-id="2afa5-136">application:/// 인증 기관은 리소스 및 콘텐츠 파일을 비롯하여 컴파일 시 알려진 애플리케이션 데이터 파일을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-136">The application:/// authority identifies application data files that are known at compile time, including resource and content files.</span></span> <span data-ttu-id="2afa5-137">siteoforigin:/// 인증 기관은 원본 사이트 파일을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-137">The siteoforigin:/// authority identifies site of origin files.</span></span> <span data-ttu-id="2afa5-138">다음 그림에서는 각 인증 기관의 범위를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-138">The scope of each authority is shown in the following figure.</span></span>

![Pack URI 다이어그램](./media/pack-uris-in-wpf/wpf-pack-uri-scheme.png)

> [!NOTE]
> <span data-ttu-id="2afa5-140">Pack URI의 authority 구성 요소는 패키지를 가리키는 포함 URI 이며 RFC 2396을 준수 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-140">The authority component of a pack URI is an embedded URI that points to a package and must conform to RFC 2396.</span></span> <span data-ttu-id="2afa5-141">또한 “/” 문자를 “,” 문자로 바꾸고 “%” 및 “?” 같은 예약 문자는 이스케이프해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-141">Additionally, the "/" character must be replaced with the "," character, and reserved characters such as "%" and "?" must be escaped.</span></span> <span data-ttu-id="2afa5-142">자세한 내용은 OPC를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2afa5-142">See the OPC for details.</span></span>

<span data-ttu-id="2afa5-143">다음 섹션에서는 리소스, 콘텐츠 및 원본 사이트 파일을 식별 하기 위한 적절 한 경로와 함께 이러한 두 가지 인증 기관을 사용 하 여 pack Uri를 구성 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-143">The following sections explain how to construct pack URIs using these two authorities in conjunction with the appropriate paths for identifying resource, content, and site of origin files.</span></span>

<a name="Resource_File_Pack_URIs___Local_Assembly"></a>

## <a name="resource-file-pack-uris"></a><span data-ttu-id="2afa5-144">리소스 파일 Pack URI</span><span class="sxs-lookup"><span data-stu-id="2afa5-144">Resource File Pack URIs</span></span>

<span data-ttu-id="2afa5-145">리소스 파일은 MSBuild 항목으로 구성 되 `Resource` 고 어셈블리로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-145">Resource files are configured as MSBuild `Resource` items and are compiled into assemblies.</span></span> <span data-ttu-id="2afa5-146">WPF는 로컬 어셈블리로 컴파일되거나 로컬 어셈블리에서 참조 되는 어셈블리로 컴파일되는 리소스 파일을 식별 하는 데 사용할 수 있는 pack Uri 생성을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-146">WPF supports the construction of pack URIs that can be used to identify resource files that are either compiled into the local assembly or compiled into an assembly that is referenced from the local assembly.</span></span>

<a name="Local_Assembly_Resource_File"></a>

### <a name="local-assembly-resource-file"></a><span data-ttu-id="2afa5-147">로컬 어셈블리 리소스 파일</span><span class="sxs-lookup"><span data-stu-id="2afa5-147">Local Assembly Resource File</span></span>

<span data-ttu-id="2afa5-148">로컬 어셈블리로 컴파일되는 리소스 파일에 대 한 pack URI는 다음 인증 기관과 경로를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-148">The pack URI for a resource file that is compiled into the local assembly uses the following authority and path:</span></span>

- <span data-ttu-id="2afa5-149">**인증 기관**: application:///</span><span class="sxs-lookup"><span data-stu-id="2afa5-149">**Authority**: application:///.</span></span>

- <span data-ttu-id="2afa5-150">**경로**: 로컬 어셈블리 프로젝트 폴더 루트에 상대적인 경로를 포함한 리소스 파일의 이름</span><span class="sxs-lookup"><span data-stu-id="2afa5-150">**Path**: The name of the resource file, including its path, relative to the local assembly project folder root.</span></span>

<span data-ttu-id="2afa5-151">다음 예제에서는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 로컬 어셈블리의 프로젝트 폴더 루트에 있는 리소스 파일의 PACK URI를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-151">The following example shows the pack URI for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] resource file that is located in the root of the local assembly's project folder.</span></span>

`pack://application:,,,/ResourceFile.xaml`

<span data-ttu-id="2afa5-152">다음 예제에서는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 로컬 어셈블리의 프로젝트 폴더 하위 폴더에 있는 리소스 파일의 PACK URI를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-152">The following example shows the pack URI for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] resource file that is located in a subfolder of the local assembly's project folder.</span></span>

`pack://application:,,,/Subfolder/ResourceFile.xaml`

<a name="Resource_File_Pack_URIs___Referenced_Assembly"></a>

### <a name="referenced-assembly-resource-file"></a><span data-ttu-id="2afa5-153">참조된 어셈블리 리소스 파일</span><span class="sxs-lookup"><span data-stu-id="2afa5-153">Referenced Assembly Resource File</span></span>

<span data-ttu-id="2afa5-154">참조 된 어셈블리로 컴파일되는 리소스 파일에 대 한 pack URI는 다음 인증 기관과 경로를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-154">The pack URI for a resource file that is compiled into a referenced assembly uses the following authority and path:</span></span>

- <span data-ttu-id="2afa5-155">**인증 기관**: application:///</span><span class="sxs-lookup"><span data-stu-id="2afa5-155">**Authority**: application:///.</span></span>

- <span data-ttu-id="2afa5-156">**경로**: 참조된 어셈블리로 컴파일되는 리소스 파일의 이름.</span><span class="sxs-lookup"><span data-stu-id="2afa5-156">**Path**: The name of a resource file that is compiled into a referenced assembly.</span></span> <span data-ttu-id="2afa5-157">경로는 다음 형식을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-157">The path must conform to the following format:</span></span>

  <span data-ttu-id="2afa5-158">*AssemblyShortName*{*; Version*] {*; PublicKey*]; 구성 요소/*경로*</span><span class="sxs-lookup"><span data-stu-id="2afa5-158">*AssemblyShortName*{*;Version*]{*;PublicKey*];component/*Path*</span></span>

  - <span data-ttu-id="2afa5-159">**AssemblyShortName**: 참조된 어셈블리에 대한 약식 이름</span><span class="sxs-lookup"><span data-stu-id="2afa5-159">**AssemblyShortName**: the short name for the referenced assembly.</span></span>

  - <span data-ttu-id="2afa5-160">**;Version**[옵션]: 리소스 파일을 포함하는 참조된 어셈블리의 버전.</span><span class="sxs-lookup"><span data-stu-id="2afa5-160">**;Version** [optional]: the version of the referenced assembly that contains the resource file.</span></span> <span data-ttu-id="2afa5-161">동일한 약식 이름을 갖는 두 개 이상의 참조된 어셈블리가 로드된 경우 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-161">This is used when two or more referenced assemblies with the same short name are loaded.</span></span>

  - <span data-ttu-id="2afa5-162">**;PublicKey**[옵션]: 참조된 어셈블리를 서명하는 데 사용된 공개 키.</span><span class="sxs-lookup"><span data-stu-id="2afa5-162">**;PublicKey** [optional]: the public key that was used to sign the referenced assembly.</span></span> <span data-ttu-id="2afa5-163">동일한 약식 이름을 갖는 두 개 이상의 참조된 어셈블리가 로드된 경우 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-163">This is used when two or more referenced assemblies with the same short name are loaded.</span></span>

  - <span data-ttu-id="2afa5-164">**;component**: 참조되는 어셈블리가 로컬 어셈블리에서 참조된다는 것을 지정</span><span class="sxs-lookup"><span data-stu-id="2afa5-164">**;component**: specifies that the assembly being referred to is referenced from the local assembly.</span></span>

  - <span data-ttu-id="2afa5-165">**/Path**: 참조된 어셈블리 프로젝트 폴더의 루트에 상대적인 경로를 포함한 리소스 파일의 이름</span><span class="sxs-lookup"><span data-stu-id="2afa5-165">**/Path**: the name of the resource file, including its path, relative to the root of the referenced assembly's project folder.</span></span>

<span data-ttu-id="2afa5-166">다음 예제에서는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 참조 된 어셈블리의 프로젝트 폴더 루트에 있는 리소스 파일의 PACK URI를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-166">The following example shows the pack URI for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] resource file that is located in the root of the referenced assembly's project folder.</span></span>

`pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml`

<span data-ttu-id="2afa5-167">다음 예제에서는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 참조 된 어셈블리의 프로젝트 폴더에 있는 하위 폴더에 있는 리소스 파일의 PACK URI를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-167">The following example shows the pack URI for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] resource file that is located in a subfolder of the referenced assembly's project folder.</span></span>

`pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml`

<span data-ttu-id="2afa5-168">다음 예제에서는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 참조 된 버전별 어셈블리의 프로젝트 폴더에 있는 루트 폴더에 있는 리소스 파일의 PACK URI를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-168">The following example shows the pack URI for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] resource file that is located in the root folder of a referenced, version-specific assembly's project folder.</span></span>

`pack://application:,,,/ReferencedAssembly;v1.0.0.1;component/ResourceFile.xaml`

<span data-ttu-id="2afa5-169">참조 된 어셈블리 리소스 파일의 pack URI 구문은 application:///authority에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-169">Note that the pack URI syntax for referenced assembly resource files can be used only with the application:/// authority.</span></span> <span data-ttu-id="2afa5-170">예를 들어 다음은 WPF에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-170">For example, the following is not supported in WPF.</span></span>

`pack://siteoforigin:,,,/SomeAssembly;component/ResourceFile.xaml`

<a name="Content_File_Pack_URIs"></a>

## <a name="content-file-pack-uris"></a><span data-ttu-id="2afa5-171">콘텐츠 파일 Pack URI</span><span class="sxs-lookup"><span data-stu-id="2afa5-171">Content File Pack URIs</span></span>

<span data-ttu-id="2afa5-172">콘텐츠 파일의 pack URI는 다음 인증 기관과 경로를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-172">The pack URI for a content file uses the following authority and path:</span></span>

- <span data-ttu-id="2afa5-173">**인증 기관**: application:///</span><span class="sxs-lookup"><span data-stu-id="2afa5-173">**Authority**: application:///.</span></span>

- <span data-ttu-id="2afa5-174">**경로**: 애플리케이션의 주 실행 가능 어셈블리의 파일 시스템 위치에 상대적인 경로를 포함한 콘텐츠 파일의 이름</span><span class="sxs-lookup"><span data-stu-id="2afa5-174">**Path**: The name of the content file, including its path relative to the file system location of the application's main executable assembly.</span></span>

<span data-ttu-id="2afa5-175">다음 예제에서는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 실행 가능한 어셈블리와 동일한 폴더에 있는 콘텐츠 파일의 PACK URI를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-175">The following example shows the pack URI for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] content file, located in the same folder as the executable assembly.</span></span>

`pack://application:,,,/ContentFile.xaml`

<span data-ttu-id="2afa5-176">다음 예제에서는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 응용 프로그램의 실행 가능 어셈블리에 상대적인 하위 폴더에 있는 콘텐츠 파일의 PACK URI를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-176">The following example shows the pack URI for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] content file, located in a subfolder that is relative to the application's executable assembly.</span></span>

`pack://application:,,,/Subfolder/ContentFile.xaml`

> [!NOTE]
> <span data-ttu-id="2afa5-177">HTML 콘텐츠 파일을 탐색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-177">HTML content files cannot be navigated to.</span></span> <span data-ttu-id="2afa5-178">URI 체계는 원본 사이트에 있는 HTML 파일 탐색만 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-178">The URI scheme only supports navigation to HTML files that are located at the site of origin.</span></span>

<a name="The_siteoforigin_____Authority"></a>

## <a name="site-of-origin-pack-uris"></a><span data-ttu-id="2afa5-179">원본 사이트 Pack URI</span><span class="sxs-lookup"><span data-stu-id="2afa5-179">Site of Origin Pack URIs</span></span>

<span data-ttu-id="2afa5-180">원본 사이트 파일에 대 한 pack URI는 다음 인증 기관과 경로를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-180">The pack URI for a site of origin file uses the following authority and path:</span></span>

- <span data-ttu-id="2afa5-181">**인증 기관**: siteoforigin:///</span><span class="sxs-lookup"><span data-stu-id="2afa5-181">**Authority**: siteoforigin:///.</span></span>

- <span data-ttu-id="2afa5-182">**경로**: 실행 가능 어셈블리가 시작된 위치에 상대적인 경로를 포함한 원본 사이트 파일의 이름</span><span class="sxs-lookup"><span data-stu-id="2afa5-182">**Path**: The name of the site of origin file, including its path relative to the location from which the executable assembly was launched.</span></span>

<span data-ttu-id="2afa5-183">다음 예제에서는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 실행 가능한 어셈블리가 시작 된 위치에 저장 된 원본 사이트 파일에 대 한 PACK URI를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-183">The following example shows the pack URI for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] site of origin file, stored in the location from which the executable assembly is launched.</span></span>

`pack://siteoforigin:,,,/SiteOfOriginFile.xaml`

<span data-ttu-id="2afa5-184">다음 예제에서는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 응용 프로그램의 실행 가능 어셈블리가 시작 된 위치에 상대적인 하위 폴더에 저장 된 원본 사이트 파일에 대 한 PACK URI를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-184">The following example shows the pack URI for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] site of origin file, stored in subfolder that is relative to the location from which the application's executable assembly is launched.</span></span>

`pack://siteoforigin:,,,/Subfolder/SiteOfOriginFile.xaml`

<a name="Page_Files"></a>

## <a name="page-files"></a><span data-ttu-id="2afa5-185">페이지 파일</span><span class="sxs-lookup"><span data-stu-id="2afa5-185">Page Files</span></span>

<span data-ttu-id="2afa5-186">MSBuild 항목으로 구성 된 XAML 파일 `Page` 은 리소스 파일과 같은 방식으로 어셈블리로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-186">XAML files that are configured as MSBuild `Page` items are compiled into assemblies in the same way as resource files.</span></span> <span data-ttu-id="2afa5-187">따라서 `Page` 리소스 파일에 대 한 Pack uri를 사용 하 여 MSBuild 항목을 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-187">Consequently, MSBuild `Page` items can be identified using pack URIs for resource files.</span></span>

<span data-ttu-id="2afa5-188">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]일반적으로 MSBuild 항목으로 구성 되는 파일 형식에는 다음 중 `Page` 하나가 루트 요소로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-188">The types of [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] files that are commonly configured as MSBuild`Page` items have one of the following as their root element:</span></span>

- <xref:System.Windows.Window?displayProperty=nameWithType>

- <xref:System.Windows.Controls.Page?displayProperty=nameWithType>

- <xref:System.Windows.Navigation.PageFunction%601?displayProperty=nameWithType>

- <xref:System.Windows.ResourceDictionary?displayProperty=nameWithType>

- <xref:System.Windows.Documents.FlowDocument?displayProperty=nameWithType>

- <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType>

<a name="Absolute_vs_Relative_Pack_URIs"></a>

## <a name="absolute-vs-relative-pack-uris"></a><span data-ttu-id="2afa5-189">절대 및 상대 Pack Uri 비교</span><span class="sxs-lookup"><span data-stu-id="2afa5-189">Absolute vs. Relative Pack URIs</span></span>

<span data-ttu-id="2afa5-190">정규화 된 pack URI에는 체계, 인증 기관 및 경로가 포함 되며 절대 pack URI로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-190">A fully qualified pack URI includes the scheme, the authority, and the path, and it is considered an absolute pack URI.</span></span> <span data-ttu-id="2afa5-191">개발자를 위한 단순화를 위해 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 요소는 일반적으로 경로만 포함 하는 상대 PACK URI를 사용 하 여 적절 한 특성을 설정할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-191">As a simplification for developers, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elements typically allow you to set appropriate attributes with a relative pack URI, which includes only the path.</span></span>

<span data-ttu-id="2afa5-192">예를 들어 로컬 어셈블리의 리소스 파일에 대 한 다음 절대 pack URI를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-192">For example, consider the following absolute pack URI for a resource file in the local assembly.</span></span>

`pack://application:,,,/ResourceFile.xaml`

<span data-ttu-id="2afa5-193">이 리소스 파일을 참조 하는 상대 pack URI는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-193">The relative pack URI that refers to this resource file would be the following.</span></span>

`/ResourceFile.xaml`

> [!NOTE]
> <span data-ttu-id="2afa5-194">원본 사이트 파일은 어셈블리와 연결 되어 있지 않으므로 절대 pack Uri로만 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-194">Because site of origin files are not associated with assemblies, they can only be referred to with absolute pack URIs.</span></span>

<span data-ttu-id="2afa5-195">기본적으로 상대 pack URI는 참조가 포함 된 태그나 코드의 위치를 기준으로 고려 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-195">By default, a relative pack URI is considered relative to the location of the markup or code that contains the reference.</span></span> <span data-ttu-id="2afa5-196">그러나 선행 백슬래시를 사용 하는 경우에는 응용 프로그램의 루트를 기준으로 상대 pack URI 참조를 고려할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-196">If a leading backslash is used, however, the relative pack URI reference is then considered relative to the root of the application.</span></span> <span data-ttu-id="2afa5-197">예를 들어 다음과 같은 프로젝트 구조를 가정해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-197">For example, consider the following project structure.</span></span>

`App.xaml`

`Page2.xaml`

`\SubFolder`

`+ Page1.xaml`

`+ Page2.xaml`

<span data-ttu-id="2afa5-198">*Root*\Subfolder\page2.xaml을 참조 하는 URI를 포함 하는 경우 참조는 다음 상대 pack URI를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-198">If Page1.xaml contains a URI that references *Root*\SubFolder\Page2.xaml, the reference can use the following relative pack URI.</span></span>

`Page2.xaml`

<span data-ttu-id="2afa5-199">.Root. xaml에 *Root*\Page2.xaml을 참조 하는 uri가 포함 된 경우 참조는 다음 상대 pack URI를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-199">If Page1.xaml contains a URI that references *Root*\Page2.xaml, the reference can use the following relative pack URI.</span></span>

`/Page2.xaml`

<a name="Pack_URI_Resolution"></a>

## <a name="pack-uri-resolution"></a><span data-ttu-id="2afa5-200">Pack URI 확인</span><span class="sxs-lookup"><span data-stu-id="2afa5-200">Pack URI Resolution</span></span>

<span data-ttu-id="2afa5-201">Pack Uri의 형식을 사용 하면 여러 파일 형식의 pack Uri가 동일 하 게 보일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-201">The format of pack URIs makes it possible for pack URIs for different types of files to look the same.</span></span> <span data-ttu-id="2afa5-202">예를 들어 다음과 같은 절대 pack URI를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-202">For example, consider the following absolute pack URI.</span></span>

`pack://application:,,,/ResourceOrContentFile.xaml`

<span data-ttu-id="2afa5-203">이 절대 pack URI는 로컬 어셈블리 또는 콘텐츠 파일의 리소스 파일을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-203">This absolute pack URI could refer to either a resource file in the local assembly or a content file.</span></span> <span data-ttu-id="2afa5-204">다음 상대 URI에도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-204">The same is true for the following relative URI.</span></span>

`/ResourceOrContentFile.xaml`

<span data-ttu-id="2afa5-205">Pack URI가 참조 하는 파일의 형식을 확인 하기 위해 WPF는 다음 추론을 사용 하 여 로컬 어셈블리 및 콘텐츠 파일의 리소스 파일에 대 한 Uri를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-205">In order to determine the type of file that a pack URI refers to, WPF resolves URIs for resource files in local assemblies and content files by using the following heuristics:</span></span>

1. <span data-ttu-id="2afa5-206"><xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>PACK URI와 일치 하는 특성에 대 한 어셈블리 메타 데이터를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-206">Probe the assembly metadata for an <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> attribute that matches the pack URI.</span></span>

2. <span data-ttu-id="2afa5-207">특성을 <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> 찾은 경우 PACK URI의 경로는 콘텐츠 파일을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-207">If the <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> attribute is found, the path of the pack URI refers to a content file.</span></span>

3. <span data-ttu-id="2afa5-208">특성을 <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> 찾을 수 없는 경우 로컬 어셈블리로 컴파일되는 집합 리소스 파일을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-208">If the <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> attribute is not found, probe the set resource files that are compiled into the local assembly.</span></span>

4. <span data-ttu-id="2afa5-209">Pack URI의 경로와 일치 하는 리소스 파일이 있는 경우 pack URI의 경로는 리소스 파일을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-209">If a resource file that matches the path of the pack URI is found, the path of the pack URI refers to a resource file.</span></span>

5. <span data-ttu-id="2afa5-210">리소스를 찾을 수 없는 경우 내부적으로 만든 <xref:System.Uri> 가 잘못 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-210">If the resource is not found, the internally created <xref:System.Uri> is invalid.</span></span>

<span data-ttu-id="2afa5-211">URI 확인은 다음을 참조 하는 uri에는 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-211">URI resolution does not apply for URIs that refer to the following:</span></span>

- <span data-ttu-id="2afa5-212">참조 된 어셈블리의 콘텐츠 파일: 이러한 파일 형식은 WPF에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-212">Content files in referenced assemblies: these file types are not supported by WPF.</span></span>

- <span data-ttu-id="2afa5-213">참조 된 어셈블리에 포함 된 파일: 참조 된 어셈블리의 이름과 접미사를 모두 포함 하기 때문에이를 식별 하는 Uri는 고유 `;component` 합니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-213">Embedded files in referenced assemblies: URIs that identify them are unique because they include both the name of the referenced assembly and the `;component` suffix.</span></span>

- <span data-ttu-id="2afa5-214">원본 사이트 파일: 해당 파일을 식별 하는 Uri는 siteoforigin:///권한이 포함 된 pack Uri에서 식별할 수 있는 유일한 파일 이므로 고유 합니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-214">Site of origin files: URIs that identify them are unique because they are the only files that can be identified by pack URIs that contain the siteoforigin:/// authority.</span></span>

<span data-ttu-id="2afa5-215">Pack URI를 확인 하는 한 가지 단순화는 코드를 리소스 및 콘텐츠 파일의 위치와 약간 독립적으로 사용할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-215">One simplification that pack URI resolution allows is for code to be somewhat independent of the locations of resource and content files.</span></span> <span data-ttu-id="2afa5-216">예를 들어 로컬 어셈블리에 콘텐츠 파일로 다시 구성 된 리소스 파일이 있는 경우 해당 리소스에 대 한 pack URI는 pack URI를 사용 하는 코드와 마찬가지로 동일 하 게 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-216">For example, if you have a resource file in the local assembly that is reconfigured to be a content file, the pack URI for the resource remains the same, as does the code that uses the pack URI.</span></span>

<a name="Programming_with_Pack_URIs"></a>

## <a name="programming-with-pack-uris"></a><span data-ttu-id="2afa5-217">Pack URI를 사용한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="2afa5-217">Programming with Pack URIs</span></span>

<span data-ttu-id="2afa5-218">많은 WPF 클래스는 다음을 포함 하 여 pack Uri를 사용 하 여 설정할 수 있는 속성을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-218">Many WPF classes implement properties that can be set with pack URIs, including:</span></span>

- <xref:System.Windows.Application.StartupUri%2A?displayProperty=nameWithType>

- <xref:System.Windows.Controls.Frame.Source%2A?displayProperty=nameWithType>

- <xref:System.Windows.Navigation.NavigationWindow.Source%2A?displayProperty=nameWithType>

- <xref:System.Windows.Documents.Hyperlink.NavigateUri%2A?displayProperty=nameWithType>

- <xref:System.Windows.Window.Icon%2A?displayProperty=nameWithType>

- <xref:System.Windows.Controls.Image.Source%2A?displayProperty=nameWithType>

<span data-ttu-id="2afa5-219">이러한 속성을 태그와 코드 모두에서 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-219">These properties can be set from both markup and code.</span></span> <span data-ttu-id="2afa5-220">이 섹션에서는 두 경우에 대한 기본 구조를 설명한 다음 일반적인 시나리오 예제를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-220">This section demonstrates the basic constructions for both and then shows examples of common scenarios.</span></span>

<a name="Using_Pack_URIs_in_Markup"></a>

### <a name="using-pack-uris-in-markup"></a><span data-ttu-id="2afa5-221">태그에서 Pack URI 사용</span><span class="sxs-lookup"><span data-stu-id="2afa5-221">Using Pack URIs in Markup</span></span>

<span data-ttu-id="2afa5-222">Pack uri를 사용 하 여 특성의 요소를 설정 하 여 태그에 pack URI를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-222">A pack URI is specified in markup by setting the element of an attribute with the pack URI.</span></span> <span data-ttu-id="2afa5-223">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-223">For example:</span></span>

`<element attribute="pack://application:,,,/File.xaml" />`

<span data-ttu-id="2afa5-224">표 1에서는 태그에 지정할 수 있는 다양 한 절대 pack Uri를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-224">Table 1 illustrates the various absolute pack URIs that you can specify in markup.</span></span>

<span data-ttu-id="2afa5-225">표 1: 태그의 절대 Pack URI</span><span class="sxs-lookup"><span data-stu-id="2afa5-225">Table 1: Absolute Pack URIs in Markup</span></span>

|<span data-ttu-id="2afa5-226">파일</span><span class="sxs-lookup"><span data-stu-id="2afa5-226">File</span></span>|<span data-ttu-id="2afa5-227">절대 pack URI</span><span class="sxs-lookup"><span data-stu-id="2afa5-227">Absolute pack URI</span></span>|
|----------|-------------------------------------------------------------------------------------------------------------------------|
|<span data-ttu-id="2afa5-228">리소스 파일 - 로컬 어셈블리</span><span class="sxs-lookup"><span data-stu-id="2afa5-228">Resource file - local assembly</span></span>|`"pack://application:,,,/ResourceFile.xaml"`|
|<span data-ttu-id="2afa5-229">하위 폴더의 리소스 파일 - 로컬 어셈블리</span><span class="sxs-lookup"><span data-stu-id="2afa5-229">Resource file in subfolder - local assembly</span></span>|`"pack://application:,,,/Subfolder/ResourceFile.xaml"`|
|<span data-ttu-id="2afa5-230">리소스 파일 - 참조된 어셈블리</span><span class="sxs-lookup"><span data-stu-id="2afa5-230">Resource file - referenced assembly</span></span>|`"pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml"`|
|<span data-ttu-id="2afa5-231">참조된 어셈블리의 하위 폴더에 있는 리소스 파일</span><span class="sxs-lookup"><span data-stu-id="2afa5-231">Resource file in subfolder of referenced assembly</span></span>|`"pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml"`|
|<span data-ttu-id="2afa5-232">버전이 있는 참조된 어셈블리의 리소스 파일</span><span class="sxs-lookup"><span data-stu-id="2afa5-232">Resource file in versioned referenced assembly</span></span>|`"pack://application:,,,/ReferencedAssembly;v1.0.0.0;component/ResourceFile.xaml"`|
|<span data-ttu-id="2afa5-233">콘텐츠 파일</span><span class="sxs-lookup"><span data-stu-id="2afa5-233">Content file</span></span>|`"pack://application:,,,/ContentFile.xaml"`|
|<span data-ttu-id="2afa5-234">하위 폴더의 콘텐츠 파일</span><span class="sxs-lookup"><span data-stu-id="2afa5-234">Content file in subfolder</span></span>|`"pack://application:,,,/Subfolder/ContentFile.xaml"`|
|<span data-ttu-id="2afa5-235">원본 사이트 파일</span><span class="sxs-lookup"><span data-stu-id="2afa5-235">Site of origin file</span></span>|`"pack://siteoforigin:,,,/SOOFile.xaml"`|
|<span data-ttu-id="2afa5-236">하위 폴더의 원본 사이트 파일</span><span class="sxs-lookup"><span data-stu-id="2afa5-236">Site of origin file in subfolder</span></span>|`"pack://siteoforigin:,,,/Subfolder/SOOFile.xaml"`|

<span data-ttu-id="2afa5-237">표 2에서는 태그에 지정할 수 있는 다양 한 상대 pack Uri를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-237">Table 2 illustrates the various relative pack URIs that you can specify in markup.</span></span>

<span data-ttu-id="2afa5-238">표 2: 태그의 상대 Pack URI</span><span class="sxs-lookup"><span data-stu-id="2afa5-238">Table 2: Relative Pack URIs in Markup</span></span>

|<span data-ttu-id="2afa5-239">파일</span><span class="sxs-lookup"><span data-stu-id="2afa5-239">File</span></span>|<span data-ttu-id="2afa5-240">상대 pack URI</span><span class="sxs-lookup"><span data-stu-id="2afa5-240">Relative pack URI</span></span>|
|----------|-------------------------------------------------------------------------------------------------------------------------|
|<span data-ttu-id="2afa5-241">로컬 어셈블리의 리소스 파일</span><span class="sxs-lookup"><span data-stu-id="2afa5-241">Resource file in local assembly</span></span>|`"/ResourceFile.xaml"`|
|<span data-ttu-id="2afa5-242">로컬 어셈블리의 하위 폴더에 있는 리소스 파일</span><span class="sxs-lookup"><span data-stu-id="2afa5-242">Resource file in subfolder of local assembly</span></span>|`"/Subfolder/ResourceFile.xaml"`|
|<span data-ttu-id="2afa5-243">참조된 어셈블리의 리소스 파일</span><span class="sxs-lookup"><span data-stu-id="2afa5-243">Resource file in referenced assembly</span></span>|`"/ReferencedAssembly;component/ResourceFile.xaml"`|
|<span data-ttu-id="2afa5-244">참조된 어셈블리의 하위 폴더에 있는 리소스 파일</span><span class="sxs-lookup"><span data-stu-id="2afa5-244">Resource file in subfolder of referenced assembly</span></span>|`"/ReferencedAssembly;component/Subfolder/ResourceFile.xaml"`|
|<span data-ttu-id="2afa5-245">콘텐츠 파일</span><span class="sxs-lookup"><span data-stu-id="2afa5-245">Content file</span></span>|`"/ContentFile.xaml"`|
|<span data-ttu-id="2afa5-246">하위 폴더의 콘텐츠 파일</span><span class="sxs-lookup"><span data-stu-id="2afa5-246">Content file in subfolder</span></span>|`"/Subfolder/ContentFile.xaml"`|

<a name="Using_Pack_URIs_in_Code"></a>

### <a name="using-pack-uris-in-code"></a><span data-ttu-id="2afa5-247">코드에서 Pack URI 사용</span><span class="sxs-lookup"><span data-stu-id="2afa5-247">Using Pack URIs in Code</span></span>

<span data-ttu-id="2afa5-248">클래스를 인스턴스화하고 <xref:System.Uri> PACK uri를 매개 변수로 생성자에 전달 하 여 코드에서 PACK uri를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-248">You specify a pack URI in code by instantiating the <xref:System.Uri> class and passing the pack URI as a parameter to the constructor.</span></span> <span data-ttu-id="2afa5-249">다음 예제에 이 내용이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-249">This is demonstrated in the following example.</span></span>

```csharp
Uri uri = new Uri("pack://application:,,,/File.xaml");
```

<span data-ttu-id="2afa5-250">기본적으로 클래스는 <xref:System.Uri> Pack uri를 절대 uri로 간주 합니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-250">By default, the <xref:System.Uri> class considers pack URIs to be absolute.</span></span> <span data-ttu-id="2afa5-251">따라서 <xref:System.Uri> 상대 PACK URI를 사용 하 여 클래스의 인스턴스를 만들 때 예외가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-251">Consequently, an exception is raised when an instance of the <xref:System.Uri> class is created with a relative pack URI.</span></span>

```csharp
Uri uri = new Uri("/File.xaml");
```

<span data-ttu-id="2afa5-252">다행히 <xref:System.Uri.%23ctor%28System.String%2CSystem.UriKind%29> 클래스 생성자의 오버 로드에서 <xref:System.Uri> 형식의 매개 변수를 <xref:System.UriKind> 사용 하 여 pack URI가 절대 인지 상대 인지를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-252">Fortunately, the <xref:System.Uri.%23ctor%28System.String%2CSystem.UriKind%29> overload of the <xref:System.Uri> class constructor accepts a parameter of type <xref:System.UriKind> to allow you to specify whether a pack URI is either absolute or relative.</span></span>

```csharp
// Absolute URI (default)
Uri absoluteUri = new Uri("pack://application:,,,/File.xaml", UriKind.Absolute);
// Relative URI
Uri relativeUri = new Uri("/File.xaml",
                        UriKind.Relative);
```

<span data-ttu-id="2afa5-253"><xref:System.UriKind.Absolute> <xref:System.UriKind.Relative> 제공 된 pack URI가 하나 또는 다른 것이 확실 한 경우 또는만 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-253">You should specify only <xref:System.UriKind.Absolute> or <xref:System.UriKind.Relative> when you are certain that the provided pack URI is one or the other.</span></span> <span data-ttu-id="2afa5-254">런타임에 사용자가 pack URI를 입력 하는 경우와 같이 사용 되는 pack URI의 형식을 모르는 경우를 <xref:System.UriKind.RelativeOrAbsolute> 대신 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-254">If you don't know the type of pack URI that is used, such as when a user enters a pack URI at run time, use <xref:System.UriKind.RelativeOrAbsolute> instead.</span></span>

```csharp
// Relative or Absolute URI provided by user via a text box
TextBox userProvidedUriTextBox = new TextBox();
Uri uri = new Uri(userProvidedUriTextBox.Text, UriKind.RelativeOrAbsolute);
```

<span data-ttu-id="2afa5-255">표 3에서는를 사용 하 여 코드에 지정할 수 있는 다양 한 상대 pack Uri를 보여 줍니다 <xref:System.Uri?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="2afa5-255">Table 3 illustrates the various relative pack URIs that you can specify in code by using <xref:System.Uri?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="2afa5-256">표 3: 코드의 절대 Pack URI</span><span class="sxs-lookup"><span data-stu-id="2afa5-256">Table 3: Absolute Pack URIs in Code</span></span>

|<span data-ttu-id="2afa5-257">파일</span><span class="sxs-lookup"><span data-stu-id="2afa5-257">File</span></span>|<span data-ttu-id="2afa5-258">절대 pack URI</span><span class="sxs-lookup"><span data-stu-id="2afa5-258">Absolute pack URI</span></span>|
|----------|-------------------------------------------------------------------------------------------------------------------------|
|<span data-ttu-id="2afa5-259">리소스 파일 - 로컬 어셈블리</span><span class="sxs-lookup"><span data-stu-id="2afa5-259">Resource file - local assembly</span></span>|`Uri uri = new Uri("pack://application:,,,/ResourceFile.xaml", UriKind.Absolute);`|
|<span data-ttu-id="2afa5-260">하위 폴더의 리소스 파일 - 로컬 어셈블리</span><span class="sxs-lookup"><span data-stu-id="2afa5-260">Resource file in subfolder - local assembly</span></span>|`Uri uri = new Uri("pack://application:,,,/Subfolder/ResourceFile.xaml", UriKind.Absolute);`|
|<span data-ttu-id="2afa5-261">리소스 파일 - 참조된 어셈블리</span><span class="sxs-lookup"><span data-stu-id="2afa5-261">Resource file - referenced assembly</span></span>|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml", UriKind.Absolute);`|
|<span data-ttu-id="2afa5-262">참조된 어셈블리의 하위 폴더에 있는 리소스 파일</span><span class="sxs-lookup"><span data-stu-id="2afa5-262">Resource file in subfolder of referenced assembly</span></span>|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml", UriKind.Absolute);`|
|<span data-ttu-id="2afa5-263">버전이 있는 참조된 어셈블리의 리소스 파일</span><span class="sxs-lookup"><span data-stu-id="2afa5-263">Resource file in versioned referenced assembly</span></span>|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;v1.0.0.0;component/ResourceFile.xaml", UriKind.Absolute);`|
|<span data-ttu-id="2afa5-264">콘텐츠 파일</span><span class="sxs-lookup"><span data-stu-id="2afa5-264">Content file</span></span>|`Uri uri = new Uri("pack://application:,,,/ContentFile.xaml", UriKind.Absolute);`|
|<span data-ttu-id="2afa5-265">하위 폴더의 콘텐츠 파일</span><span class="sxs-lookup"><span data-stu-id="2afa5-265">Content file in subfolder</span></span>|`Uri uri = new Uri("pack://application:,,,/Subfolder/ContentFile.xaml", UriKind.Absolute);`|
|<span data-ttu-id="2afa5-266">원본 사이트 파일</span><span class="sxs-lookup"><span data-stu-id="2afa5-266">Site of origin file</span></span>|`Uri uri = new Uri("pack://siteoforigin:,,,/SOOFile.xaml", UriKind.Absolute);`|
|<span data-ttu-id="2afa5-267">하위 폴더의 원본 사이트 파일</span><span class="sxs-lookup"><span data-stu-id="2afa5-267">Site of origin file in subfolder</span></span>|`Uri uri = new Uri("pack://siteoforigin:,,,/Subfolder/SOOFile.xaml", UriKind.Absolute);`|

<span data-ttu-id="2afa5-268">표 4에서는를 사용 하 여 코드에서 지정할 수 있는 다양 한 상대 pack Uri를 보여 줍니다 <xref:System.Uri?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="2afa5-268">Table 4 illustrates the various relative pack URIs that you can specify in code using <xref:System.Uri?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="2afa5-269">표 4: 코드의 상대 Pack URI</span><span class="sxs-lookup"><span data-stu-id="2afa5-269">Table 4: Relative Pack URIs in Code</span></span>

|<span data-ttu-id="2afa5-270">파일</span><span class="sxs-lookup"><span data-stu-id="2afa5-270">File</span></span>|<span data-ttu-id="2afa5-271">상대 pack URI</span><span class="sxs-lookup"><span data-stu-id="2afa5-271">Relative pack URI</span></span>|
|----------|-------------------------------------------------------------------------------------------------------------------------|
|<span data-ttu-id="2afa5-272">리소스 파일 - 로컬 어셈블리</span><span class="sxs-lookup"><span data-stu-id="2afa5-272">Resource file - local assembly</span></span>|`Uri uri = new Uri("/ResourceFile.xaml", UriKind.Relative);`|
|<span data-ttu-id="2afa5-273">하위 폴더의 리소스 파일 - 로컬 어셈블리</span><span class="sxs-lookup"><span data-stu-id="2afa5-273">Resource file in subfolder - local assembly</span></span>|`Uri uri = new Uri("/Subfolder/ResourceFile.xaml", UriKind.Relative);`|
|<span data-ttu-id="2afa5-274">리소스 파일 - 참조된 어셈블리</span><span class="sxs-lookup"><span data-stu-id="2afa5-274">Resource file - referenced assembly</span></span>|`Uri uri = new Uri("/ReferencedAssembly;component/ResourceFile.xaml", UriKind.Relative);`|
|<span data-ttu-id="2afa5-275">하위 폴더의 리소스 파일 - 참조된 어셈블리</span><span class="sxs-lookup"><span data-stu-id="2afa5-275">Resource file in subfolder - referenced assembly</span></span>|`Uri uri = new Uri("/ReferencedAssembly;component/Subfolder/ResourceFile.xaml", UriKind.Relative);`|
|<span data-ttu-id="2afa5-276">콘텐츠 파일</span><span class="sxs-lookup"><span data-stu-id="2afa5-276">Content file</span></span>|`Uri uri = new Uri("/ContentFile.xaml", UriKind.Relative);`|
|<span data-ttu-id="2afa5-277">하위 폴더의 콘텐츠 파일</span><span class="sxs-lookup"><span data-stu-id="2afa5-277">Content file in subfolder</span></span>|`Uri uri = new Uri("/Subfolder/ContentFile.xaml", UriKind.Relative);`|

<a name="Common_Pack_URI_Scenarios"></a>

### <a name="common-pack-uri-scenarios"></a><span data-ttu-id="2afa5-278">일반적인 Pack URI 시나리오</span><span class="sxs-lookup"><span data-stu-id="2afa5-278">Common Pack URI Scenarios</span></span>

<span data-ttu-id="2afa5-279">이전 섹션에서는 pack Uri를 구성 하 여 리소스, 콘텐츠 및 원본 사이트 파일을 식별 하는 방법에 대해 설명 했습니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-279">The preceding sections have discussed how to construct pack URIs to identify resource, content, and site of origin files.</span></span> <span data-ttu-id="2afa5-280">WPF에서 이러한 구성은 다양 한 방법으로 사용 되며, 다음 섹션에서는 몇 가지 일반적인 사용법을 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-280">In WPF, these constructions are used in a variety of ways, and the following sections cover several common usages.</span></span>

<a name="Specifying_the_UI_to_Show_when_an_Application_Starts"></a>

#### <a name="specifying-the-ui-to-show-when-an-application-starts"></a><span data-ttu-id="2afa5-281">애플리케이션을 시작할 때 표시되는 UI 지정</span><span class="sxs-lookup"><span data-stu-id="2afa5-281">Specifying the UI to Show When an Application Starts</span></span>

<span data-ttu-id="2afa5-282"><xref:System.Windows.Application.StartupUri%2A>[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]WPF 응용 프로그램이 시작 될 때 표시 되는 첫 번째를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-282"><xref:System.Windows.Application.StartupUri%2A> specifies the first [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] to show when a WPF application is launched.</span></span> <span data-ttu-id="2afa5-283">독립 실행형 응용 프로그램의 경우는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 다음 예제와 같이 창이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-283">For standalone applications, the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] can be a window, as shown in the following example.</span></span>

[!code-xaml[PackURIOverviewSnippets#StartupUriWindow](~/samples/snippets/csharp/VS_Snippets_Wpf/PackURIOverviewSnippets/CS/Copy of App.xaml#startupuriwindow)]

<span data-ttu-id="2afa5-284">다음 예제와 같이 독립 실행형 응용 프로그램과 Xbap (XAML 브라우저 응용 프로그램)는 페이지를 초기 UI로 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-284">Standalone applications and XAML browser applications (XBAPs) can also specify a page as the initial UI, as shown in the following example.</span></span>

[!code-xaml[PackURIOverviewSnippets#StartupUriPage](~/samples/snippets/csharp/VS_Snippets_Wpf/PackURIOverviewSnippets/CS/App.xaml#startupuripage)]

<span data-ttu-id="2afa5-285">응용 프로그램이 독립 실행형 응용 프로그램이 고를 사용 하 여 페이지를 지정 하는 경우 <xref:System.Windows.Application.StartupUri%2A> WPF는 페이지를 호스트 하는를 엽니다 <xref:System.Windows.Navigation.NavigationWindow> .</span><span class="sxs-lookup"><span data-stu-id="2afa5-285">If the application is a standalone application and a page is specified with <xref:System.Windows.Application.StartupUri%2A>, WPF opens a <xref:System.Windows.Navigation.NavigationWindow> to host the page.</span></span> <span data-ttu-id="2afa5-286">Xbap의 경우 페이지가 호스트 브라우저에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-286">For XBAPs, the page is shown in the host browser.</span></span>

<a name="Navigating_to_a_Page"></a>

#### <a name="navigating-to-a-page"></a><span data-ttu-id="2afa5-287">페이지 탐색</span><span class="sxs-lookup"><span data-stu-id="2afa5-287">Navigating to a Page</span></span>

<span data-ttu-id="2afa5-288">다음 예제에서는 페이지를 탐색하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-288">The following example shows how to navigate to a page.</span></span>

[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml1)]
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml2)]
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml3)]

<span data-ttu-id="2afa5-289">WPF에서 다양 한 탐색 방법에 대 한 자세한 내용은 [탐색 개요](navigation-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2afa5-289">For more information on the various ways to navigate in WPF, see [Navigation Overview](navigation-overview.md).</span></span>

<a name="Specifying_a_Window_Icon"></a>

#### <a name="specifying-a-window-icon"></a><span data-ttu-id="2afa5-290">창 아이콘 지정</span><span class="sxs-lookup"><span data-stu-id="2afa5-290">Specifying a Window Icon</span></span>

<span data-ttu-id="2afa5-291">다음 예제에서는 URI를 사용하여 창 아이콘을 지정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-291">The following example shows how to use a URI to specify a window's icon.</span></span>

[!code-xaml[WindowIconSnippets#WindowIconSetXAML](~/samples/snippets/xaml/VS_Snippets_Wpf/WindowIconSnippets/XAML/MainWindow.xaml#windowiconsetxaml)]

<span data-ttu-id="2afa5-292">자세한 내용은 <xref:System.Windows.Window.Icon%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2afa5-292">For more information, see <xref:System.Windows.Window.Icon%2A>.</span></span>

<a name="Loading_Image__Audio__and_Video_Files"></a>

#### <a name="loading-image-audio-and-video-files"></a><span data-ttu-id="2afa5-293">이미지, 오디오 및 비디오 파일 로드</span><span class="sxs-lookup"><span data-stu-id="2afa5-293">Loading Image, Audio, and Video Files</span></span>

<span data-ttu-id="2afa5-294">WPF를 사용 하면 다음 예제와 같이 응용 프로그램에서 다양 한 미디어 형식을 사용할 수 있으며,이는 모두 pack Uri를 사용 하 여 식별 하 고 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-294">WPF allows applications to use a wide variety of media types, all of which can be identified and loaded with pack URIs, as shown in the following examples.</span></span>

[!code-xaml[MediaPlayerVideoSample#VideoPackURIAtSOO](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaPlayerVideoSample/CS/HomePage.xaml#videopackuriatsoo)]

[!code-xaml[MediaPlayerAudioSample#AudioPackURIAtSOO](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaPlayerAudioSample/CS/HomePage.xaml#audiopackuriatsoo)]

[!code-xaml[ImageSample#ImagePackURIContent](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageSample/CS/HomePage.xaml#imagepackuricontent)]

<span data-ttu-id="2afa5-295">미디어 콘텐츠로 작업 하는 방법에 대 한 자세한 내용은 [그래픽 및 멀티미디어](../graphics-multimedia/index.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2afa5-295">For more information on working with media content, see [Graphics and Multimedia](../graphics-multimedia/index.md).</span></span>

<a name="Loading_a_Resource_Dictionary_from_the_Site_of_Origin"></a>

#### <a name="loading-a-resource-dictionary-from-the-site-of-origin"></a><span data-ttu-id="2afa5-296">원본 사이트에서 리소스 사전 로드</span><span class="sxs-lookup"><span data-stu-id="2afa5-296">Loading a Resource Dictionary from the Site of Origin</span></span>

<span data-ttu-id="2afa5-297">리소스 사전 ( <xref:System.Windows.ResourceDictionary> )을 사용 하 여 응용 프로그램 테마를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-297">Resource dictionaries (<xref:System.Windows.ResourceDictionary>) can be used to support application themes.</span></span> <span data-ttu-id="2afa5-298">테마를 만들고 관리하는 한 가지 방법은 애플리케이션의 원본 사이트에 위치한 리소스 사전으로 여러 개의 테마를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-298">One way to create and manage themes is to create multiple themes as resource dictionaries that are located at an application's site of origin.</span></span> <span data-ttu-id="2afa5-299">이렇게 하면 애플리케이션을 다시 컴파일하여 배포할 필요 없이 테마를 추가하고 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-299">This allows themes to be added and updated without recompiling and redeploying an application.</span></span> <span data-ttu-id="2afa5-300">다음 예제와 같이 pack Uri를 사용 하 여 이러한 리소스 사전을 식별 하 고 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2afa5-300">These resource dictionaries can be identified and loaded using pack URIs, which is shown in the following example.</span></span>

[!code-xaml[ResourceDictionarySnippets#ResourceDictionaryPackURI](~/samples/snippets/csharp/VS_Snippets_Wpf/ResourceDictionarySnippets/CS/App.xaml#resourcedictionarypackuri)]

<span data-ttu-id="2afa5-301">WPF의 테마에 대 한 개요는 [스타일 지정 및 템플릿](../../../desktop-wpf/fundamentals/styles-templates-overview.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2afa5-301">For an overview of themes in WPF, see [Styling and Templating](../../../desktop-wpf/fundamentals/styles-templates-overview.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2afa5-302">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2afa5-302">See also</span></span>

- [<span data-ttu-id="2afa5-303">WPF 애플리케이션 리소스, 콘텐츠 및 데이터 파일</span><span class="sxs-lookup"><span data-stu-id="2afa5-303">WPF Application Resource, Content, and Data Files</span></span>](wpf-application-resource-content-and-data-files.md)
