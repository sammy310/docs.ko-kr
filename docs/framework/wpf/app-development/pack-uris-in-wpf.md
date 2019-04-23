---
title: WPF의 Pack URI
ms.date: 03/30/2017
helpviewer_keywords:
- pack URI scheme [WPF]
- loading embedded resources [WPF]
- URIs (Uniform Resource Identifiers)
- Uniform Resource Identifiers (URIs)
- loading non-resource files
- application management [WPF]
ms.assetid: 43adb517-21a7-4df3-98e8-09e9cdf764c4
ms.openlocfilehash: 4e005ea96df45da8326386f8b43aa5640ce810b1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59344353"
---
# <a name="pack-uris-in-wpf"></a><span data-ttu-id="4803e-102">WPF의 Pack URI</span><span class="sxs-lookup"><span data-stu-id="4803e-102">Pack URIs in WPF</span></span>
<span data-ttu-id="4803e-103">Windows Presentation Foundation (WPF), [!INCLUDE[TLA#tla_uri#plural](../../../../includes/tlasharptla-urisharpplural-md.md)] 식별 하 고 다음을 비롯 한 다양 한 방식 파일을 로드 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-103">In Windows Presentation Foundation (WPF), [!INCLUDE[TLA#tla_uri#plural](../../../../includes/tlasharptla-urisharpplural-md.md)] are used to identify and load files in many ways, including the following:</span></span>  
  
-   <span data-ttu-id="4803e-104">지정 된 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 표시할 때 응용 프로그램이 처음 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-104">Specifying the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] to show when an application first starts.</span></span>  
  
-   <span data-ttu-id="4803e-105">이미지 로드</span><span class="sxs-lookup"><span data-stu-id="4803e-105">Loading images.</span></span>  
  
-   <span data-ttu-id="4803e-106">페이지 탐색</span><span class="sxs-lookup"><span data-stu-id="4803e-106">Navigating to pages.</span></span>  
  
-   <span data-ttu-id="4803e-107">비실행 데이터 파일 로드</span><span class="sxs-lookup"><span data-stu-id="4803e-107">Loading non-executable data files.</span></span>  
  
 <span data-ttu-id="4803e-108">또한 [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] 식별 하 고 다양 한 다음을 비롯 한 위치에서에서 파일 로드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-108">Furthermore, [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] can be used to identify and load files from a variety of locations, including the following:</span></span>  
  
-   <span data-ttu-id="4803e-109">현재 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-109">The current assembly.</span></span>  
  
-   <span data-ttu-id="4803e-110">참조된 어셈블리</span><span class="sxs-lookup"><span data-stu-id="4803e-110">A referenced assembly.</span></span>  
  
-   <span data-ttu-id="4803e-111">어셈블리에 상대적인 위치</span><span class="sxs-lookup"><span data-stu-id="4803e-111">A location relative to an assembly.</span></span>  
  
-   <span data-ttu-id="4803e-112">애플리케이션의 원본 사이트</span><span class="sxs-lookup"><span data-stu-id="4803e-112">The application's site of origin.</span></span>  
  
 <span data-ttu-id="4803e-113">식별 하 고 이러한 위치에서 이러한 형식의 파일을 로드 하는 것에 대 한 일관 된 메커니즘을 제공할 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 확장성을 이용 합니다 *pack URI 체계*합니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-113">To provide a consistent mechanism for identifying and loading these types of files from these locations, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] leverages the extensibility of the *pack URI scheme*.</span></span> <span data-ttu-id="4803e-114">이 항목에서는 스키마의 개요를 제공, 팩을 생성 하는 방법에 설명 [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] 는 다양 한 시나리오에 대 한 설명 absolute 및 relative [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] 하 고 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 팩을 사용 하는 방법을 보여 주기 전에 해상도 [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] 두 태그에서 및 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-114">This topic provides an overview of the scheme, covers how to construct pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] for a variety of scenarios, discusses absolute and relative [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] and [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] resolution, before showing how to use pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] from both markup and code.</span></span>  

