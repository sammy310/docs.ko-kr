---
title: macOS Catalina 공증 관련 사항
description: .NET Core로 빌드된 .NET Core 런타임, SDK 및 앱을 설치할 때 macOS의 공증 및 인증 문제를 처리하는 방법.
author: adegeo
ms.author: adegeo
ms.date: 02/14/2020
ms.openlocfilehash: cd3886b2e772a182156d212aefb9705a3fb5e17c
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324625"
---
# <a name="macos-catalina-notarization-and-the-impact-on-net-core-downloads-and-projects"></a><span data-ttu-id="5500b-103">macOS Catalina 공증과 이것이 .NET Core 다운로드 및 프로젝트에 미치는 영향</span><span class="sxs-lookup"><span data-stu-id="5500b-103">macOS Catalina Notarization and the impact on .NET Core downloads and projects</span></span>

<span data-ttu-id="5500b-104">macOS Catalina(버전10.15)부터, 2019년 6월 1일 이후에 빌드되어 개발자 ID로 배포되는 모든 소프트웨어는 공증을 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5500b-104">Beginning with macOS Catalina (version 10.15), all software built after June 1, 2019, and distributed with Developer ID, must be notarized.</span></span> <span data-ttu-id="5500b-105">이 요구 사항은 .NET Core 런타임, .NET Core SDK, 그리고 .NET Core로 만든 소프트웨어에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5500b-105">This requirement applies to the .NET Core runtime, .NET Core SDK, and software created with .NET Core.</span></span> <span data-ttu-id="5500b-106">이 문서에서는 .NET Core 및 macOS 공증과 관련하여 자주 발생하는 시나리오에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5500b-106">This article describes the common scenarios you may face with .NET Core and macOS notarization.</span></span>

## <a name="installing-net-core"></a><span data-ttu-id="5500b-107">.NET Core 설치</span><span class="sxs-lookup"><span data-stu-id="5500b-107">Installing .NET Core</span></span>

