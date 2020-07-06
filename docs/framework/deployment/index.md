---
title: .NET Framework 및 애플리케이션 배포
description: 애플리케이션을 사용하여 .NET 배포를 시작합니다. .NET은 영향을 주지 않는 애플리케이션, 기본적으로 프라이빗 구성 요소, 제어된 코드 공유 등을 제공합니다.
ms.date: 03/30/2017
helpviewer_keywords:
- deploying applications [.NET Framework], packaging
- deploying applications [.NET Framework]
- deploying applications [.NET Framework], features
- deploying applications [.NET Framework], distribution
- .NET Framework, deploying
- .NET Framework application deployment
ms.assetid: 238d8284-6042-4a38-a7f6-1ee8efd719da
ms.openlocfilehash: cce888c962c9ab83c13cce4040eb9ba50270972d
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85803504"
---
# <a name="deploying-the-net-framework-and-applications"></a><span data-ttu-id="c0a17-104">.NET Framework 및 애플리케이션 배포</span><span class="sxs-lookup"><span data-stu-id="c0a17-104">Deploying the .NET Framework and Applications</span></span>

<span data-ttu-id="c0a17-105">이 문서는 애플리케이션과 함께 .NET Framework 배포를 시작하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0a17-105">This article helps you get started deploying the .NET Framework with your application.</span></span> <span data-ttu-id="c0a17-106">대부분의 정보는 개발자, OEM 및 엔터프라이즈 관리자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c0a17-106">Most of the information is intended for developers, OEMs, and enterprise administrators.</span></span> <span data-ttu-id="c0a17-107">컴퓨터에 .NET Framework를 설치하려는 사용자는 [.NET Framework 설치](../install/index.md)를 읽어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0a17-107">Users who want to install the .NET Framework on their computers should read [Installing the .NET Framework](../install/index.md).</span></span>

## <a name="key-deployment-resources"></a><span data-ttu-id="c0a17-108">주요 배포 리소스</span><span class="sxs-lookup"><span data-stu-id="c0a17-108">Key Deployment Resources</span></span>

<span data-ttu-id="c0a17-109">.NET Framework 배포 및 서비스와 관련된 특정 정보는 다른 MSDN 항목의 다음 링크를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c0a17-109">Use the following links to other MSDN topics for specific information about deploying and servicing the .NET Framework.</span></span>

<span data-ttu-id="c0a17-110">**설치 및 배포**</span><span class="sxs-lookup"><span data-stu-id="c0a17-110">**Setup and deployment**</span></span>