<a name="The_Pack_URI_Scheme"></a>   
## <a name="the-pack-uri-scheme"></a><span data-ttu-id="4803e-115">Pack URI 체계</span><span class="sxs-lookup"><span data-stu-id="4803e-115">The Pack URI Scheme</span></span>  
 <span data-ttu-id="4803e-116">Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 체계를 사용 하 여 합니다 [Open Packaging Conventions](https://go.microsoft.com/fwlink/?LinkID=71255) 구성 및 콘텐츠 식별에 대 한 모델을 설명 하는 (OPC) 사양입니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-116">The pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] scheme is used by the [Open Packaging Conventions](https://go.microsoft.com/fwlink/?LinkID=71255) (OPC) specification, which describes a model for organizing and identifying content.</span></span> <span data-ttu-id="4803e-117">이 모델의 주요 요소는 패키지와 파트 위치를 *패키지* 인지 하는 논리 컨테이너 하나에 대 한 더 많은 논리 *파트*합니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-117">The key elements of this model are packages and parts, where a *package* is a logical container for one or more logical *parts*.</span></span> <span data-ttu-id="4803e-118">다음 그림에서는 이 개념을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-118">The following figure illustrates this concept.</span></span>  
  
 ![패키지 및 파트 다이어그램](./media/pack-uris-in-wpf/wpf-package-parts-diagram.png)  
  
 <span data-ttu-id="4803e-120">OPC 사양 부분을 식별 하려면 RFC 2396의 확장성을 이용 합니다 (리소스 URI (Uniform Identifier): 팩을 정의 하려면 제네릭 구문) [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 구성표입니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-120">To identify parts, the OPC specification leverages the extensibility of RFC 2396 (Uniform Resource Identifiers (URI): Generic Syntax) to define the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] scheme.</span></span>  
  
 <span data-ttu-id="4803e-121">지정 된 구성표를 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 접두사로 정의 됩니다 http, ftp 및 file은 잘 알려진 예입니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-121">The scheme that is specified by a [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] is defined by its prefix; http, ftp, and file are well-known examples.</span></span> <span data-ttu-id="4803e-122">Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 체계 "pack"을 사용 하 여 해당 체계로 및 두 개의 구성 요소를 포함 합니다: 인증 기관과 경로.</span><span class="sxs-lookup"><span data-stu-id="4803e-122">The pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] scheme uses "pack" as its scheme, and contains two components: authority and path.</span></span> <span data-ttu-id="4803e-123">다음은 pack에 대 한 형식 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-123">The following is the format for a pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span>  
  
 <span data-ttu-id="4803e-124">pack://*authority*/*path*</span><span class="sxs-lookup"><span data-stu-id="4803e-124">pack://*authority*/*path*</span></span>
  
 <span data-ttu-id="4803e-125">*기관* 파트에서 포함 된 패키지의 유형을 지정 하는 동안 합니다 *경로* 패키지 내의 파트의 위치를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-125">The *authority* specifies the type of package that a part is contained by, while the *path* specifies the location of a part within a package.</span></span>  
  
 <span data-ttu-id="4803e-126">다음 그림에서는 이 개념을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-126">This concept is illustrated by the following figure:</span></span>  
  
 ![패키지, 권한 및 경로의 관계](./media/pack-uris-in-wpf/wpf-relationship-diagram.png)  
  
 <span data-ttu-id="4803e-128">패키지와 파트는 애플리케이션 및 파일과 유사합니다. 즉, 애플리케이션(패키지)은 다음을 비롯한 하나 이상의 파일(파트)을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-128">Packages and parts are analogous to applications and files, where an application (package) can include one or more files (parts), including:</span></span>  
  
-   <span data-ttu-id="4803e-129">로컬 어셈블리로 컴파일되는 리소스 파일</span><span class="sxs-lookup"><span data-stu-id="4803e-129">Resource files that are compiled into the local assembly.</span></span>  
  
-   <span data-ttu-id="4803e-130">참조된 어셈블리로 컴파일되는 리소스 파일</span><span class="sxs-lookup"><span data-stu-id="4803e-130">Resource files that are compiled into a referenced assembly.</span></span>  
  
-   <span data-ttu-id="4803e-131">참조하는 어셈블리로 컴파일되는 리소스 파일</span><span class="sxs-lookup"><span data-stu-id="4803e-131">Resource files that are compiled into a referencing assembly.</span></span>  
  
-   <span data-ttu-id="4803e-132">콘텐츠 파일</span><span class="sxs-lookup"><span data-stu-id="4803e-132">Content files.</span></span>  
  
-   <span data-ttu-id="4803e-133">원본 사이트 파일</span><span class="sxs-lookup"><span data-stu-id="4803e-133">Site of origin files.</span></span>  
  
 <span data-ttu-id="4803e-134">이러한 종류의 파일에 액세스 하려면 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 두 기관을 지원: 응용 프로그램: / / / 및 siteoforigin:///: / / /입니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-134">To access these types of files, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] supports two authorities: application:/// and siteoforigin:///.</span></span> <span data-ttu-id="4803e-135">application:/// 인증 기관은 리소스 및 콘텐츠 파일을 비롯하여 컴파일 시 알려진 애플리케이션 데이터 파일을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-135">The application:/// authority identifies application data files that are known at compile time, including resource and content files.</span></span> <span data-ttu-id="4803e-136">siteoforigin:/// 인증 기관은 원본 사이트 파일을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-136">The siteoforigin:/// authority identifies site of origin files.</span></span> <span data-ttu-id="4803e-137">다음 그림에서는 각 인증 기관의 범위를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-137">The scope of each authority is shown in the following figure.</span></span>  
  
 ![Pack URI 다이어그램](./media/pack-uris-in-wpf/wpf-pack-uri-scheme.png)  
  
> [!NOTE]
>  <span data-ttu-id="4803e-139">팩의 인증 기관 구성 요소가 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 포함 된 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 패키지를 가리키는 RFC 2396을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-139">The authority component of a pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] is an embedded [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] that points to a package and must conform to RFC 2396.</span></span> <span data-ttu-id="4803e-140">또한 “/” 문자를 “,” 문자로 바꾸고 “%” 및 “?” 같은 예약 문자는 이스케이프해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-140">Additionally, the "/" character must be replaced with the "," character, and reserved characters such as "%" and "?" must be escaped.</span></span> <span data-ttu-id="4803e-141">자세한 내용은 OPC를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4803e-141">See the OPC for details.</span></span>  
  
 <span data-ttu-id="4803e-142">다음 섹션에서는 팩을 생성 하는 방법에 설명 [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] 적절 한 경로와 함께이 두 인증 기관과 리소스, 콘텐츠 및 원본 사이트 파일을 식별 하는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-142">The following sections explain how to construct pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] using these two authorities in conjunction with the appropriate paths for identifying resource, content, and site of origin files.</span></span>  
  
<a name="Resource_File_Pack_URIs___Local_Assembly"></a>   
## <a name="resource-file-pack-uris"></a><span data-ttu-id="4803e-143">리소스 파일 Pack URI</span><span class="sxs-lookup"><span data-stu-id="4803e-143">Resource File Pack URIs</span></span>  
 <span data-ttu-id="4803e-144">로 구성 된 리소스 파일 [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `Resource` 항목 및 어셈블리에 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-144">Resource files are configured as [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]`Resource` items and are compiled into assemblies.</span></span> [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] <span data-ttu-id="4803e-145">팩의 생성을 지원 [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] 리소스 파일을 로컬 어셈블리로 컴파일된 되거나 로컬 어셈블리에서 참조 되는 어셈블리로 컴파일되는 데 사용할 수 있는 합니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-145">supports the construction of pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] that can be used to identify resource files that are either compiled into the local assembly or compiled into an assembly that is referenced from the local assembly.</span></span>  
  
<a name="Local_Assembly_Resource_File"></a>   
### <a name="local-assembly-resource-file"></a><span data-ttu-id="4803e-146">로컬 어셈블리 리소스 파일</span><span class="sxs-lookup"><span data-stu-id="4803e-146">Local Assembly Resource File</span></span>  
 <span data-ttu-id="4803e-147">Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 리소스에 대 한 로컬 어셈블리로 컴파일되는 파일은 다음 인증 기관과 경로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-147">The pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a resource file that is compiled into the local assembly uses the following authority and path:</span></span>  
  
-   <span data-ttu-id="4803e-148">**인증 기관**: application:///</span><span class="sxs-lookup"><span data-stu-id="4803e-148">**Authority**: application:///.</span></span>  
  
-   <span data-ttu-id="4803e-149">**경로**: 로컬 어셈블리 프로젝트 폴더 루트에 상대적인 경로 포함 하는 리소스 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-149">**Path**: The name of the resource file, including its path, relative to the local assembly project folder root.</span></span>  
  
 <span data-ttu-id="4803e-150">다음 예제에서는 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 에 대 한는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 로컬 어셈블리의 프로젝트 폴더의 루트에 있는 리소스 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-150">The following example shows the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] resource file that is located in the root of the local assembly's project folder.</span></span>  
  
 `pack://application:,,,/ResourceFile.xaml`  
  
 <span data-ttu-id="4803e-151">다음 예제에서는 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 에 대 한는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 로컬 어셈블리의 프로젝트 폴더의 하위 폴더에 있는 리소스 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-151">The following example shows the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] resource file that is located in a subfolder of the local assembly's project folder.</span></span>  
  
 `pack://application:,,,/Subfolder/ResourceFile.xaml`  
  
<a name="Resource_File_Pack_URIs___Referenced_Assembly"></a>   
### <a name="referenced-assembly-resource-file"></a><span data-ttu-id="4803e-152">참조된 어셈블리 리소스 파일</span><span class="sxs-lookup"><span data-stu-id="4803e-152">Referenced Assembly Resource File</span></span>  
 <span data-ttu-id="4803e-153">Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 리소스에 대 한 참조 된 어셈블리로 컴파일되는 파일은 다음 인증 기관과 경로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-153">The pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a resource file that is compiled into a referenced assembly uses the following authority and path:</span></span>  
  
-   <span data-ttu-id="4803e-154">**인증 기관**: application:///</span><span class="sxs-lookup"><span data-stu-id="4803e-154">**Authority**: application:///.</span></span>  
  
-   <span data-ttu-id="4803e-155">**경로**: 참조 된 어셈블리로 컴파일되는 리소스 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-155">**Path**: The name of a resource file that is compiled into a referenced assembly.</span></span> <span data-ttu-id="4803e-156">경로는 다음 형식을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-156">The path must conform to the following format:</span></span>  
  
     <span data-ttu-id="4803e-157">*AssemblyShortName*{*;Version*]{*;PublicKey*];component/*Path*</span><span class="sxs-lookup"><span data-stu-id="4803e-157">*AssemblyShortName*{*;Version*]{*;PublicKey*];component/*Path*</span></span>  
  
    -   <span data-ttu-id="4803e-158">**AssemblyShortName**: 참조된 어셈블리에 대한 약식 이름</span><span class="sxs-lookup"><span data-stu-id="4803e-158">**AssemblyShortName**: the short name for the referenced assembly.</span></span>  
  
    -   <span data-ttu-id="4803e-159">**;Version**[옵션]: 리소스 파일을 포함하는 참조된 어셈블리의 버전.</span><span class="sxs-lookup"><span data-stu-id="4803e-159">**;Version** [optional]: the version of the referenced assembly that contains the resource file.</span></span> <span data-ttu-id="4803e-160">동일한 약식 이름을 갖는 두 개 이상의 참조된 어셈블리가 로드된 경우 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-160">This is used when two or more referenced assemblies with the same short name are loaded.</span></span>  
  
    -   <span data-ttu-id="4803e-161">**;PublicKey**[옵션]: 참조된 어셈블리를 서명하는 데 사용된 공개 키.</span><span class="sxs-lookup"><span data-stu-id="4803e-161">**;PublicKey** [optional]: the public key that was used to sign the referenced assembly.</span></span> <span data-ttu-id="4803e-162">동일한 약식 이름을 갖는 두 개 이상의 참조된 어셈블리가 로드된 경우 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-162">This is used when two or more referenced assemblies with the same short name are loaded.</span></span>  
  
    -   <span data-ttu-id="4803e-163">**;component**: 참조되는 어셈블리가 로컬 어셈블리에서 참조된다는 것을 지정</span><span class="sxs-lookup"><span data-stu-id="4803e-163">**;component**: specifies that the assembly being referred to is referenced from the local assembly.</span></span>  
  
    -   <span data-ttu-id="4803e-164">**/Path**: 참조된 어셈블리 프로젝트 폴더의 루트에 상대적인 경로를 포함한 리소스 파일의 이름</span><span class="sxs-lookup"><span data-stu-id="4803e-164">**/Path**: the name of the resource file, including its path, relative to the root of the referenced assembly's project folder.</span></span>  
  
 <span data-ttu-id="4803e-165">다음 예제에서는 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 에 대 한는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 참조 된 어셈블리의 프로젝트 폴더의 루트에 있는 리소스 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-165">The following example shows the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] resource file that is located in the root of the referenced assembly's project folder.</span></span>  
  
 `pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml`  
  
 <span data-ttu-id="4803e-166">다음 예제에서는 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 에 대 한는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 참조 된 어셈블리의 프로젝트 폴더의 하위 폴더에 있는 리소스 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-166">The following example shows the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] resource file that is located in a subfolder of the referenced assembly's project folder.</span></span>  
  
 `pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml`  
  
 <span data-ttu-id="4803e-167">다음 예제에서는 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 에 대 한는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 참조, 버전별 어셈블리의 프로젝트 폴더의 루트 폴더에 있는 리소스 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-167">The following example shows the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] resource file that is located in the root folder of a referenced, version-specific assembly's project folder.</span></span>  
  
 `pack://application:,,,/ReferencedAssembly;v1.0.0.1;component/ResourceFile.xaml`  
  
 <span data-ttu-id="4803e-168">pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 참조 된 어셈블리 리소스 파일의 구문에만 사용할 수: / / / 기관.</span><span class="sxs-lookup"><span data-stu-id="4803e-168">Note that the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] syntax for referenced assembly resource files can be used only with the application:/// authority.</span></span> <span data-ttu-id="4803e-169">예를 들어, 다음에서 지원 되지 않습니다 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-169">For example, the following is not supported in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].</span></span>  
  
 `pack://siteoforigin:,,,/SomeAssembly;component/ResourceFile.xaml`  
  
<a name="Content_File_Pack_URIs"></a>   
## <a name="content-file-pack-uris"></a><span data-ttu-id="4803e-170">콘텐츠 파일 Pack URI</span><span class="sxs-lookup"><span data-stu-id="4803e-170">Content File Pack URIs</span></span>  
 <span data-ttu-id="4803e-171">Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 는 다음 인증 기관과 경로 사용 하는 콘텐츠 파일:</span><span class="sxs-lookup"><span data-stu-id="4803e-171">The pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a content file uses the following authority and path:</span></span>  
  
-   <span data-ttu-id="4803e-172">**인증 기관**: application:///</span><span class="sxs-lookup"><span data-stu-id="4803e-172">**Authority**: application:///.</span></span>  
  
-   <span data-ttu-id="4803e-173">**경로**: 응용 프로그램의 주 실행 어셈블리의 파일 시스템 위치에 상대적인 경로 포함 하는 콘텐츠 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-173">**Path**: The name of the content file, including its path relative to the file system location of the application's main executable assembly.</span></span>  
  
 <span data-ttu-id="4803e-174">다음 예제에서는 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 에 대 한는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 실행 가능한 어셈블리와 동일한 폴더에 있는 콘텐츠 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-174">The following example shows the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] content file, located in the same folder as the executable assembly.</span></span>  
  
 `pack://application:,,,/ContentFile.xaml`  
  
 <span data-ttu-id="4803e-175">다음 예제에서는 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 에 대 한는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 응용 프로그램의 실행 가능한 어셈블리에 상대적인 하위 폴더에 있는 콘텐츠 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-175">The following example shows the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] content file, located in a subfolder that is relative to the application's executable assembly.</span></span>  
  
 `pack://application:,,,/Subfolder/ContentFile.xaml`  
  
> [!NOTE]
>  [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] <span data-ttu-id="4803e-176">콘텐츠 파일은 탐색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-176">content files cannot be navigated to.</span></span> <span data-ttu-id="4803e-177">합니다 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 구성표에 대 한 탐색 지원 [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] 원본 사이트에 있는 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-177">The [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] scheme only supports navigation to [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] files that are located at the site of origin.</span></span>  
  
<a name="The_siteoforigin_____Authority"></a>   
## <a name="site-of-origin-pack-uris"></a><span data-ttu-id="4803e-178">원본 사이트 Pack URI</span><span class="sxs-lookup"><span data-stu-id="4803e-178">Site of Origin Pack URIs</span></span>  
 <span data-ttu-id="4803e-179">Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 원본 사이트에 대 한 파일은 다음 인증 기관과 경로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-179">The pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a site of origin file uses the following authority and path:</span></span>  
  
-   <span data-ttu-id="4803e-180">**인증 기관**: siteoforigin:///</span><span class="sxs-lookup"><span data-stu-id="4803e-180">**Authority**: siteoforigin:///.</span></span>  
  
-   <span data-ttu-id="4803e-181">**경로**: 사이트는 실행 가능 어셈블리가 시작 된 위치에 상대적인 경로 포함 한 원본 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-181">**Path**: The name of the site of origin file, including its path relative to the location from which the executable assembly was launched.</span></span>  
  
 <span data-ttu-id="4803e-182">다음 예제에서는 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 에 대 한는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 원본 사이트 파일을 실행 가능 어셈블리가 시작 된 위치에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-182">The following example shows the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] site of origin file, stored in the location from which the executable assembly is launched.</span></span>  
  
 `pack://siteoforigin:,,,/SiteOfOriginFile.xaml`  
  
 <span data-ttu-id="4803e-183">다음 예제에서는 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 에 대 한는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 원본 사이트 파일을 응용 프로그램의 실행 가능 어셈블리가 시작 된 위치를 기준으로 하는 하위 폴더에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-183">The following example shows the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] site of origin file, stored in subfolder that is relative to the location from which the application's executable assembly is launched.</span></span>  
  
 `pack://siteoforigin:,,,/Subfolder/SiteOfOriginFile.xaml`  
  
<a name="Page_Files"></a>   
## <a name="page-files"></a><span data-ttu-id="4803e-184">페이지 파일</span><span class="sxs-lookup"><span data-stu-id="4803e-184">Page Files</span></span>  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] <span data-ttu-id="4803e-185">으로 구성 된 파일 [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `Page` 항목 리소스 파일과 같은 방식으로 어셈블리로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-185">files that are configured as [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]`Page` items are compiled into assemblies in the same way as resource files.</span></span> <span data-ttu-id="4803e-186">따라서 [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `Page` 팩을 사용 하 여 항목을 식별할 수 있습니다 [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] 리소스 파일에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-186">Consequently, [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]`Page` items can be identified using pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] for resource files.</span></span>  
  
 <span data-ttu-id="4803e-187">유형에 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 일반적으로 구성 된 파일 [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `Page` 항목에 해당 루트 요소로 다음 중 하나:</span><span class="sxs-lookup"><span data-stu-id="4803e-187">The types of [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] files that are commonly configured as [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]`Page` items have one of the following as their root element:</span></span>  
  
-   <xref:System.Windows.Window?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Controls.Page?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Navigation.PageFunction%601?displayProperty=nameWithType>  
  
-   <xref:System.Windows.ResourceDictionary?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Documents.FlowDocument?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType>  
  
<a name="Absolute_vs_Relative_Pack_URIs"></a>   
## <a name="absolute-vs-relative-pack-uris"></a><span data-ttu-id="4803e-188">절대 및 상대 Pack URI</span><span class="sxs-lookup"><span data-stu-id="4803e-188">Absolute vs. Relative Pack URIs</span></span>  
 <span data-ttu-id="4803e-189">정규화 된 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 체계, 인증 기관 및 경로 포함 하며 절대 pack 것으로 간주 됩니다 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-189">A fully qualified pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] includes the scheme, the authority, and the path, and it is considered an absolute pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span> <span data-ttu-id="4803e-190">개발자에 게 쉽게 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 요소를 일반적으로 상대 pack 사용 하 여 적절 한 특성을 설정 하는 데 허용 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)], 경로만 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-190">As a simplification for developers, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elements typically allow you to set appropriate attributes with a relative pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)], which includes only the path.</span></span>  
  
 <span data-ttu-id="4803e-191">예를 들어 다음과 같은 절대 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 로컬 어셈블리에 리소스 파일에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-191">For example, consider the following absolute pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a resource file in the local assembly.</span></span>  
  
 `pack://application:,,,/ResourceFile.xaml`  
  
 <span data-ttu-id="4803e-192">상대 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 이 리소스를 참조 하는 파일에는 다음 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-192">The relative pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] that refers to this resource file would be the following.</span></span>  
  
 `/ResourceFile.xaml`  
  