<span data-ttu-id="5500b-108">.NET Core(런타임 및 SDK) 버전 3.1, 3.0, 2.1용 설치 프로그램은 2020년 2월 18일부터 공증되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5500b-108">The installers for .NET Core (both runtime and SDK) versions 3.1, 3.0, and 2.1, have been notarized since February 18, 2020.</span></span> <span data-ttu-id="5500b-109">그 전에 릴리스된 버전은 공증되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="5500b-109">Prior released versions aren't notarized.</span></span> <span data-ttu-id="5500b-110">공증되지 않은 버전의 .NET Core는 먼저 설치 프로그램을 다운로드한 다음 `sudo installer` 명령을 사용하여 수동으로 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5500b-110">You can manually install a non-notarized version of .NET Core by first downloading the installer, and then using the `sudo installer` command.</span></span> <span data-ttu-id="5500b-111">자세한 내용은 [Download and manually install for macOS](sdk.md?pivots=os-macos#download-and-manually-install)(macOS에 대해 다운로드 및 수동 설치)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5500b-111">For more information, see [Download and manually install for macOS](sdk.md?pivots=os-macos#download-and-manually-install).</span></span>

<span data-ttu-id="5500b-112">아래의 버전부터는 .NET Core 설치 프로그램이 공증됩니다.</span><span class="sxs-lookup"><span data-stu-id="5500b-112">Beginning with the following versions, the .NET Core installers are notarized:</span></span>

- <span data-ttu-id="5500b-113">.NET Core 런타임</span><span class="sxs-lookup"><span data-stu-id="5500b-113">.NET Core Runtime</span></span>
  - <span data-ttu-id="5500b-114">2.1.16</span><span class="sxs-lookup"><span data-stu-id="5500b-114">2.1.16</span></span>
  - <span data-ttu-id="5500b-115">3.0.3</span><span class="sxs-lookup"><span data-stu-id="5500b-115">3.0.3</span></span>
  - <span data-ttu-id="5500b-116">3.1.2</span><span class="sxs-lookup"><span data-stu-id="5500b-116">3.1.2</span></span>

- <span data-ttu-id="5500b-117">.NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="5500b-117">.NET Core SDK</span></span>
  - <span data-ttu-id="5500b-118">2.1.512</span><span class="sxs-lookup"><span data-stu-id="5500b-118">2.1.512</span></span>
  - <span data-ttu-id="5500b-119">3.0.103</span><span class="sxs-lookup"><span data-stu-id="5500b-119">3.0.103</span></span>
  - <span data-ttu-id="5500b-120">3.1.102</span><span class="sxs-lookup"><span data-stu-id="5500b-120">3.1.102</span></span>

## <a name="apphost-is-disabled-by-default"></a><span data-ttu-id="5500b-121">appHost는 기본적으로 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="5500b-121">appHost is disabled by default</span></span>

<span data-ttu-id="5500b-122">기본적으로, .NET Core SDK 3.0 이상의 공증되지 않은 버전은 프로젝트가 컴파일, 게시 또는 실행되면 네이티브 Mach-O 실행 파일(**appHost**)을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="5500b-122">By default, non-notarized versions of the .NET Core SDK 3.0 and above produce a native Mach-O executable (known as the **appHost**) when your project compiles, publishes, or is run.</span></span> <span data-ttu-id="5500b-123">이 실행 파일은 앱을 편리하게 실행하는 한 가지 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="5500b-123">This executable is a convenient way to run your app.</span></span> <span data-ttu-id="5500b-124">이 실행 파일을 사용하지 않고 앱을 시작하려면 `dotnet <filename.dll>`을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5500b-124">Otherwise, your app must be started by running `dotnet <filename.dll>`.</span></span> <span data-ttu-id="5500b-125">appHost가 사용하도록 설정되면 `dotnet run` 명령이 appHost의 컨텍스트에서 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="5500b-125">When the appHost is enabled, the `dotnet run` command is invoked in the context of the appHost.</span></span> <span data-ttu-id="5500b-126">자세한 내용은 [appHost의 컨텍스트](#context-of-the-apphost)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5500b-126">For more information, see [Context of the appHost](#context-of-the-apphost).</span></span>

<span data-ttu-id="5500b-127">.NET Core SDK 3.0 이상의 공증된 버전부터, appHost 실행 파일이 기본적으로 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5500b-127">Starting with the notarized versions of the .NET Core SDK 3.0 and above, the appHost executable isn't generated by default.</span></span> <span data-ttu-id="5500b-128">프로젝트 파일의 [`UseAppHost`](../project-sdk/msbuild-props.md#useapphost) 부울 설정을 사용하여 appHost가 생성되도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5500b-128">You can turn on appHost generation with the [`UseAppHost`](../project-sdk/msbuild-props.md#useapphost) boolean setting in the project file.</span></span> <span data-ttu-id="5500b-129">명령줄에서 `-p:UseAppHost` 매개 변수를 사용하여 실행하는 특정 `dotnet` 명령에 대해 appHost를 켜거나 끌 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5500b-129">You can also toggle the appHost with the `-p:UseAppHost` parameter on the command line for the specific `dotnet` command you run:</span></span>

- <span data-ttu-id="5500b-130">프로젝트 파일</span><span class="sxs-lookup"><span data-stu-id="5500b-130">Project file</span></span>

  ```xml
  <PropertyGroup>
    <UseAppHost>true</UseAppHost>
  </PropertyGroup>
  ```

- <span data-ttu-id="5500b-131">명령줄 매개 변수</span><span class="sxs-lookup"><span data-stu-id="5500b-131">Command-line parameter</span></span>

  ```dotnetcli
  dotnet run -p:UseAppHost=true
  ```

<span data-ttu-id="5500b-132">appHost는 앱을 [자체 포함](../deploying/index.md#publish-self-contained) 방식으로 게시하면 항상 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="5500b-132">An appHost is always created when you publish your app [self-contained](../deploying/index.md#publish-self-contained).</span></span>

<span data-ttu-id="5500b-133">`UseAppHost` 설정에 대한 자세한 내용은 [MSBuild properties for Microsoft.NET.Sdk](../project-sdk/msbuild-props.md#useapphost)(Microsoft.NET.Sdk의 MSBuild 속성)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5500b-133">For more information about the `UseAppHost` setting, see [MSBuild properties for Microsoft.NET.Sdk](../project-sdk/msbuild-props.md#useapphost).</span></span>

### <a name="context-of-the-apphost"></a><span data-ttu-id="5500b-134">appHost의 컨텍스트</span><span class="sxs-lookup"><span data-stu-id="5500b-134">Context of the appHost</span></span>

<span data-ttu-id="5500b-135">프로젝트에서 appHost가 사용하도록 설정된 상태에서 `dotnet run` 명령을 사용하여 앱을 실행하면 앱이 기본 호스트(기본 호스트는 `dotnet` 명령임)가 아닌 appHost의 컨텍스트에서 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="5500b-135">When the appHost is enabled in your project, and you use the `dotnet run` command to run your app, the app is invoked in the context of the appHost and not the default host (the default host is the `dotnet` command).</span></span> <span data-ttu-id="5500b-136">프로젝트에서 appHost를 사용하지 않도록 설정된 경우 `dotnet run` 명령이 기본 호스트의 컨텍스트에서 앱을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="5500b-136">If the appHost is disabled in your project, the `dotnet run` command runs your app in the context of the default host.</span></span> <span data-ttu-id="5500b-137">appHost를 사용하지 않도록 설정된 경우에도 앱을 자체 포함 방식으로 게시하면 appHost 실행 파일이 생성되고, 사용자가 해당 실행 파일을 사용하여 앱을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5500b-137">Even if the appHost is disabled, publishing your app as self-contained generates an appHost executable, and users use that executable to run your app.</span></span> <span data-ttu-id="5500b-138">`dotnet <filename.dll>`을 사용하여 앱을 실행하면 기본 호스트인 공유 런타임으로 앱이 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="5500b-138">Running your app with `dotnet <filename.dll>` invokes the app with the default host, the shared runtime.</span></span>

<span data-ttu-id="5500b-139">appHost를 사용하는 앱이 호출될 경우, 앱에서 액세스하는 인증서 파티션은 공증된 기본 호스트와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="5500b-139">When an app using the appHost is invoked, the certificate partition accessed by the app is different from the notarized default host.</span></span> <span data-ttu-id="5500b-140">앱에서 기본 호스트를 통해 설치된 인증서에 액세스해야 하는 경우, `dotnet run` 명령을 사용하여 앱을 프로젝트 파일에서 실행하거나 `dotnet <filename.dll>` 명령을 사용하여 앱을 직접 시작하세요.</span><span class="sxs-lookup"><span data-stu-id="5500b-140">If your app must access the certificates installed through the default host, use the `dotnet run` command to run your app from its project file, or use the `dotnet <filename.dll>` command to start the app directly.</span></span>

<span data-ttu-id="5500b-141">[ASP.NET Core 및 macOS와 인증서](#aspnet-core-and-macos-and-certificates) 섹션에서 이 시나리오에 대한 자세한 내용을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5500b-141">More information about this scenario is provided in the [ASP.NET Core and macOS and certificates](#aspnet-core-and-macos-and-certificates) section.</span></span>

## <a name="aspnet-core-and-macos-and-certificates"></a><span data-ttu-id="5500b-142">ASP.NET Core 및 macOS와 인증서</span><span class="sxs-lookup"><span data-stu-id="5500b-142">ASP.NET Core and macOS and certificates</span></span>

<span data-ttu-id="5500b-143">.NET Core는 macOS 키체인에서 <xref:System.Security.Cryptography.X509Certificates> 클래스로 인증서를 관리하는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5500b-143">.NET Core provides the ability to manage certificates in the macOS Keychain with the <xref:System.Security.Cryptography.X509Certificates> class.</span></span> <span data-ttu-id="5500b-144">macOS 키체인에 대한 액세스에서는 어느 파티션을 고려해야 할지 결정할 때 애플리케이션 ID를 기본 키로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5500b-144">Access to the macOS Keychain uses the applications identity as the primary key when deciding which partition to consider.</span></span> <span data-ttu-id="5500b-145">예를 들어, 서명되지 않은 애플리케이션은 비밀을 서명되지 않은 파티션에 저장하지만, 서명된 애플리케이션은 비밀을 해당 애플리케이션에서만 액세스할 수 있는 파티션에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="5500b-145">For example, unsigned applications store secrets in the unsigned partition, but signed applications store their secrets in partitions only they can access.</span></span> <span data-ttu-id="5500b-146">앱을 호출하는 실행 파일의 소스가 어느 파티션을 사용할지를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="5500b-146">The source of execution that invokes your app decides which partition to use.</span></span>

<span data-ttu-id="5500b-147">.NET Core는 [appHost](#apphost-is-disabled-by-default), 기본 호스트(`dotnet` 명령), 사용자 지정 호스트와 같은 3가지 소스의 실행을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5500b-147">.NET Core provides three sources of execution: [appHost](#apphost-is-disabled-by-default), default host (the `dotnet` command), and a custom host.</span></span> <span data-ttu-id="5500b-148">각 실행 모델에는 서명되었거나 서명되지 않은 서로 다른 ID를 가질 수 있으며, 키체인 내의 서로 다른 파티션에 대한 액세스를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="5500b-148">Each execution model may have different identities, either signed or unsigned, and has access to different partitions within the Keychain.</span></span> <span data-ttu-id="5500b-149">하나의 모드로 가져온 인증서는 다른 모드에서 액세스하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5500b-149">Certificates imported by one mode may not be accessible from another.</span></span> <span data-ttu-id="5500b-150">예를 들어, .NET Core의 공증된 버전에는 서명된 기본 호스트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5500b-150">For example, the notarized versions of .NET Core have a default host that is signed.</span></span> <span data-ttu-id="5500b-151">인증서는 그 ID에 따라 보안 파티션으로 가져와집니다.</span><span class="sxs-lookup"><span data-stu-id="5500b-151">Certificates are imported into a secure partition based on its identity.</span></span> <span data-ttu-id="5500b-152">appHost는 서명되지 않았으므로 appHost에서 이러한 인증서에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5500b-152">These certificates aren't accessible from a generated appHost, as the appHost is unsigned.</span></span>

<span data-ttu-id="5500b-153">또 다른 예로, 기본적으로 ASP.NET Core는 기본 호스트를 통해 기본 SSL 인증서를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5500b-153">Another example, by default, ASP.NET Core imports a default SSL certificate through the default host.</span></span> <span data-ttu-id="5500b-154">appHost를 사용하는 ASP.NET Core 애플리케이션은 이 인증서에 액세스할 수 없으며, .NET Core에서 이 인증서에 액세스할 수 없다는 사실을 감지하면 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="5500b-154">ASP.NET Core applications that use an appHost won't have access to this certificate and will receive an error when .NET Core detects the certificate isn't accessible.</span></span> <span data-ttu-id="5500b-155">오류 메시지는 이 문제를 해결하는 방법에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5500b-155">The error message provides instructions on how to fix this problem.</span></span>

<span data-ttu-id="5500b-156">인증서 공유가 필요한 경우, macOS는 `security` 유틸리티를 통해 구성 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5500b-156">If certificate sharing is required, macOS provides configuration options with the `security` utility.</span></span>

<span data-ttu-id="5500b-157">ASP.NET Core 인증서 문제를 해결하는 방법에 대한 자세한 내용은 [Enforce HTTPS in ASP.NET Core](/aspnet/core/security/enforcing-ssl?view=aspnetcore-3.1&tabs=visual-studio#troubleshoot-certificate-problems)(ASP.NET Core에서 HTTPS 강제 적용)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5500b-157">For more information on how to troubleshoot ASP.NET Core certificate issues, see [Enforce HTTPS in ASP.NET Core](/aspnet/core/security/enforcing-ssl?view=aspnetcore-3.1&tabs=visual-studio#troubleshoot-certificate-problems).</span></span>

## <a name="default-entitlements"></a><span data-ttu-id="5500b-158">기본 자격</span><span class="sxs-lookup"><span data-stu-id="5500b-158">Default entitlements</span></span>

<span data-ttu-id="5500b-159">.NET Core의 기본 호스트(`dotnet` 명령)는 기본 자격 집합을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="5500b-159">.NET Core’s default host (the `dotnet` command) has a set of default entitlements.</span></span> <span data-ttu-id="5500b-160">이러한 자격은 .NET Core가 올바르게 작동하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5500b-160">These entitlements are required for proper operation of .NET Core.</span></span> <span data-ttu-id="5500b-161">애플리케이션에 그 밖의 자격이 필요한 경우가 있는데, 이 경우 [appHost](#apphost-is-disabled-by-default)를 생성하여 사용한 다음 로컬에서 필수 자격을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5500b-161">It's possible that your application may need additional entitlements, in which case you'll need to generate and use an [appHost](#apphost-is-disabled-by-default) and then add the necessary entitlements locally.</span></span>

<span data-ttu-id="5500b-162">.NET Core의 기본 자격 집합</span><span class="sxs-lookup"><span data-stu-id="5500b-162">Default set of entitlements for .NET Core:</span></span>

- `com.apple.security.cs.allow-jit`
- `com.apple.security.cs.allow-unsigned-executable-memory`
- `com.apple.security.cs.allow-dyld-environment-variables`
- `com.apple.security.cs.disable-library-validation`

## <a name="notarize-a-net-core-app"></a><span data-ttu-id="5500b-163">.NET Core 앱 공증하기</span><span class="sxs-lookup"><span data-stu-id="5500b-163">Notarize a .NET Core app</span></span>

<span data-ttu-id="5500b-164">애플리케이션을 macOS Catalina(버전 10.15) 이상에서 실행하려면 앱을 공증해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5500b-164">If you want your application to run on macOS Catalina (version 10.15) or higher, you'll want to notarize your app.</span></span> <span data-ttu-id="5500b-165">공증을 위해 애플리케이션과 함께 제출하는 appHost에는 .NET Core의 [기본 자격](#default-entitlements)과 같거나 높은 기본 자격을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5500b-165">The appHost you submit with your application for notarization should be used with at least the same [default entitlements](#default-entitlements) for .NET Core.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5500b-166">다음 단계</span><span class="sxs-lookup"><span data-stu-id="5500b-166">Next steps</span></span>

- <span data-ttu-id="5500b-167">[..NET Core 종속성 및 요구 사항](dependencies.md)</span><span class="sxs-lookup"><span data-stu-id="5500b-167">[.NET Core dependencies and requirements](dependencies.md).</span></span>
- <span data-ttu-id="5500b-168">[Install the .NET Core SDK](sdk.md)(.NET Core SDK 설치)</span><span class="sxs-lookup"><span data-stu-id="5500b-168">[Install the .NET Core SDK](sdk.md).</span></span>
- [<span data-ttu-id="5500b-169">.NET Core 런타임 설치</span><span class="sxs-lookup"><span data-stu-id="5500b-169">Install the .NET Core Runtime</span></span>](runtime.md)