- <span data-ttu-id="c0a17-111">일반적인 설치 관리자 및 배포 정보:</span><span class="sxs-lookup"><span data-stu-id="c0a17-111">General installer and deployment information:</span></span>

  - <span data-ttu-id="c0a17-112">설치 관리자 옵션:</span><span class="sxs-lookup"><span data-stu-id="c0a17-112">Installer options:</span></span>

    - [<span data-ttu-id="c0a17-113">웹 설치 관리자</span><span class="sxs-lookup"><span data-stu-id="c0a17-113">Web installer</span></span>](../install/guide-for-developers.md#to-install-or-download-the-net-framework-redistributable)

    - [<span data-ttu-id="c0a17-114">오프라인 설치 관리자</span><span class="sxs-lookup"><span data-stu-id="c0a17-114">Offline installer</span></span>](../install/guide-for-developers.md#to-install-or-download-the-net-framework-redistributable)

  - <span data-ttu-id="c0a17-115">설치 모드:</span><span class="sxs-lookup"><span data-stu-id="c0a17-115">Installation modes:</span></span>

    - [<span data-ttu-id="c0a17-116">자동 설치</span><span class="sxs-lookup"><span data-stu-id="c0a17-116">Silent installation</span></span>](deployment-guide-for-developers.md#chaining_custom)

    - [<span data-ttu-id="c0a17-117">UI 표시</span><span class="sxs-lookup"><span data-stu-id="c0a17-117">Displaying a UI</span></span>](deployment-guide-for-developers.md#chaining_default)

  - [<span data-ttu-id="c0a17-118">.NET Framework 4.5를 설치하는 동안 시스템 다시 시작 줄이기</span><span class="sxs-lookup"><span data-stu-id="c0a17-118">Reducing system restarts during .NET Framework 4.5 installations</span></span>](reducing-system-restarts.md)

  - [<span data-ttu-id="c0a17-119">차단된 .NET Framework 설치 및 제거 문제 해결</span><span class="sxs-lookup"><span data-stu-id="c0a17-119">Troubleshoot blocked .NET Framework installations and uninstallations</span></span>](../install/troubleshoot-blocked-installations-and-uninstallations.md)

- <span data-ttu-id="c0a17-120">클라이언트 애플리케이션과 함께 .NET Framework 배포(개발자용):</span><span class="sxs-lookup"><span data-stu-id="c0a17-120">Deploying the .NET Framework with a client application (for developers):</span></span>

  - <span data-ttu-id="c0a17-121">설치 및 배포 프로젝트에 [InstallShield 사용](deployment-guide-for-developers.md#installshield-deployment)</span><span class="sxs-lookup"><span data-stu-id="c0a17-121">[Using InstallShield](deployment-guide-for-developers.md#installshield-deployment) in a setup and deployment project</span></span>

  - [<span data-ttu-id="c0a17-122">Visual Studio ClickOnce 애플리케이션 사용</span><span class="sxs-lookup"><span data-stu-id="c0a17-122">Using a Visual Studio ClickOnce application</span></span>](deployment-guide-for-developers.md#clickonce-deployment)

  - [<span data-ttu-id="c0a17-123">WiX 설치 패키지 만들기</span><span class="sxs-lookup"><span data-stu-id="c0a17-123">Creating a WiX installation package</span></span>](deployment-guide-for-developers.md#wix)

  - [<span data-ttu-id="c0a17-124">사용자 지정 설치 관리자 사용</span><span class="sxs-lookup"><span data-stu-id="c0a17-124">Using a custom installer</span></span>](deployment-guide-for-developers.md#chaining)

  - <span data-ttu-id="c0a17-125">개발자용 [추가 정보](deployment-guide-for-developers.md)</span><span class="sxs-lookup"><span data-stu-id="c0a17-125">[Additional information](deployment-guide-for-developers.md) for developers</span></span>

- <span data-ttu-id="c0a17-126">.NET Framework 배포(OEM 및 관리자용):</span><span class="sxs-lookup"><span data-stu-id="c0a17-126">Deploying the .NET Framework (for OEMs and administrators):</span></span>

  - [<span data-ttu-id="c0a17-127">Windows ADK(평가 및 배포 키트)</span><span class="sxs-lookup"><span data-stu-id="c0a17-127">Windows Assessment and Deployment Kit (ADK)</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=254976)

  - [<span data-ttu-id="c0a17-128">관리자 가이드</span><span class="sxs-lookup"><span data-stu-id="c0a17-128">Administrator's guide</span></span>](guide-for-administrators.md)

<span data-ttu-id="c0a17-129">**서비스**</span><span class="sxs-lookup"><span data-stu-id="c0a17-129">**Servicing**</span></span>

- <span data-ttu-id="c0a17-130">일반적인 내용은 [.NET Framework 블로그](https://devblogs.microsoft.com/dotnet/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c0a17-130">For general information, see the [.NET Framework blog](https://devblogs.microsoft.com/dotnet/).</span></span>

- [<span data-ttu-id="c0a17-131">버전 검색</span><span class="sxs-lookup"><span data-stu-id="c0a17-131">Detecting versions</span></span>](../migration-guide/how-to-determine-which-versions-are-installed.md)

- [<span data-ttu-id="c0a17-132">서비스 팩과 업데이트 검색</span><span class="sxs-lookup"><span data-stu-id="c0a17-132">Detecting service packs and updates</span></span>](../migration-guide/how-to-determine-which-net-framework-updates-are-installed.md)

## <a name="features-that-simplify-deployment"></a><span data-ttu-id="c0a17-133">배포를 간소화하는 기능</span><span class="sxs-lookup"><span data-stu-id="c0a17-133">Features That Simplify Deployment</span></span>

<span data-ttu-id="c0a17-134">.NET Framework에서는 애플리케이션을 보다 쉽게 배포할 수 있게 해주는 다음과 같은 많은 기본 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c0a17-134">The .NET Framework provides a number of basic features that make it easier to deploy your applications:</span></span>

- <span data-ttu-id="c0a17-135">영향을 주지 않은 애플리케이션.</span><span class="sxs-lookup"><span data-stu-id="c0a17-135">No-impact applications.</span></span>

     <span data-ttu-id="c0a17-136">이 기능은 애플리케이션 격리를 제공하고 DLL 충돌을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="c0a17-136">This feature provides application isolation and eliminates DLL conflicts.</span></span> <span data-ttu-id="c0a17-137">기본적으로 구성 요소는 다른 애플리케이션에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c0a17-137">By default, components do not affect other applications.</span></span>

- <span data-ttu-id="c0a17-138">기본적으로 전용 구성 요소.</span><span class="sxs-lookup"><span data-stu-id="c0a17-138">Private components by default.</span></span>

     <span data-ttu-id="c0a17-139">기본적으로 구성 요소는 애플리케이션 디렉터리에 배포되며 포함하는 애플리케이션에만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0a17-139">By default, components are deployed to the application directory and are visible only to the containing application.</span></span>

- <span data-ttu-id="c0a17-140">제어된 코드 공유.</span><span class="sxs-lookup"><span data-stu-id="c0a17-140">Controlled code sharing.</span></span>

     <span data-ttu-id="c0a17-141">코드를 공유하려면 기본 동작 대신 코드를 공유할 수 있도록 명시적으로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0a17-141">Code sharing requires you to explicitly make code available for sharing instead of being the default behavior.</span></span>

- <span data-ttu-id="c0a17-142">Side-by-side 버전 관리.</span><span class="sxs-lookup"><span data-stu-id="c0a17-142">Side-by-side versioning.</span></span>

     <span data-ttu-id="c0a17-143">구성 요소 또는 애플리케이션의 여러 버전이 동시에 존재할 수 있으며, 사용할 버전을 선택하면 공용 언어 런타임에서 버전 관리 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="c0a17-143">Multiple versions of a component or application can coexist, you can choose which versions to use, and the common language runtime enforces versioning policy.</span></span>

- <span data-ttu-id="c0a17-144">XCOPY 배포 및 복제.</span><span class="sxs-lookup"><span data-stu-id="c0a17-144">XCOPY deployment and replication.</span></span>

     <span data-ttu-id="c0a17-145">레지스트리 항목이나 종속성 없이 자체 설명적 및 자체 포함된 구성 요소와 애플리케이션을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0a17-145">Self-described and self-contained components and applications can be deployed without registry entries or dependencies.</span></span>

- <span data-ttu-id="c0a17-146">즉시 업데이트.</span><span class="sxs-lookup"><span data-stu-id="c0a17-146">On-the-fly updates.</span></span>

     <span data-ttu-id="c0a17-147">관리자는 ASP.NET과 같은 호스트를 사용하여 원격 컴퓨터에서도 프로그램 Dll을 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0a17-147">Administrators can use hosts, such as ASP.NET, to update program DLLs, even on remote computers.</span></span>

- <span data-ttu-id="c0a17-148">Windows Installer와 통합.</span><span class="sxs-lookup"><span data-stu-id="c0a17-148">Integration with the Windows Installer.</span></span>

     <span data-ttu-id="c0a17-149">애플리케이션을 배포할 때 광고, 게시, 복구 및 요청 시 설치를 모두 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0a17-149">Advertisement, publishing, repair, and install-on-demand are all available when deploying your application.</span></span>

- <span data-ttu-id="c0a17-150">엔터프라이즈 배포</span><span class="sxs-lookup"><span data-stu-id="c0a17-150">Enterprise deployment.</span></span>

     <span data-ttu-id="c0a17-151">이 기능은 Active Directory 사용을 포함하여 소프트웨어를 쉽게 배포할 수 있게 해줍니다.</span><span class="sxs-lookup"><span data-stu-id="c0a17-151">This feature provides easy software distribution, including using Active Directory.</span></span>

- <span data-ttu-id="c0a17-152">다운로드 및 캐시.</span><span class="sxs-lookup"><span data-stu-id="c0a17-152">Downloading and caching.</span></span>

     <span data-ttu-id="c0a17-153">증분 다운로드를 통해 다운로드가 더 작게 유지되며, 배포 영향을 최소화하기 위해 애플리케이션에서만 사용하도록 구성 요소를 격리시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0a17-153">Incremental downloads keep downloads smaller, and components can be isolated for use only by the application for low-impact deployment.</span></span>

- <span data-ttu-id="c0a17-154">부분적으로 신뢰할 수 있는 코드.</span><span class="sxs-lookup"><span data-stu-id="c0a17-154">Partially trusted code.</span></span>

     <span data-ttu-id="c0a17-155">ID가 사용자 대신 코드를 기반으로 하며 인증서 대화 상자가 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c0a17-155">Identity is based on the code instead of the user, and no certificate dialog boxes appear.</span></span>

## <a name="packaging-and-distributing-net-framework-applications"></a><span data-ttu-id="c0a17-156">.NET Framework 애플리케이션 패키징 및 배포</span><span class="sxs-lookup"><span data-stu-id="c0a17-156">Packaging and Distributing .NET Framework Applications</span></span>

<span data-ttu-id="c0a17-157">.NET Framework에 대한 패키징 및 배포 정보 중 일부는 설명서의 다른 섹션에서 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c0a17-157">Some of the packaging and deployment information for the .NET Framework is described in other sections of the documentation.</span></span> <span data-ttu-id="c0a17-158">이러한 섹션에서는 레지스트리 항목이 필요 없는 [어셈블리](../../standard/assembly/index.md)라는 자체 설명적 단위, 이름 고유성을 유지하고 이름 스푸핑을 방지하는 [강력한 이름의 어셈블리](../../standard/assembly/strong-named.md) 및 DLL 충돌과 관련된 많은 문제를 해결하는 [어셈블리 버전 관리](../../standard/assembly/versioning.md)에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c0a17-158">Those sections provide information about the self-describing units called [assemblies](../../standard/assembly/index.md), which require no registry entries, [strong-named assemblies](../../standard/assembly/strong-named.md), which ensure name uniqueness and prevent name spoofing, and [assembly versioning](../../standard/assembly/versioning.md), which addresses many of the problems associated with DLL conflicts.</span></span> <span data-ttu-id="c0a17-159">다음 섹션에서는 .NET Framework 애플리케이션 패키징 및 배포에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c0a17-159">The following sections provide information about packaging and distributing .NET Framework applications.</span></span>

### <a name="packaging"></a><span data-ttu-id="c0a17-160">패키지</span><span class="sxs-lookup"><span data-stu-id="c0a17-160">Packaging</span></span>

<span data-ttu-id="c0a17-161">.NET Framework는 다음과 같은 애플리케이션 패키징 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c0a17-161">The .NET Framework provides the following options for packaging applications:</span></span>

- <span data-ttu-id="c0a17-162">단일 어셈블리 또는 어셈블리 컬렉션으로.</span><span class="sxs-lookup"><span data-stu-id="c0a17-162">As a single assembly or as a collection of assemblies.</span></span>

     <span data-ttu-id="c0a17-163">이 옵션을 사용하는 경우 빌드된 .dll 또는 .exe 파일을 사용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0a17-163">With this option, you simply use the .dll or .exe files as they were built.</span></span>

- <span data-ttu-id="c0a17-164">캐비닛(CAB) 파일로.</span><span class="sxs-lookup"><span data-stu-id="c0a17-164">As cabinet (CAB) files.</span></span>

     <span data-ttu-id="c0a17-165">이 옵션을 사용하는 경우 파일을 .cab 파일로 압축하여 배포 또는 다운로드 시간을 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="c0a17-165">With this option, you compress files into .cab files to make distribution or download less time consuming.</span></span>

- <span data-ttu-id="c0a17-166">Windows Installer 패키지 또는 다른 설치 관리자 형식으로.</span><span class="sxs-lookup"><span data-stu-id="c0a17-166">As a Windows Installer package or in other installer formats.</span></span>

     <span data-ttu-id="c0a17-167">이 옵션을 사용하는 경우 Windows Installer에서 사용할 .msi 파일을 만들거나 다른 설치 관리자에서 사용하기 위해 애플리케이션을 패키징합니다.</span><span class="sxs-lookup"><span data-stu-id="c0a17-167">With this option, you create .msi files for use with the Windows Installer, or you package your application for use with some other installer.</span></span>

### <a name="distribution"></a><span data-ttu-id="c0a17-168">분포</span><span class="sxs-lookup"><span data-stu-id="c0a17-168">Distribution</span></span>

<span data-ttu-id="c0a17-169">.NET Framework는 다음과 같은 애플리케이션 배포 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c0a17-169">The .NET Framework provides the following options for distributing applications:</span></span>

- <span data-ttu-id="c0a17-170">XCOPY 또는 FTP 사용.</span><span class="sxs-lookup"><span data-stu-id="c0a17-170">Use XCOPY or FTP.</span></span>

     <span data-ttu-id="c0a17-171">공용 언어 런타임 애플리케이션은 자체 설명적이며 레지스트리 항목이 필요하지 않으므로 XCOPY 또는 FTP를 사용하여 애플리케이션을 해당 디렉터리에 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0a17-171">Because common language runtime applications are self-describing and require no registry entries, you can use XCOPY or FTP to simply copy the application to an appropriate directory.</span></span> <span data-ttu-id="c0a17-172">그런 다음 해당 디렉터리에서 애플리케이션을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0a17-172">The application can then be run from that directory.</span></span>

- <span data-ttu-id="c0a17-173">코드 다운로드 사용.</span><span class="sxs-lookup"><span data-stu-id="c0a17-173">Use code download.</span></span>

     <span data-ttu-id="c0a17-174">인터넷이나 회사 인트라넷을 통해 애플리케이션을 배포하는 경우 코드를 컴퓨터로 다운로드하고 여기서 애플리케이션을 실행하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0a17-174">If you are distributing your application over the Internet or through a corporate intranet, you can simply download the code to a computer and run the application there.</span></span>

- <span data-ttu-id="c0a17-175">Windows Installer 2.0과 같은 설치 관리자 프로그램 사용.</span><span class="sxs-lookup"><span data-stu-id="c0a17-175">Use an installer program such as Windows Installer 2.0.</span></span>

     <span data-ttu-id="c0a17-176">Windows Installer 2.0은 전역 어셈블리 캐시와 전용 디렉터리에서 .NET Framework 어셈블리를 설치, 복구 또는 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0a17-176">Windows Installer 2.0 can install, repair, or remove .NET Framework assemblies in the global assembly cache and in private directories.</span></span>

### <a name="installation-location"></a><span data-ttu-id="c0a17-177">설치 위치</span><span class="sxs-lookup"><span data-stu-id="c0a17-177">Installation Location</span></span>

<span data-ttu-id="c0a17-178">런타임에서 찾을 수 있도록 애플리케이션의 어셈블리를 배포할 위치를 확인하려면 [런타임에서 어셈블리를 찾는 방법](how-the-runtime-locates-assemblies.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c0a17-178">To determine where to deploy your application's assemblies so they can be found by the runtime, see [How the Runtime Locates Assemblies](how-the-runtime-locates-assemblies.md).</span></span>

<span data-ttu-id="c0a17-179">보안 고려 사항도 애플리케이션 배포 방법에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0a17-179">Security considerations can also affect how you deploy your application.</span></span> <span data-ttu-id="c0a17-180">코드의 위치에 따라 관리 코드에 보안 권한이 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0a17-180">Security permissions are granted to managed code according to where the code is located.</span></span> <span data-ttu-id="c0a17-181">인터넷과 같은 거의 신뢰되지 않는 위치에 애플리케이션이나 구성 요소를 배포하면 애플리케이션이나 구성 요소가 수행할 수 있는 기능이 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0a17-181">Deploying an application or component to a location where it receives little trust, such as the Internet, limits what the application or component can do.</span></span> <span data-ttu-id="c0a17-182">배포 및 보안 고려 사항에 대한 자세한 내용은 [코드 액세스 보안 기본 사항](../misc/code-access-security-basics.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c0a17-182">For more information about deployment and security considerations, see [Code Access Security Basics](../misc/code-access-security-basics.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="c0a17-183">관련 항목</span><span class="sxs-lookup"><span data-stu-id="c0a17-183">Related Topics</span></span>

|<span data-ttu-id="c0a17-184">제목</span><span class="sxs-lookup"><span data-stu-id="c0a17-184">Title</span></span>|<span data-ttu-id="c0a17-185">설명</span><span class="sxs-lookup"><span data-stu-id="c0a17-185">Description</span></span>|
|-----------|-----------------|
|[<span data-ttu-id="c0a17-186">런타임에서 어셈블리를 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="c0a17-186">How the Runtime Locates Assemblies</span></span>](how-the-runtime-locates-assemblies.md)|<span data-ttu-id="c0a17-187">공용 언어 런타임에서 바인딩 요청을 충족하는 데 사용할 어셈블리를 확인하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c0a17-187">Describes how the common language runtime determines which assembly to use to fulfill a binding request.</span></span>|
|[<span data-ttu-id="c0a17-188">최선의 어셈블리 로드 방법</span><span class="sxs-lookup"><span data-stu-id="c0a17-188">Best Practices for Assembly Loading</span></span>](best-practices-for-assembly-loading.md)|<span data-ttu-id="c0a17-189"><xref:System.InvalidCastException>, <xref:System.MissingMethodException> 및 다른 오류를 발생시킬 수 있는 형식 ID 문제를 방지하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c0a17-189">Discusses ways to avoid problems of type identity that can lead to <xref:System.InvalidCastException>, <xref:System.MissingMethodException>, and other errors.</span></span>|
|[<span data-ttu-id="c0a17-190">.NET Framework 4.5를 설치하는 동안 시스템 다시 시작 줄이기</span><span class="sxs-lookup"><span data-stu-id="c0a17-190">Reducing System Restarts During .NET Framework 4.5 Installations</span></span>](reducing-system-restarts.md)|<span data-ttu-id="c0a17-191">최대한 다시 시작을 방지하는 다시 시작 관리자 및 .NET Framework를 설치하는 애플리케이션이 다시 시작 관리자를 활용할 수 있는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c0a17-191">Describes the Restart Manager, which prevents reboots whenever possible, and explains how applications that install the .NET Framework can take advantage of it.</span></span>|
|[<span data-ttu-id="c0a17-192">관리자를 위한 배포 가이드</span><span class="sxs-lookup"><span data-stu-id="c0a17-192">Deployment Guide for Administrators</span></span>](guide-for-administrators.md)|<span data-ttu-id="c0a17-193">시스템 관리자가 Microsoft Endpoint Configuration Manager를 사용하여 .NET Framework 및 해당 시스템 종속성을 네트워크 전체에 배포할 수 있는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c0a17-193">Explains how a system administrator can deploy the .NET Framework and its system dependencies across a network by using Microsoft Endpoint Configuration Manager.</span></span>|
|[<span data-ttu-id="c0a17-194">개발자를 위한 배포 가이드</span><span class="sxs-lookup"><span data-stu-id="c0a17-194">Deployment Guide for Developers</span></span>](deployment-guide-for-developers.md)|<span data-ttu-id="c0a17-195">개발자가 애플리케이션과 함께 .NET Framework를 사용자 컴퓨터에 설치할 수 있는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c0a17-195">Explains how developers can install .NET Framework on their users' computers with their applications.</span></span>|
|[<span data-ttu-id="c0a17-196">애플리케이션, 서비스 및 구성 요소 배포</span><span class="sxs-lookup"><span data-stu-id="c0a17-196">Deploying Applications, Services, and Components</span></span>](/visualstudio/deployment/deploying-applications-services-and-components)|<span data-ttu-id="c0a17-197">ClickOnce 및 Windows Installer 기술을 사용하여 애플리케이션을 게시하기 위한 지침을 포함하여 Visual Studio의 배포 옵션을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c0a17-197">Discusses deployment options in Visual Studio, including instructions for publishing an application using the ClickOnce and Windows Installer technologies.</span></span>|
|[<span data-ttu-id="c0a17-198">ClickOnce 애플리케이션 게시</span><span class="sxs-lookup"><span data-stu-id="c0a17-198">Publishing ClickOnce Applications</span></span>](/visualstudio/deployment/publishing-clickonce-applications)|<span data-ttu-id="c0a17-199">Windows Forms 애플리케이션을 패키징하고 ClickOnce로 네트워크의 클라이언트 컴퓨터에 배포하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c0a17-199">Describes how to package a Windows Forms application and deploy it with ClickOnce to client computers on a network.</span></span>|
|[<span data-ttu-id="c0a17-200">리소스 패키징 및 배포</span><span class="sxs-lookup"><span data-stu-id="c0a17-200">Packaging and Deploying Resources</span></span>](../resources/packaging-and-deploying-resources-in-desktop-apps.md)|<span data-ttu-id="c0a17-201">.NET Framework에서 리소스를 패키징 및 배포하는 데 사용하는 허브 및 스포크 모델을 설명합니다. 리소스 명명 규칙, 대체(fallback) 프로세스 및 패키징 대안을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c0a17-201">Describes the hub and spoke model that the .NET Framework uses to package and deploy resources; covers resource naming conventions, fallback process, and packaging alternatives.</span></span>|
|[<span data-ttu-id="c0a17-202">Interop 애플리케이션 배포</span><span class="sxs-lookup"><span data-stu-id="c0a17-202">Deploying an Interop Application</span></span>](../interop/deploying-an-interop-application.md)|<span data-ttu-id="c0a17-203">일반적으로 .NET Framework 클라이언트 어셈블리, 고유한 COM 형식 라이브러리를 나타내는 하나 이상의 interop 어셈블리 및 하나 이상의 등록된 COM 구성 요소를 포함하는 interop 애플리케이션을 제공하고 설치하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c0a17-203">Explains how to ship and install interop applications, which typically include a .NET Framework client assembly, one or more interop assemblies representing distinct COM type libraries, and one or more registered COM components.</span></span>|
|[<span data-ttu-id="c0a17-204">방법: .NET Framework 4.5 설치 관리자에서 진행률 가져오기</span><span class="sxs-lookup"><span data-stu-id="c0a17-204">How to: Get Progress from the .NET Framework 4.5 Installer</span></span>](how-to-get-progress-from-the-dotnet-installer.md)|<span data-ttu-id="c0a17-205">설치 진행 상황을 자체적으로 표시하면서 .NET Framework 설치 프로세스를 자동으로 시작하고 추적하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c0a17-205">Describes how to silently launch and track the .NET Framework setup process while showing your own view of the setup progress.</span></span>|

## <a name="see-also"></a><span data-ttu-id="c0a17-206">참조</span><span class="sxs-lookup"><span data-stu-id="c0a17-206">See also</span></span>

- [<span data-ttu-id="c0a17-207">개발 가이드</span><span class="sxs-lookup"><span data-stu-id="c0a17-207">Development Guide</span></span>](../development-guide.md)