> [!NOTE]
>  <span data-ttu-id="4803e-193">원본 사이트 파일에 어셈블리를 사용 하 여 연결 되어 있지 않으므로 참조할 수를 절대 pack을 사용 하 여 [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]입니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-193">Because site of origin files are not associated with assemblies, they can only be referred to with absolute pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)].</span></span>  
  
 <span data-ttu-id="4803e-194">기본적으로 상대 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 태그 또는 참조를 포함 하는 코드의 위치에 상대적인 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-194">By default, a relative pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] is considered relative to the location of the markup or code that contains the reference.</span></span> <span data-ttu-id="4803e-195">그러나 앞에 백슬래시를 사용 하는 경우 상대 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 참조 한 다음 응용 프로그램의 루트에 상대적인 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-195">If a leading backslash is used, however, the relative pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] reference is then considered relative to the root of the application.</span></span> <span data-ttu-id="4803e-196">예를 들어 다음과 같은 프로젝트 구조를 가정해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-196">For example, consider the following project structure.</span></span>  
  
 `App.xaml`  
  
 `Page2.xaml`  
  
 `\SubFolder`  
  
 `+ Page1.xaml`  
  
 `+ Page2.xaml`  
  
 <span data-ttu-id="4803e-197">Page1.xaml를 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 를 참조 하는 *루트*\SubFolder\Page2.xaml, 참조는 다음과 같은 상대 pack을 사용할 수 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]입니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-197">If Page1.xaml contains a [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] that references *Root*\SubFolder\Page2.xaml, the reference can use the following relative pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span>  
  
 `Page2.xaml`  
  
 <span data-ttu-id="4803e-198">Page1.xaml를 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 를 참조 하는 *루트*\Page2.xaml, 참조는 다음과 같은 상대 pack을 사용할 수 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]입니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-198">If Page1.xaml contains a [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] that references *Root*\Page2.xaml, the reference can use the following relative pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span>  
  
 `/Page2.xaml`  
  
<a name="Pack_URI_Resolution"></a>   
## <a name="pack-uri-resolution"></a><span data-ttu-id="4803e-199">Pack URI 확인</span><span class="sxs-lookup"><span data-stu-id="4803e-199">Pack URI Resolution</span></span>  
 <span data-ttu-id="4803e-200">팩 형식의 [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] 팩용 수 있도록 [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] 다른 유형의 파일을 동일 하 게 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-200">The format of pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] makes it possible for pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] for different types of files to look the same.</span></span> <span data-ttu-id="4803e-201">예를 들어 다음과 같은 절대 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-201">For example, consider the following absolute pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span>  
  
 `pack://application:,,,/ResourceOrContentFile.xaml`  
  
 <span data-ttu-id="4803e-202">이 절대 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 로컬 어셈블리에 리소스 파일 또는 콘텐츠 파일을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-202">This absolute pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] could refer to either a resource file in the local assembly or a content file.</span></span> <span data-ttu-id="4803e-203">다음과 같은 상대에 대 한 마찬가지 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-203">The same is true for the following relative [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span>  
  
 `/ResourceOrContentFile.xaml`  
  
 <span data-ttu-id="4803e-204">형식의 파일을 확인 하기 위해 팩을 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 를 참조 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 확인 [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] 로컬 어셈블리와 같은 경험적 접근을 사용 하 여 콘텐츠 파일에서 리소스 파일:</span><span class="sxs-lookup"><span data-stu-id="4803e-204">In order to determine the type of file that a pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] refers to, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] resolves [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] for resource files in local assemblies and content files by using the following heuristics:</span></span>  
  
1. <span data-ttu-id="4803e-205">프로브에 대 한 어셈블리 메타 데이터를 <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> 팩은 일치 하는 특성 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-205">Probe the assembly metadata for an <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> attribute that matches the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span>  
  
2. <span data-ttu-id="4803e-206">경우는 <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> 특성이 있으면 pack 경로의 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 콘텐츠 파일을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-206">If the <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> attribute is found, the path of the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] refers to a content file.</span></span>  
  
3. <span data-ttu-id="4803e-207">경우는 <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> 특성이 없으면 로컬 어셈블리로 컴파일되는 리소스 파일 집합을 조사 합니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-207">If the <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> attribute is not found, probe the set resource files that are compiled into the local assembly.</span></span>  
  
4. <span data-ttu-id="4803e-208">팩의 경로 일치 하는 리소스 파일이 있으면 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 발견 되는 팩 경로의 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 리소스 파일을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-208">If a resource file that matches the path of the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] is found, the path of the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] refers to a resource file.</span></span>  
  
5. <span data-ttu-id="4803e-209">리소스가 없는 경우, 내부적으로 만든 <xref:System.Uri> 올바르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-209">If the resource is not found, the internally created <xref:System.Uri> is invalid.</span></span>  
  
 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] <span data-ttu-id="4803e-210">해결 방법에 대 한 적용 되지 않습니다 [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] 는 다음을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="4803e-210">resolution does not apply for [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] that refer to the following:</span></span>  
  
-   <span data-ttu-id="4803e-211">참조 된 어셈블리의 콘텐츠 파일: 하 여 이러한 파일 형식은 지원 되지 않습니다 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-211">Content files in referenced assemblies: these file types are not supported by [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].</span></span>  
  
-   <span data-ttu-id="4803e-212">참조 된 어셈블리에 포함 된 파일: [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] 식별 하는 참조 된 어셈블리의 이름을 둘 다 포함 되어 있으므로 고유 하며 `;component` 접미사.</span><span class="sxs-lookup"><span data-stu-id="4803e-212">Embedded files in referenced assemblies: [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] that identify them are unique because they include both the name of the referenced assembly and the `;component` suffix.</span></span>  
  
-   <span data-ttu-id="4803e-213">원본 사이트 파일: [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] 식별 하는 팩에서 식별할 수 있는 유일한 파일 이므로 고유 [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] siteoforigin:/// 인증 포함 된: / / / 기관.</span><span class="sxs-lookup"><span data-stu-id="4803e-213">Site of origin files: [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] that identify them are unique because they are the only files that can be identified by pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] that contain the siteoforigin:/// authority.</span></span>  
  
 <span data-ttu-id="4803e-214">팩는 한 가지 단순화 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 확인 코드가 리소스 및 콘텐츠 파일의 위치와 다소 독립적일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-214">One simplification that pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] resolution allows is for code to be somewhat independent of the locations of resource and content files.</span></span> <span data-ttu-id="4803e-215">예를 들어 팩은 콘텐츠 파일을 다시 구성 되는 로컬 어셈블리의 리소스 파일이 있다고 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 팩을 사용 하는 코드와 마찬가지로 똑같이 리소스 유지에 대 한 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-215">For example, if you have a resource file in the local assembly that is reconfigured to be a content file, the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for the resource remains the same, as does the code that uses the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span>  
  
<a name="Programming_with_Pack_URIs"></a>   
## <a name="programming-with-pack-uris"></a><span data-ttu-id="4803e-216">Pack URI를 사용한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="4803e-216">Programming with Pack URIs</span></span>  
 <span data-ttu-id="4803e-217">많은 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 팩을 사용 하 여 설정할 수 있는 속성을 구현 하는 클래스 [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]등.</span><span class="sxs-lookup"><span data-stu-id="4803e-217">Many [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] classes implement properties that can be set with pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)], including:</span></span>  
  
-   <xref:System.Windows.Application.StartupUri%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Controls.Frame.Source%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Navigation.NavigationWindow.Source%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Documents.Hyperlink.NavigateUri%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Window.Icon%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Controls.Image.Source%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="4803e-218">이러한 속성을 태그와 코드 모두에서 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-218">These properties can be set from both markup and code.</span></span> <span data-ttu-id="4803e-219">이 섹션에서는 두 경우에 대한 기본 구조를 설명한 다음 일반적인 시나리오 예제를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-219">This section demonstrates the basic constructions for both and then shows examples of common scenarios.</span></span>  
  
<a name="Using_Pack_URIs_in_Markup"></a>   
### <a name="using-pack-uris-in-markup"></a><span data-ttu-id="4803e-220">태그에서 Pack URI 사용</span><span class="sxs-lookup"><span data-stu-id="4803e-220">Using Pack URIs in Markup</span></span>  
 <span data-ttu-id="4803e-221">Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 팩을 사용 하 여 특성의 요소를 설정 하 여 태그에 지정 된 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-221">A pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] is specified in markup by setting the element of an attribute with the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span> <span data-ttu-id="4803e-222">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="4803e-222">For example:</span></span>  
  
 `<element attribute="pack://application:,,,/File.xaml" />`  
  
 <span data-ttu-id="4803e-223">테이블 1에서는 다양 한 절대 pack 보여 줍니다. [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] 는 태그에 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-223">Table 1 illustrates the various absolute pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] that you can specify in markup.</span></span>  
  
 <span data-ttu-id="4803e-224">표 1: 태그의 절대 Pack Uri</span><span class="sxs-lookup"><span data-stu-id="4803e-224">Table 1: Absolute Pack URIs in Markup</span></span>  
  
|<span data-ttu-id="4803e-225">파일</span><span class="sxs-lookup"><span data-stu-id="4803e-225">File</span></span>|<span data-ttu-id="4803e-226">절대 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4803e-226">Absolute pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]</span></span>|  
|----------|-------------------------------------------------------------------------------------------------------------------------|  
|<span data-ttu-id="4803e-227">리소스 파일 - 로컬 어셈블리</span><span class="sxs-lookup"><span data-stu-id="4803e-227">Resource file - local assembly</span></span>|`"pack://application:,,,/ResourceFile.xaml"`|  
|<span data-ttu-id="4803e-228">하위 폴더의 리소스 파일 - 로컬 어셈블리</span><span class="sxs-lookup"><span data-stu-id="4803e-228">Resource file in subfolder - local assembly</span></span>|`"pack://application:,,,/Subfolder/ResourceFile.xaml"`|  
|<span data-ttu-id="4803e-229">리소스 파일 - 참조된 어셈블리</span><span class="sxs-lookup"><span data-stu-id="4803e-229">Resource file - referenced assembly</span></span>|`"pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml"`|  
|<span data-ttu-id="4803e-230">참조된 어셈블리의 하위 폴더에 있는 리소스 파일</span><span class="sxs-lookup"><span data-stu-id="4803e-230">Resource file in subfolder of referenced assembly</span></span>|`"pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml"`|  
|<span data-ttu-id="4803e-231">버전이 있는 참조된 어셈블리의 리소스 파일</span><span class="sxs-lookup"><span data-stu-id="4803e-231">Resource file in versioned referenced assembly</span></span>|`"pack://application:,,,/ReferencedAssembly;v1.0.0.0;component/ResourceFile.xaml"`|  
|<span data-ttu-id="4803e-232">콘텐츠 파일</span><span class="sxs-lookup"><span data-stu-id="4803e-232">Content file</span></span>|`"pack://application:,,,/ContentFile.xaml"`|  
|<span data-ttu-id="4803e-233">하위 폴더의 콘텐츠 파일</span><span class="sxs-lookup"><span data-stu-id="4803e-233">Content file in subfolder</span></span>|`"pack://application:,,,/Subfolder/ContentFile.xaml"`|  
|<span data-ttu-id="4803e-234">원본 사이트 파일</span><span class="sxs-lookup"><span data-stu-id="4803e-234">Site of origin file</span></span>|`"pack://siteoforigin:,,,/SOOFile.xaml"`|  
|<span data-ttu-id="4803e-235">하위 폴더의 원본 사이트 파일</span><span class="sxs-lookup"><span data-stu-id="4803e-235">Site of origin file in subfolder</span></span>|`"pack://siteoforigin:,,,/Subfolder/SOOFile.xaml"`|  
  
 <span data-ttu-id="4803e-236">테이블 2에서는 다양 한 상대 pack 보여 줍니다. [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] 는 태그에 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-236">Table 2 illustrates the various relative pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] that you can specify in markup.</span></span>  
  
 <span data-ttu-id="4803e-237">표 2: 태그의 상대 Pack Uri</span><span class="sxs-lookup"><span data-stu-id="4803e-237">Table 2: Relative Pack URIs in Markup</span></span>  
  
|<span data-ttu-id="4803e-238">파일</span><span class="sxs-lookup"><span data-stu-id="4803e-238">File</span></span>|<span data-ttu-id="4803e-239">상대 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4803e-239">Relative pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]</span></span>|  
|----------|-------------------------------------------------------------------------------------------------------------------------|  
|<span data-ttu-id="4803e-240">로컬 어셈블리의 리소스 파일</span><span class="sxs-lookup"><span data-stu-id="4803e-240">Resource file in local assembly</span></span>|`"/ResourceFile.xaml"`|  
|<span data-ttu-id="4803e-241">로컬 어셈블리의 하위 폴더에 있는 리소스 파일</span><span class="sxs-lookup"><span data-stu-id="4803e-241">Resource file in subfolder of local assembly</span></span>|`"/Subfolder/ResourceFile.xaml"`|  
|<span data-ttu-id="4803e-242">참조된 어셈블리의 리소스 파일</span><span class="sxs-lookup"><span data-stu-id="4803e-242">Resource file in referenced assembly</span></span>|`"/ReferencedAssembly;component/ResourceFile.xaml"`|  
|<span data-ttu-id="4803e-243">참조된 어셈블리의 하위 폴더에 있는 리소스 파일</span><span class="sxs-lookup"><span data-stu-id="4803e-243">Resource file in subfolder of referenced assembly</span></span>|`"/ReferencedAssembly;component/Subfolder/ResourceFile.xaml"`|  
|<span data-ttu-id="4803e-244">콘텐츠 파일</span><span class="sxs-lookup"><span data-stu-id="4803e-244">Content file</span></span>|`"/ContentFile.xaml"`|  
|<span data-ttu-id="4803e-245">하위 폴더의 콘텐츠 파일</span><span class="sxs-lookup"><span data-stu-id="4803e-245">Content file in subfolder</span></span>|`"/Subfolder/ContentFile.xaml"`|  
  
<a name="Using_Pack_URIs_in_Code"></a>   
### <a name="using-pack-uris-in-code"></a><span data-ttu-id="4803e-246">코드에서 Pack URI 사용</span><span class="sxs-lookup"><span data-stu-id="4803e-246">Using Pack URIs in Code</span></span>  
 <span data-ttu-id="4803e-247">팩을 지정 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 인스턴스화하여 코드에는 <xref:System.Uri> 팩을 전달과 클래스 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 생성자에 매개 변수로 합니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-247">You specify a pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] in code by instantiating the <xref:System.Uri> class and passing the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] as a parameter to the constructor.</span></span> <span data-ttu-id="4803e-248">다음 예제를 통해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-248">This is demonstrated in the following example.</span></span>  
  
```csharp  
Uri uri = new Uri("pack://application:,,,/File.xaml");  
```  
  
 <span data-ttu-id="4803e-249">기본적으로 <xref:System.Uri> 클래스는 pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] 에 절대 경로 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-249">By default, the <xref:System.Uri> class considers pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] to be absolute.</span></span> <span data-ttu-id="4803e-250">인스턴스의 경우 예외가 발생 하는 결과적으로 <xref:System.Uri> 상대 pack을 사용 하 여 클래스를 만들 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-250">Consequently, an exception is raised when an instance of the <xref:System.Uri> class is created with a relative pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span>  
  
```csharp  
Uri uri = new Uri("/File.xaml");  
```  
  
 <span data-ttu-id="4803e-251">다행 스럽게도 합니다 <xref:System.Uri.%23ctor%28System.String%2CSystem.UriKind%29> 오버 로드는 <xref:System.Uri> 형식의 매개 변수를 허용 하는 클래스 생성자 <xref:System.UriKind> 지정할 수 있도록 팩을 여부를 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 가 절대 인지 상대 합니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-251">Fortunately, the <xref:System.Uri.%23ctor%28System.String%2CSystem.UriKind%29> overload of the <xref:System.Uri> class constructor accepts a parameter of type <xref:System.UriKind> to allow you to specify whether a pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] is either absolute or relative.</span></span>  
  
```csharp  
// Absolute URI (default)  
Uri absoluteUri = new Uri("pack://application:,,,/File.xaml", UriKind.Absolute);  
// Relative URI  
Uri relativeUri = new Uri("/File.xaml",   
                        UriKind.Relative);  
```  
  
 <span data-ttu-id="4803e-252">만 지정 해야 <xref:System.UriKind.Absolute> 나 <xref:System.UriKind.Relative> 되었음을 확인 하는 경우 제공 된 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 둘 중 하나는 합니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-252">You should specify only <xref:System.UriKind.Absolute> or <xref:System.UriKind.Relative> when you are certain that the provided pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] is one or the other.</span></span> <span data-ttu-id="4803e-253">팩의 유형을 알 수 없는 경우 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 사용 되는, 팩을 사용자가 입력 하는 경우와 같은 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 런타임 시 사용 하 여 <xref:System.UriKind.RelativeOrAbsolute> 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-253">If you don't know the type of pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] that is used, such as when a user enters a pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] at run time, use <xref:System.UriKind.RelativeOrAbsolute> instead.</span></span>  
  
```csharp  
// Relative or Absolute URI provided by user via a text box  
TextBox userProvidedUriTextBox = new TextBox();  
Uri uri = new Uri(userProvidedUriTextBox.Text, UriKind.RelativeOrAbsolute);  
```  
  
 <span data-ttu-id="4803e-254">표 3은 다양 한 상대 pack 보여줍니다 [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] 를 사용 하 여 코드에서 지정할 수 있는 <xref:System.Uri?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-254">Table 3 illustrates the various relative pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] that you can specify in code by using <xref:System.Uri?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="4803e-255">표 3: 코드의 절대 Pack Uri</span><span class="sxs-lookup"><span data-stu-id="4803e-255">Table 3: Absolute Pack URIs in Code</span></span>  
  
|<span data-ttu-id="4803e-256">파일</span><span class="sxs-lookup"><span data-stu-id="4803e-256">File</span></span>|<span data-ttu-id="4803e-257">절대 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4803e-257">Absolute pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]</span></span>|  
|----------|-------------------------------------------------------------------------------------------------------------------------|  
|<span data-ttu-id="4803e-258">리소스 파일 - 로컬 어셈블리</span><span class="sxs-lookup"><span data-stu-id="4803e-258">Resource file - local assembly</span></span>|`Uri uri = new Uri("pack://application:,,,/ResourceFile.xaml", UriKind.Absolute);`|  
|<span data-ttu-id="4803e-259">하위 폴더의 리소스 파일 - 로컬 어셈블리</span><span class="sxs-lookup"><span data-stu-id="4803e-259">Resource file in subfolder - local assembly</span></span>|`Uri uri = new Uri("pack://application:,,,/Subfolder/ResourceFile.xaml", UriKind.Absolute);`|  
|<span data-ttu-id="4803e-260">리소스 파일 - 참조된 어셈블리</span><span class="sxs-lookup"><span data-stu-id="4803e-260">Resource file - referenced assembly</span></span>|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml", UriKind.Absolute);`|  
|<span data-ttu-id="4803e-261">참조된 어셈블리의 하위 폴더에 있는 리소스 파일</span><span class="sxs-lookup"><span data-stu-id="4803e-261">Resource file in subfolder of referenced assembly</span></span>|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml", UriKind.Absolute);`|  
|<span data-ttu-id="4803e-262">버전이 있는 참조된 어셈블리의 리소스 파일</span><span class="sxs-lookup"><span data-stu-id="4803e-262">Resource file in versioned referenced assembly</span></span>|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;v1.0.0.0;component/ResourceFile.xaml", UriKind.Absolute);`|  
|<span data-ttu-id="4803e-263">콘텐츠 파일</span><span class="sxs-lookup"><span data-stu-id="4803e-263">Content file</span></span>|`Uri uri = new Uri("pack://application:,,,/ContentFile.xaml", UriKind.Absolute);`|  
|<span data-ttu-id="4803e-264">하위 폴더의 콘텐츠 파일</span><span class="sxs-lookup"><span data-stu-id="4803e-264">Content file in subfolder</span></span>|`Uri uri = new Uri("pack://application:,,,/Subfolder/ContentFile.xaml", UriKind.Absolute);`|  
|<span data-ttu-id="4803e-265">원본 사이트 파일</span><span class="sxs-lookup"><span data-stu-id="4803e-265">Site of origin file</span></span>|`Uri uri = new Uri("pack://siteoforigin:,,,/SOOFile.xaml", UriKind.Absolute);`|  
|<span data-ttu-id="4803e-266">하위 폴더의 원본 사이트 파일</span><span class="sxs-lookup"><span data-stu-id="4803e-266">Site of origin file in subfolder</span></span>|`Uri uri = new Uri("pack://siteoforigin:,,,/Subfolder/SOOFile.xaml", UriKind.Absolute);`|  
  
 <span data-ttu-id="4803e-267">표 4에는 다양 한 상대 pack 보여 줍니다 [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] 사용 하 여 코드에서 지정할 수 있는 <xref:System.Uri?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-267">Table 4 illustrates the various relative pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] that you can specify in code using <xref:System.Uri?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="4803e-268">표 4: 코드의 상대 Pack Uri</span><span class="sxs-lookup"><span data-stu-id="4803e-268">Table 4: Relative Pack URIs in Code</span></span>  
  
|<span data-ttu-id="4803e-269">파일</span><span class="sxs-lookup"><span data-stu-id="4803e-269">File</span></span>|<span data-ttu-id="4803e-270">상대 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4803e-270">Relative pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]</span></span>|  
|----------|-------------------------------------------------------------------------------------------------------------------------|  
|<span data-ttu-id="4803e-271">리소스 파일 - 로컬 어셈블리</span><span class="sxs-lookup"><span data-stu-id="4803e-271">Resource file - local assembly</span></span>|`Uri uri = new Uri("/ResourceFile.xaml", UriKind.Relative);`|  
|<span data-ttu-id="4803e-272">하위 폴더의 리소스 파일 - 로컬 어셈블리</span><span class="sxs-lookup"><span data-stu-id="4803e-272">Resource file in subfolder - local assembly</span></span>|`Uri uri = new Uri("/Subfolder/ResourceFile.xaml", UriKind.Relative);`|  
|<span data-ttu-id="4803e-273">리소스 파일 - 참조된 어셈블리</span><span class="sxs-lookup"><span data-stu-id="4803e-273">Resource file - referenced assembly</span></span>|`Uri uri = new Uri("/ReferencedAssembly;component/ResourceFile.xaml", UriKind.Relative);`|  
|<span data-ttu-id="4803e-274">하위 폴더의 리소스 파일 - 참조된 어셈블리</span><span class="sxs-lookup"><span data-stu-id="4803e-274">Resource file in subfolder - referenced assembly</span></span>|`Uri uri = new Uri("/ReferencedAssembly;component/Subfolder/ResourceFile.xaml", UriKind.Relative);`|  
|<span data-ttu-id="4803e-275">콘텐츠 파일</span><span class="sxs-lookup"><span data-stu-id="4803e-275">Content file</span></span>|`Uri uri = new Uri("/ContentFile.xaml", UriKind.Relative);`|  
|<span data-ttu-id="4803e-276">하위 폴더의 콘텐츠 파일</span><span class="sxs-lookup"><span data-stu-id="4803e-276">Content file in subfolder</span></span>|`Uri uri = new Uri("/Subfolder/ContentFile.xaml", UriKind.Relative);`|  
  
<a name="Common_Pack_URI_Scenarios"></a>   
### <a name="common-pack-uri-scenarios"></a><span data-ttu-id="4803e-277">일반적인 Pack URI 시나리오</span><span class="sxs-lookup"><span data-stu-id="4803e-277">Common Pack URI Scenarios</span></span>  
 <span data-ttu-id="4803e-278">이전 섹션에서는 팩을 생성 하는 방법을 설명한 [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] 리소스, 콘텐츠 및 원본 사이트 파일을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-278">The preceding sections have discussed how to construct pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] to identify resource, content, and site of origin files.</span></span> <span data-ttu-id="4803e-279">[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]이러한 구성은 다양 한 방법으로 사용 되 고 다음 섹션에서 몇 가지 일반적인 사용법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-279">In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], these constructions are used in a variety of ways, and the following sections cover several common usages.</span></span>  
  
<a name="Specifying_the_UI_to_Show_when_an_Application_Starts"></a>   
#### <a name="specifying-the-ui-to-show-when-an-application-starts"></a><span data-ttu-id="4803e-280">애플리케이션을 시작할 때 표시되는 UI 지정</span><span class="sxs-lookup"><span data-stu-id="4803e-280">Specifying the UI to Show When an Application Starts</span></span>  
 <span data-ttu-id="4803e-281"><xref:System.Windows.Application.StartupUri%2A> 첫 번째 지정 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 때 표시 되는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램이 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-281"><xref:System.Windows.Application.StartupUri%2A> specifies the first [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] to show when a [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] application is launched.</span></span> <span data-ttu-id="4803e-282">독립 실행형 응용 프로그램의 경우는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 다음 예와에서 같이 창 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-282">For standalone applications, the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] can be a window, as shown in the following example.</span></span>  
  
 [!code-xaml[PackURIOverviewSnippets#StartupUriWindow](~/samples/snippets/csharp/VS_Snippets_Wpf/PackURIOverviewSnippets/CS/Copy of App.xaml#startupuriwindow)]  
  
 <span data-ttu-id="4803e-283">독립 실행형 응용 프로그램 및 [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] 다음 예제에서와 같이 초기 UI로 페이지를 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-283">Standalone applications and [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] can also specify a page as the initial UI, as shown in the following example.</span></span>  
  
 [!code-xaml[PackURIOverviewSnippets#StartupUriPage](~/samples/snippets/csharp/VS_Snippets_Wpf/PackURIOverviewSnippets/CS/App.xaml#startupuripage)]  
  
 <span data-ttu-id="4803e-284">응용 프로그램은 독립 실행형 응용 프로그램 및 페이지를 사용 하 여 지정한 경우 <xref:System.Windows.Application.StartupUri%2A>, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 열립니다는 <xref:System.Windows.Navigation.NavigationWindow> 페이지를 호스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-284">If the application is a standalone application and a page is specified with <xref:System.Windows.Application.StartupUri%2A>, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] opens a <xref:System.Windows.Navigation.NavigationWindow> to host the page.</span></span> <span data-ttu-id="4803e-285">에 대 한 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], 호스트 브라우저에 페이지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-285">For [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], the page is shown in the host browser.</span></span>  
  
<a name="Navigating_to_a_Page"></a>   
#### <a name="navigating-to-a-page"></a><span data-ttu-id="4803e-286">페이지 탐색</span><span class="sxs-lookup"><span data-stu-id="4803e-286">Navigating to a Page</span></span>  
 <span data-ttu-id="4803e-287">다음 예제에서는 페이지를 탐색하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-287">The following example shows how to navigate to a page.</span></span>  
  
 [!code-xaml[NavigationOverviewSnippets#HyperlinkXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml1)]  
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml2)]  
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml3)]  
  
 <span data-ttu-id="4803e-288">탐색 하는 다양 한 방법에 대 한 자세한 내용은 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]를 참조 하세요 [탐색 개요](navigation-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-288">For more information on the various ways to navigate in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], see [Navigation Overview](navigation-overview.md).</span></span>  
  
<a name="Specifying_a_Window_Icon"></a>   
#### <a name="specifying-a-window-icon"></a><span data-ttu-id="4803e-289">창 아이콘 지정</span><span class="sxs-lookup"><span data-stu-id="4803e-289">Specifying a Window Icon</span></span>  
 <span data-ttu-id="4803e-290">다음 예제에서는 URI를 사용하여 창 아이콘을 지정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-290">The following example shows how to use a URI to specify a window's icon.</span></span>  
  
 [!code-xaml[WindowIconSnippets#WindowIconSetXAML](~/samples/snippets/xaml/VS_Snippets_Wpf/WindowIconSnippets/XAML/MainWindow.xaml#windowiconsetxaml)]  
  
 <span data-ttu-id="4803e-291">자세한 내용은 <xref:System.Windows.Window.Icon%2A>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4803e-291">For more information, see <xref:System.Windows.Window.Icon%2A>.</span></span>  
  
<a name="Loading_Image__Audio__and_Video_Files"></a>   
#### <a name="loading-image-audio-and-video-files"></a><span data-ttu-id="4803e-292">이미지, 오디오 및 비디오 파일 로드</span><span class="sxs-lookup"><span data-stu-id="4803e-292">Loading Image, Audio, and Video Files</span></span>  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] <span data-ttu-id="4803e-293">다양 한 미디어 유형 모두를 식별 하 고 팩을 사용 하 여 로드를 사용 하도록 응용 프로그램을 사용 하면 [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]다음 예제에 나와 있는 것 처럼 합니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-293">allows applications to use a wide variety of media types, all of which can be identified and loaded with pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)], as shown in the following examples.</span></span>  
  
 [!code-xaml[MediaPlayerVideoSample#VideoPackURIAtSOO](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaPlayerVideoSample/CS/HomePage.xaml#videopackuriatsoo)]  
  
 [!code-xaml[MediaPlayerAudioSample#AudioPackURIAtSOO](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaPlayerAudioSample/CS/HomePage.xaml#audiopackuriatsoo)]  
  
 [!code-xaml[ImageSample#ImagePackURIContent](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageSample/CS/HomePage.xaml#imagepackuricontent)]  
  
 <span data-ttu-id="4803e-294">미디어 콘텐츠가 포함 된 작업에 대 한 자세한 내용은 참조 하세요. [그래픽 및 멀티미디어](../graphics-multimedia/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-294">For more information on working with media content, see [Graphics and Multimedia](../graphics-multimedia/index.md).</span></span>  
  
<a name="Loading_a_Resource_Dictionary_from_the_Site_of_Origin"></a>   
#### <a name="loading-a-resource-dictionary-from-the-site-of-origin"></a><span data-ttu-id="4803e-295">원본 사이트에서 리소스 사전 로드</span><span class="sxs-lookup"><span data-stu-id="4803e-295">Loading a Resource Dictionary from the Site of Origin</span></span>  
 <span data-ttu-id="4803e-296">리소스 사전 (<xref:System.Windows.ResourceDictionary>) 응용 프로그램 테마를 지 원하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-296">Resource dictionaries (<xref:System.Windows.ResourceDictionary>) can be used to support application themes.</span></span> <span data-ttu-id="4803e-297">테마를 만들고 관리하는 한 가지 방법은 애플리케이션의 원본 사이트에 위치한 리소스 사전으로 여러 개의 테마를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-297">One way to create and manage themes is to create multiple themes as resource dictionaries that are located at an application's site of origin.</span></span> <span data-ttu-id="4803e-298">이렇게 하면 애플리케이션을 다시 컴파일하여 배포할 필요 없이 테마를 추가하고 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-298">This allows themes to be added and updated without recompiling and redeploying an application.</span></span> <span data-ttu-id="4803e-299">이러한 리소스 사전은 확인할 수 있으며 팩을 사용 하 여 로드 [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)], 다음 예제에 나와 있는 합니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-299">These resource dictionaries can be identified and loaded using pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)], which is shown in the following example.</span></span>  
  
 [!code-xaml[ResourceDictionarySnippets#ResourceDictionaryPackURI](~/samples/snippets/csharp/VS_Snippets_Wpf/ResourceDictionarySnippets/CS/App.xaml#resourcedictionarypackuri)]  
  
 <span data-ttu-id="4803e-300">테마에 대 한 개요 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]를 참조 하세요 [스타일 및 템플릿](../controls/styling-and-templating.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4803e-300">For an overview of themes in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], see [Styling and Templating](../controls/styling-and-templating.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4803e-301">참고자료</span><span class="sxs-lookup"><span data-stu-id="4803e-301">See also</span></span>

- [<span data-ttu-id="4803e-302">WPF 응용 프로그램 리소스, 콘텐츠 및 데이터 파일</span><span class="sxs-lookup"><span data-stu-id="4803e-302">WPF Application Resource, Content, and Data Files</span></span>](wpf-application-resource-content-and-data-files.md)
