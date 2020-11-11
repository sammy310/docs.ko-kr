---
title: .NET Framework의 새로운 기능
description: .NET Framework의 다양한 버전에서 제공되는 새로운 기능을 참조하세요. 각 버전의 주요 새로운 기능 및 향상된 기능에 대한 요약을 확인하세요.
ms.date: 10/21/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- what's new [.NET Framework]
ms.assetid: 1d971dd7-10fc-4692-8dac-30ca308fc0fa
ms.openlocfilehash: da0e92f394507a37b0b6c163b41a575abc1c1a2b
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2020
ms.locfileid: "94441111"
---
# <a name="whats-new-in-net-framework"></a><span data-ttu-id="9bae0-104">.NET Framework의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="9bae0-104">What's new in .NET Framework</span></span>

[!INCLUDE [net-framework-future](../../../includes/net-framework-future.md)]

<span data-ttu-id="9bae0-105">이 문서에서는 다음 버전의 .NET Framework에 새로 추가된 주요 기능과 향상된 내용을 요약합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-105">This article summarizes key new features and improvements in the following versions of .NET Framework:</span></span>

- [<span data-ttu-id="9bae0-106">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="9bae0-106">.NET Framework 4.8</span></span>](#v48)
- [<span data-ttu-id="9bae0-107">.NET Framework 4.7.2</span><span class="sxs-lookup"><span data-stu-id="9bae0-107">.NET Framework 4.7.2</span></span>](#v472)
- [<span data-ttu-id="9bae0-108">.NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="9bae0-108">.NET Framework 4.7.1</span></span>](#v471)
- [<span data-ttu-id="9bae0-109">.NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="9bae0-109">.NET Framework 4.7</span></span>](#v47)
- [<span data-ttu-id="9bae0-110">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="9bae0-110">.NET Framework 4.6.2</span></span>](#v462)
- [<span data-ttu-id="9bae0-111">.NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="9bae0-111">.NET Framework 4.6.1</span></span>](#v461)
- [<span data-ttu-id="9bae0-112">.NET 2015 및 .NET Framework 4.6</span><span class="sxs-lookup"><span data-stu-id="9bae0-112">.NET 2015 and .NET Framework 4.6</span></span>](#v46)
- [<span data-ttu-id="9bae0-113">.NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="9bae0-113">.NET Framework 4.5.2</span></span>](#v452)
- [<span data-ttu-id="9bae0-114">.NET Framework 4.5.1</span><span class="sxs-lookup"><span data-stu-id="9bae0-114">.NET Framework 4.5.1</span></span>](#v451)
- [<span data-ttu-id="9bae0-115">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="9bae0-115">.NET Framework 4.5</span></span>](#v45)

<span data-ttu-id="9bae0-116">이 문서는 각 새로운 기능에 대한 포괄적인 정보를 제공하지 않으며 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-116">This article does not provide comprehensive information about each new feature and is subject to change.</span></span> <span data-ttu-id="9bae0-117">.NET Framework에 대한 일반적인 내용은 [시작](../get-started/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bae0-117">For general information about .NET Framework, see [Getting Started](../get-started/index.md).</span></span> <span data-ttu-id="9bae0-118">지원되는 플랫폼은 [시스템 요구 사항](../get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9bae0-118">For supported platforms, see [System Requirements](../get-started/system-requirements.md).</span></span> <span data-ttu-id="9bae0-119">다운로드 링크와 설치 지침은 [설치 가이드](../install/guide-for-developers.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9bae0-119">For download links and installation instructions, see [Installation Guide](../install/guide-for-developers.md).</span></span>

> [!NOTE]
> <span data-ttu-id="9bae0-120">.NET Framework 팀에서는 플랫폼 지원을 확장하고 새로운 기능(예: 변경할 수 없는 컬렉션 및 SIMD 사용 벡터 형식)을 도입하기 위한 NuGet을 사용하는 번외 기능도 릴리스했습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-120">The .NET Framework team also releases features out of band, using NuGet, to expand platform support and introduce new functionality, such as immutable collections and SIMD-enabled vector types.</span></span> <span data-ttu-id="9bae0-121">자세한 내용은 [추가 클래스 라이브러리 및 API](../additional-apis/index.md) 및 [.NET Framework 및 번외 릴리스](../get-started/the-net-framework-and-out-of-band-releases.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bae0-121">For more information, see [Additional Class Libraries and APIs](../additional-apis/index.md) and [.NET Framework and Out-of-Band Releases](../get-started/the-net-framework-and-out-of-band-releases.md).</span></span>
> <span data-ttu-id="9bae0-122">.NET Framework에 대해서는 [NuGet 패키지의 전체 목록](https://www.nuget.org/profiles/dotnetframework)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bae0-122">See a [complete list of NuGet packages](https://www.nuget.org/profiles/dotnetframework) for .NET Framework.</span></span>

<a name="v48"></a>

## <a name="introducing-net-framework-48"></a><span data-ttu-id="9bae0-123">.NET Framework 4.8 소개</span><span class="sxs-lookup"><span data-stu-id="9bae0-123">Introducing .NET Framework 4.8</span></span>

<span data-ttu-id="9bae0-124">.NET Framework 4.8은 .NET Framework 4.x의 이전 버전에서 빌드되며 제품의 안정성을 유지하면서 많은 새로운 수정 사항 및 여러 가지 새 기능이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-124">.NET Framework 4.8 builds on previous versions of .NET Framework 4.x by adding many new fixes and several new features while remaining a very stable product.</span></span>

### <a name="download-and-install-net-framework-48"></a><span data-ttu-id="9bae0-125">.NET Framework 4.8 다운로드 및 설치</span><span class="sxs-lookup"><span data-stu-id="9bae0-125">Download and install .NET Framework 4.8</span></span>

<span data-ttu-id="9bae0-126">다음 위치에서 .NET Framework 4.8을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-126">You can download .NET Framework 4.8 from the following locations:</span></span>

- [<span data-ttu-id="9bae0-127">.NET Framework 4.8 웹 설치 관리자</span><span class="sxs-lookup"><span data-stu-id="9bae0-127">.NET Framework 4.8 Web Installer</span></span>](https://dotnet.microsoft.com/download/dotnet-framework/net48)

- [<span data-ttu-id="9bae0-128">.NET Framework 4.8 오프라인 설치 관리자</span><span class="sxs-lookup"><span data-stu-id="9bae0-128">NET Framework 4.8 Offline Installer</span></span>](https://dotnet.microsoft.com/download/dotnet-framework/net48)

<span data-ttu-id="9bae0-129">.NET Framework 4.8은 Windows 10, Windows 8.1, Windows 7 SP1 및 Windows Server 2008 R2 SP1 이상의 해당 서버 플랫폼에 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-129">.NET Framework 4.8 can be installed on Windows 10, Windows 8.1, Windows 7 SP1, and the corresponding server platforms starting with Windows Server 2008 R2 SP1.</span></span> <span data-ttu-id="9bae0-130">웹 설치 관리자 또는 오프라인 설치 관리자를 사용하여 .NET Framework 4.8을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-130">You can install .NET Framework 4.8 by using either the web installer or the offline installer.</span></span> <span data-ttu-id="9bae0-131">대부분의 사용자에게 권장되는 방법은 웹 설치 관리자를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-131">The recommended way for most users is to use the web installer.</span></span>

<span data-ttu-id="9bae0-132">[.NET Framework 4.8 개발자 팩](https://go.microsoft.com/fwlink/?LinkId=2085167)을 설치하여 Visual Studio 2012 이상 버전에서 .NET Framework 4.8을 대상으로 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-132">You can target .NET Framework 4.8 in Visual Studio 2012 or later by installing the [.NET Framework 4.8 Developer Pack](https://go.microsoft.com/fwlink/?LinkId=2085167).</span></span>

### <a name="whats-new-in-net-framework-48"></a><span data-ttu-id="9bae0-133">.NET Framework 4.8의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="9bae0-133">What's new in .NET Framework 4.8</span></span>

<span data-ttu-id="9bae0-134">.NET Framework 4.8에는 다음과 같은 영역의 새 기능이 소개됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-134">.NET Framework 4.8 introduces new features in the following areas:</span></span>

- [<span data-ttu-id="9bae0-135">기본 클래스</span><span class="sxs-lookup"><span data-stu-id="9bae0-135">Base classes</span></span>](#core48)
- [<span data-ttu-id="9bae0-136">WCF(Windows Communication Foundation)</span><span class="sxs-lookup"><span data-stu-id="9bae0-136">Windows Communication Foundation (WCF)</span></span>](#wcf48)
- [<span data-ttu-id="9bae0-137">WPF(Windows Presentation Foundation)</span><span class="sxs-lookup"><span data-stu-id="9bae0-137">Windows Presentation Foundation (WPF)</span></span>](#wpf48)
- [<span data-ttu-id="9bae0-138">공용 언어 런타임</span><span class="sxs-lookup"><span data-stu-id="9bae0-138">Common language runtime</span></span>](#clr48)

<span data-ttu-id="9bae0-139">애플리케이션이 보조 기술 사용자에게 적절한 환경을 제공할 수 있도록 하는 향상된 내게 필요한 옵션 기능이 계속해서 .NET Framework 4.8의 주력 기능이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-139">Improved accessibility, which allows an application to provide an appropriate experience for users of Assistive Technology, continues to be a major focus of .NET Framework 4.8.</span></span> <span data-ttu-id="9bae0-140">.NET Framework 4.8에서 내게 필요한 옵션의 기능 향상에 대한 자세한 내용은 [.NET Framework의 내게 필요한 옵션의 새로운 기능](whats-new-in-accessibility.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bae0-140">For information on accessibility improvements in .NET Framework 4.8, see [What's new in accessibility in .NET Framework](whats-new-in-accessibility.md).</span></span>

<a name="core48"></a>

#### <a name="base-classes"></a><span data-ttu-id="9bae0-141">기본 클래스</span><span class="sxs-lookup"><span data-stu-id="9bae0-141">Base classes</span></span>

<span data-ttu-id="9bae0-142">**암호화에 대한 FIPS 영향 감소**.</span><span class="sxs-lookup"><span data-stu-id="9bae0-142">**Reduced FIPS impact on Cryptography**.</span></span> <span data-ttu-id="9bae0-143">이전 버전의 .NET Framework에서 <xref:System.Security.Cryptography.SHA256Managed>와 같은 관리형 암호화 공급자 클래스는 시스템 암호화 라이브러리가 “FIPS 모드”로 구성될 때 <xref:System.Security.Cryptography.CryptographicException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-143">In previous versions of .NET Framework, managed cryptographic provider classes such as <xref:System.Security.Cryptography.SHA256Managed> throw a <xref:System.Security.Cryptography.CryptographicException> when the system cryptographic libraries are configured in "FIPS mode".</span></span> <span data-ttu-id="9bae0-144">암호화 공급자 클래스의 관리형 버전은 시스템 암호화 라이브러리와 달리 FIPS(Federal Information Processing Standard) 140-2 인증을 거치지 않았으므로 이 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-144">These exceptions are thrown because the managed versions of the cryptographic provider classes, unlike the system cryptographic libraries, have not undergone FIPS (Federal Information Processing Standards) 140-2 certification.</span></span> <span data-ttu-id="9bae0-145">개발 머신을 FIPS 모드에서 사용하는 개발자는 거의 없으므로 일반적으로 예외는 프로덕션 시스템에서 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-145">Because few developers have their development machines in FIPS mode, the exceptions are commonly thrown in production systems.</span></span>

<span data-ttu-id="9bae0-146">기본적으로 .NET Framework 4.8을 대상으로 하는 애플리케이션에서 다음 관리형 암호화 클래스는 더 이상 다음 경우에 <xref:System.Security.Cryptography.CryptographicException>을 throw하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-146">By default in applications that target .NET Framework 4.8, the following managed cryptography classes no longer throw a <xref:System.Security.Cryptography.CryptographicException> in this case:</span></span>

- <xref:System.Security.Cryptography.MD5Cng>
- <xref:System.Security.Cryptography.MD5CryptoServiceProvider>
- <xref:System.Security.Cryptography.RC2CryptoServiceProvider>
- <xref:System.Security.Cryptography.RijndaelManaged>
- <xref:System.Security.Cryptography.RIPEMD160Managed>
- <xref:System.Security.Cryptography.SHA256Managed>

<span data-ttu-id="9bae0-147">대신, 이 클래스는 암호화 작업을 시스템 암호화 라이브러리로 리디렉션합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-147">Instead, these classes redirect cryptographic operations to a system cryptography library.</span></span> <span data-ttu-id="9bae0-148">이 변경에 따라 개발자 환경과 프로덕션 환경 간에 혼동될 수 있는 차이가 효과적으로 제거되고 네이티브 구성 요소와 관리형 구성 요소가 동일한 암호화 정책에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-148">This change effectively removes a potentially confusing difference between developer environments and production environments and makes native components and managed components operate under the same cryptographic policy.</span></span> <span data-ttu-id="9bae0-149">이 예외에 의존하는 애플리케이션은 AppContext 스위치 `Switch.System.Security.Cryptography.UseLegacyFipsThrow`를 `true`로 설정하여 이전 동작을 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-149">Applications that depend on these exceptions can restore the previous behavior by setting the AppContext switch `Switch.System.Security.Cryptography.UseLegacyFipsThrow` to `true`.</span></span> <span data-ttu-id="9bae0-150">자세한 내용은 [관리형 암호화 클래스가 FIPS 모드에서 CryptographyException을 throw하지 않음](../migration-guide/retargeting/4.7.2-4.8.md#managed-cryptography-classes-do-not-throw-a-cryptographyexception-in-fips-mode)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bae0-150">For more information, see [Managed cryptography classes do not throw a CryptographyException in FIPS mode](../migration-guide/retargeting/4.7.2-4.8.md#managed-cryptography-classes-do-not-throw-a-cryptographyexception-in-fips-mode).</span></span>

<span data-ttu-id="9bae0-151">**업데이트된 버전의 ZLib 사용**</span><span class="sxs-lookup"><span data-stu-id="9bae0-151">**Use of updated version of ZLib**</span></span>

<span data-ttu-id="9bae0-152">.NET Framework 4.5부터 clrcompression.dll 어셈블리는 압축 알고리즘 구현을 제공하기 위해 데이터 압축용 네이티브 외부 라이브러리인 [ZLib](https://www.zlib.net)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-152">Starting with .NET Framework 4.5, the clrcompression.dll assembly uses [ZLib](https://www.zlib.net), a native external library for data compression, in order to provide an implementation for the deflate algorithm.</span></span> <span data-ttu-id="9bae0-153">.NET Framework 4.8 버전의 clrcompression.dll은 ZLib 버전 1.2.11을 사용하도록 업데이트되며, 여기에는 몇 가지 주요 개선 사항과 수정 사항이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-153">The .NET Framework 4.8 version of clrcompression.dll is updated to use ZLib Version 1.2.11, which includes several key improvements and fixes.</span></span>

<a name="wcf48"></a>

#### <a name="windows-communication-foundation-wcf"></a><span data-ttu-id="9bae0-154">WCF(Windows Communication Foundation)</span><span class="sxs-lookup"><span data-stu-id="9bae0-154">Windows Communication Foundation (WCF)</span></span>

<span data-ttu-id="9bae0-155">**ServiceHealthBehavior 소개**</span><span class="sxs-lookup"><span data-stu-id="9bae0-155">**Introduction of ServiceHealthBehavior**</span></span>

<span data-ttu-id="9bae0-156">상태 엔드포인트는 상태를 기반으로 서비스를 관리하기 위해 오케스트레이션 도구에서 광범위하게 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-156">Health endpoints are widely used by orchestration tools to manage services based on their health status.</span></span> <span data-ttu-id="9bae0-157">또한 상태 검사는 모니터링 도구에서 서비스의 가용성 및 성능에 대한 알림을 추적하고 제공하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-157">Health checks can also be used by monitoring tools to track and provide notifications about the availability and performance of a service.</span></span>

<span data-ttu-id="9bae0-158">**ServiceHealthBehavior** 는 <xref:System.ServiceModel.Description.IServiceBehavior>를 확장하는 WCF 서비스 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-158">**ServiceHealthBehavior** is a WCF service behavior that extends <xref:System.ServiceModel.Description.IServiceBehavior>.</span></span>  <span data-ttu-id="9bae0-159"><xref:System.ServiceModel.Description.ServiceDescription.Behaviors?displayProperty=nameWithType> 컬렉션에 추가될 경우 서비스 동작은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-159">When added to the <xref:System.ServiceModel.Description.ServiceDescription.Behaviors?displayProperty=nameWithType> collection, a service behavior does the following:</span></span>

- <span data-ttu-id="9bae0-160">HTTP 응답 코드를 사용하여 서비스 상태를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-160">Returns service health status with HTTP response codes.</span></span> <span data-ttu-id="9bae0-161">HTTP/GET 상태 프로브 요청에 대한 HTTP 상태 코드를 쿼리 문자열로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-161">You can specify in a query string the HTTP status code for a HTTP/GET health probe request.</span></span>

- <span data-ttu-id="9bae0-162">서비스 상태에 대한 정보를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-162">Publishes information about service health.</span></span> <span data-ttu-id="9bae0-163">서비스 상태, 제한 개수 및 용량을 포함한 서비스별 세부 정보는 `?health` 쿼리 문자열과 함께 HTTP/GET 요청을 사용하여 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-163">Service-specific details, including service state, throttle counts, and capacity can be displayed by using an HTTP/GET request with the `?health` query string.</span></span> <span data-ttu-id="9bae0-164">잘못 동작하는 WCF 서비스 문제를 해결할 때 해당 정보에 쉽게 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-164">Ease of access to such information is important when troubleshooting a misbehaving WCF service.</span></span>

<span data-ttu-id="9bae0-165">다음과 같은 두 가지 방법으로 상태 엔드포인트를 공개하고 WCF 서비스 상태 정보를 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-165">There are two ways to expose the health endpoint and publish WCF service health information:</span></span>

- <span data-ttu-id="9bae0-166">코드를 통해.</span><span class="sxs-lookup"><span data-stu-id="9bae0-166">Through code.</span></span> <span data-ttu-id="9bae0-167">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="9bae0-167">For example:</span></span>

  ```csharp
  ServiceHost host = new ServiceHost(typeof(Service1),
                     new Uri("http://contoso:81/Service1"));
  ServiceHealthBehavior healthBehavior =
      host.Description.Behaviors.Find<ServiceHealthBehavior>();
  healthBehavior ??= new ServiceHealthBehavior();
  host.Description.Behaviors.Add(healthBehavior);
  ```

  ```vb
  Dim host As New ServiceHost(GetType(Service1),
              New Uri("http://contoso:81/Service1"))
  Dim healthBehavior As ServiceHealthBehavior =
     host.Description.Behaviors.Find(Of ServiceHealthBehavior)()
  If healthBehavior Is Nothing Then
     healthBehavior = New ServiceHealthBehavior()
  End If
  host.Description.Behaviors.Add(healthBehavior)
  ```

- <span data-ttu-id="9bae0-168">구성 파일 사용.</span><span class="sxs-lookup"><span data-stu-id="9bae0-168">By using a configuration file.</span></span> <span data-ttu-id="9bae0-169">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="9bae0-169">For example:</span></span>

  ```xml
  <behaviors>
    <serviceBehaviors>
      <behavior name="DefaultBehavior">
        <serviceHealth httpsGetEnabled="true"/>
      </behavior>
    </serviceBehaviors>
  </behaviors>
  ```

<span data-ttu-id="9bae0-170">서비스 상태는 `OnServiceFailure`, `OnDispatcherFailure`, `OnListenerFailure`, `OnThrottlePercentExceeded` 등의 쿼리 매개 변수를 사용하여 쿼리할 수 있고 각 쿼리 매개 변수에 대한 HTTP 응답 코드를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-170">A service's health status can be queried by using query parameters such as `OnServiceFailure`, `OnDispatcherFailure`, `OnListenerFailure`, `OnThrottlePercentExceeded`), and an HTTP response code can be specified for each query parameter.</span></span> <span data-ttu-id="9bae0-171">쿼리 매개 변수에 대한 HTTP 응답 코드가 생략되면 기본적으로 503 HTTP 응답 코드가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-171">If the HTTP response code is omitted for a query parameter, a 503 HTTP response code is used by default.</span></span> <span data-ttu-id="9bae0-172">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="9bae0-172">For example:</span></span>

- <span data-ttu-id="9bae0-173">OnServiceFailure: `https://contoso:81/Service1?health&OnServiceFailure=450`</span><span class="sxs-lookup"><span data-stu-id="9bae0-173">OnServiceFailure: `https://contoso:81/Service1?health&OnServiceFailure=450`</span></span>

  <span data-ttu-id="9bae0-174">[ServiceHost.State](xref:System.ServiceModel.Channels.CommunicationObject.State)가 <xref:System.ServiceModel.CommunicationState.Opened?displayProperty=nameWithType>보다 크면 450 HTTP 응답 상태 코드가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-174">A 450 HTTP response status code is returned when [ServiceHost.State](xref:System.ServiceModel.Channels.CommunicationObject.State) is greater than <xref:System.ServiceModel.CommunicationState.Opened?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="9bae0-175">쿼리 매개 변수 및 예제:</span><span class="sxs-lookup"><span data-stu-id="9bae0-175">Query parameters and examples:</span></span>

- <span data-ttu-id="9bae0-176">OnDispatcherFailure: `https://contoso:81/Service1?health&OnDispatcherFailure=455`</span><span class="sxs-lookup"><span data-stu-id="9bae0-176">OnDispatcherFailure: `https://contoso:81/Service1?health&OnDispatcherFailure=455`</span></span>

  <span data-ttu-id="9bae0-177">채널 디스패처의 상태가 <xref:System.ServiceModel.CommunicationState.Opened?displayProperty=nameWithType>보다 크면 455 HTTP 응답 상태 코드가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-177">A 455 HTTP response status code is returned when the state of any of the channel dispatchers is greater than <xref:System.ServiceModel.CommunicationState.Opened?displayProperty=nameWithType>.</span></span>

- <span data-ttu-id="9bae0-178">OnListenerFailure: `https://contoso:81/Service1?health&OnListenerFailure=465`</span><span class="sxs-lookup"><span data-stu-id="9bae0-178">OnListenerFailure: `https://contoso:81/Service1?health&OnListenerFailure=465`</span></span>

  <span data-ttu-id="9bae0-179">채널 수신기의 상태가 <xref:System.ServiceModel.CommunicationState.Opened?displayProperty=nameWithType>보다 크면 465 HTTP 응답 상태 코드가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-179">A 465 HTTP response status code is returned when the state of any of the channel listeners is greater than <xref:System.ServiceModel.CommunicationState.Opened?displayProperty=nameWithType>.</span></span>

- <span data-ttu-id="9bae0-180">OnThrottlePercentExceeded: `https://contoso:81/Service1?health&OnThrottlePercentExceeded= 70:350,95:500`</span><span class="sxs-lookup"><span data-stu-id="9bae0-180">OnThrottlePercentExceeded: `https://contoso:81/Service1?health&OnThrottlePercentExceeded= 70:350,95:500`</span></span>

  <span data-ttu-id="9bae0-181">응답 및 해당 HTTP 응답 코드 {200~599}를 트리거하는 백분율 {1~100}을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-181">Specifies the percentage {1 – 100} that triggers the response and its HTTP response code {200 – 599}.</span></span> <span data-ttu-id="9bae0-182">이 예제에 대한 설명:</span><span class="sxs-lookup"><span data-stu-id="9bae0-182">In this example:</span></span>

  - <span data-ttu-id="9bae0-183">백분율이 95보다 크면 500 HTTP 응답 코드가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-183">If the percentage is greater than 95, a 500 HTTP response code is returned.</span></span>

  - <span data-ttu-id="9bae0-184">백분율 또는 70~95 사이이면 350이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-184">If the percentage or between 70 and 95, 350 is returned.</span></span>

  - <span data-ttu-id="9bae0-185">그렇지 않으면 200이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-185">Otherwise, 200 is returned.</span></span>

<span data-ttu-id="9bae0-186">HTML에서 `https://contoso:81/Service1?health` 같은 쿼리 문자열을 지정하거나 XML에서 `https://contoso:81/Service1?health&Xml` 같은 쿼리 문자열을 지정하여 서비스 상태를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-186">The service health status can be displayed either in HTML by specifying a query string like `https://contoso:81/Service1?health` or in XML by specifying a query string like `https://contoso:81/Service1?health&Xml`.</span></span> <span data-ttu-id="9bae0-187">`https://contoso:81/Service1?health&NoContent` 같은 쿼리 문자열은 빈 HTML 페이지를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-187">A query string like `https://contoso:81/Service1?health&NoContent` returns an empty HTML page.</span></span>

<a name="wpf48"></a>

#### <a name="windows-presentation-foundation-wpf"></a><span data-ttu-id="9bae0-188">WPF(Windows Presentation Foundation)</span><span class="sxs-lookup"><span data-stu-id="9bae0-188">Windows Presentation Foundation (WPF)</span></span>

<span data-ttu-id="9bae0-189">**높은 DPI 기능 향상**</span><span class="sxs-lookup"><span data-stu-id="9bae0-189">**High DPI enhancements**</span></span>

<span data-ttu-id="9bae0-190">.NET Framework 4.8에서 WPF는 모니터별 V2 DPI 인식 및 혼합 모드 DPI 크기 조정에 대한 지원을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-190">In .NET Framework 4.8, WPF adds support for Per-Monitor V2 DPI Awareness and Mixed-Mode DPI scaling.</span></span> <span data-ttu-id="9bae0-191">높은 DPI 개발에 대한 자세한 내용은 [Windows에서 높은 DPI 데스크톱 애플리케이션 개발](/windows/win32/hidpi/high-dpi-desktop-application-development-on-windows)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bae0-191">See [High DPI Desktop Application Development on Windows](/windows/win32/hidpi/high-dpi-desktop-application-development-on-windows) for additional information about high DPI development.</span></span>

<span data-ttu-id="9bae0-192">.NET Framework 4.8은 혼합 모드 DPI 크기 조정(Windows 10 2018년 4월 업데이트부터)을 지원하는 플랫폼의 높은 DPI WPF 애플리케이션에서 호스트되는 HWND 및 Windows Forms 상호 운용 지원을 향상합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-192">.NET Framework 4.8 improves support for hosted HWNDs and Windows Forms interoperation in High-DPI WPF applications on platforms that support Mixed-Mode DPI scaling (starting with Windows 10 April 2018 Update).</span></span> <span data-ttu-id="9bae0-193">호스트된 HWND 또는 Windows Forms 컨트롤이 [SetThreadDpiHostingBehavior](/windows/desktop/api/winuser/nf-winuser-setthreaddpihostingbehavior) 및 [SetThreadDpiAwarenessContext](/windows/desktop/api/winuser/nf-winuser-setthreaddpiawarenesscontext)를 호출하여 혼합 모드 DPI 크기 조정 창으로 만들어지면 이 컨트롤은 모니터별 V2 WPF 애플리케이션에서 호스트될 수 있고 적절하게 크기가 지정되거나 조정됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-193">When hosted HWNDs or Windows Forms controls are created as Mixed-Mode DPI-scaled windows by calling [SetThreadDpiHostingBehavior](/windows/desktop/api/winuser/nf-winuser-setthreaddpihostingbehavior) and [SetThreadDpiAwarenessContext](/windows/desktop/api/winuser/nf-winuser-setthreaddpiawarenesscontext), they can be hosted in a Per-Monitor V2 WPF application and are sized and scaled appropriately.</span></span> <span data-ttu-id="9bae0-194">해당 호스트된 콘텐츠는 네이티브 DPI로 렌더링되지 않습니다. 대신 운영 체제가 호스트된 콘텐츠를 적절한 크기로 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-194">Such hosted content is not rendered at the native DPI; instead, the operating system scales the hosted content to the appropriate size.</span></span> <span data-ttu-id="9bae0-195">모니터별 v2 DPI 인식 모드에 대한 지원도 높은 DPI 애플리케이션의 네이티브 창에 WPF 컨트롤을 호스트(부모 지정)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-195">The support for Per-Monitor v2 DPI awareness mode also allows WPF controls to be hosted (i.e., parented) in a native window in a high-DPI application.</span></span>

<span data-ttu-id="9bae0-196">혼합 모드 높은 DPI 크기 조정을 지원하려면 다음 [AppContext](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)가 애플리케이션 구성 파일을 전환하도록 설정하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-196">To enable support for Mixed-Mode High DPI scaling, you can set the following [AppContext](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) switches the application configuration file:</span></span>

```xml
<runtime>
   <AppContextSwitchOverrides value = "Switch.System.Windows.DoNotScaleForDpiChanges=false; Switch.System.Windows.DoNotUsePresentationDpiCapabilityTier2OrGreater=false"/>
</runtime>
```

<a name="clr48"></a>

#### <a name="common-language-runtime"></a><span data-ttu-id="9bae0-197">공용 언어 런타임</span><span class="sxs-lookup"><span data-stu-id="9bae0-197">Common language runtime</span></span>

<span data-ttu-id="9bae0-198">.NET Framework 4.8의 런타임은 다음과 같은 변경 내용과 향상된 기능을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-198">The runtime in .NET Framework 4.8 includes the following changes and improvements:</span></span>

<span data-ttu-id="9bae0-199">**JIT 컴파일러의 향상된 기능**.</span><span class="sxs-lookup"><span data-stu-id="9bae0-199">**Improvements to the JIT compiler**.</span></span> <span data-ttu-id="9bae0-200">.NET Framework 4.8의 JIT(Just-In-Time) 컴파일러는 .NET Core 2.1의 JIT 컴파일러를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-200">The Just-in-time (JIT) compiler in .NET Framework 4.8 is based on the JIT compiler in .NET Core 2.1.</span></span> <span data-ttu-id="9bae0-201">.NET Core 2.1 JIT 컴파일러에 적용된 대부분의 최적화 및 모든 버그 수정은 .NET Framework 4.8 JIT 컴파일러에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-201">Many of the optimizations and all of the bug fixes made to the .NET Core 2.1 JIT compiler are included in the .NET Framework 4.8 JIT compiler.</span></span>

<span data-ttu-id="9bae0-202">**NGEN 향상된 기능**.</span><span class="sxs-lookup"><span data-stu-id="9bae0-202">**NGEN improvements**.</span></span> <span data-ttu-id="9bae0-203">NGEN 이미지에서 매핑된 데이터가 메모리에 상주되지 않도록 런타임은 NGEN([네이티브 이미지 생성기](../tools/ngen-exe-native-image-generator.md)) 이미지의 메모리 관리를 개선했습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-203">The runtime has improved its memory management for [Native Image Generator](../tools/ngen-exe-native-image-generator.md) (NGEN) images so that data mapped from NGEN images are not memory-resident.</span></span> <span data-ttu-id="9bae0-204">실행될 메모리를 수정하여 임의 코드를 실행하려고 시도하는 공격에 사용할 수 있는 노출 영역이 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-204">This reduces the surface area available to attacks that attempt to execute arbitrary code by modifying memory that will be executed.</span></span>

<span data-ttu-id="9bae0-205">**모든 어셈블리에 대한 맬웨어 방지 검사**.</span><span class="sxs-lookup"><span data-stu-id="9bae0-205">**Antimalware scanning for all assemblies**.</span></span> <span data-ttu-id="9bae0-206">이전 버전의 .NET Framework에서 런타임은 Windows Defender 또는 타사 맬웨어 방지 프로그램을 사용하여 디스크에서 로드된 모든 어셈블리를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-206">In previous versions of .NET Framework, the runtime scans all assemblies loaded from disk using either Windows Defender or third-party antimalware software.</span></span> <span data-ttu-id="9bae0-207">그러나 <xref:System.Reflection.Assembly.Load(System.Byte[])?displayProperty=nameWithType> 메서드와 같은 기타 소스에서 로드된 어셈블리는 검사되지 않으며 검색되지 않은 맬웨어를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-207">However, assemblies loaded from other sources, such as by the <xref:System.Reflection.Assembly.Load(System.Byte[])?displayProperty=nameWithType> method, are not scanned and can potentially contain undetected malware.</span></span> <span data-ttu-id="9bae0-208">Windows 10에서 실행되는 .NET Framework 4.8부터 런타임은 [AMSI(맬웨어 방지 검사 인터페이스)](/windows/desktop/AMSI/antimalware-scan-interface-portal)를 구현하는 맬웨어 방지 솔루션을 통해 검사를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-208">Starting with .NET Framework 4.8 running on Windows 10, the runtime triggers a scan by antimalware solutions that implement the [Antimalware Scan Interface (AMSI)](/windows/desktop/AMSI/antimalware-scan-interface-portal).</span></span>

<a name="v472"></a>

## <a name="whats-new-in-net-framework-472"></a><span data-ttu-id="9bae0-209">.NET Framework 4.7.2의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="9bae0-209">What's new in .NET Framework 4.7.2</span></span>

<span data-ttu-id="9bae0-210">.NET Framework 4.7.2에는 다음 영역의 새 기능이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-210">.NET Framework 4.7.2 includes new features in the following areas:</span></span>

- [<span data-ttu-id="9bae0-211">기본 클래스</span><span class="sxs-lookup"><span data-stu-id="9bae0-211">Base classes</span></span>](#core-472)
- [<span data-ttu-id="9bae0-212">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="9bae0-212">ASP.NET</span></span>](#asp-net472)
- [<span data-ttu-id="9bae0-213">네트워킹</span><span class="sxs-lookup"><span data-stu-id="9bae0-213">Networking</span></span>](#net472)
- [<span data-ttu-id="9bae0-214">SQL</span><span class="sxs-lookup"><span data-stu-id="9bae0-214">SQL</span></span>](#sql472)
- [<span data-ttu-id="9bae0-215">WPF</span><span class="sxs-lookup"><span data-stu-id="9bae0-215">WPF</span></span>](#wpf472)
- [<span data-ttu-id="9bae0-216">ClickOnce</span><span class="sxs-lookup"><span data-stu-id="9bae0-216">ClickOnce</span></span>](#clickonce)

<span data-ttu-id="9bae0-217">.NET Framework 4.7.2는 내게 필요한 옵션 기능을 개선하는 데 주력하여 애플리케이션이 보조 기술 사용자에게 적절한 환경을 제공할 수 있도록 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-217">A continuing focus in .NET Framework 4.7.2 is improved accessibility, which allows an application to provide an appropriate experience for users of Assistive Technology.</span></span> <span data-ttu-id="9bae0-218">.NET Framework 4.7.2에서 내게 필요한 옵션의 기능 향상에 대한 자세한 내용은 [.NET Framework의 내게 필요한 옵션의 새로운 기능](whats-new-in-accessibility.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bae0-218">For information on accessibility improvements in .NET Framework 4.7.2, see [What's new in accessibility in .NET Framework](whats-new-in-accessibility.md).</span></span>

<a name="core-472"></a>

#### <a name="base-classes"></a><span data-ttu-id="9bae0-219">기본 클래스</span><span class="sxs-lookup"><span data-stu-id="9bae0-219">Base classes</span></span>

<span data-ttu-id="9bae0-220">.NET Framework 4.7.2는 여러 향상된 암호화 기능, ZIP 보관을 위한 더 나은 압축 풀기 지원 및 추가적인 컬렉션 API를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-220">.NET Framework 4.7.2 features a large number of cryptographic enhancements, better decompression support for ZIP archives, and additional collection APIs.</span></span>

<span data-ttu-id="9bae0-221">**RSA.Create 및 DSA.Create의 새 오버로드**</span><span class="sxs-lookup"><span data-stu-id="9bae0-221">**New overloads of RSA.Create and DSA.Create**</span></span>

<span data-ttu-id="9bae0-222"><xref:System.Security.Cryptography.DSA.Create(System.Security.Cryptography.DSAParameters)?displayProperty=nameWithType> 및 <xref:System.Security.Cryptography.RSA.Create(System.Security.Cryptography.RSAParameters)?displayProperty=nameWithType> 메서드를 통해 새 <xref:System.Security.Cryptography.DSA> 또는 <xref:System.Security.Cryptography.RSA> 키를 인스턴스화할 때 키 매개 변수를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-222">The <xref:System.Security.Cryptography.DSA.Create(System.Security.Cryptography.DSAParameters)?displayProperty=nameWithType> and <xref:System.Security.Cryptography.RSA.Create(System.Security.Cryptography.RSAParameters)?displayProperty=nameWithType> methods let you supply key parameters when instantiating a new <xref:System.Security.Cryptography.DSA> or <xref:System.Security.Cryptography.RSA> key.</span></span> <span data-ttu-id="9bae0-223">그러면 다음과 같은 코드를 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-223">They allow you to replace code like the following:</span></span>

```csharp
// Before .NET Framework 4.7.2
using (RSA rsa = RSA.Create())
{
   rsa.ImportParameters(rsaParameters);
   // Other code to execute using the RSA instance.
}
```

```vb
' Before .NET Framework 4.7.2
Using rsa = RSA.Create()
   rsa.ImportParameters(rsaParameters)
   ' Other code to execute using the rsa instance.
End Using
```

<span data-ttu-id="9bae0-224">다음과 같은 코드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-224">with code like this:</span></span>

```csharp
// Starting with .NET Framework 4.7.2
using (RSA rsa = RSA.Create(rsaParameters))
{
   // Other code to execute using the rsa instance.
}
```

```vb
' Starting with .NET Framework 4.7.2
Using rsa = RSA.Create(rsaParameters)
   ' Other code to execute using the rsa instance.
End Using
```

<span data-ttu-id="9bae0-225"><xref:System.Security.Cryptography.DSA.Create(System.Int32)?displayProperty=nameWithType> 및 <xref:System.Security.Cryptography.RSA.Create(System.Int32)?displayProperty=nameWithType> 메서드를 통해 특정 키 크기의 새로운 <xref:System.Security.Cryptography.DSA> 또는 <xref:System.Security.Cryptography.RSA> 키를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-225">The <xref:System.Security.Cryptography.DSA.Create(System.Int32)?displayProperty=nameWithType> and <xref:System.Security.Cryptography.RSA.Create(System.Int32)?displayProperty=nameWithType> methods let you generate new <xref:System.Security.Cryptography.DSA> or <xref:System.Security.Cryptography.RSA> keys with a specific key size.</span></span> <span data-ttu-id="9bae0-226">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="9bae0-226">For example:</span></span>

```csharp
using (DSA dsa = DSA.Create(2048))
{
   // Other code to execute using the dsa instance.
}
```

```vb
Using dsa = DSA.Create(2048)
   ' Other code to execute using the dsa instance.
End Using
```

<span data-ttu-id="9bae0-227">**Rfc2898DeriveBytes 생성자가 해시 알고리즘 이름을 수락**</span><span class="sxs-lookup"><span data-stu-id="9bae0-227">**Rfc2898DeriveBytes constructors accept a hash algorithm name**</span></span>

<span data-ttu-id="9bae0-228"><xref:System.Security.Cryptography.Rfc2898DeriveBytes> 클래스에 키를 파생할 때 사용하는 HMAC 알고리즘을 식별하는 <xref:System.Security.Cryptography.HashAlgorithmName> 매개 변수를 사용하는 세 명의 새로운 생성자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-228">The <xref:System.Security.Cryptography.Rfc2898DeriveBytes> class has three new constructors with a <xref:System.Security.Cryptography.HashAlgorithmName> parameter that identifies the HMAC algorithm to use when deriving keys.</span></span> <span data-ttu-id="9bae0-229">SHA-1을 사용하는 대신 개발자는 다음 예제에 표시된 대로 SHA-256과 같은 SHA-2 기반 HMAC를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-229">Instead of using SHA-1, developers should use a SHA-2-based HMAC like SHA-256, as shown in the following example:</span></span>

```csharp
private static byte[] DeriveKey(string password, out int iterations, out byte[] salt,
                                out HashAlgorithmName algorithm)
{
   iterations = 100000;
   algorithm = HashAlgorithmName.SHA256;

   const int SaltSize = 32;
   const int DerivedValueSize = 32;

   using (Rfc2898DeriveBytes pbkdf2 = new Rfc2898DeriveBytes(password, SaltSize,
                                                             iterations, algorithm))
   {
      salt = pbkdf2.Salt;
      return pbkdf2.GetBytes(DerivedValueSize);
   }
}
```

```vb
Private Shared Function DeriveKey(password As String, ByRef iterations As Integer,
                                  ByRef salt AS Byte(), ByRef algorithm As HashAlgorithmName) As Byte()
   iterations = 100000
   algorithm = HashAlgorithmName.SHA256

   Const SaltSize As Integer = 32
   Const  DerivedValueSize As Integer = 32

   Using pbkdf2 = New Rfc2898DeriveBytes(password, SaltSize, iterations, algorithm)
      salt = pbkdf2.Salt
      Return pbkdf2.GetBytes(DerivedValueSize)
   End Using
End Function
```

<span data-ttu-id="9bae0-230">**임시 키에 대한 지원**</span><span class="sxs-lookup"><span data-stu-id="9bae0-230">**Support for ephemeral keys**</span></span>

<span data-ttu-id="9bae0-231">필요에 따라 PFX 가져오기는 하드 드라이브를 무시하고 메모리에서 직접 프라이빗 키를 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-231">PFX import can optionally load private keys directly from memory, bypassing the hard drive.</span></span> <span data-ttu-id="9bae0-232"> 새로운 <xref:System.Security.Cryptography.X509Certificates.X509KeyStorageFlags.EphemeralKeySet?displayProperty=nameWithType> 플래그가 <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> 생성자 또는 <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.Import%2A?displayProperty=nameWithType> 메서드의 오버로드 중 하나에 지정되는 경우 프라이빗 키는 임시 키로 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-232">When the new <xref:System.Security.Cryptography.X509Certificates.X509KeyStorageFlags.EphemeralKeySet?displayProperty=nameWithType> flag is specified in an <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> constructor or one of the overloads of the <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.Import%2A?displayProperty=nameWithType> method, the private keys will be loaded as ephemeral keys.</span></span> <span data-ttu-id="9bae0-233">이렇게 하면 키가 디스크에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-233">This prevents the keys from being visible on the disk.</span></span> <span data-ttu-id="9bae0-234">단,</span><span class="sxs-lookup"><span data-stu-id="9bae0-234">However:</span></span>

- <span data-ttu-id="9bae0-235">키가 디스크에 유지되지 않으므로 이 플래그로 로드된 인증서는 X509Store에 추가하기에 적합하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-235">Since the keys are not persisted to disk, certificates loaded with this flag are not good candidates to add to an X509Store.</span></span>

- <span data-ttu-id="9bae0-236">이 방식으로 로드된 키는 거의 항상 Windows CNG를 통해 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-236">Keys loaded in this manner are almost always loaded via Windows CNG.</span></span> <span data-ttu-id="9bae0-237">따라서 호출자는 [cert.GetRSAPrivateKey()](xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey%2A)와 같은 확장 메서드를 호출하여 개인 키에 액세스해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-237">Therefore, callers must access the private key by calling extension methods, such as [cert.GetRSAPrivateKey()](xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey%2A).</span></span> <span data-ttu-id="9bae0-238"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> 속성은 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-238">The <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> property does not function.</span></span>

- <span data-ttu-id="9bae0-239">레거시 <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> 속성은 인증서와 함께 작동하지 않으므로 개발자는 임시 키로 전환하기 전에 엄격한 테스트를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-239">Since the legacy <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> property does not work with certificates, developers should perform rigorous testing before switching to ephemeral keys.</span></span>

<span data-ttu-id="9bae0-240">**PKCS#10 인증서 서명 요청 및 X.509 공개 키 인증서의 프로그래밍 방식 생성**</span><span class="sxs-lookup"><span data-stu-id="9bae0-240">**Programmatic creation of PKCS#10 certification signing requests and X.509 public key certificates**</span></span>

<span data-ttu-id="9bae0-241">.NET Framework 4.7.2부터 워크로드는 인증서 요청 생성이 기존 도구에 준비되도록 CSR(인증서 서명 요청)을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-241">Starting with .NET Framework 4.7.2, workloads can generate certificate signing requests (CSRs), which allows certificate request generation to be staged into existing tooling.</span></span> <span data-ttu-id="9bae0-242">이는 테스트 시나리오에서 자주 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-242">This is frequently useful in test scenarios.</span></span>

<span data-ttu-id="9bae0-243">자세한 내용 및 코드 예제는 [.NET 블로그](https://devblogs.microsoft.com/dotnet/net-framework-4-7-2-developer-pack-early-access-build-3056-is-available/)의 “PKCS #10 인증서 서명 요청 및 X.509 공개 키 인증서의 프로그래밍 방식 생성”을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bae0-243">For more information and code examples, see "Programmatic creation of PKCS#10 certification signing requests and X.509 public key certificates" in the [.NET Blog](https://devblogs.microsoft.com/dotnet/net-framework-4-7-2-developer-pack-early-access-build-3056-is-available/).</span></span>

<span data-ttu-id="9bae0-244">**새 SignerInfo 멤버**</span><span class="sxs-lookup"><span data-stu-id="9bae0-244">**New SignerInfo members**</span></span>

<span data-ttu-id="9bae0-245">.NET Framework 4.7.2부터 <xref:System.Security.Cryptography.Pkcs.SignerInfo> 클래스는 서명에 대한 자세한 정보를 공개합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-245">Starting with .NET Framework 4.7.2, the <xref:System.Security.Cryptography.Pkcs.SignerInfo> class exposes more information about the signature.</span></span> <span data-ttu-id="9bae0-246"><xref:System.Security.Cryptography.Pkcs.SignerInfo.SignatureAlgorithm?displayProperty=fullName> 속성의 값을 검색하여 서명자가 사용한 서명 알고리즘을 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-246">You can retrieve the value of the <xref:System.Security.Cryptography.Pkcs.SignerInfo.SignatureAlgorithm?displayProperty=fullName> property to determine the signature algorithm used by the signer.</span></span> <span data-ttu-id="9bae0-247"><xref:System.Security.Cryptography.Pkcs.SignerInfo.GetSignature%2A?displayProperty=nameWithType>를 호출하여 이 서명자에 대한 암호화 서명의 복사본을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-247"><xref:System.Security.Cryptography.Pkcs.SignerInfo.GetSignature%2A?displayProperty=nameWithType> can be called to get a copy of the cryptographic signature for this signer.</span></span>

<span data-ttu-id="9bae0-248">**CryptoStream을 삭제한 후 래핑된 스트림이 열려있음**</span><span class="sxs-lookup"><span data-stu-id="9bae0-248">**Leaving a wrapped stream open after CryptoStream is disposed**</span></span>

<span data-ttu-id="9bae0-249">.NET Framework 4.7.2부터 <xref:System.Security.Cryptography.CryptoStream> 클래스에는 <xref:System.Security.Cryptography.CryptoStream.Dispose%2A>가 래핑된 스트림을 닫지 않도록 허용하는 추가 생성자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-249">Starting with .NET Framework 4.7.2, the <xref:System.Security.Cryptography.CryptoStream> class has an additional constructor that allows <xref:System.Security.Cryptography.CryptoStream.Dispose%2A> to not close the wrapped stream.</span></span> <span data-ttu-id="9bae0-250"> <xref:System.Security.Cryptography.CryptoStream> 인스턴스를 삭제한 후 래핑된 스트림을 연 상태로 두려면 새로운 <xref:System.Security.Cryptography.CryptoStream> 생성자를 다음과 같이 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-250">To leave the wrapped stream open after the <xref:System.Security.Cryptography.CryptoStream> instance is disposed, call the new <xref:System.Security.Cryptography.CryptoStream> constructor as follows:</span></span>

```csharp
var cStream = new CryptoStream(stream, transform, mode, leaveOpen: true);
```

```vb
Dim cStream = New CryptoStream(stream, transform, mode, leaveOpen:=true)
```

<span data-ttu-id="9bae0-251">**DeflateStream에서 압축 풀기 변경 내용**</span><span class="sxs-lookup"><span data-stu-id="9bae0-251">**Decompression changes in DeflateStream**</span></span>

<span data-ttu-id="9bae0-252">.NET Framework 4.7.2부터 <xref:System.IO.Compression.DeflateStream> 클래스에서 압축 풀기 작업의 구현은 기본적으로 네이티브 Windows API를 사용하는 것으로 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-252">Starting with .NET Framework 4.7.2, the implementation of decompression operations in the <xref:System.IO.Compression.DeflateStream> class has changed to use native Windows APIs by default.</span></span> <span data-ttu-id="9bae0-253">일반적으로 이로 인해 성능이 크게 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-253">Typically, this results in a substantial performance improvement.</span></span>

<span data-ttu-id="9bae0-254">Windows API를 사용한 압축 풀기에 대한 지원은 .NET Framework 4.7.2를 대상으로 하는 애플리케이션에 기본적으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-254">Support for decompression by using Windows APIs is enabled by default for applications that target .NET Framework 4.7.2.</span></span> <span data-ttu-id="9bae0-255">이전 버전의 .NET Framework를 대상으로 하지만 .NET Framework 4.7.2에서 실행되는 애플리케이션은 애플리케이션 구성 파일에 다음 [AppContext switch](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)를 추가하여 이 동작을 옵트인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-255">Applications that target earlier versions of .NET Framework but are running under .NET Framework 4.7.2 can opt into this behavior by adding the following [AppContext switch](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) to the application configuration file:</span></span>

```xml
<AppContextSwitchOverrides value="Switch.System.IO.Compression.DoNotUseNativeZipLibraryForDecompression=false" />
```

<span data-ttu-id="9bae0-256">**추가 컬렉션 API**</span><span class="sxs-lookup"><span data-stu-id="9bae0-256">**Additional collection APIs**</span></span>

<span data-ttu-id="9bae0-257">.NET Framework 4.7.2는 다양한 새 API를 <xref:System.Collections.Generic.SortedSet%601> 및 <xref:System.Collections.Generic.HashSet%601> 형식에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-257">.NET Framework 4.7.2 adds a number of new APIs to the <xref:System.Collections.Generic.SortedSet%601> and <xref:System.Collections.Generic.HashSet%601> types.</span></span> <span data-ttu-id="9bae0-258">여기에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-258">These include:</span></span>

- <span data-ttu-id="9bae0-259">`TryGetValue` 메서드 - 이러한 두 가지 형식으로 다른 컬렉션 형식에 사용되는 try 패턴을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-259">`TryGetValue` methods, which extend the try pattern used in other collection types to these two types.</span></span> <span data-ttu-id="9bae0-260">이 메서드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-260">The methods are:</span></span>

  - [<span data-ttu-id="9bae0-261">public bool HashSet\<T>.TryGetValue(T equalValue, out T actualValue)</span><span class="sxs-lookup"><span data-stu-id="9bae0-261">public bool HashSet\<T>.TryGetValue(T equalValue, out T actualValue)</span></span>](xref:System.Collections.Generic.SortedSet%601.TryGetValue%2A)
  - [<span data-ttu-id="9bae0-262">public bool SortedSet\<T>.TryGetValue(T equalValue, out T actualValue)</span><span class="sxs-lookup"><span data-stu-id="9bae0-262">public bool SortedSet\<T>.TryGetValue(T equalValue, out T actualValue)</span></span>](xref:System.Collections.Generic.SortedSet%601.TryGetValue%2A)

- <span data-ttu-id="9bae0-263">`Enumerable.To*` 확장 메서드 - 컬렉션을 <xref:System.Collections.Generic.HashSet%601>로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-263">`Enumerable.To*` extension methods, which convert a collection to a <xref:System.Collections.Generic.HashSet%601>:</span></span>

  - [<span data-ttu-id="9bae0-264">public static HashSet\<TSource> ToHashSet\<TSource>(this IEnumerable\<TSource> source)</span><span class="sxs-lookup"><span data-stu-id="9bae0-264">public static HashSet\<TSource> ToHashSet\<TSource>(this IEnumerable\<TSource> source)</span></span>](xref:System.Linq.Enumerable.ToHashSet%2A)
  - [<span data-ttu-id="9bae0-265">public static HashSet\<TSource> ToHashSet\<TSource>(this IEnumerable\<TSource> source, IEqualityComparer\<TSource> comparer)</span><span class="sxs-lookup"><span data-stu-id="9bae0-265">public static HashSet\<TSource> ToHashSet\<TSource>(this IEnumerable\<TSource> source, IEqualityComparer\<TSource> comparer)</span></span>](xref:System.Linq.Enumerable.ToHashSet%2A)

- <span data-ttu-id="9bae0-266">컬렉션의 용량을 설정할 수 있도록 하는 새 <xref:System.Collections.Generic.HashSet%601> 생성자 - 미리 <xref:System.Collections.Generic.HashSet%601>의 크기를 알고 있는 경우 성능상의 이점을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-266">New <xref:System.Collections.Generic.HashSet%601> constructors that let you set the collection's capacity, which yields a performance benefit when you know the size of the <xref:System.Collections.Generic.HashSet%601> in advance:</span></span>

  - <span data-ttu-id="9bae0-267">[public HashSet(int capacity)](xref:System.Collections.Generic.HashSet%601.%23ctor(System.Int32))</span><span class="sxs-lookup"><span data-stu-id="9bae0-267">[public HashSet(int capacity)](xref:System.Collections.Generic.HashSet%601.%23ctor(System.Int32))</span></span>
  - <span data-ttu-id="9bae0-268">[public HashSet(int capacity, IEqualityComparer\<T> comparer)](xref:System.Collections.Generic.HashSet%601.%23ctor(System.Int32,System.Collections.Generic.IEqualityComparer%7B%600%7D))</span><span class="sxs-lookup"><span data-stu-id="9bae0-268">[public HashSet(int capacity, IEqualityComparer\<T> comparer)](xref:System.Collections.Generic.HashSet%601.%23ctor(System.Int32,System.Collections.Generic.IEqualityComparer%7B%600%7D))</span></span>

<span data-ttu-id="9bae0-269"><xref:System.Collections.Concurrent.ConcurrentDictionary%602> 클래스에는 사전에서 값을 검색하거나 찾을 수 없는 경우 추가하고, 사전에 값을 추가하거나 이미 존재하는 경우 업데이트하는 <xref:System.Collections.Concurrent.ConcurrentDictionary%602.AddOrUpdate%2A> 및 <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A> 메서드의 새 오버로드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-269">The <xref:System.Collections.Concurrent.ConcurrentDictionary%602> class includes new overloads of the <xref:System.Collections.Concurrent.ConcurrentDictionary%602.AddOrUpdate%2A> and <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A> methods to retrieve a value from the dictionary or to add it if it is not found, and to add a value to the dictionary or to update it if it already exists.</span></span>

```csharp
public TValue AddOrUpdate<TArg>(TKey key, Func<TKey, TArg, TValue> addValueFactory, Func<TKey, TValue, TArg, TValue> updateValueFactory, TArg factoryArgument)

public TValue GetOrAdd<TArg>(TKey key, Func<TKey, TArg, TValue> valueFactory, TArg factoryArgument)
```

```vb
Public AddOrUpdate(Of TArg)(key As TKey, addValueFactory As Func(Of TKey, TArg, TValue), updateValueFactory As Func(Of TKey, TValue, TArg, TValue), factoryArgument As TArg) As TValue

Public GetOrAdd(Of TArg)(key As TKey, valueFactory As Func(Of TKey, TArg, TValue), factoryArgument As TArg) As TValue
```

<a name="asp-net472"></a>

#### <a name="aspnet"></a><span data-ttu-id="9bae0-270">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="9bae0-270">ASP.NET</span></span>

<span data-ttu-id="9bae0-271">**Web Forms에서 종속성 주입을 위한 지원**</span><span class="sxs-lookup"><span data-stu-id="9bae0-271">**Support for dependency injection in Web Forms**</span></span>

<span data-ttu-id="9bae0-272">[DI(종속성 주입)](/aspnet/core/fundamentals/dependency-injection#overview-of-dependency-injection)는 개체와 해당 종속성을 분리하여 종속성이 변경으로 인해 개체의 코드를 더 이상 분리할 필요가 없도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-272">[Dependency injection (DI)](/aspnet/core/fundamentals/dependency-injection#overview-of-dependency-injection) decouples objects and their dependencies so that an object's code no longer needs to be changed just because a dependency has changed.</span></span> <span data-ttu-id="9bae0-273">.NET Framework 4.7.2를 대상으로 하는 ASP.NET 애플리케이션을 개발하는 경우 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-273">When developing ASP.NET applications that target .NET Framework 4.7.2, you can:</span></span>

- <span data-ttu-id="9bae0-274">ASP.NET 웹 애플리케이션 프로젝트의 [처리기 및 모듈](/previous-versions/aspnet/bb398986(v=vs.100)), [페이지 인스턴스](xref:System.Web.UI.Page) 및 [사용자 정의 컨트롤](/previous-versions/aspnet/y6wb1a0e(v=vs.100))에서 setter 기반, 인터페이스 기반 및 생성자 기반 주입을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-274">Use setter-based, interface-based, and constructor-based injection in [handlers and modules](/previous-versions/aspnet/bb398986(v=vs.100)), [Page instances](xref:System.Web.UI.Page), and [user controls](/previous-versions/aspnet/y6wb1a0e(v=vs.100)) of ASP.NET web application projects.</span></span>

- <span data-ttu-id="9bae0-275">ASP.NET 웹 사이트 프로젝트의 [처리기 및 모듈](/previous-versions/aspnet/bb398986(v=vs.100)), [페이지 인스턴스](xref:System.Web.UI.Page) 및 [사용자 정의 컨트롤](/previous-versions/aspnet/y6wb1a0e(v=vs.100))에서 setter 기반 및 인터페이스 기반 주입을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-275">Use setter-based and interface-based injection in [handlers and modules](/previous-versions/aspnet/bb398986(v=vs.100)), [Page instances](xref:System.Web.UI.Page), and [user controls](/previous-versions/aspnet/y6wb1a0e(v=vs.100)) of ASP.NET web site projects.</span></span>

- <span data-ttu-id="9bae0-276">다른 종속성 주입 프레임워크에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-276">Plug in different dependency injection frameworks.</span></span>

<span data-ttu-id="9bae0-277">**동일한 사이트 쿠키에 대한 지원**</span><span class="sxs-lookup"><span data-stu-id="9bae0-277">**Support for same-site cookies**</span></span>

<span data-ttu-id="9bae0-278">[SameSite](https://tools.ietf.org/html/draft-west-first-party-cookies-07)는 브라우저가 사이트 간 요청과 함께 쿠키를 보낼 수 없도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-278">[SameSite](https://tools.ietf.org/html/draft-west-first-party-cookies-07) prevents a browser from sending a cookie along with a cross-site request.</span></span> <span data-ttu-id="9bae0-279">.NET Framework 4.7.2는 값이 <xref:System.Web.SameSiteMode?displayProperty=nameWithType> 열거형 멤버인 <xref:System.Web.HttpCookie.SameSite?displayProperty=nameWithType> 속성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-279">.NET Framework 4.7.2 adds a <xref:System.Web.HttpCookie.SameSite?displayProperty=nameWithType> property whose value is a <xref:System.Web.SameSiteMode?displayProperty=nameWithType> enumeration member.</span></span> <span data-ttu-id="9bae0-280">해당 값이 <xref:System.Web.SameSiteMode.Strict?displayProperty=nameWithType> 또는 <xref:System.Web.SameSiteMode.Lax?displayProperty=nameWithType>인 경우 ASP.NET이 `SameSite` 특성을 set-cookie 헤더에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-280">If its value is <xref:System.Web.SameSiteMode.Strict?displayProperty=nameWithType> or <xref:System.Web.SameSiteMode.Lax?displayProperty=nameWithType>, ASP.NET adds the `SameSite` attribute to the set-cookie header.</span></span> <span data-ttu-id="9bae0-281">SameSite 지원은 <xref:System.Web.Security.FormsAuthentication> 및 <xref:System.Web.SessionState> 쿠키와 마찬가지로 <xref:System.Web.HttpCookie> 개체에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-281">SameSite support applies to <xref:System.Web.HttpCookie> objects, as well as to <xref:System.Web.Security.FormsAuthentication> and <xref:System.Web.SessionState> cookies.</span></span>

<span data-ttu-id="9bae0-282">다음과 같이 <xref:System.Web.HttpCookie> 개체에 대한 SameSite를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-282">You can set SameSite for an <xref:System.Web.HttpCookie> object as follows:</span></span>

```csharp
var c = new HttpCookie("secureCookie", "same origin");
c.SameSite = SameSiteMode.Lax;
```

```vb
Dim c As New HttpCookie("secureCookie", "same origin")
c.SameSite = SameSiteMode.Lax
```

<span data-ttu-id="9bae0-283">또한 web.config 파일을 수정하여 애플리케이션 수준에서 SameSite 쿠키를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-283">You can also configure SameSite cookies at the application level by modifying the web.config file:</span></span>

```xml
<system.web>
   <httpCookies sameSite="Strict" />
</system.web>
```

<span data-ttu-id="9bae0-284">또한 웹 구성 파일을 수정하여 <xref:System.Web.Security.FormsAuthentication> 및 <xref:System.Web.SessionState> 쿠키에 대한 SameSite를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-284">You can add SameSite for <xref:System.Web.Security.FormsAuthentication> and <xref:System.Web.SessionState> cookies by modifying the web config file:</span></span>

```xml
<system.web>
   <authentication mode="Forms">
      <forms cookieSameSite="Lax">
         <!-- ...   -->
      </forms>
   </authentication>
   <sessionState cookieSameSite="Lax"></sessionState>
</system.web>
```

<a name="net472"></a>

#### <a name="networking"></a><span data-ttu-id="9bae0-285">네트워킹</span><span class="sxs-lookup"><span data-stu-id="9bae0-285">Networking</span></span>

<span data-ttu-id="9bae0-286">**HttpClientHandler 속성의 구현**</span><span class="sxs-lookup"><span data-stu-id="9bae0-286">**Implementation of HttpClientHandler properties**</span></span>

<span data-ttu-id="9bae0-287">.NET Framework 4.7.1에서는 8가지 속성을 <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> 클래스에 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-287">.NET Framework 4.7.1 added eight properties to the <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="9bae0-288">단, 두 가지 속성은 <xref:System.PlatformNotSupportedException>을 throw했습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-288">However, two threw a <xref:System.PlatformNotSupportedException>.</span></span> <span data-ttu-id="9bae0-289">이제 .NET Framework 4.7.2는 이 속성에 대한 구현을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-289">.NET Framework 4.7.2 now provides an implementation for these properties.</span></span> <span data-ttu-id="9bae0-290">속성은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-290">The properties are:</span></span>

- <xref:System.Net.Http.HttpClientHandler.CheckCertificateRevocationList>
- <xref:System.Net.Http.HttpClientHandler.SslProtocols>

<a name="sql472"></a>

#### <a name="sqlclient"></a><span data-ttu-id="9bae0-291">SQLClient</span><span class="sxs-lookup"><span data-stu-id="9bae0-291">SQLClient</span></span>

<span data-ttu-id="9bae0-292">**Azure Active Directory 유니버설 인증 및 다단계 인증에 대한 지원**</span><span class="sxs-lookup"><span data-stu-id="9bae0-292">**Support for Azure Active Directory Universal Authentication and Multi-Factor authentication**</span></span>

<span data-ttu-id="9bae0-293">높아지는 규정 준수 및 보안 요구에 따라 많은 고객들은 MFA(다단계 인증)를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-293">Growing compliance and security demands require that many customers use multi-factor authentication (MFA).</span></span> <span data-ttu-id="9bae0-294">또한 현재 모범 사례들은 연결 문자열에서 직접 사용자 암호를 포함하는 것을 배제합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-294">In addition, current best practices discourage including user passwords directly in connection strings.</span></span> <span data-ttu-id="9bae0-295">이 변경 내용을 지원하기 위해 .NET Framework 4.7.2는 기존 “인증” 키워드가 MFA 및 [Azure AD 인증](/azure/sql-database/sql-database-aad-authentication-configure)을 지원하도록 새로운 값인 “Active Directory 대화형”을 추가하여 [SQLClient 연결 문자열](xref:System.Data.SqlClient.SqlConnection.ConnectionString)을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-295">To support these changes, .NET Framework 4.7.2 extends [SQLClient connection strings](xref:System.Data.SqlClient.SqlConnection.ConnectionString) by adding a new value, "Active Directory Interactive", for the existing "Authentication" keyword to support MFA and [Azure AD Authentication](/azure/sql-database/sql-database-aad-authentication-configure).</span></span> <span data-ttu-id="9bae0-296">새로운 대화형 메서드는 Azure AD 게스트 사용자와 함께 네이티브 및 페더레이션 Azure AD 사용자를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-296">The new interactive method supports native and federated Azure AD users as well as Azure AD guest users.</span></span> <span data-ttu-id="9bae0-297">이 메서드를 사용하는 경우 Azure AD에서 도입된 MFA 인증은 SQL 데이터베이스에 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-297">When this method is used, the MFA authentication imposed by Azure AD is supported for SQL databases.</span></span> <span data-ttu-id="9bae0-298">또한 인증 프로세스에는 보안 모범 사례에 적합한 사용자 암호가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-298">In addition, the authentication process requests a user password to adhere to security best practices.</span></span>

<span data-ttu-id="9bae0-299">이전 버전의 .NET Framework에서 SQL 연결은 <xref:System.Data.SqlClient.SqlAuthenticationMethod.ActiveDirectoryPassword?displayProperty=nameWithType> 및 <xref:System.Data.SqlClient.SqlAuthenticationMethod.ActiveDirectoryIntegrated?displayProperty=nameWithType> 옵션만 지원했습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-299">In previous versions of .NET Framework, SQL connectivity supported only the <xref:System.Data.SqlClient.SqlAuthenticationMethod.ActiveDirectoryPassword?displayProperty=nameWithType> and <xref:System.Data.SqlClient.SqlAuthenticationMethod.ActiveDirectoryIntegrated?displayProperty=nameWithType> options.</span></span> <span data-ttu-id="9bae0-300">이 두 가지는 모두 비대화형 [ADAL 프로토콜](/azure/active-directory/develop/active-directory-authentication-libraries)의 일부로 MFA를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-300">Both of these are part of the non-interactive [ADAL protocol](/azure/active-directory/develop/active-directory-authentication-libraries), which does not support MFA.</span></span> <span data-ttu-id="9bae0-301">새 <xref:System.Data.SqlClient.SqlAuthenticationMethod.ActiveDirectoryInteractive?displayProperty=nameWithType> 옵션을 사용하면 SQL 연결은 기존 인증 방법(암호 및 통합된 인증)과 함께 MFA를 지원하므로 연결 문자열에 암호를 유지할 필요 없이 사용자가 사용자 암호를 대화형으로 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-301">With the new <xref:System.Data.SqlClient.SqlAuthenticationMethod.ActiveDirectoryInteractive?displayProperty=nameWithType> option, SQL connectivity supports MFA as well as existing authentication methods (password and integrated authentication), which allows users to enter user passwords interactively without persisting passwords in the connection string.</span></span>

<span data-ttu-id="9bae0-302">자세한 내용 및 예제는 [.NET 블로그](https://devblogs.microsoft.com/dotnet/net-framework-4-7-2-developer-pack-early-access-build-3056-is-available/)의 “SQL -- Azure AD 유니버설 및 다단계 인증 지원”을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bae0-302">For more information and an example, see "SQL -- Azure AD Universal and Multi-factor Authentication Support" in the [.NET Blog](https://devblogs.microsoft.com/dotnet/net-framework-4-7-2-developer-pack-early-access-build-3056-is-available/).</span></span>

<span data-ttu-id="9bae0-303">**Always Encrypted 버전 2에 대한 지원**</span><span class="sxs-lookup"><span data-stu-id="9bae0-303">**Support for Always Encrypted version 2**</span></span>

<span data-ttu-id="9bae0-304">.NET Framework 4.7.2는 enclave 기반 Always Encrypted에 대한 지원을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-304">NET Framework 4.7.2 adds supports for enclave-based Always Encrypted.</span></span> <span data-ttu-id="9bae0-305">Always Encrypted의 원래 버전은 암호화 키가 항상 클라이언트에게 있는 클라이언트 쪽 암호화 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-305">The original version of Always Encrypted is a client-side encryption technology in which encryption keys never leave the client.</span></span> <span data-ttu-id="9bae0-306">enclave 기반 Always Encrypted에서는 클라이언트가 SQL Server의 일부로 간주될 수 있으나 조작할 수는 없는 보안 계산 항목인 보안 enclave에 암호화 키를 선택적으로 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-306">In enclave-based Always Encrypted, the client can optionally send the encryption keys to a secure enclave, which is a secure computational entity that can be considered part of SQL Server but that SQL Server code cannot tamper with.</span></span> <span data-ttu-id="9bae0-307">enclave 기반 Always Encrypted를 지원하기 위해 .NET Framework 4.7.2는 다음과 같은 형식 및 멤버를 <xref:System.Data.SqlClient> 네임스페이스에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-307">To support enclave-based Always Encrypted, .NET Framework 4.7.2 adds the following types and members to the <xref:System.Data.SqlClient> namespace:</span></span>

- <span data-ttu-id="9bae0-308"><xref:System.Data.SqlClient.SqlConnectionStringBuilder.EnclaveAttestationUrl?displayProperty=nameWithType> - enclave 기반 Always Encrypted에 대한 URI를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-308"><xref:System.Data.SqlClient.SqlConnectionStringBuilder.EnclaveAttestationUrl?displayProperty=nameWithType>, which specifies the Uri for enclave-based Always Encrypted.</span></span>

- <span data-ttu-id="9bae0-309"><xref:System.Data.SqlClient.SqlColumnEncryptionEnclaveProvider> - 모든 enclave 공급자가 파생되는 추상 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-309"><xref:System.Data.SqlClient.SqlColumnEncryptionEnclaveProvider>, which is an abstract class from which all enclave providers are derived.</span></span>

- <span data-ttu-id="9bae0-310"><xref:System.Data.SqlClient.SqlEnclaveSession> - 주어진 enclave 세션에 대한 상태를 캡슐화합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-310"><xref:System.Data.SqlClient.SqlEnclaveSession>, which encapsulates the state for a given enclave session.</span></span>

- <span data-ttu-id="9bae0-311"><xref:System.Data.SqlClient.SqlEnclaveAttestationParameters> - 특정 증명 프로토콜을 실행하는 데 필요한 정보를 얻기 위해 SQL Server에서 사용하는 증명 매개 변수를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-311"><xref:System.Data.SqlClient.SqlEnclaveAttestationParameters>, which provides the attestation parameters used by SQL Server to get information required to execute a particular Attestation Protocol.</span></span>

<span data-ttu-id="9bae0-312">그런 다음, 애플리케이션 구성 파일에서 enclave 공급자에 대한 기능을 제공하는 추상 <xref:System.Data.SqlClient.SqlColumnEncryptionEnclaveProvider?displayProperty=nameWithType> 클래스의 구체적인 구현을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-312">The application configuration file then specifies a concrete implementation of the abstract <xref:System.Data.SqlClient.SqlColumnEncryptionEnclaveProvider?displayProperty=nameWithType> class that provides the functionality for the enclave provider.</span></span> <span data-ttu-id="9bae0-313">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="9bae0-313">For example:</span></span>

```xml
<configuration>
  <configSections>
    <section name="SqlColumnEncryptionEnclaveProviders" type="System.Data.SqlClient.SqlColumnEncryptionEnclaveProviderConfigurationSection,System.Data,Version=4.0.0.0,Culture=neutral,PublicKeyToken=b77a5c561934e089"/>
  </configSections>
  <SqlColumnEncryptionEnclaveProviders>
    <providers>
      <add name="Azure" type="Microsoft.SqlServer.Management.AlwaysEncrypted.AzureEnclaveProvider,MyApp"/>
      <add name="HGS" type="Microsoft.SqlServer.Management.AlwaysEncrypted.HGSEnclaveProvider,MyApp" />
    </providers>
  </SqlColumnEncryptionEnclaveProviders >
</configuration>
```

<span data-ttu-id="9bae0-314">enclave 기반 Always Encrypted의 기본 흐름은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-314">The basic flow of enclave-based Always Encrypted is:</span></span>

1. <span data-ttu-id="9bae0-315">사용자가 enclave 기반 Always Encrypted를 지원하는 SQL Server에 대한 AlwaysEncrypted 연결을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-315">The user creates an AlwaysEncrypted connection to SQL Server that supported enclave-based Always Encrypted.</span></span> <span data-ttu-id="9bae0-316">올바른 enclave에 연결되도록 드라이버가 증명 서비스에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-316">The driver contacts the attestation service to ensure that it is connecting to right enclave.</span></span>

1. <span data-ttu-id="9bae0-317">일단 enclave가 증명되면 드라이버가 SQL Server에서 호스트된 보안 enclave를 사용하는 보안 채널을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-317">Once the enclave has been attested, the driver establishes a secure channel with the secure enclave hosted on SQL Server.</span></span>

1. <span data-ttu-id="9bae0-318">드라이버는 SQL 연결 기간 동안 보안 enclave와 클라이언트에서 승인한 암호화 키를 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-318">The driver shares encryption keys authorized by the client with the secure enclave for the duration of the SQL connection.</span></span>

<a name="wpf472"></a>

#### <a name="windows-presentation-foundation"></a><span data-ttu-id="9bae0-319">Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="9bae0-319">Windows Presentation Foundation</span></span>

<span data-ttu-id="9bae0-320">**원본 제공 ResourceDictionaries 찾기**</span><span class="sxs-lookup"><span data-stu-id="9bae0-320">**Finding ResourceDictionaries by Source**</span></span>

<span data-ttu-id="9bae0-321">.NET Framework 4.7.2부터 진단 도우미는 지정된 소스 URI에서 만든 <xref:System.Windows.Xps.Packaging.IXpsFixedPageReader.ResourceDictionaries>를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-321">Starting with .NET Framework 4.7.2, a diagnostic assistant can locate the <xref:System.Windows.Xps.Packaging.IXpsFixedPageReader.ResourceDictionaries> that have been created from a given source Uri.</span></span> <span data-ttu-id="9bae0-322"> (이는 프로덕션 애플리케이션이 아닌 진단 도우미에서 사용하기 위한 기능입니다.) 사용자는 Visual Studio의 “편집하며 계속하기” 기능과 같은 진단 도우미를 사용하면 변경 사항이 실행 중인 애플리케이션에 적용될 수 있도록 ResourceDictionary를 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-322">(This feature is for use by diagnostic assistants, not by production applications.) A diagnostic assistant such as Visual Studio's "Edit-and-Continue" facility lets its user edit a ResourceDictionary with the intent that the changes be applied to the running application.</span></span> <span data-ttu-id="9bae0-323">이를 수행하기 위한 한 단계는 실행 중인 애플리케이션이 편집 중인 사전에서 만든 모든 ResourceDictionaries를 찾는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-323">One step in achieving this is finding all the ResourceDictionaries that the running application has created from the dictionary that's being edited.</span></span> <span data-ttu-id="9bae0-324">예를 들어 애플리케이션이 지정된 원본 URI에서 해당 콘텐츠가 복사된 ResourceDictionary를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-324">For example, an application can declare a ResourceDictionary whose content is copied from a given source URI:</span></span>

```xml
<ResourceDictionary Source="MyRD.xaml" />
```

<span data-ttu-id="9bae0-325">*MyRD.xaml* 에서 원래 태그를 편집하는 진단 도우미는 새로운 기능을 사용하여 사전을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-325">A diagnostic assistant that edits the original markup in *MyRD.xaml* can use the new feature to locate the dictionary.</span></span> <span data-ttu-id="9bae0-326"> 이 기능은 새 정적 메서드인 <xref:System.Windows.Diagnostics.ResourceDictionaryDiagnostics.GetResourceDictionariesForSource%2A?displayProperty=nameWithType>에서 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-326">The feature is implemented by a new static method, <xref:System.Windows.Diagnostics.ResourceDictionaryDiagnostics.GetResourceDictionariesForSource%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="9bae0-327">다음 코드에 표시된 것처럼 진단 도우미는 원래 태그를 식별하는 절대 URI를 사용하여 새 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-327">The diagnostic assistant calls the new method using an absolute Uri that identifies the original markup, as illustrated by the following code:</span></span>

```csharp
IEnumerable<ResourceDictionary> dictionaries = ResourceDictionaryDiagnostics.GetResourceDictionariesForSource(new Uri("pack://application:,,,/MyApp;component/MyRD.xaml"));
```

```vb
Dim dictionaries As IEnumerable(Of ResourceDictionary) = ResourceDictionaryDiagnostics.GetResourceDictionariesForSource(New Uri("pack://application:,,,/MyApp;component/MyRD.xaml"))
```

<span data-ttu-id="9bae0-328">메서드는 <xref:System.Windows.Diagnostics.VisualDiagnostics>가 활성화되고 [`ENABLE_XAML_DIAGNOSTICS_SOURCE_INFO`](xref:System.Windows.Diagnostics.VisualDiagnostics.GetXamlSourceInfo%2A) 환경 변수가 설정된 경우 외에는 빈 열거를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-328">The method returns an empty enumerable unless <xref:System.Windows.Diagnostics.VisualDiagnostics> is enabled and the [`ENABLE_XAML_DIAGNOSTICS_SOURCE_INFO`](xref:System.Windows.Diagnostics.VisualDiagnostics.GetXamlSourceInfo%2A) environment variable is set.</span></span>

<span data-ttu-id="9bae0-329">**ResourceDictionary 소유자 찾기**</span><span class="sxs-lookup"><span data-stu-id="9bae0-329">**Finding ResourceDictionary owners**</span></span>

<span data-ttu-id="9bae0-330">.NET Framework 4.7.2부터 진단 도우미는 지정된 <xref:Windows.UI.Xaml.ResourceDictionary>의 소유자를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-330">Starting with .NET Framework 4.7.2, a diagnostic assistant can locate the owners of a given <xref:Windows.UI.Xaml.ResourceDictionary>.</span></span> <span data-ttu-id="9bae0-331"> (이는 프로덕션 애플리케이션이 아닌 진단 도우미에서 사용하기 위한 기능입니다.) <xref:Windows.UI.Xaml.ResourceDictionary>를 변경할 때마다 WPF는 변경 사항의 영향을 받을 수도 있는 모든 [DynamicResource](/dotnet/desktop/wpf/advanced/dynamicresource-markup-extension) 참조를 자동으로 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-331">(The feature is for use by diagnostic assistants and not by production applications.) Whenever a change is made to a <xref:Windows.UI.Xaml.ResourceDictionary>, WPF automatically finds all [DynamicResource](/dotnet/desktop/wpf/advanced/dynamicresource-markup-extension) references that might be affected by the change.</span></span>

<span data-ttu-id="9bae0-332">Visual Studio의 “편집하며 계속하기” 기능과 같은 진단 도우미는 [StaticResource](/dotnet/desktop/wpf/advanced/staticresource-markup-extension) 참조를 처리하기 위해 이를 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-332">A diagnostic assistant such as Visual Studio's "Edit-and-Continue" facility may want to extend this to handle [StaticResource](/dotnet/desktop/wpf/advanced/staticresource-markup-extension) references.</span></span> <span data-ttu-id="9bae0-333">이 프로세스의 첫 번째 단계는 사전의 소유자를 찾는 것입니다. 즉, `Resources` 속성이 사전을 참조하는 모든 개체를 찾습니다(<xref:System.Windows.ResourceDictionary.MergedDictionaries?displayProperty=nameWithType> 속성을 통해 직접 또는 간접적).</span><span class="sxs-lookup"><span data-stu-id="9bae0-333">The first step in this process is to find the owners of the dictionary; that is, to find all the objects whose `Resources` property refers to the dictionary (either directly, or indirectly via the <xref:System.Windows.ResourceDictionary.MergedDictionaries?displayProperty=nameWithType> property).</span></span> <span data-ttu-id="9bae0-334">`Resources` 속성이 있는 각 기본 형식을 위한 <xref:System.Windows.Diagnostics.ResourceDictionaryDiagnostics?displayProperty=nameWithType> 클래스에서 구현된 세 개의 새로운 정적 메서드는 이 단계를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-334">Three new static methods implemented on the <xref:System.Windows.Diagnostics.ResourceDictionaryDiagnostics?displayProperty=nameWithType> class, one for each of the base types that has a `Resources` property, support this step:</span></span>

- [`public static IEnumerable<FrameworkElement> GetFrameworkElementOwners(ResourceDictionary dictionary);`](xref:System.Windows.Diagnostics.ResourceDictionaryDiagnostics.GetFrameworkElementOwners%2A)

- [`public static IEnumerable<FrameworkContentElement> GetFrameworkContentElementOwners(ResourceDictionary dictionary);`](xref:System.Windows.Diagnostics.ResourceDictionaryDiagnostics.GetFrameworkContentElementOwners%2A)

- [`public static IEnumerable<Application> GetApplicationOwners(ResourceDictionary dictionary);`](xref:System.Windows.Diagnostics.ResourceDictionaryDiagnostics.GetApplicationOwners%2A)

<span data-ttu-id="9bae0-335">이러한 메서드는 <xref:System.Windows.Diagnostics.VisualDiagnostics>가 활성화되고 [`ENABLE_XAML_DIAGNOSTICS_SOURCE_INFO`](xref:System.Windows.Diagnostics.VisualDiagnostics.GetXamlSourceInfo%2A) 환경 변수가 설정된 경우 외에는 빈 열거를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-335">These methods return an empty enumerable unless <xref:System.Windows.Diagnostics.VisualDiagnostics> is enabled and the [`ENABLE_XAML_DIAGNOSTICS_SOURCE_INFO`](xref:System.Windows.Diagnostics.VisualDiagnostics.GetXamlSourceInfo%2A) environment variable is set.</span></span>

<span data-ttu-id="9bae0-336">**StaticResource 참조 찾기**</span><span class="sxs-lookup"><span data-stu-id="9bae0-336">**Finding StaticResource references**</span></span>

<span data-ttu-id="9bae0-337">이제 진단 도우미는 [StaticResource](/dotnet/desktop/wpf/advanced/staticresource-markup-extension) 참조가 확인될 때마다 알림을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-337">A diagnostic assistant can now receive a notification whenever a [StaticResource](/dotnet/desktop/wpf/advanced/staticresource-markup-extension) reference is resolved.</span></span> <span data-ttu-id="9bae0-338"> (이는 프로덕션 애플리케이션이 아닌 진단 도우미에서 사용하기 위한 기능입니다.) Visual Studio의 “편집하며 계속하기” 기능과 같은 진단 도우미는 해당 값이 <xref:Windows.UI.Xaml.ResourceDictionary> 변경 내용에 포함된 경우 리소스의 모든 사용을 업데이트해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-338">(The feature is for use by diagnostic assistants, not by production applications.) A diagnostic assistant such as Visual Studio's "Edit-and-Continue" facility may want to update all uses of a resource when its value in a <xref:Windows.UI.Xaml.ResourceDictionary> changes.</span></span> <span data-ttu-id="9bae0-339">WPF는 [DynamicResource](/dotnet/desktop/wpf/advanced/dynamicresource-markup-extension) 참조에 대해 이를 자동으로 수행하지만, [StaticResource](/dotnet/desktop/wpf/advanced/staticresource-markup-extension) 참조에 대해서는 의도적으로 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-339">WPF does this automatically for [DynamicResource](/dotnet/desktop/wpf/advanced/dynamicresource-markup-extension) references, but it intentionally does not do so for [StaticResource](/dotnet/desktop/wpf/advanced/staticresource-markup-extension) references.</span></span> <span data-ttu-id="9bae0-340">.NET Framework 4.7.2부터 진단 도우미는 이 알림을 사용하여 정적 리소스의 해당 사용을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-340">Starting with .NET Framework 4.7.2, the diagnostic assistant can use these notifications to locate those uses of the static resource.</span></span>

<span data-ttu-id="9bae0-341">알림은 새로운 <xref:System.Windows.Diagnostics.ResourceDictionaryDiagnostics.StaticResourceResolved?displayProperty=nameWithType> 이벤트에 의해 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-341">The notification is implemented by the new <xref:System.Windows.Diagnostics.ResourceDictionaryDiagnostics.StaticResourceResolved?displayProperty=nameWithType> event:</span></span>

```csharp
public static event EventHandler<StaticResourceResolvedEventArgs> StaticResourceResolved;
```

```vb
Public Shared Event StaticResourceResolved As EventHandler(Of StaticResourceResolvedEventArgs)
```

<span data-ttu-id="9bae0-342">이 이벤트는 런타임이 [StaticResource](/dotnet/desktop/wpf/advanced/staticresource-markup-extension) 참조를 확인할 때마다 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-342">This event is raised whenever the runtime resolves a [StaticResource](/dotnet/desktop/wpf/advanced/staticresource-markup-extension) reference.</span></span> <span data-ttu-id="9bae0-343"><xref:System.Windows.Diagnostics.StaticResourceResolvedEventArgs> 인수는 해상도를 설명하고 [StaticResource](/dotnet/desktop/wpf/advanced/staticresource-markup-extension) 참조를 호스트하는 개체 및 속성과 해상도에 사용되는 <xref:Windows.UI.Xaml.ResourceDictionary> 및 키를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-343">The <xref:System.Windows.Diagnostics.StaticResourceResolvedEventArgs> arguments describe the resolution, and indicate the object and property that host the [StaticResource](/dotnet/desktop/wpf/advanced/staticresource-markup-extension) reference and the <xref:Windows.UI.Xaml.ResourceDictionary> and key used for the resolution:</span></span>

```csharp
public class StaticResourceResolvedEventArgs : EventArgs
{
   public Object TargetObject { get; }

   public Object TargetProperty { get; }

   public ResourceDictionary ResourceDictionary { get; }

   public object ResourceKey { get; }
}
```

```vb
Public Class StaticResourceResolvedEventArgs : Inherits EventArgs
   Public ReadOnly Property TargetObject As Object
   Public ReadOnly Property TargetProperty As Object
   Public ReadOnly Property ResourceDictionary As ResourceDictionary
   Public ReadOnly Property ResourceKey As Object
End Class
```

<span data-ttu-id="9bae0-344">이벤트는 <xref:System.Windows.Diagnostics.VisualDiagnostics>가 활성화되고 [`ENABLE_XAML_DIAGNOSTICS_SOURCE_INFO`](xref:System.Windows.Diagnostics.VisualDiagnostics.GetXamlSourceInfo%2A) 환경 변수가 설정된 경우 외에는 발생하지 않습니다(및 해당 `add` 접근자는 무시됨).</span><span class="sxs-lookup"><span data-stu-id="9bae0-344">The event is not raised (and its `add` accessor is ignored) unless <xref:System.Windows.Diagnostics.VisualDiagnostics> is enabled and the [`ENABLE_XAML_DIAGNOSTICS_SOURCE_INFO`](xref:System.Windows.Diagnostics.VisualDiagnostics.GetXamlSourceInfo%2A) environment variable is set.</span></span>

#### <a name="clickonce"></a><span data-ttu-id="9bae0-345">ClickOnce</span><span class="sxs-lookup"><span data-stu-id="9bae0-345">ClickOnce</span></span>

<span data-ttu-id="9bae0-346">Windows Forms, WPF(Windows Presentation Foundation) 및 VSTO(Visual Studio Tools for Office)에 대한 HDPI 인식 애플리케이션은 모두 ClickOnce를 사용하여 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-346">HDPI-aware applications for Windows Forms, Windows Presentation Foundation (WPF), and Visual Studio Tools for Office (VSTO) can all be deployed by using ClickOnce.</span></span> <span data-ttu-id="9bae0-347">다음 항목이 애플리케이션 매니페스트에 있으면 .NET Framework 4.7.2에서 배포에 성공합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-347">If the following entry is found in the application manifest, deployment will succeed under .NET Framework 4.7.2:</span></span>

```xml
<windowsSettings>
   <dpiAware xmlns="http://schemas.microsoft.com/SMI/2005/WindowsSettings">true</dpiAware>
</windowsSettings>
```

<span data-ttu-id="9bae0-348">Windows Forms 애플리케이션의 경우 애플리케이션 매니페스트가 아닌 애플리케이션 구성 파일에서 DPI 인식을 설정하는 이전 해결책은 성공적인 ClickOnce 배포에 더 이상 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-348">For Windows Forms application, the previous workaround of setting DPI awareness in the application configuration file rather than the application manifest is no longer necessary for ClickOnce deployment to succeed.</span></span>

<a name="v471"></a>

## <a name="whats-new-in-net-framework-471"></a><span data-ttu-id="9bae0-349">.NET Framework 4.7.1의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="9bae0-349">What's new in .NET Framework 4.7.1</span></span>

<span data-ttu-id="9bae0-350">.NET Framework 4.7.1에는 다음 영역의 새 기능이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-350">.NET Framework 4.7.1 includes new features in the following areas:</span></span>

- [<span data-ttu-id="9bae0-351">기본 클래스</span><span class="sxs-lookup"><span data-stu-id="9bae0-351">Base classes</span></span>](#core471)
- [<span data-ttu-id="9bae0-352">CLR(공용 언어 런타임)</span><span class="sxs-lookup"><span data-stu-id="9bae0-352">Common language runtime (CLR)</span></span>](#clr)
- [<span data-ttu-id="9bae0-353">네트워킹</span><span class="sxs-lookup"><span data-stu-id="9bae0-353">Networking</span></span>](#net471)
- [<span data-ttu-id="9bae0-354">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="9bae0-354">ASP.NET</span></span>](#asp-net471)

<span data-ttu-id="9bae0-355">또한 .NET Framework 4.7.1은 내게 필요한 옵션 기능을 개선하는 데 주력하여 애플리케이션이 보조 기술 사용자에게 적절한 환경을 제공할 수 있도록 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-355">In addition, a major focus in .NET Framework 4.7.1 is improved accessibility, which allows an application to provide an appropriate experience for users of Assistive Technology.</span></span> <span data-ttu-id="9bae0-356">.NET Framework 4.7.1에서 내게 필요한 옵션의 기능 향상에 대한 자세한 내용은 [.NET Framework의 내게 필요한 옵션의 새로운 기능](whats-new-in-accessibility.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bae0-356">For information on accessibility improvements in .NET Framework 4.7.1, see [What's new in accessibility in .NET Framework](whats-new-in-accessibility.md).</span></span>

<a name="core471"></a>

#### <a name="base-classes"></a><span data-ttu-id="9bae0-357">기본 클래스</span><span class="sxs-lookup"><span data-stu-id="9bae0-357">Base classes</span></span>

<span data-ttu-id="9bae0-358">**.NET Standard 2.0에 대한 지원**</span><span class="sxs-lookup"><span data-stu-id="9bae0-358">**Support for .NET Standard 2.0**</span></span>

<span data-ttu-id="9bae0-359">[.NET Standard](../../standard/net-standard.md)는 해당 버전의 표준을 지원하는 각 .NET 구현에서 사용할 수 있어야 하는 API 집합을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-359">[.NET Standard](../../standard/net-standard.md) defines a set of APIs that must be available on each .NET implementation that supports that version of the standard.</span></span> <span data-ttu-id="9bae0-360">.NET Framework 4.7.1은 .NET Standard 2.0을 완전히 지원하며 .NET Standard 2.0에 정의되어 있지만 .NET Framework 4.6.1, 4.6.2 및 4.7에서는 제공하지 않았던 [약 200개의 API](https://github.com/dotnet/standard/blob/master/src/netstandard/src/ApiCompatBaseline.net461.txt)를 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-360">.NET Framework 4.7.1 fully supports .NET Standard 2.0 and adds [about 200 APIs](https://github.com/dotnet/standard/blob/master/src/netstandard/src/ApiCompatBaseline.net461.txt) that are defined in .NET Standard 2.0 and are missing from .NET Framework 4.6.1, 4.6.2, and 4.7.</span></span> <span data-ttu-id="9bae0-361">(이러한 .NET Framework 버전은 대상 시스템에 추가적인 .NET Standard 지원 파일도 배포된 경우에만 .NET Standard 2.0을 지원합니다.) 자세한 내용은 [.NET Framework 4.7.1 Runtime and Compiler Features](https://devblogs.microsoft.com/dotnet/net-framework-4-7-1-runtime-and-compiler-features/)(.NET Framework 4.7.1 런타임 및 컴파일러 기능) 블로그 게시물의 "BCL - .NET Standard 2.0 Support"(BCL - .NET Standard 2.0 지원)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bae0-361">(Note that these versions of .NET Framework support .NET Standard 2.0 only if additional .NET Standard support files are also deployed on the target system.) For more information, see "BCL - .NET Standard 2.0 Support" in the [.NET Framework 4.7.1 Runtime and Compiler Features](https://devblogs.microsoft.com/dotnet/net-framework-4-7-1-runtime-and-compiler-features/) blog post.</span></span>

<span data-ttu-id="9bae0-362">**구성 작성기에 대한 지원**</span><span class="sxs-lookup"><span data-stu-id="9bae0-362">**Support for configuration builders**</span></span>

<span data-ttu-id="9bae0-363">구성 작성기를 사용하여 런타임 시 동적으로 애플리케이션에 대한 구성 설정을 삽입하고 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-363">Configuration builders allow developers to inject and build configuration settings for applications dynamically at run time.</span></span> <span data-ttu-id="9bae0-364">사용자 지정 구성 작성기를 사용하여 구성 섹션에 있는 기존 데이터를 수정하거나 구성 섹션을 처음부터 새로 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-364">Custom configuration builders can be used to modify existing data in a configuration section or to build a configuration section entirely from scratch.</span></span> <span data-ttu-id="9bae0-365">구성 작성기를 사용하지 않으면 .config 파일이 정적이며, 애플리케이션이 시작되기 얼마 전에 해당 파일의 설정이 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-365">Without configuration builders, .config files are static, and their settings are defined some time before an application is launched.</span></span>

<span data-ttu-id="9bae0-366">사용자 지정 구성 작성기를 만들려면 추상 클래스 <xref:System.Configuration.ConfigurationBuilder>에서 작성기를 파생시켜 <xref:System.Configuration.ConfigurationBuilder.ProcessConfigurationSection%2A?displayProperty=nameWithType> 및 <xref:System.Configuration.ConfigurationBuilder.ProcessRawXml%2A?displayProperty=nameWithType>을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-366">To create a custom configuration builder, you derive your builder from the abstract <xref:System.Configuration.ConfigurationBuilder> class and override its <xref:System.Configuration.ConfigurationBuilder.ProcessConfigurationSection%2A?displayProperty=nameWithType> and <xref:System.Configuration.ConfigurationBuilder.ProcessRawXml%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="9bae0-367">또한 .config 파일에 작성기를 정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-367">You also define your builders in your .config file.</span></span> <span data-ttu-id="9bae0-368">자세한 내용은 [.NET Framework 4.7.1 ASP.NET and Configuration Features](https://devblogs.microsoft.com/dotnet/net-framework-4-7-1-asp-net-and-configuration-features/)(.NET Framework 4.7.1 ASP.NET 및 구성 기능) 블로그 게시물의 "Configuration Builders"(구성 작성기) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bae0-368">For more information, see the "Configuration Builders" section in the [.NET Framework 4.7.1 ASP.NET and Configuration Features](https://devblogs.microsoft.com/dotnet/net-framework-4-7-1-asp-net-and-configuration-features/) blog post.</span></span>

<span data-ttu-id="9bae0-369">**런타임 기능 검색**</span><span class="sxs-lookup"><span data-stu-id="9bae0-369">**Run-time feature detection**</span></span>

<span data-ttu-id="9bae0-370"><xref:System.Runtime.CompilerServices.RuntimeFeature?displayProperty=nameWithType> 클래스는 컴파일 시간이나 런타임에 미리 정의된 기능이 지정된 .NET 구현에서 지원되는지 확인하는 메커니즘을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-370">The <xref:System.Runtime.CompilerServices.RuntimeFeature?displayProperty=nameWithType> class provides a mechanism for determine whether a predefined feature is supported on a given .NET implementation at compile time or run time.</span></span> <span data-ttu-id="9bae0-371">컴파일 시간에 컴파일러는 지정된 필드가 존재하는지 확인하여 기능의 지원 여부를 파악합니다. 존재할 경우 해당 기능을 활용하는 코드를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-371">At compile time, a compiler can check whether a specified field exists to determine whether the feature is supported; if so, it can emit code that takes advantage of that feature.</span></span> <span data-ttu-id="9bae0-372">런타임 시 애플리케이션은 <xref:System.Runtime.CompilerServices.RuntimeFeature.IsSupported%2A?displayProperty=nameWithType> 메서드를 호출한 후 런타임에 코드를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-372">At run time, an application can call the <xref:System.Runtime.CompilerServices.RuntimeFeature.IsSupported%2A?displayProperty=nameWithType> method before emitting code at runtime.</span></span> <span data-ttu-id="9bae0-373">자세한 내용은 [런타임에서 지원하는 기능을 설명하는 도우미 메서드 추가](https://github.com/dotnet/corefx/issues/17116)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bae0-373">For more information, see [Add helper method to describe features supported by the runtime](https://github.com/dotnet/corefx/issues/17116).</span></span>

<span data-ttu-id="9bae0-374">**값 튜플 형식 serialize 가능**</span><span class="sxs-lookup"><span data-stu-id="9bae0-374">**Value tuple types are serializable**</span></span>

<span data-ttu-id="9bae0-375">.NET Framework 4.7.1부터 <xref:System.ValueTuple?displayProperty=nameWithType> 및 관련 제네릭 형식은 [Serializable](xref:System.SerializableAttribute)로 표시되며, 이진 serialization을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-375">Starting with .NET Framework 4.7.1, <xref:System.ValueTuple?displayProperty=nameWithType> and its associated generic types are marked as [Serializable](xref:System.SerializableAttribute), which allows binary serialization.</span></span> <span data-ttu-id="9bae0-376">이는 <xref:System.Tuple%603> 및 <xref:System.Tuple%604> 같은 튜플 형식을 값 튜플 형식으로 더 쉽게 마이그레이션할 수 있게 해줍니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-376">This should make migrating Tuple types, such as <xref:System.Tuple%603> and <xref:System.Tuple%604>, to value tuple types easier.</span></span> <span data-ttu-id="9bae0-377">자세한 내용은 [.NET Framework 4.7.1 Runtime and Compiler Features](https://devblogs.microsoft.com/dotnet/net-framework-4-7-1-runtime-and-compiler-features/)(.NET Framework 4.7.1 런타임 및 컴파일러 기능) 블로그 게시물의 "Compiler -- ValueTuple is Serializable"(컴파일러 - 값 튜플 serialize 가능)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bae0-377">For more information, see "Compiler -- ValueTuple is Serializable" in the [.NET Framework 4.7.1 Runtime and Compiler Features](https://devblogs.microsoft.com/dotnet/net-framework-4-7-1-runtime-and-compiler-features/) blog post.</span></span>

<span data-ttu-id="9bae0-378">**읽기 전용 참조에 대한 지원**</span><span class="sxs-lookup"><span data-stu-id="9bae0-378">**Support for read-only references**</span></span>

<span data-ttu-id="9bae0-379">.NET Framework 4.7.1에는 <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute?displayProperty=nameWithType>이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-379">.NET Framework 4.7.1 adds the <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute?displayProperty=nameWithType>.</span></span> <span data-ttu-id="9bae0-380">이 특성은 언어 컴파일러에서 읽기 전용 참조 반환 형식 또는 매개 변수가 있는 멤버를 표시하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-380">This attribute is used by language compilers to mark members that have read-only ref return types or parameters.</span></span> <span data-ttu-id="9bae0-381">자세한 내용은 [.NET Framework 4.7.1 Runtime and Compiler Features](https://devblogs.microsoft.com/dotnet/net-framework-4-7-1-runtime-and-compiler-features/)(.NET Framework 4.7.1 런타임 및 컴파일러 기능) 블로그 게시물의 "Compiler -- Support for ReadOnlyReferences"(컴파일러 - 읽기 전용 참조에 대한 지원)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bae0-381">For more information, see "Compiler -- Support for ReadOnlyReferences" in the [.NET Framework 4.7.1 Runtime and Compiler Features](https://devblogs.microsoft.com/dotnet/net-framework-4-7-1-runtime-and-compiler-features/) blog post.</span></span> <span data-ttu-id="9bae0-382">참조 반환 값에 대한 자세한 내용은 [참조 반환 값 및 참조 로컬(C# 가이드)](../../csharp/programming-guide/classes-and-structs/ref-returns.md) 및 [참조 반환 값(Visual Basic)](../../visual-basic/programming-guide/language-features/procedures/ref-return-values.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bae0-382">For information on ref return values, see [Ref return values and ref locals (C# Guide)](../../csharp/programming-guide/classes-and-structs/ref-returns.md) and [Ref return values (Visual Basic)](../../visual-basic/programming-guide/language-features/procedures/ref-return-values.md).</span></span>

<a name="clr"></a>

#### <a name="common-language-runtime-clr"></a><span data-ttu-id="9bae0-383">CLR(공용 언어 런타임)</span><span class="sxs-lookup"><span data-stu-id="9bae0-383">Common language runtime (CLR)</span></span>

<span data-ttu-id="9bae0-384">**가비지 수집 성능 향상**</span><span class="sxs-lookup"><span data-stu-id="9bae0-384">**Garbage collection performance improvements**</span></span>

<span data-ttu-id="9bae0-385">.NET Framework 4.7.1의 GC(가비지 수집) 기능이 변경되어 전반적인 성능이 개선되었으며, LOH(대형 개체 힙) 할당 성능이 특히 개선되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-385">Changes to garbage collection (GC) in .NET Framework 4.7.1 improve overall performance, especially for large object heap (LOH) allocations.</span></span> <span data-ttu-id="9bae0-386">.NET Framework 4.7.1에서는 SOH(소형 개체 힙) 및 LOH 할당에 별도의 잠금이 사용되므로 백그라운드 GC가 SOH를 비울 때 LOH 할당이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-386">In .NET Framework 4.7.1, separate locks are used for small object heap (SOH) and LOH allocations, which allows LOH allocations to occur when background GC is sweeping the SOH.</span></span> <span data-ttu-id="9bae0-387">따라서 다수의 LOH 할당을 수행하는 애플리케이션은 할당 잠금 경합 감소와 성능 향상 효과를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-387">As a result, applications that make a large number of LOH allocations should see a reduction in allocation lock contention and improved performance.</span></span> <span data-ttu-id="9bae0-388">자세한 내용은 [.NET Framework 4.7.1 Runtime and Compiler Features](https://devblogs.microsoft.com/dotnet/net-framework-4-7-1-runtime-and-compiler-features/)(.NET Framework 4.7.1 런타임 및 컴파일러 기능) 블로그 게시물의 "Runtime -- GC Performance Improvements"(런타임 -- GC 성능 및 개선 사항) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bae0-388">For more information, see the "Runtime -- GC Performance Improvements" section in the [.NET Framework 4.7.1 Runtime and Compiler Features](https://devblogs.microsoft.com/dotnet/net-framework-4-7-1-runtime-and-compiler-features/) blog post.</span></span>

<a name="net471"/>

#### <a name="networking"></a><span data-ttu-id="9bae0-389">네트워킹</span><span class="sxs-lookup"><span data-stu-id="9bae0-389">Networking</span></span>

<span data-ttu-id="9bae0-390">**Message.HashAlgorithm에 대한 SHA-2 지원**</span><span class="sxs-lookup"><span data-stu-id="9bae0-390">**SHA-2 support for Message.HashAlgorithm**</span></span>

<span data-ttu-id="9bae0-391">.NET Framework 4.7 및 이전 버전에서 <xref:System.Messaging.Message.HashAlgorithm%2A?displayProperty=nameWithType> 속성은 <xref:System.Messaging.HashAlgorithm.Md5?displayProperty=nameWithType> 및 <xref:System.Messaging.HashAlgorithm.Sha?displayProperty=nameWithType> 값만 지원했습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-391">In .NET Framework 4.7 and earlier versions, the <xref:System.Messaging.Message.HashAlgorithm%2A?displayProperty=nameWithType> property supported values of <xref:System.Messaging.HashAlgorithm.Md5?displayProperty=nameWithType> and <xref:System.Messaging.HashAlgorithm.Sha?displayProperty=nameWithType> only.</span></span> <span data-ttu-id="9bae0-392">.NET Framework 4.7.1부터는 <xref:System.Messaging.HashAlgorithm.Sha256?displayProperty=nameWithType>, <xref:System.Messaging.HashAlgorithm.Sha384?displayProperty=nameWithType> 및 <xref:System.Messaging.HashAlgorithm.Sha512?displayProperty=nameWithType>도 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-392">Starting with .NET Framework 4.7.1, <xref:System.Messaging.HashAlgorithm.Sha256?displayProperty=nameWithType>, <xref:System.Messaging.HashAlgorithm.Sha384?displayProperty=nameWithType>, and <xref:System.Messaging.HashAlgorithm.Sha512?displayProperty=nameWithType> are also supported.</span></span> <span data-ttu-id="9bae0-393"><xref:System.Messaging.Message> 인스턴스 자체가 해싱을 수행하지는 않지만 MSMQ에 값을 전달하므로 이 값이 실제로 사용되는지 여부는 MSMQ에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-393">Whether this value is actually used depends on MSMQ, since the <xref:System.Messaging.Message> instance itself does no hashing but simply passes on values to MSMQ.</span></span> <span data-ttu-id="9bae0-394">자세한 내용은 [.NET Framework 4.7.1 ASP.NET and Configuration Features](https://devblogs.microsoft.com/dotnet/net-framework-4-7-1-asp-net-and-configuration-features/)(.NET Framework 4.7.1 ASP.NET 및 구성 기능) 블로그 게시물의 "SHA-2 support for Message.HashAlgorithm"(Message.HashAlgorithm에 대한 SHA-2 지원) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bae0-394">For more information, see the "SHA-2 support for Message.HashAlgorithm" section in the [.NET Framework 4.7.1 ASP.NET and Configuration features](https://devblogs.microsoft.com/dotnet/net-framework-4-7-1-asp-net-and-configuration-features/) blog post.</span></span>

<a name="asp-net471"></a>

#### <a name="aspnet"></a><span data-ttu-id="9bae0-395">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="9bae0-395">ASP.NET</span></span>

<span data-ttu-id="9bae0-396">**ASP.NET 애플리케이션의 실행 단계**</span><span class="sxs-lookup"><span data-stu-id="9bae0-396">**Execution steps in ASP.NET applications**</span></span>

<span data-ttu-id="9bae0-397">ASP.NET은 23개 이벤트가 포함된 미리 정의된 파이프라인의 요청을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-397">ASP.NET processes requests in a predefined pipeline that includes 23 events.</span></span> <span data-ttu-id="9bae0-398">ASP.NET은 실행 단계로 각 이벤트 처리기를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-398">ASP.NET executes each event handler as an execution step.</span></span> <span data-ttu-id="9bae0-399">.NET Framework 4.7 이하의 ASP.NET 버전에서는 전용 및 관리 스레드 간의 전환으로 인해 실행 컨텍스트를 진행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-399">In versions of ASP.NET up to .NET Framework 4.7, ASP.NET can't flow the execution context due to switching between native and managed threads.</span></span> <span data-ttu-id="9bae0-400">대신, ASP.NET이 선택적으로 <xref:System.Web.HttpContext>만 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-400">Instead, ASP.NET selectively flows only the <xref:System.Web.HttpContext>.</span></span> <span data-ttu-id="9bae0-401">.NET Framework 4.7.1부터는 <xref:System.Web.HttpApplication.OnExecuteRequestStep(System.Action{System.Web.HttpContextBase,System.Action})?displayProperty=nameWithType> 메서드가 모듈의 앰비언트 데이터 복원도 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-401">Starting with .NET Framework 4.7.1, the <xref:System.Web.HttpApplication.OnExecuteRequestStep(System.Action{System.Web.HttpContextBase,System.Action})?displayProperty=nameWithType> method also allows modules to restore ambient data.</span></span> <span data-ttu-id="9bae0-402">이 기능은 추적, 프로파일링, 진단 또는 트랜잭션과 관련된 라이브러리를 대상으로 합니다(예: 애플리케이션의 실행 흐름 관리).</span><span class="sxs-lookup"><span data-stu-id="9bae0-402">This feature is targeted at libraries concerned with tracing, profiling, diagnostics, or transactions, for example, that care about the execution flow of the application.</span></span> <span data-ttu-id="9bae0-403">자세한 내용은 [.NET Framework 4.7.1 ASP.NET and Configuration Features](https://devblogs.microsoft.com/dotnet/net-framework-4-7-1-asp-net-and-configuration-features/)(.NET Framework 4.7.1 ASP.NET 및 구성 기능) 블로그 게시물의 "ASP.NET Execution Step Feature"(ASP.NET 실행 단계 기능)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bae0-403">For more information, see the "ASP.NET Execution Step Feature" in the [.NET Framework 4.7.1 ASP.NET and Configuration Features](https://devblogs.microsoft.com/dotnet/net-framework-4-7-1-asp-net-and-configuration-features/) blog post.</span></span>

<span data-ttu-id="9bae0-404">**ASP.NET HttpCookie 구문 분석**</span><span class="sxs-lookup"><span data-stu-id="9bae0-404">**ASP.NET HttpCookie parsing**</span></span>

<span data-ttu-id="9bae0-405">.NET Framework 4.7.1에는 문자열에서 <xref:System.Web.HttpCookie> 개체를 만들고 만료 날짜 및 경로와 같은 쿠키 값을 정확하게 할당하는 표준화된 방법을 제공하는 <xref:System.Web.HttpCookie.TryParse%2A?displayProperty=nameWithType>이라는 새로운 메서드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-405">.NET Framework 4.7.1 includes a new method, <xref:System.Web.HttpCookie.TryParse%2A?displayProperty=nameWithType>, that provides a standardized way to create an <xref:System.Web.HttpCookie> object from a string and accurately assign cookie values such as expiration date and path.</span></span> <span data-ttu-id="9bae0-406">자세한 내용은 [.NET Framework 4.7.1 ASP.NET and Configuration Features](https://devblogs.microsoft.com/dotnet/net-framework-4-7-1-asp-net-and-configuration-features/)(.NET Framework 4.7.1 ASP.NET 및 구성 기능) 블로그 게시물의 "ASP.NET HttpCookie parsing"(ASP.NET HttpCookie 구문 분석)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bae0-406">For more information, see "ASP.NET HttpCookie parsing" in the [.NET Framework 4.7.1 ASP.NET and Configuration Features](https://devblogs.microsoft.com/dotnet/net-framework-4-7-1-asp-net-and-configuration-features/) blog post.</span></span>

<span data-ttu-id="9bae0-407">**ASP.NET 양식 인증 자격 증명에 대한 SHA-2 해시 지원**</span><span class="sxs-lookup"><span data-stu-id="9bae0-407">**SHA-2 hash options for ASP.NET forms authentication credentials**</span></span>

<span data-ttu-id="9bae0-408">.NET Framework 4.7 이하 버전에서는 개발자가 MD5 또는 SHA1을 사용하여 구성 파일에 해시 암호와 사용자 자격 증명을 저장할 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-408">In .NET Framework 4.7 and earlier versions, ASP.NET allowed developers to store user credentials with hashed passwords in configuration files using either MD5 or SHA1.</span></span> <span data-ttu-id="9bae0-409">.NET Framework 4.7.1부터 ASP.NET은 SHA256, SHA384 및 SHA512 같은 새로운 보안 SHA-2 해시 옵션도 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-409">Starting with .NET Framework 4.7.1, ASP.NET also supports new secure SHA-2 hash options such as SHA256, SHA384, and SHA512.</span></span> <span data-ttu-id="9bae0-410">SHA1은 기본값을 유지하며, 기본값이 아닌 해시 알고리즘은 웹 구성 파일에 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-410">SHA1 remains the default, and a non-default hash algorithm can be defined in the web configuration file.</span></span> <span data-ttu-id="9bae0-411">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="9bae0-411">For example:</span></span>

```xml
<system.web>
    <authentication mode="Forms">
        <forms loginUrl="~/login.aspx">
          <credentials passwordFormat="SHA512">
            <user name="jdoe" password="6D003E98EA1C7F04ABF8FCB375388907B7F3EE06F278DB966BE960E7CBBD103DF30CA6D61F7E7FD981B2E4E3A64D43C836A4BEDCA165C33B163E6BCDC538A664" />
          </credentials>
        </forms>
    </authentication>
</system.web>
```

<a name="v47"></a>

## <a name="whats-new-in-net-framework-47"></a><span data-ttu-id="9bae0-412">.NET Framework 4.7의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="9bae0-412">What's new in .NET Framework 4.7</span></span>

<span data-ttu-id="9bae0-413">.NET Framework 4.7에는 다음 영역의 새 기능이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-413">.NET Framework 4.7 includes new features in the following areas:</span></span>

- [<span data-ttu-id="9bae0-414">기본 클래스</span><span class="sxs-lookup"><span data-stu-id="9bae0-414">Base classes</span></span>](#Core47)
- [<span data-ttu-id="9bae0-415">네트워킹</span><span class="sxs-lookup"><span data-stu-id="9bae0-415">Networking</span></span>](#net47)
- [<span data-ttu-id="9bae0-416">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="9bae0-416">ASP.NET</span></span>](#ASP-NET47)
- [<span data-ttu-id="9bae0-417">WCF(Windows Communication Foundation)</span><span class="sxs-lookup"><span data-stu-id="9bae0-417">Windows Communication Foundation (WCF)</span></span>](#wcf47)
- [<span data-ttu-id="9bae0-418">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9bae0-418">Windows Forms</span></span>](#wf47)
- [<span data-ttu-id="9bae0-419">WPF(Windows Presentation Foundation)</span><span class="sxs-lookup"><span data-stu-id="9bae0-419">Windows Presentation Foundation (WPF)</span></span>](#WPF47)

<span data-ttu-id="9bae0-420">.NET Framework 4.7에 추가된 새 API 목록은 GitHub에서 [.NET Framework 4.7 API 변경 내용](https://github.com/Microsoft/dotnet/blob/master/releases/net47/dotnet47-api-changes.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bae0-420">For a list of new APIs added to .NET Framework 4.7, see [.NET Framework 4.7 API Changes](https://github.com/Microsoft/dotnet/blob/master/releases/net47/dotnet47-api-changes.md) on GitHub.</span></span> <span data-ttu-id="9bae0-421">.NET Framework 4.7의 향상된 기능 및 버그 수정 목록은 GitHub에서 [.NET Framework 4.7 변경 내용 목록](https://github.com/Microsoft/dotnet/blob/master/releases/net47/dotnet47-changes.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bae0-421">For a list of feature improvements and bug fixes in .NET Framework 4.7, see [.NET Framework 4.7 List of Changes](https://github.com/Microsoft/dotnet/blob/master/releases/net47/dotnet47-changes.md) on GitHub.</span></span> <span data-ttu-id="9bae0-422">자세한 내용은 .NET 블로그에서 [.NET Framework 4.7 알림](https://devblogs.microsoft.com/dotnet/announcing-the-net-framework-4-7/)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bae0-422">For more information, see [Announcing .NET Framework 4.7](https://devblogs.microsoft.com/dotnet/announcing-the-net-framework-4-7/) in the .NET blog.</span></span>

<a name="Core47"></a>

#### <a name="base-classes"></a><span data-ttu-id="9bae0-423">기본 클래스</span><span class="sxs-lookup"><span data-stu-id="9bae0-423">Base classes</span></span>

<span data-ttu-id="9bae0-424">.NET Framework 4.7은 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>를 통해 serialization을 향상합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-424">.NET Framework 4.7 improves serialization by the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>:</span></span>

<span data-ttu-id="9bae0-425">**ECC(타원 곡선 암호화)로 향상된 기능** _</span><span class="sxs-lookup"><span data-stu-id="9bae0-425">**Enhanced functionality with Elliptic Curve Cryptography (ECC)** _</span></span>

<span data-ttu-id="9bae0-426">.NET Framework 4.7에서는 `ImportParameters(ECParameters)` 메서드가 <xref:System.Security.Cryptography.ECDsa> 및 <xref:System.Security.Cryptography.ECDiffieHellman> 클래스에 추가되어 개체에서 이미 설정된 키를 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-426">In .NET Framework 4.7, `ImportParameters(ECParameters)` methods were added to the <xref:System.Security.Cryptography.ECDsa> and <xref:System.Security.Cryptography.ECDiffieHellman> classes to allow for an object to represent an already-established key.</span></span> <span data-ttu-id="9bae0-427">또한 명시적 곡선 매개 변수를 사용하여 키를 내보내기 위한 `ExportParameters(Boolean)` 메서드도 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-427">An `ExportParameters(Boolean)` method was also added for exporting the key using explicit curve parameters.</span></span>

<span data-ttu-id="9bae0-428">그뿐 아니라 .NET Framework 4.7에서는 추가 곡선(Brainpool 곡선 도구 모음 포함)을 지원하며 새로운 <xref:System.Security.Cryptography.ECDsa.Create%2A> 및 <xref:System.Security.Cryptography.ECDiffieHellman.Create%2A> 팩터리 메서드를 통해 쉽게 만들 수 있도록 미리 정의된 정의도 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-428">.NET Framework 4.7 also adds support for additional curves (including the Brainpool curve suite), and has added predefined definitions for ease-of-creation through the new <xref:System.Security.Cryptography.ECDsa.Create%2A> and <xref:System.Security.Cryptography.ECDiffieHellman.Create%2A> factory methods.</span></span>

<span data-ttu-id="9bae0-429">GitHub에서 [.NET Framework 4.7 암호화 개선 예제](https://gist.github.com/richlander/5a182899895a87a296c21ada97f7a54e)를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-429">You can see an [example of .NET Framework 4.7 cryptography improvements](https://gist.github.com/richlander/5a182899895a87a296c21ada97f7a54e) on GitHub.</span></span>

<span data-ttu-id="9bae0-430">_ *DataContractJsonSerializer를 통한 더욱 나은 제어 문자 지원*\*</span><span class="sxs-lookup"><span data-stu-id="9bae0-430">_ *Better support for control characters by the DataContractJsonSerializer*\*</span></span>

<span data-ttu-id="9bae0-431">.NET Framework 4.7에서 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>는 ECMAScript 6 표준에 따라 제어 문자를 serialize합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-431">In .NET Framework 4.7, the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> class serializes control characters in conformity with the ECMAScript 6 standard.</span></span> <span data-ttu-id="9bae0-432">이 동작은 .NET Framework 4.7을 대상으로 하는 애플리케이션에 대해 기본적으로 사용되도록 설정되며, .NET Framework 4.7에서 실행되지만 이전 버전의 .NET Framework를 대상으로 하는 애플리케이션에 대한 옵트인 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-432">This behavior is enabled by default for applications that target .NET Framework 4.7, and is an opt-in feature for applications that are running under .NET Framework 4.7 but target a previous version of .NET Framework.</span></span> <span data-ttu-id="9bae0-433">자세한 내용은 [애플리케이션 호환성](../migration-guide/application-compatibility.md) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bae0-433">For more information, see the [Application compatibility](../migration-guide/application-compatibility.md) section.</span></span>

<a name="net47"></a>

#### <a name="networking"></a><span data-ttu-id="9bae0-434">네트워킹</span><span class="sxs-lookup"><span data-stu-id="9bae0-434">Networking</span></span>

<span data-ttu-id="9bae0-435">.NET Framework 4.7에서는 다음과 같은 네트워크 관련 기능을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-435">.NET Framework 4.7 adds the following network-related feature:</span></span>

<span data-ttu-id="9bae0-436">**TLS 프로토콜에 대한 기본 운영 체제 지원** _</span><span class="sxs-lookup"><span data-stu-id="9bae0-436">**Default operating system support for TLS protocols** _</span></span>

<span data-ttu-id="9bae0-437"><xref:System.Net.Security.SslStream?displayProperty=nameWithType>및 업스택 구성 요소(예: HTTP, FTP, SMTP)에서 사용되는 TLS 스택을 통해 개발자는 운영 체제에서 지원하는 기본 TLS 프로토콜을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-437">The TLS stack, which is used by <xref:System.Net.Security.SslStream?displayProperty=nameWithType> and up-stack components such as HTTP, FTP, and SMTP, allows developers to use the default TLS protocols supported by the operating system.</span></span> <span data-ttu-id="9bae0-438">개발자에게 더 이상 하드 코딩 TLS 버전은 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-438">Developers need no longer hard-code a TLS version.</span></span>

<a name="ASP-NET47"></a>

#### <a name="aspnet"></a><span data-ttu-id="9bae0-439">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="9bae0-439">ASP.NET</span></span>

<span data-ttu-id="9bae0-440">.NET Framework 4.7에서 ASP.NET에는 다음과 같은 새 기능이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-440">In .NET Framework 4.7, ASP.NET includes the following new features:</span></span>

<span data-ttu-id="9bae0-441">_ *개체 캐시 확장성*\*</span><span class="sxs-lookup"><span data-stu-id="9bae0-441">_ *Object Cache Extensibility*\*</span></span>

<span data-ttu-id="9bae0-442">.NET Framework 4.7부터 ASP.NET에서는 개발자가 메모리 내 개체 캐싱 및 메모리 모니터링을 위한 기본 ASP.NET 구현을 대체할 수 있도록 하는 새로운 API 집합을 추가적으로 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-442">Starting with .NET Framework 4.7, ASP.NET adds a new set of APIs that allow developers to replace the default ASP.NET implementations for in-memory object caching and memory monitoring.</span></span> <span data-ttu-id="9bae0-443">개발자는 이제 ASP.NET 구현이 적절하지 않은 경우 다음 세 가지 구성 요소 중 하나를 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-443">Developers can now replace any of the following three components if the ASP.NET implementation is not adequate:</span></span>

- <span data-ttu-id="9bae0-444">**개체 캐시 저장소**.</span><span class="sxs-lookup"><span data-stu-id="9bae0-444">**Object Cache Store**.</span></span> <span data-ttu-id="9bae0-445">개발자는 새 캐시 공급자 구성 섹션에서 새 **ICacheStoreProvider** 인터페이스를 사용하여 ASP.NET 애플리케이션의 새로운 개체 캐시 구현을 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-445">By using the new cache providers configuration section, developers can plug in new implementations of an object cache for an ASP.NET application by using the new **ICacheStoreProvider** interface.</span></span>

- <span data-ttu-id="9bae0-446">**메모리 모니터링**.</span><span class="sxs-lookup"><span data-stu-id="9bae0-446">**Memory monitoring**.</span></span> <span data-ttu-id="9bae0-447">ASP.NET의 기본 메모리 모니터는 프로세스에 대해 구성된 전용 바이트 제한에 가까워지거나 컴퓨터의 사용 가능한 총 실제 RAM이 부족할 때 애플리케이션에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-447">The default memory monitor in ASP.NET notifies applications when they are running close to the configured private bytes limit for the process, or when the machine is low on total available physical RAM.</span></span> <span data-ttu-id="9bae0-448">이러한 제한에 가까워지면 알림이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-448">When these limits are near, notifications are fired.</span></span> <span data-ttu-id="9bae0-449">일부 애플리케이션의 경우 알림이 구성된 제한에 너무 가까운 상태에서 발생하여 제대로 대응하지 못하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-449">For some applications, notifications are fired too close to the configured limits to allow for useful reactions.</span></span> <span data-ttu-id="9bae0-450">개발자는 <xref:System.Web.Hosting.ApplicationMonitors.MemoryMonitor%2A?displayProperty=nameWithType> 속성으로 메모리 모니터를 직접 작성해 기본 모니터를 대체할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-450">Developers can now write their own memory monitors to replace the default by using the <xref:System.Web.Hosting.ApplicationMonitors.MemoryMonitor%2A?displayProperty=nameWithType> property.</span></span>

- <span data-ttu-id="9bae0-451">**메모리 제한 반응**.</span><span class="sxs-lookup"><span data-stu-id="9bae0-451">**Memory Limit Reactions**.</span></span> <span data-ttu-id="9bae0-452">기본적으로 ASP.NET은 전용 바이트 제한에 가까워지면 개체 캐시를 트리밍하고 주기적으로 <xref:System.GC.Collect%2A?displayProperty=nameWithType>를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-452">By default, ASP.NET attempts to trim the object cache and periodically call <xref:System.GC.Collect%2A?displayProperty=nameWithType> when the private byte process limit is near.</span></span> <span data-ttu-id="9bae0-453">일부 애플리케이션의 경우 <xref:System.GC.Collect%2A?displayProperty=nameWithType> 호출 빈도 또는 트리밍되는 캐시 양이 효율적이지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-453">For some applications, the frequency of calls to <xref:System.GC.Collect%2A?displayProperty=nameWithType> or the amount of cache that is trimmed are inefficient.</span></span> <span data-ttu-id="9bae0-454">이제 개발자는 **IObserver** 구현을 애플리케이션의 메모리 모니터에 구독하여 기본 동작을 바꾸거나 보완할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-454">Developers can now replace or supplement the default behavior by subscribing **IObserver** implementations to the application's memory monitor.</span></span>

<a name="wcf47"></a>

#### <a name="windows-communication-foundation-wcf"></a><span data-ttu-id="9bae0-455">WCF(Windows Communication Foundation)</span><span class="sxs-lookup"><span data-stu-id="9bae0-455">Windows Communication Foundation (WCF)</span></span>

<span data-ttu-id="9bae0-456">WCF(Windows Communication Foundation)는 다음과 같은 기능 및 변경 내용을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-456">Windows Communication Foundation (WCF) adds the following features and changes:</span></span>

<span data-ttu-id="9bae0-457">**TLS1.1.1 또는 TLS1.2에 대한 기본 메시지 보안 설정 구성 가능**</span><span class="sxs-lookup"><span data-stu-id="9bae0-457">**Ability to configure the default message security settings to TLS 1.1 or TLS 1.2**</span></span>

<span data-ttu-id="9bae0-458">.NET Framework 4.7부터 WCF에서 SSL 3.0 및 TLS 1.0 외에도 TLS 1.1 또는 TLS 1.2를 기본 메시지 보안 프로토콜로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-458">Starting with .NET Framework 4.7, WCF allows you to configure TLS 1.1 or TLS 1.2 in addition to SSL 3.0 and TLS 1.0 as the default message security protocol.</span></span> <span data-ttu-id="9bae0-459">이것은 옵트인 설정으로 이 기능을 사용하려면 애플리케이션 구성 파일에 다음 항목을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-459">This is an opt-in setting; to enable it, you must add the following entry to your application configuration file:</span></span>

```xml
<runtime>
   <AppContextSwitchOverrides value="Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols=false;Switch.System.Net.DontEnableSchUseStrongCrypto=false" />
</runtime>
```

<span data-ttu-id="9bae0-460">**WCF 애플리케이션 및 WCF serialization의 향상된 안정성**</span><span class="sxs-lookup"><span data-stu-id="9bae0-460">**Improved reliability of WCF applications and WCF serialization**</span></span>

<span data-ttu-id="9bae0-461">WCF에는 경합 상태를 제거하는 다양한 코드 변경 내용이 포함되어 있으므로 serialization 옵션의 성능과 안정성이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-461">WCF includes a number of code changes that eliminate race conditions, thereby improving performance and the reliability of serialization options.</span></span> <span data-ttu-id="9bae0-462">여기에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-462">These include:</span></span>

- <span data-ttu-id="9bae0-463">**SocketConnection.BeginRead** 및 **SocketConnection.Read** 호출에서 보다 향상된 비동기식 및 동기식 코드 혼합</span><span class="sxs-lookup"><span data-stu-id="9bae0-463">Better support for mixing asynchronous and synchronous code in calls to **SocketConnection.BeginRead** and **SocketConnection.Read**.</span></span>
- <span data-ttu-id="9bae0-464">**SharedConnectionListener** 및 **DuplexChannelBinder** 와의 연결 중단 시 안정성 향상</span><span class="sxs-lookup"><span data-stu-id="9bae0-464">Improved reliability when aborting a connection with **SharedConnectionListener** and **DuplexChannelBinder**.</span></span>
- <span data-ttu-id="9bae0-465"><xref:System.Runtime.Serialization.FormatterServices.GetSerializableMembers%28System.Type%29?displayProperty=nameWithType> 메서드를 호출할 때 serialization 작업의 안정성 향상</span><span class="sxs-lookup"><span data-stu-id="9bae0-465">Improved reliability of serialization operations when calling the <xref:System.Runtime.Serialization.FormatterServices.GetSerializableMembers%28System.Type%29?displayProperty=nameWithType> method.</span></span>
- <span data-ttu-id="9bae0-466">**ChannelSynchronizer.RemoveWaiter** 메서드를 호출하여 waiter를 제거할 때 안정성 개선</span><span class="sxs-lookup"><span data-stu-id="9bae0-466">Improved reliability when removing a waiter by calling the **ChannelSynchronizer.RemoveWaiter** method.</span></span>

<a name="wf47"></a>

#### <a name="windows-forms"></a><span data-ttu-id="9bae0-467">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9bae0-467">Windows Forms</span></span>

<span data-ttu-id="9bae0-468">.NET Framework 4.7에서 Windows Forms는 높은 DPI 모니터에 대한 지원을 향상시킵니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-468">In .NET Framework 4.7, Windows Forms improves support for high DPI monitors.</span></span>

<span data-ttu-id="9bae0-469">**높은 DPI 지원**</span><span class="sxs-lookup"><span data-stu-id="9bae0-469">**High DPI support**</span></span>

<span data-ttu-id="9bae0-470">.NET Framework 4.7을 대상으로 하는 애플리케이션부터 .NET Framework는 Windows Forms 애플리케이션에 대한 높은 DPI 및 동적 DPI 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-470">Starting with applications that target .NET Framework 4.7, .NET Framework features high DPI and dynamic DPI support for Windows Forms applications.</span></span> <span data-ttu-id="9bae0-471">높은 DPI 지원은 높은 DPI 모니터에는 폼 및 컨트롤의 모양과 레이아웃을 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-471">High DPI support improves the layout and appearance of forms and controls on high DPI monitors.</span></span> <span data-ttu-id="9bae0-472">동적 DPI는 사용자가 실행 중인 애플리케이션의 DPI 또는 디스플레이 배율을 변경할 때 폼 및 컨트롤의 모양과 레이아웃을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-472">Dynamic DPI changes the layout and appearance of forms and controls when the user changes the DPI or display scale factor of a running application.</span></span>

<span data-ttu-id="9bae0-473">높은 DPI 지원은 애플리케이션 구성 파일의 [\<System.Windows.Forms.ConfigurationSection>](../configure-apps/file-schema/winforms/index.md) 섹션을 정의하여 구성하는 옵트인 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-473">High DPI support is an opt-in feature that you configure by defining a [\<System.Windows.Forms.ConfigurationSection>](../configure-apps/file-schema/winforms/index.md) section in your application configuration file.</span></span> <span data-ttu-id="9bae0-474">Windows Forms 애플리케이션에 높은 DPI 지원 및 동적 DPI 지원을 추가하는 방법에 대한 자세한 내용은 [Windows Forms의 높은 DPI 지원](/dotnet/desktop/winforms/high-dpi-support-in-windows-forms)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bae0-474">For more information on adding high DPI support and dynamic DPI support to your Windows Forms application, see [High DPI Support in Windows Forms](/dotnet/desktop/winforms/high-dpi-support-in-windows-forms).</span></span>

<a name="WPF47"></a>

#### <a name="windows-presentation-foundation-wpf"></a><span data-ttu-id="9bae0-475">WPF(Windows Presentation Foundation)</span><span class="sxs-lookup"><span data-stu-id="9bae0-475">Windows Presentation Foundation (WPF)</span></span>

<span data-ttu-id="9bae0-476">.NET Framework 4.7의 WPF에는 다음과 같은 향상된 기능이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-476">In .NET Framework 4.7, WPF includes the following enhancements:</span></span>

<span data-ttu-id="9bae0-477">**Windows WM_POINTER 메시지 기반의 터치/스타일러스 스택 지원**</span><span class="sxs-lookup"><span data-stu-id="9bae0-477">**Support for a touch/stylus stack based on Windows WM_POINTER messages**</span></span>

<span data-ttu-id="9bae0-478">WISP(Windows 잉크 서비스 플랫폼) 대신 [WM_POINTER 메시지](/previous-versions/windows/desktop/InputMsg/messages) 기반의 터치/스타일러스 스택 사용 옵션이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-478">You now have the option of using a touch/stylus stack based on [WM_POINTER messages](/previous-versions/windows/desktop/InputMsg/messages) instead of the Windows Ink Services Platform (WISP).</span></span> <span data-ttu-id="9bae0-479">이것은 .NET Framework의 옵트인 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-479">This is an opt-in feature in .NET Framework.</span></span> <span data-ttu-id="9bae0-480">자세한 내용은 [애플리케이션 호환성](../migration-guide/application-compatibility.md) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bae0-480">For more information, see the [Application compatibility](../migration-guide/application-compatibility.md) section.</span></span>

<span data-ttu-id="9bae0-481">**WPF 인쇄 API에 대한 새로운 구현**</span><span class="sxs-lookup"><span data-stu-id="9bae0-481">**New implementation for WPF printing APIs**</span></span>

<span data-ttu-id="9bae0-482"><xref:System.Printing.PrintQueue?displayProperty=nameWithType> 클래스의 WPF 인쇄 API는 사용되지 않는 [XPS 인쇄 API](/windows/desktop/printdocs/xps-printing) 대신, Windows [인쇄 문서 패키지 API](/windows/desktop/printdocs/tailored-app-printing-api)를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-482">WPF's printing APIs in the <xref:System.Printing.PrintQueue?displayProperty=nameWithType> class call the Windows [Print Document Package API](/windows/desktop/printdocs/tailored-app-printing-api) instead of the deprecated [XPS Print API](/windows/desktop/printdocs/xps-printing).</span></span> <span data-ttu-id="9bae0-483">이러한 변경 사항이 애플리케이션 호환성에 미치는 영향에 대한 자세한 내용은 [애플리케이션 호환성](../migration-guide/application-compatibility.md) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bae0-483">For the impact of this change on application compatibility, see the [Application compatibility](../migration-guide/application-compatibility.md) section.</span></span>

<a name="v462"></a>

## <a name="whats-new-in-net-framework-462"></a><span data-ttu-id="9bae0-484">.NET Framework 4.6.2의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="9bae0-484">What's new in .NET Framework 4.6.2</span></span>

<span data-ttu-id="9bae0-485">.NET Framework 4.6.2에는 다음 영역의 새 기능이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-485">.NET Framework 4.6.2 includes new features in the following areas:</span></span>

- [<span data-ttu-id="9bae0-486">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="9bae0-486">ASP.NET</span></span>](#ASPNET462)

- [<span data-ttu-id="9bae0-487">문자 범주</span><span class="sxs-lookup"><span data-stu-id="9bae0-487">Character categories</span></span>](#Strings)

- [<span data-ttu-id="9bae0-488">암호화</span><span class="sxs-lookup"><span data-stu-id="9bae0-488">Cryptography</span></span>](#Crypto462)

- [<span data-ttu-id="9bae0-489">SqlClient</span><span class="sxs-lookup"><span data-stu-id="9bae0-489">SqlClient</span></span>](#SQLClient)

- [<span data-ttu-id="9bae0-490">Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="9bae0-490">Windows Communication Foundation</span></span>](#WCF)

- [<span data-ttu-id="9bae0-491">WPF(Windows Presentation Foundation)</span><span class="sxs-lookup"><span data-stu-id="9bae0-491">Windows Presentation Foundation (WPF)</span></span>](#WPF462)

- [<span data-ttu-id="9bae0-492">Windows WF(Workflow Foundation)</span><span class="sxs-lookup"><span data-stu-id="9bae0-492">Windows Workflow Foundation (WF)</span></span>](#WF462)

- [<span data-ttu-id="9bae0-493">ClickOnce</span><span class="sxs-lookup"><span data-stu-id="9bae0-493">ClickOnce</span></span>](#clickonce-1)

- [<span data-ttu-id="9bae0-494">Windows Forms 및 WPF 앱을 UWP 앱으로 변환</span><span class="sxs-lookup"><span data-stu-id="9bae0-494">Converting Windows Forms and WPF apps to UWP apps</span></span>](#UWPConvert)

- [<span data-ttu-id="9bae0-495">디버깅 기능 향상</span><span class="sxs-lookup"><span data-stu-id="9bae0-495">Debugging improvements</span></span>](#Debug462)

<span data-ttu-id="9bae0-496">.NET Framework 4.6.2에 추가된 새 API 목록은 GitHub에서 [.NET Framework 4.6.2 API 변경 내용](https://github.com/Microsoft/dotnet/blob/master/releases/net462/dotnet462-api-changes.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bae0-496">For a list of new APIs added to .NET Framework 4.6.2, see [.NET Framework 4.6.2 API Changes](https://github.com/Microsoft/dotnet/blob/master/releases/net462/dotnet462-api-changes.md) on GitHub.</span></span> <span data-ttu-id="9bae0-497">.NET Framework 4.6.2의 향상된 기능 및 버그 수정 목록은 GitHub에서 [.NET Framework 4.6.2 변경 내용 목록](https://github.com/Microsoft/dotnet/blob/master/releases/net462/dotnet462-changes.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bae0-497">For a list of feature improvements and bug fixes in .NET Framework 4.6.2, see [.NET Framework 4.6.2 List of Changes](https://github.com/Microsoft/dotnet/blob/master/releases/net462/dotnet462-changes.md) on GitHub.</span></span> <span data-ttu-id="9bae0-498">자세한 내용은 .NET 블로그에서 [.NET Framework 4.6.2 알림](https://devblogs.microsoft.com/dotnet/announcing-net-framework-4-6-2/)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bae0-498">For more information, see [Announcing .NET Framework 4.6.2](https://devblogs.microsoft.com/dotnet/announcing-net-framework-4-6-2/) in the .NET blog.</span></span>

<a name="ASPNET462"></a>

### <a name="aspnet"></a><span data-ttu-id="9bae0-499">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="9bae0-499">ASP.NET</span></span>

<span data-ttu-id="9bae0-500">.NET Framework 4.6.2에서 ASP.NET에는 다음과 같은 향상된 기능이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-500">In  .NET Framework 4.6.2, ASP.NET includes the following enhancements:</span></span>

<span data-ttu-id="9bae0-501">**데이터 주석 유효성 검사기의 지역화된 오류 메시지에 대한 지원 개선**</span><span class="sxs-lookup"><span data-stu-id="9bae0-501">**Improved support for localized error messages in data annotation validators**</span></span>

<span data-ttu-id="9bae0-502">데이터 주석 유효성 검사기를 통해 클래스 속성에 하나 이상의 특성을 추가하여 유효성 검사를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-502">Data annotation validators enable you to perform validation by adding one or more attributes to a class property.</span></span> <span data-ttu-id="9bae0-503">특성의 <xref:System.ComponentModel.DataAnnotations.ValidationAttribute.ErrorMessage%2A?displayProperty=nameWithType> 요소는 유효성 검사가 실패할 경우에 표시할 오류 메시지의 텍스트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-503">The attribute's <xref:System.ComponentModel.DataAnnotations.ValidationAttribute.ErrorMessage%2A?displayProperty=nameWithType> element defines the text of the error message if validation fails.</span></span> <span data-ttu-id="9bae0-504">.NET Framework 4.6.2 이상에서는 ASP.NET을 사용하여 오류 메시지를 쉽게 지역화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-504">Starting with .NET Framework 4.6.2, ASP.NET makes it easy to localize error messages.</span></span> <span data-ttu-id="9bae0-505">다음과 같은 경우에 오류 메시지를 지역화합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-505">Error messages will be localized if:</span></span>

1. <span data-ttu-id="9bae0-506"><xref:System.ComponentModel.DataAnnotations.ValidationAttribute.ErrorMessage%2A?displayProperty=nameWithType>가 유효성 검사 특성에 제공되는 경우</span><span class="sxs-lookup"><span data-stu-id="9bae0-506">The <xref:System.ComponentModel.DataAnnotations.ValidationAttribute.ErrorMessage%2A?displayProperty=nameWithType> is provided in the validation attribute.</span></span>

2. <span data-ttu-id="9bae0-507">리소스 파일 App_LocalResources 폴더에 저장되어 있는 경우</span><span class="sxs-lookup"><span data-stu-id="9bae0-507">The resource file is stored in the App_LocalResources folder.</span></span>

3. <span data-ttu-id="9bae0-508">지역화된 리소스 파일의 이름이 `DataAnnotation.Localization.{`*이름*`}.resx` 형식인 경우(여기서 *이름* 은 *languageCode*`-`*country/regionCode* 또는 *languageCode* 형식의 문화권 이름임)</span><span class="sxs-lookup"><span data-stu-id="9bae0-508">The name of the localized resources file has the form `DataAnnotation.Localization.{`*name*`}.resx`, where *name* is a culture name in the format *languageCode*`-`*country/regionCode* or *languageCode*.</span></span>

4. <span data-ttu-id="9bae0-509">리소스의 키 이름이 <xref:System.ComponentModel.DataAnnotations.ValidationAttribute.ErrorMessage%2A?displayProperty=nameWithType> 특성에 할당된 문자열이고 해당 값이 지역화된 오류 메시지인 경우</span><span class="sxs-lookup"><span data-stu-id="9bae0-509">The key name of the resource is the string assigned to the <xref:System.ComponentModel.DataAnnotations.ValidationAttribute.ErrorMessage%2A?displayProperty=nameWithType> attribute,  and its value is the localized error message.</span></span>

<span data-ttu-id="9bae0-510">예를 들어, 다음 데이터 주석 특성은 잘못된 등급에 대한 기본 문화권의 오류 메시지를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-510">For example, the following data annotation attribute defines the default culture's error message for an invalid rating.</span></span>

```csharp
public class RatingInfo
{
   [Required(ErrorMessage = "The rating must be between 1 and 10.")]
   [Display(Name = "Your Rating")]
   public int Rating { get; set; }
}
```

```vb
Public Class RatingInfo
   <Required(ErrorMessage = "The rating must be between 1 and 10.")>
   <Display(Name = "Your Rating")>
   Public Property Rating As Integer = 1
End Class
```

<span data-ttu-id="9bae0-511">그런 다음 키가 오류 메시지 문자열이고 값이 지역화된 오류 메시지인 리소스 파일 DataAnnotation.Localization.fr.resx를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-511">You can then create a resource file, DataAnnotation.Localization.fr.resx, whose key is the error message string and whose value is the localized error message.</span></span> <span data-ttu-id="9bae0-512">해당 파일은 `App.LocalResources` 폴더에서 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-512">The file must be found in the `App.LocalResources` folder.</span></span> <span data-ttu-id="9bae0-513">예를 들면, 다음은 지역화된 프랑스어(fr) 오류 메시지의 값과 키입니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-513">For example, the following is the key and its value in a localized French (fr) language error message:</span></span>

| <span data-ttu-id="9bae0-514">이름</span><span class="sxs-lookup"><span data-stu-id="9bae0-514">Name</span></span>                                 | <span data-ttu-id="9bae0-515">값</span><span class="sxs-lookup"><span data-stu-id="9bae0-515">Value</span></span>                                     |
| ------------------------------------ | ----------------------------------------- |
| <span data-ttu-id="9bae0-516">등급은 1에서 10 사이여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-516">The rating must be between 1 and 10.</span></span> | <span data-ttu-id="9bae0-517">La note doit être comprise entre 1 et 10.</span><span class="sxs-lookup"><span data-stu-id="9bae0-517">La note doit être comprise entre 1 et 10.</span></span> |

 <span data-ttu-id="9bae0-518">또한, 데이터 주석 지역화를 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-518">In addition, data annotation localization is extensible.</span></span> <span data-ttu-id="9bae0-519">개발자는 <xref:System.Web.Globalization.IStringLocalizerProvider> 인터페이스를 구현하여 리소스 파일 내부 이외의 위치에 지역화 문자열을 저장함으로써 문자열 로컬라이저 공급자를 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-519">Developers can plug in their own string localizer provider by implementing the <xref:System.Web.Globalization.IStringLocalizerProvider> interface to store localization string somewhere other than in a resource file.</span></span>

 <span data-ttu-id="9bae0-520">**세션 상태 저장소 공급자와 비동기 지원**</span><span class="sxs-lookup"><span data-stu-id="9bae0-520">**Async support with session-state store providers**</span></span>

 <span data-ttu-id="9bae0-521">이제 ASP.NET을 통해 태스크 반환 메서드를 세션 상태 저장소 공급자와 함께 사용할 수 있으므로, ASP.NET 앱에서 비동기화의 확장성 이점을 누릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-521">ASP.NET now allows task-returning methods to be used with session-state store providers, thereby allowing ASP.NET apps to get the scalability benefits of async.</span></span> <span data-ttu-id="9bae0-522">세션 상태 저장소 공급자와의 비동기 작업을 지원하기 위해 ASP.NET에는 <xref:System.Web.SessionState.ISessionStateModule?displayProperty=nameWithType>이라는 새 인터페이스가 포함되어 있습니다. 이 인터페이스는 <xref:System.Web.IHttpModule>에서 상속하며 개발자가 자체 세션 상태 모듈과 비동기 세션 저장소 공급자를 구현할 수 있도록 해줍니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-522">To supports asynchronous operations with session state store providers, ASP.NET includes  a new interface, <xref:System.Web.SessionState.ISessionStateModule?displayProperty=nameWithType>, which inherits from <xref:System.Web.IHttpModule> and allows developers to implement their own session-state module and async session store providers.</span></span> <span data-ttu-id="9bae0-523">인터페이스는 다음과 같이 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-523">The interface is defined as follows:</span></span>

```csharp
public interface ISessionStateModule : IHttpModule {
    void ReleaseSessionState(HttpContext context);
    Task ReleaseSessionStateAsync(HttpContext context);
}
```

```vb
Public Interface ISessionStateModule : Inherits IHttpModule
   Sub ReleaseSessionState(context As HttpContext)
   Function ReleaseSessionStateAsync(context As HttpContext) As Task
End Interface
```

 <span data-ttu-id="9bae0-524">또한 <xref:System.Web.SessionState.SessionStateUtility> 클래스는 비동기 작업을 지원하는 데 사용할 수 있는 두 개의 새로운 메서드 <xref:System.Web.SessionState.SessionStateUtility.IsSessionStateReadOnly%2A> 및 <xref:System.Web.SessionState.SessionStateUtility.IsSessionStateRequired%2A>를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-524">In addition, the <xref:System.Web.SessionState.SessionStateUtility> class includes two new methods, <xref:System.Web.SessionState.SessionStateUtility.IsSessionStateReadOnly%2A> and <xref:System.Web.SessionState.SessionStateUtility.IsSessionStateRequired%2A>, that can be used to support asynchronous operations.</span></span>

 <span data-ttu-id="9bae0-525">**출력 캐시 공급자에 대한 비동기 지원**</span><span class="sxs-lookup"><span data-stu-id="9bae0-525">**Async support for output-cache providers**</span></span>

 <span data-ttu-id="9bae0-526">.NET Framework 4.6.2 이상에서는 태스크 반환 메서드를 출력 캐시 공급자와 함께 사용하여 비동기화의 스케일링 성능 이점을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-526">Starting with .NET Framework 4.6.2, task-returning methods can be used with output-cache providers to provide the scalability benefits of async.</span></span>  <span data-ttu-id="9bae0-527">이러한 메서드를 구현하는 공급자는 웹 서버에서 스레드 차단을 줄이고 ASP.NET 서비스의 확장성을 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-527">Providers that implement these methods reduce thread-blocking on a web server and improve the scalability of an ASP.NET service.</span></span>

 <span data-ttu-id="9bae0-528">비동기 출력 캐시 공급자를 지원하기 위해 다음 API를 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-528">The following APIs have been added to support asynchronous output-cache providers:</span></span>

- <span data-ttu-id="9bae0-529"><xref:System.Web.Caching.OutputCacheProviderAsync?displayProperty=nameWithType> 클래스: <xref:System.Web.Caching.OutputCacheProvider?displayProperty=nameWithType>에서 상속하며 개발자가 비동기 출력 캐시 공급자를 구현할 수 있도록 해줍니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-529">The <xref:System.Web.Caching.OutputCacheProviderAsync?displayProperty=nameWithType> class, which inherits from <xref:System.Web.Caching.OutputCacheProvider?displayProperty=nameWithType> and allows developers to implement an asynchronous output-cache provider.</span></span>

- <span data-ttu-id="9bae0-530"><xref:System.Web.Caching.OutputCacheUtility> 클래스: 출력 캐시를 구성하기 위한 도우미 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-530">The <xref:System.Web.Caching.OutputCacheUtility> class, which provides helper methods for configuring the output cache.</span></span>

- <span data-ttu-id="9bae0-531"><xref:System.Web.HttpCachePolicy?displayProperty=nameWithType> 클래스의 새로운 메서드 18개.</span><span class="sxs-lookup"><span data-stu-id="9bae0-531">18 new methods in the <xref:System.Web.HttpCachePolicy?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="9bae0-532">여기에는 <xref:System.Web.HttpCachePolicy.GetCacheability%2A>, <xref:System.Web.HttpCachePolicy.GetCacheExtensions%2A>, <xref:System.Web.HttpCachePolicy.GetETag%2A>, <xref:System.Web.HttpCachePolicy.GetETagFromFileDependencies%2A>, <xref:System.Web.HttpCachePolicy.GetMaxAge%2A>, <xref:System.Web.HttpCachePolicy.GetMaxAge%2A>, <xref:System.Web.HttpCachePolicy.GetNoStore%2A>, <xref:System.Web.HttpCachePolicy.GetNoTransforms%2A>, <xref:System.Web.HttpCachePolicy.GetOmitVaryStar%2A>, <xref:System.Web.HttpCachePolicy.GetProxyMaxAge%2A>, <xref:System.Web.HttpCachePolicy.GetRevalidation%2A>, <xref:System.Web.HttpCachePolicy.GetUtcLastModified%2A>, <xref:System.Web.HttpCachePolicy.GetVaryByCustom%2A>, <xref:System.Web.HttpCachePolicy.HasSlidingExpiration%2A>, <xref:System.Web.HttpCachePolicy.IsValidUntilExpires%2A> 등이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-532">These include <xref:System.Web.HttpCachePolicy.GetCacheability%2A>, <xref:System.Web.HttpCachePolicy.GetCacheExtensions%2A>, <xref:System.Web.HttpCachePolicy.GetETag%2A>, <xref:System.Web.HttpCachePolicy.GetETagFromFileDependencies%2A>, <xref:System.Web.HttpCachePolicy.GetMaxAge%2A>, <xref:System.Web.HttpCachePolicy.GetMaxAge%2A>, <xref:System.Web.HttpCachePolicy.GetNoStore%2A>, <xref:System.Web.HttpCachePolicy.GetNoTransforms%2A>, <xref:System.Web.HttpCachePolicy.GetOmitVaryStar%2A>, <xref:System.Web.HttpCachePolicy.GetProxyMaxAge%2A>, <xref:System.Web.HttpCachePolicy.GetRevalidation%2A>, <xref:System.Web.HttpCachePolicy.GetUtcLastModified%2A>, <xref:System.Web.HttpCachePolicy.GetVaryByCustom%2A>, <xref:System.Web.HttpCachePolicy.HasSlidingExpiration%2A>, and <xref:System.Web.HttpCachePolicy.IsValidUntilExpires%2A>.</span></span>

- <span data-ttu-id="9bae0-533"><xref:System.Web.HttpCacheVaryByContentEncodings?displayProperty=nameWithType> 클래스의 새로운 메서드 2개: <xref:System.Web.HttpCacheVaryByContentEncodings.GetContentEncodings%2A> 및 <xref:System.Web.HttpCacheVaryByContentEncodings.SetContentEncodings%2A>.</span><span class="sxs-lookup"><span data-stu-id="9bae0-533">2 new methods in the <xref:System.Web.HttpCacheVaryByContentEncodings?displayProperty=nameWithType> class:  <xref:System.Web.HttpCacheVaryByContentEncodings.GetContentEncodings%2A> and <xref:System.Web.HttpCacheVaryByContentEncodings.SetContentEncodings%2A>.</span></span>

- <span data-ttu-id="9bae0-534"><xref:System.Web.HttpCacheVaryByHeaders?displayProperty=nameWithType> 클래스의 새로운 메서드 2개: <xref:System.Web.HttpCacheVaryByHeaders.GetHeaders%2A> 및 <xref:System.Web.HttpCacheVaryByHeaders.SetHeaders%2A>.</span><span class="sxs-lookup"><span data-stu-id="9bae0-534">2 new methods in the <xref:System.Web.HttpCacheVaryByHeaders?displayProperty=nameWithType> class: <xref:System.Web.HttpCacheVaryByHeaders.GetHeaders%2A> and <xref:System.Web.HttpCacheVaryByHeaders.SetHeaders%2A>.</span></span>

- <span data-ttu-id="9bae0-535"><xref:System.Web.HttpCacheVaryByParams?displayProperty=nameWithType> 클래스의 새로운 메서드 2개: <xref:System.Web.HttpCacheVaryByParams.GetParams%2A> 및 <xref:System.Web.HttpCacheVaryByParams.SetParams%2A>.</span><span class="sxs-lookup"><span data-stu-id="9bae0-535">2 new methods in the <xref:System.Web.HttpCacheVaryByParams?displayProperty=nameWithType> class: <xref:System.Web.HttpCacheVaryByParams.GetParams%2A> and <xref:System.Web.HttpCacheVaryByParams.SetParams%2A>.</span></span>

- <span data-ttu-id="9bae0-536"><xref:System.Web.Caching.AggregateCacheDependency?displayProperty=nameWithType> 클래스의 <xref:System.Web.Caching.AggregateCacheDependency.GetFileDependencies%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="9bae0-536">In the <xref:System.Web.Caching.AggregateCacheDependency?displayProperty=nameWithType> class, the <xref:System.Web.Caching.AggregateCacheDependency.GetFileDependencies%2A> method.</span></span>

- <span data-ttu-id="9bae0-537"><xref:System.Web.Caching.CacheDependency>의 <xref:System.Web.Caching.CacheDependency.GetFileDependencies%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="9bae0-537">In the <xref:System.Web.Caching.CacheDependency>, the <xref:System.Web.Caching.CacheDependency.GetFileDependencies%2A> method.</span></span>

<a name="Strings"></a>

### <a name="character-categories"></a><span data-ttu-id="9bae0-538">문자 범주</span><span class="sxs-lookup"><span data-stu-id="9bae0-538">Character categories</span></span>

<span data-ttu-id="9bae0-539">.NET Framework 4.6.2의 문자는 [유니코드 표준 버전 8.0.0](https://www.unicode.org/versions/Unicode8.0.0/)을 기반으로 분류됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-539">Characters in .NET Framework 4.6.2 are classified based on the [Unicode Standard, Version 8.0.0](https://www.unicode.org/versions/Unicode8.0.0/).</span></span> <span data-ttu-id="9bae0-540">.NET Framework 4.6 및 .NET Framework 4.6.1의 문자는 유니코드 6.3 문자 범주를 기반으로 분류됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-540">In .NET Framework 4.6 and .NET Framework 4.6.1, characters were classified based on Unicode 6.3 character categories.</span></span>

<span data-ttu-id="9bae0-541">유니코드 8.0 지원은 <xref:System.Globalization.CharUnicodeInfo> 클래스에 의한 문자 분류와 해당 클래스를 사용하는 유형 및 메서드로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-541">Support for Unicode 8.0 is limited to the classification of characters by the <xref:System.Globalization.CharUnicodeInfo> class and to types and methods that rely on it.</span></span> <span data-ttu-id="9bae0-542">여기에는 <xref:System.Globalization.StringInfo> 클래스, 오버로드된 <xref:System.Char.GetUnicodeCategory%2A?displayProperty=nameWithType> 메서드, .NET Framework 정규식 엔진에서 인식되는 [문자 클래스](../../standard/base-types/character-classes-in-regular-expressions.md)가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-542">These include the <xref:System.Globalization.StringInfo> class, the overloaded <xref:System.Char.GetUnicodeCategory%2A?displayProperty=nameWithType> method, and the [character classes](../../standard/base-types/character-classes-in-regular-expressions.md) recognized by the .NET Framework regular expression engine.</span></span>  <span data-ttu-id="9bae0-543">문자 및 문자열 비교와 정렬은 이 변경의 영향을 받지 않으며, 기본 운영 체제, Windows 7 시스템 또는 .NET Framework에서 제공하는 문자 데이터를 계속해서 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-543">Character and string comparison and sorting is unaffected by this change and continues to rely on the underlying operating system or, on Windows 7 systems, on character data provided by .NET Framework.</span></span>

<span data-ttu-id="9bae0-544">문자 범주를 유니코드 6.0에서 유니코드 7.0으로 변경하려면 유니코드 컨소시엄 웹 사이트에서 [유니코드 표준, 버전 7.0.0](https://www.unicode.org/versions/Unicode7.0.0/)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9bae0-544">For changes in character categories from Unicode 6.0 to Unicode 7.0, see [The Unicode Standard, Version 7.0.0](https://www.unicode.org/versions/Unicode7.0.0/) at The Unicode Consortium website.</span></span> <span data-ttu-id="9bae0-545">유니코드 7.0에서 유니코드 8.0으로 변경하려면 유니코드 컨소시엄 웹 사이트에서 [유니코드 표준, 버전 8.0.0](https://www.unicode.org/versions/Unicode8.0.0/)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9bae0-545">For changes from Unicode 7.0 to Unicode 8.0, see [The Unicode Standard, Version 8.0.0](https://www.unicode.org/versions/Unicode8.0.0/) at The Unicode Consortium website.</span></span>

<a name="Crypto462"></a>

### <a name="cryptography"></a><span data-ttu-id="9bae0-546">암호화</span><span class="sxs-lookup"><span data-stu-id="9bae0-546">Cryptography</span></span>

<span data-ttu-id="9bae0-547">**FIPS 186-3 DSA를 포함하는 X509 인증서에 대한 지원**</span><span class="sxs-lookup"><span data-stu-id="9bae0-547">**Support for X509 certificates containing FIPS 186-3 DSA**</span></span>

<span data-ttu-id="9bae0-548">.NET Framework 4.6.2에서는 키가 FIPS 186-2 1024비트 제한을 초과하는 DSA(디지털 서명 알고리즘) X509 인증서에 대한 지원을 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-548">.NET Framework 4.6.2 adds support for DSA (Digital Signature Algorithm) X509 certificates whose keys exceed the FIPS 186-2 1024-bit limit.</span></span>

<span data-ttu-id="9bae0-549">FIPS 186-3의 더 큰 키 크기를 지원할 뿐만 아니라 .NET Framework 4.6.2에서는 SHA-4.6.2 해시 알고리즘 패밀리(SHA256, SHA384 및 SHA512)를 통한 컴퓨팅 서명을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-549">In addition to supporting the larger key sizes of FIPS 186-3, .NET Framework 4.6.2 allows computing signatures with the SHA-2 family of hash algorithms (SHA256, SHA384, and SHA512).</span></span> <span data-ttu-id="9bae0-550">FIPS 186-3 지원은 새 <xref:System.Security.Cryptography.DSACng?displayProperty=nameWithType> 클래스에 의해 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-550">FIPS 186-3 support is provided by the new <xref:System.Security.Cryptography.DSACng?displayProperty=nameWithType> class.</span></span>

<span data-ttu-id="9bae0-551">.NET Framework 4.6의 <xref:System.Security.Cryptography.RSA> 클래스 및 .NET Framework 4.6.1의 <xref:System.Security.Cryptography.ECDsa> 클래스에 대한 최신 변경 내용을 유지하면서 .NET Framework 4.6.2의 <xref:System.Security.Cryptography.DSA> 추상 기본 클래스에는 호출자가 캐스팅하지 않고 이 기능을 사용할 수 있도록 해주는 추가 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-551">In keeping with recent changes to the <xref:System.Security.Cryptography.RSA> class in .NET Framework 4.6 and the <xref:System.Security.Cryptography.ECDsa> class in .NET Framework 4.6.1, the <xref:System.Security.Cryptography.DSA> abstract base class in .NET Framework 4.6.2 has additional methods to allow callers to use this functionality without casting.</span></span> <span data-ttu-id="9bae0-552">다음 예제와 같이 <xref:System.Security.Cryptography.X509Certificates.DSACertificateExtensions.GetDSAPrivateKey%2A?displayProperty=nameWithType> 확장 메서드를 호출하여 데이터에 서명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-552">You can call the <xref:System.Security.Cryptography.X509Certificates.DSACertificateExtensions.GetDSAPrivateKey%2A?displayProperty=nameWithType> extension method to sign data, as the following example shows.</span></span>

```csharp
public static byte[] SignDataDsaSha384(byte[] data, X509Certificate2 cert)
{
    using (DSA dsa = cert.GetDSAPrivateKey())
    {
        return dsa.SignData(data, HashAlgorithmName.SHA384);
    }
}
```

```vb
Public Shared Function SignDataDsaSha384(data As Byte(), cert As X509Certificate2) As Byte()
    Using DSA As DSA = cert.GetDSAPrivateKey()
        Return DSA.SignData(data, HashAlgorithmName.SHA384)
    End Using
End Function
```

<span data-ttu-id="9bae0-553">다음 예제와 같이 <xref:System.Security.Cryptography.X509Certificates.DSACertificateExtensions.GetDSAPublicKey%2A?displayProperty=nameWithType> 확장 메서드를 호출하여 서명된 데이터를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-553">And you can call the <xref:System.Security.Cryptography.X509Certificates.DSACertificateExtensions.GetDSAPublicKey%2A?displayProperty=nameWithType> extension method to verify signed data, as the following example shows.</span></span>

```csharp
public static bool VerifyDataDsaSha384(byte[] data, byte[] signature, X509Certificate2 cert)
{
    using (DSA dsa = cert.GetDSAPublicKey())
    {
        return dsa.VerifyData(data, signature, HashAlgorithmName.SHA384);
    }
}
```

```vb
 Public Shared Function VerifyDataDsaSha384(data As Byte(), signature As Byte(), cert As X509Certificate2) As Boolean
    Using dsa As DSA = cert.GetDSAPublicKey()
        Return dsa.VerifyData(data, signature, HashAlgorithmName.SHA384)
    End Using
End Function
```

<span data-ttu-id="9bae0-554">**ECDiffieHellman 키 파생 루틴에 대한 입력 정확성 향상**</span><span class="sxs-lookup"><span data-stu-id="9bae0-554">**Increased clarity for inputs to ECDiffieHellman key derivation routines**</span></span>

<span data-ttu-id="9bae0-555">.NET Framework 3.5에서는 세 가지 KDF(키 파생 함수) 루틴을 가진 타원 곡선 Diffie-Hellman 키 계약에 대한 지원을 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-555">.NET Framework 3.5 added support for Elliptic Curve Diffie-Hellman Key Agreement with three different Key Derivation Function (KDF) routines.</span></span> <span data-ttu-id="9bae0-556">루틴에 대한 입력과 루틴 자체는 <xref:System.Security.Cryptography.ECDiffieHellmanCng> 개체에 대한 속성을 통해 구성했습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-556">The inputs to the routines, and the routines themselves, were configured via properties on the <xref:System.Security.Cryptography.ECDiffieHellmanCng> object.</span></span> <span data-ttu-id="9bae0-557">하지만 일부 루틴이 일부 입력 속성을 읽지 않기 때문에 개발자의 과거에 대해 혼동을 일으킬 여지가 충분합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-557">But since not every routine read every input property, there was ample room for confusion on the past of the developer.</span></span>

<span data-ttu-id="9bae0-558">.NET Framework 4.6.2에서 이 문제를 해결하기 위해 이러한 KDF 루틴과 해당 입력을 더욱 정확하게 표시하도록 다음 세 가지 메서드를 <xref:System.Security.Cryptography.ECDiffieHellman> 기본 클래스에 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-558">To address this in .NET Framework 4.6.2, the following three methods have been added to the  <xref:System.Security.Cryptography.ECDiffieHellman> base class to more clearly represent these KDF routines and their inputs:</span></span>

|<span data-ttu-id="9bae0-559">ECDiffieHellman 메서드</span><span class="sxs-lookup"><span data-stu-id="9bae0-559">ECDiffieHellman method</span></span>|<span data-ttu-id="9bae0-560">설명</span><span class="sxs-lookup"><span data-stu-id="9bae0-560">Description</span></span>|
|----------------------------|-----------------|
|<xref:System.Security.Cryptography.ECDiffieHellman.DeriveKeyFromHash%28System.Security.Cryptography.ECDiffieHellmanPublicKey%2CSystem.Security.Cryptography.HashAlgorithmName%2CSystem.Byte%5B%5D%2CSystem.Byte%5B%5D%29>|<span data-ttu-id="9bae0-561">수식을 사용하여 키 자료 파생</span><span class="sxs-lookup"><span data-stu-id="9bae0-561">Derives key material using the formula</span></span><br /><br /> <span data-ttu-id="9bae0-562">HASH(secretPrepend &#124;&#124; *x* &#124;&#124; secretAppend)</span><span class="sxs-lookup"><span data-stu-id="9bae0-562">HASH(secretPrepend &#124;&#124; *x* &#124;&#124; secretAppend)</span></span><br /><br /> <span data-ttu-id="9bae0-563">HASH(secretPrepend OrElse *x* OrElse secretAppend)</span><span class="sxs-lookup"><span data-stu-id="9bae0-563">HASH(secretPrepend OrElse *x* OrElse secretAppend)</span></span><br /><br /> <span data-ttu-id="9bae0-564">여기서 *x* 는 EC Diffie-hellman 알고리즘의 계산된 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-564">where *x* is the computed result of the EC Diffie-Hellman algorithm.</span></span>|
|<xref:System.Security.Cryptography.ECDiffieHellman.DeriveKeyFromHmac%28System.Security.Cryptography.ECDiffieHellmanPublicKey%2CSystem.Security.Cryptography.HashAlgorithmName%2CSystem.Byte%5B%5D%2CSystem.Byte%5B%5D%2CSystem.Byte%5B%5D%29>|<span data-ttu-id="9bae0-565">수식을 사용하여 키 자료 파생</span><span class="sxs-lookup"><span data-stu-id="9bae0-565">Derives key material using the formula</span></span><br /><br /> <span data-ttu-id="9bae0-566">HMAC(hmacKey, secretPrepend &#124;&#124; *x* &#124;&#124; secretAppend)</span><span class="sxs-lookup"><span data-stu-id="9bae0-566">HMAC(hmacKey, secretPrepend &#124;&#124; *x* &#124;&#124; secretAppend)</span></span><br /><br /> <span data-ttu-id="9bae0-567">HMAC(hmacKey, secretPrepend OrElse *x* OrElse secretAppend)</span><span class="sxs-lookup"><span data-stu-id="9bae0-567">HMAC(hmacKey, secretPrepend OrElse *x* OrElse secretAppend)</span></span><br /><br /> <span data-ttu-id="9bae0-568">여기서 *x* 는 EC Diffie-hellman 알고리즘의 계산된 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-568">where *x* is the computed result of the EC Diffie-Hellman algorithm.</span></span>|
|<xref:System.Security.Cryptography.ECDiffieHellman.DeriveKeyTls%28System.Security.Cryptography.ECDiffieHellmanPublicKey%2CSystem.Byte%5B%5D%2CSystem.Byte%5B%5D%29>|<span data-ttu-id="9bae0-569">TLS PRF(의사 난수 함수) 파생 알고리즘을 사용하여 키 자료 파생</span><span class="sxs-lookup"><span data-stu-id="9bae0-569">Derives key material using the TLS pseudo-random function (PRF) derivation algorithm.</span></span>|

<span data-ttu-id="9bae0-570">**지속형 키 대칭 암호화 지원**</span><span class="sxs-lookup"><span data-stu-id="9bae0-570">**Support for persisted-key symmetric encryption**</span></span>

<span data-ttu-id="9bae0-571">Windows 암호화 라이브러리(CNG)에서는 지속형 대칭 키 저장과 하드웨어에 저장된 대칭 키 사용에 대한 지원을 추가했으며 개발자는 .NET Framework 4.6.2를 통해 이 기능을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-571">The Windows cryptography library (CNG) added support for storing persisted symmetric keys and using hardware-stored symmetric keys, and .NET Framework 4.6.2 made it possible for developers to make use of this feature.</span></span>  <span data-ttu-id="9bae0-572">키 이름과 키 공급자가 구현별로 다르게 표시되므로, 이 기능을 사용하려면 기본 팩토리 접근 방식 대신 구체적인 구현 형식의 생성자를 활용해야 합니다(예: `Aes.Create` 호출).</span><span class="sxs-lookup"><span data-stu-id="9bae0-572">Since the notion of key names and key providers is implementation-specific, using this feature requires utilizing the constructor of the concrete implementation types instead of the preferred factory approach (such as calling `Aes.Create`).</span></span>

<span data-ttu-id="9bae0-573">AES(<xref:System.Security.Cryptography.AesCng>) 및 3DES(<xref:System.Security.Cryptography.TripleDESCng>) 알고리즘에 대해 지속형 키 대칭 암호화가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-573">Persisted-key symmetric encryption support exists for the AES (<xref:System.Security.Cryptography.AesCng>) and 3DES (<xref:System.Security.Cryptography.TripleDESCng>) algorithms.</span></span> <span data-ttu-id="9bae0-574">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="9bae0-574">For example:</span></span>

```csharp
public static byte[] EncryptDataWithPersistedKey(byte[] data, byte[] iv)
{
    using (Aes aes = new AesCng("AesDemoKey", CngProvider.MicrosoftSoftwareKeyStorageProvider))
    {
        aes.IV = iv;

        // Using the zero-argument overload is required to make use of the persisted key
        using (ICryptoTransform encryptor = aes.CreateEncryptor())
        {
            if (!encryptor.CanTransformMultipleBlocks)
            {
                throw new InvalidOperationException("This is a sample, this case wasn't handled...");
            }

            return encryptor.TransformFinalBlock(data, 0, data.Length);
        }
    }
}
```

```vb
Public Shared Function EncryptDataWithPersistedKey(data As Byte(), iv As Byte()) As Byte()
    Using Aes As Aes = New AesCng("AesDemoKey", CngProvider.MicrosoftSoftwareKeyStorageProvider)
        Aes.IV = iv

        ' Using the zero-argument overload Is required to make use of the persisted key
        Using encryptor As ICryptoTransform = Aes.CreateEncryptor()
            If Not encryptor.CanTransformMultipleBlocks Then
                Throw New InvalidOperationException("This is a sample, this case wasn't handled...")
            End If
            Return encryptor.TransformFinalBlock(data, 0, data.Length)
        End Using
    End Using
End Function
```

<span data-ttu-id="9bae0-575">**SHA-2 해시에 대한 SignedXml 지원**</span><span class="sxs-lookup"><span data-stu-id="9bae0-575">**SignedXml support for SHA-2 hashing**</span></span>

<span data-ttu-id="9bae0-576">.NET Framework 4.6.2에서는 RSA-SHA256, RSA-SHA384 및 RSA-SHA512 PKCS#1 서명 메서드, SHA256, SHA384 및 SHA512 참조 다이제스트 알고리즘에 대한 <xref:System.Security.Cryptography.Xml.SignedXml> 클래스 지원을 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-576">.NET Framework 4.6.2 adds support to  the <xref:System.Security.Cryptography.Xml.SignedXml> class for RSA-SHA256, RSA-SHA384, and RSA-SHA512 PKCS#1 signature methods, and SHA256, SHA384, and SHA512 reference digest algorithms.</span></span>

<span data-ttu-id="9bae0-577">URI 상수가 <xref:System.Security.Cryptography.Xml.SignedXml>에 모두 노출됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-577">The URI constants are all exposed on <xref:System.Security.Cryptography.Xml.SignedXml>:</span></span>

|<span data-ttu-id="9bae0-578">SignedXml 필드</span><span class="sxs-lookup"><span data-stu-id="9bae0-578">SignedXml field</span></span>|<span data-ttu-id="9bae0-579">상수</span><span class="sxs-lookup"><span data-stu-id="9bae0-579">Constant</span></span>|
|---------------------|--------------|
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigSHA256Url>|<span data-ttu-id="9bae0-580">"http://www.w3.org/2001/04/xmlenc#sha256"</span><span class="sxs-lookup"><span data-stu-id="9bae0-580">"http://www.w3.org/2001/04/xmlenc#sha256"</span></span>|
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigRSASHA256Url>|<span data-ttu-id="9bae0-581">"http://www.w3.org/2001/04/xmldsig-more#rsa-sha256"</span><span class="sxs-lookup"><span data-stu-id="9bae0-581">"http://www.w3.org/2001/04/xmldsig-more#rsa-sha256"</span></span>|
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigSHA384Url>|<span data-ttu-id="9bae0-582">"http://www.w3.org/2001/04/xmldsig-more#sha384"</span><span class="sxs-lookup"><span data-stu-id="9bae0-582">"http://www.w3.org/2001/04/xmldsig-more#sha384"</span></span>|
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigRSASHA384Url>|<span data-ttu-id="9bae0-583">"http://www.w3.org/2001/04/xmldsig-more#rsa-sha384"</span><span class="sxs-lookup"><span data-stu-id="9bae0-583">"http://www.w3.org/2001/04/xmldsig-more#rsa-sha384"</span></span>|
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigSHA512Url>|<span data-ttu-id="9bae0-584">"http://www.w3.org/2001/04/xmlenc#sha512"</span><span class="sxs-lookup"><span data-stu-id="9bae0-584">"http://www.w3.org/2001/04/xmlenc#sha512"</span></span>|
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigRSASHA512Url>|<span data-ttu-id="9bae0-585">"http://www.w3.org/2001/04/xmldsig-more#rsa-sha512"</span><span class="sxs-lookup"><span data-stu-id="9bae0-585">"http://www.w3.org/2001/04/xmldsig-more#rsa-sha512"</span></span>|

 <span data-ttu-id="9bae0-586">사용자 지정 <xref:System.Security.Cryptography.SignatureDescription> 처리기를 <xref:System.Security.Cryptography.CryptoConfig>에 등록하여 이러한 알고리즘에 대한 지원을 추가한 모든 프로그램은 계속해서 이전처럼 작동하지만, 이제 플랫폼 기본값이 없으므로 <xref:System.Security.Cryptography.CryptoConfig> 등록이 더 이상 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-586">Any programs that have registered a custom <xref:System.Security.Cryptography.SignatureDescription> handler into <xref:System.Security.Cryptography.CryptoConfig> to add support for these algorithms will continue to function as they did in the past, but since there are now platform defaults, the <xref:System.Security.Cryptography.CryptoConfig> registration is no longer necessary.</span></span>

<a name="SQLClient"></a>

### <a name="sqlclient"></a><span data-ttu-id="9bae0-587">SqlClient</span><span class="sxs-lookup"><span data-stu-id="9bae0-587">SqlClient</span></span>

<span data-ttu-id="9bae0-588">.NET Framework Data Provider for SQL Server(<xref:System.Data.SqlClient?displayProperty=nameWithType>)는 .NET Framework 4.6.2에 다음과 같은 새로운 기능이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-588">.NET Framework Data Provider for SQL Server (<xref:System.Data.SqlClient?displayProperty=nameWithType>) includes the following new features in .NET Framework 4.6.2:</span></span>

<span data-ttu-id="9bae0-589">**Azure SQL Database와의 연결 풀링 및 시간 초과**</span><span class="sxs-lookup"><span data-stu-id="9bae0-589">**Connection pooling and timeouts with Azure SQL databases**</span></span>

<span data-ttu-id="9bae0-590">연결 풀링을 사용하도록 설정한 상태에서 시간 초과 또는 다른 오류가 발생할 경우 예외가 캐시되고 다음에 연결하려고 시도할 때 캐시된 예외가 5초-1분 동안 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-590">When connection pooling is enabled and a timeout or other login error occurs, an exception is cached, and the cached exception is thrown on any subsequent connection attempt for the next 5 seconds to 1 minute.</span></span> <span data-ttu-id="9bae0-591">자세한 내용은 [SQL Server 연결 풀링(ADO.NET)](../data/adonet/sql-server-connection-pooling.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bae0-591">For more information, see [SQL Server Connection Pooling (ADO.NET)](../data/adonet/sql-server-connection-pooling.md).</span></span>

<span data-ttu-id="9bae0-592">Azure SQL Database에 연결할 때 일반적으로 빠르게 복구되는 일시적인 오류로 인해 연결 시도가 실패할 수 있으므로 이 동작은 바람직하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-592">This behavior is not desirable when connecting to Azure SQL Databases, since connection attempts can fail with transient errors that are typically recovered quickly.</span></span> <span data-ttu-id="9bae0-593">연결 재시도 경험을 효율적으로 최적화하기 위해 Azure SQL Database 연결이 실패할 때 연결 풀 차단 기간 동작을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-593">To better optimize the connection retry experience, the connection pool blocking period behavior is removed when connections to Azure SQL Databases fail.</span></span>

<span data-ttu-id="9bae0-594">새로운 `PoolBlockingPeriod` 키워드를 추가하여 앱에 가장 적합한 차단 기간을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-594">The addition of the new `PoolBlockingPeriod` keyword lets you select the blocking period best suited for your app.</span></span> <span data-ttu-id="9bae0-595">값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-595">Values include:</span></span>

<xref:System.Data.SqlClient.PoolBlockingPeriod.Auto>

<span data-ttu-id="9bae0-596">Azure SQL Database에 연결하는 애플리케이션에 대한 연결 풀 차단 기간은 비활성화되고, 다른 SQL Server 인스턴스에 연결하는 애플리케이션에 대한 연결 풀 차단 기간은 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-596">The connection pool blocking period for an application that connects to an Azure SQL Database is disabled, and the connection pool blocking period for an application that connects to any other SQL Server instance is enabled.</span></span> <span data-ttu-id="9bae0-597">기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-597">This is the default value.</span></span> <span data-ttu-id="9bae0-598">서버 엔드포인트 이름이 다음 중 하나로 끝나는 경우 Azure SQL Database로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-598">If the Server endpoint name ends with any of the following, they are considered Azure SQL Databases:</span></span>

- <span data-ttu-id="9bae0-599">.database.windows.net</span><span class="sxs-lookup"><span data-stu-id="9bae0-599">.database.windows.net</span></span>

- <span data-ttu-id="9bae0-600">.database.chinacloudapi.cn</span><span class="sxs-lookup"><span data-stu-id="9bae0-600">.database.chinacloudapi.cn</span></span>

- <span data-ttu-id="9bae0-601">.database.usgovcloudapi.net</span><span class="sxs-lookup"><span data-stu-id="9bae0-601">.database.usgovcloudapi.net</span></span>

- <span data-ttu-id="9bae0-602">.database.cloudapi.de</span><span class="sxs-lookup"><span data-stu-id="9bae0-602">.database.cloudapi.de</span></span>

<xref:System.Data.SqlClient.PoolBlockingPeriod.AlwaysBlock>

<span data-ttu-id="9bae0-603">연결 풀 차단 기간이 항상 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-603">The connection pool blocking period is always enabled.</span></span>

<xref:System.Data.SqlClient.PoolBlockingPeriod.NeverBlock>

<span data-ttu-id="9bae0-604">연결 풀 차단 기간이 항상 비활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-604">The connection pool blocking period is always disabled.</span></span>

<span data-ttu-id="9bae0-605">**상시 암호화 기능 향상**</span><span class="sxs-lookup"><span data-stu-id="9bae0-605">**Enhancements for Always Encrypted**</span></span>

<span data-ttu-id="9bae0-606">SQLClient에서는 상시 암호화에 대한 두 가지 향상된 기능을 도입했습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-606">SQLClient introduces two enhancements for Always Encrypted:</span></span>

- <span data-ttu-id="9bae0-607">암호화된 데이터베이스 열에 대한 매개 변수화된 쿼리 성능을 향상하기 위해 이제 쿼리 매개 변수에 대한 암호화 메타데이터가 캐시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-607">To improve performance of parameterized queries against encrypted database columns, encryption metadata for query parameters is now cached.</span></span> <span data-ttu-id="9bae0-608"><xref:System.Data.SqlClient.SqlConnection.ColumnEncryptionQueryMetadataCacheEnabled%2A?displayProperty=nameWithType> 속성을 `true`(기본값)로 설정한 상태에서 동일한 쿼리를 여러 번 호출할 경우 클라이언트는 서버에서 매개 변수 메타데이터를 한 번만 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-608">With the <xref:System.Data.SqlClient.SqlConnection.ColumnEncryptionQueryMetadataCacheEnabled%2A?displayProperty=nameWithType> property set to `true` (which is the default value), if the same query is called multiple times, the client retrieves parameter metadata from the server only once.</span></span>

- <span data-ttu-id="9bae0-609">키 캐시의 열 암호화 키 항목은 이제 <xref:System.Data.SqlClient.SqlConnection.ColumnEncryptionKeyCacheTtl%2A?displayProperty=nameWithType> 속성을 사용하여 설정된 구성 가능한 시간 간격 후에 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-609">Column encryption key entries in the key cache are now evicted after a configurable time interval, set using the <xref:System.Data.SqlClient.SqlConnection.ColumnEncryptionKeyCacheTtl%2A?displayProperty=nameWithType> property.</span></span>

<a name="WCF"></a>

### <a name="windows-communication-foundation"></a><span data-ttu-id="9bae0-610">Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="9bae0-610">Windows Communication Foundation</span></span>

<span data-ttu-id="9bae0-611">.NET Framework 4.6.2에서 Windows Communication Foundation이 다음과 같은 영역에서 향상되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-611">In .NET Framework 4.6.2, Windows Communication Foundation has been enhanced in the following areas:</span></span>

<span data-ttu-id="9bae0-612">**CNG를 사용하여 저장한 인증서에 대한 WCF 전송 보안 지원**</span><span class="sxs-lookup"><span data-stu-id="9bae0-612">**WCF transport security support for certificates stored using CNG**</span></span>

<span data-ttu-id="9bae0-613">WCF 전송 보안에서 Windows 암호화 라이브러리(CNG)를 사용하여 저장한 인증서를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-613">WCF transport security supports certificates stored using the Windows cryptography library (CNG).</span></span> <span data-ttu-id="9bae0-614">.NET Framework 4.6.2에서 이 지원은 지수 길이가 32비트 이하인 퍼블릭 키로 인증서를 사용하도록 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-614">In .NET Framework 4.6.2, this support is limited to using certificates with a public key that has an exponent no more than 32 bits in length.</span></span> <span data-ttu-id="9bae0-615">애플리케이션이 .NET Framework 4.6.2를 대상으로 하는 경우 이 기능은 기본적으로 켜집니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-615">When an application targets .NET Framework 4.6.2, this feature is on by default.</span></span>

<span data-ttu-id="9bae0-616">.NET Framework 4.6.1 및 이전 버전을 대상으로 하지만 .NET Framework 4.6.2에서 실행 중인 애플리케이션의 경우 app.config 또는 web.config 파일의 [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) 섹션에 다음 줄을 추가하여 이 기능을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-616">For applications that target .NET Framework 4.6.1 and earlier but are running on .NET Framework 4.6.2, this feature can be enabled by adding the following line to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of the app.config or web.config file.</span></span>

```xml
<AppContextSwitchOverrides
    value="Switch.System.ServiceModel.DisableCngCertificates=false"
/>
```

<span data-ttu-id="9bae0-617">다음과 같은 코드를 사용하여 프로그래밍 방식으로 이 작업을 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-617">This can also be done programmatically with code like the following:</span></span>

```csharp
private const string DisableCngCertificates = @"Switch.System.ServiceModel.DisableCngCertificates";
AppContext.SetSwitch(disableCngCertificates, false);
```

```vb
Const DisableCngCertificates As String = "Switch.System.ServiceModel.DisableCngCertificates"
AppContext.SetSwitch(disableCngCertificates, False)
```

<span data-ttu-id="9bae0-618">**DataContractJsonSerializer 클래스에 의한 여러 일광 절약 시간 조정 규칙에 대한 지원 개선**</span><span class="sxs-lookup"><span data-stu-id="9bae0-618">**Better support for multiple daylight saving time adjustment rules by the DataContractJsonSerializer class**</span></span>

<span data-ttu-id="9bae0-619">고객이 애플리케이션 구성 설정을 사용하여 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 클래스에서 단일 표준 시간대에 대해 여러 조정 규칙을 지원하는지 여부를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-619">Customers can use an application configuration setting to determine whether the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> class supports multiple adjustment rules for a single time zone.</span></span> <span data-ttu-id="9bae0-620">이 기능은 옵트인 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-620">This is an opt-in feature.</span></span> <span data-ttu-id="9bae0-621">이 기능을 사용하려면 app.config 파일에 다음 설정을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-621">To enable it, add the following setting to your app.config file:</span></span>

```xml
<runtime>
     <AppContextSwitchOverrides value="Switch.System.Runtime.Serialization.DoNotUseTimeZoneInfo=false" />
</runtime>
```

<span data-ttu-id="9bae0-622">이 기능을 사용하도록 설정한 경우 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 개체에서는 <xref:System.TimeZone> 형식 대신 <xref:System.TimeZoneInfo> 형식을 사용하여 날짜 및 시간 데이터를 역직렬화합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-622">When this feature is enabled, a <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> object uses the <xref:System.TimeZoneInfo> type instead of the <xref:System.TimeZone> type to deserialize date and time data.</span></span> <span data-ttu-id="9bae0-623"><xref:System.TimeZoneInfo>에서는 여러 조정 규칙을 지원하므로 기록 표준 시간대 데이터로 작업할 수 있지만 <xref:System.TimeZone>에서는 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-623"><xref:System.TimeZoneInfo> supports multiple adjustment rules, which makes it possible to work with historic time zone data;   <xref:System.TimeZone> does not.</span></span>

<span data-ttu-id="9bae0-624"><xref:System.TimeZoneInfo> 구조 및 시간대 조정에 대한 자세한 내용은 [표준 시간대 개요](../../standard/datetime/time-zone-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bae0-624">For more information on the <xref:System.TimeZoneInfo> structure and time zone adjustments, see [Time Zone Overview](../../standard/datetime/time-zone-overview.md).</span></span>

<span data-ttu-id="9bae0-625">**NetNamedPipeBinding 가장 일치하는 항목**</span><span class="sxs-lookup"><span data-stu-id="9bae0-625">**NetNamedPipeBinding best match**</span></span>

<span data-ttu-id="9bae0-626">WCF에는 클라이언트 애플리케이션에서 요청한 항목과 가장 일치하는 URI를 수신하는 서비스에 항상 연결하도록 설정 가능한 새 앱 설정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-626">WCF has a new app setting that can be set on client applications to ensure they always connect to the service listening on the URI that best matches the one that they request.</span></span> <span data-ttu-id="9bae0-627">이 앱 설정을 `false`(기본값)로 지정한 경우 클라이언트에서 <xref:System.ServiceModel.NetNamedPipeBinding>을 사용하여 요청한 URI의 부분 문자열인 URI를 수신하는 서비스에 연결하려고 시도할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-627">With this app setting set to `false` (the default), it is possible for clients using <xref:System.ServiceModel.NetNamedPipeBinding> to attempt to connect to a service listening on a URI that is a substring of the requested URI.</span></span>

<span data-ttu-id="9bae0-628">예를 들어 클라이언트가 `net.pipe://localhost/Service1`에서 수신하는 서비스에 연결하려고 하지만, 관리자 권한으로 실행 중인 컴퓨터의 다른 서비스에서 `net.pipe://localhost`를 수신하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-628">For example, a client tries to connect to a service listening at `net.pipe://localhost/Service1`, but a different service on that machine running with administrator privilege is listening at `net.pipe://localhost`.</span></span> <span data-ttu-id="9bae0-629">이 앱 설정을 `false`로 지정한 경우 클라이언트에서 잘못된 서비스에 연결하려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-629">With this app setting set to `false`, the client would attempt to connect to the wrong service.</span></span> <span data-ttu-id="9bae0-630">앱 설정을 `true`로 설정하면 클라이언트에서는 항상 가장 일치하는 서비스에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-630">After setting the app setting to `true`, the client will always connect to the best matching service.</span></span>

> [!NOTE]
> <span data-ttu-id="9bae0-631"><xref:System.ServiceModel.NetNamedPipeBinding>을 사용하는 클라이언트는 전체 엔드포인트 주소 대신 서비스의 기준 주소(있는 경우)를 기반으로 서비스를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-631">Clients using <xref:System.ServiceModel.NetNamedPipeBinding> find services based on the service's base address (if it exists) rather than the full endpoint address.</span></span> <span data-ttu-id="9bae0-632">이 설정을 항상 작동하게 하려면 서비스에서 고유 기준 주소를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-632">To ensure this setting always works the service should use a unique base address.</span></span>

<span data-ttu-id="9bae0-633">이 변경을 사용하려면 클라이언트 애플리케이션의 App.config 또는 Web.config 파일에 다음 앱 설정을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-633">To enable this change, add the following app setting to your client application's App.config or Web.config file:</span></span>

```xml
<configuration>
    <appSettings>
        <add key="wcf:useBestMatchNamedPipeUri" value="true" />
    </appSettings>
</configuration>
```

<span data-ttu-id="9bae0-634">**SSL 3.0은 기본 프로토콜이 아닙니다.**</span><span class="sxs-lookup"><span data-stu-id="9bae0-634">**SSL 3.0 is not a default protocol**</span></span>

<span data-ttu-id="9bae0-635">전송 보안 및 자격 증명 유형의 인증서를 지원하는 NetTcp를 사용할 경우 SSL 3.0은 더 이상 보안 연결을 협상하는 데 사용되는 기본 프로토콜이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-635">When using NetTcp with transport security and a credential type of certificate, SSL 3.0 is no longer a default protocol used for negotiating a secure connection.</span></span> <span data-ttu-id="9bae0-636">대부분의 경우 TLS 1.0이 NetTcp에 대한 프로토콜 목록에 포함되어 있으므로 기존 앱에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-636">In most cases, there should be no impact to existing apps, because TLS 1.0 is included in the protocol list for NetTcp.</span></span> <span data-ttu-id="9bae0-637">모든 기존 클라이언트에서는 TLS 1.0 이상을 사용하여 연결을 협상할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-637">All existing clients should be able to negotiate a connection using at least TLS 1.0.</span></span> <span data-ttu-id="9bae0-638">Ssl3가 필요한 경우 다음 구성 메커니즘 중 하나를 사용하여 협상된 프로토콜 목록에 Ssl3를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-638">If Ssl3 is required, use one of the following configuration mechanisms to add it to the list of negotiated protocols.</span></span>

- <span data-ttu-id="9bae0-639"><xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols%2A?displayProperty=nameWithType> 속성</span><span class="sxs-lookup"><span data-stu-id="9bae0-639">The <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols%2A?displayProperty=nameWithType> property</span></span>

- <span data-ttu-id="9bae0-640"><xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A?displayProperty=nameWithType> 속성</span><span class="sxs-lookup"><span data-stu-id="9bae0-640">The <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A?displayProperty=nameWithType> property</span></span>

- <span data-ttu-id="9bae0-641">[\<netTcpBinding>](../configure-apps/file-schema/wcf/nettcpbinding.md) 섹션의 [\<transport>](../configure-apps/file-schema/wcf/transport-of-nettcpbinding.md) 섹션</span><span class="sxs-lookup"><span data-stu-id="9bae0-641">The [\<transport>](../configure-apps/file-schema/wcf/transport-of-nettcpbinding.md) section of the [\<netTcpBinding>](../configure-apps/file-schema/wcf/nettcpbinding.md) section</span></span>

- <span data-ttu-id="9bae0-642">[\<customBinding>](../configure-apps/file-schema/wcf/custombinding.md) 섹션의 [\<sslStreamSecurity>](../configure-apps/file-schema/wcf/sslstreamsecurity.md) 섹션</span><span class="sxs-lookup"><span data-stu-id="9bae0-642">The [\<sslStreamSecurity>](../configure-apps/file-schema/wcf/sslstreamsecurity.md) section of the [\<customBinding>](../configure-apps/file-schema/wcf/custombinding.md) section</span></span>

<a name="WPF462"></a>

### <a name="windows-presentation-foundation-wpf"></a><span data-ttu-id="9bae0-643">WPF(Windows Presentation Foundation)</span><span class="sxs-lookup"><span data-stu-id="9bae0-643">Windows Presentation Foundation (WPF)</span></span>

<span data-ttu-id="9bae0-644">.NET Framework 4.6.2에서 Windows Presentation Foundation이 다음 영역에서 향상되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-644">In .NET Framework 4.6.2, Windows Presentation Foundation has been enhanced in the following areas:</span></span>

<span data-ttu-id="9bae0-645">**그룹 정렬**</span><span class="sxs-lookup"><span data-stu-id="9bae0-645">**Group sorting**</span></span>

<span data-ttu-id="9bae0-646"><xref:System.Windows.Data.CollectionView> 개체를 사용하여 데이터를 그룹화하는 애플리케이션에서는 이제 그룹 정렬 방법을 명시적으로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-646">An application that uses a <xref:System.Windows.Data.CollectionView> object to group data can now explicitly declare how to  sort the groups.</span></span> <span data-ttu-id="9bae0-647">명시적으로 정렬하면 응용 프로그램에서 그룹을 동적으로 추가 또는 제거하거나 그룹화에 포함된 항목의 속성 값을 변경할 때 발생하는 직관적이지 않은 순서 지정 문제가 해결됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-647">Explicit sorting addresses the problem of non-intuitive ordering that occurs when an app dynamically adds or removes groups, or when it changes the value of item properties involved in grouping.</span></span> <span data-ttu-id="9bae0-648">또한 그룹화 속성 비교를 전체 컬렉션 정렬에서 그룹화 정렬로 전환하여 그룹 만들기 프로세스의 성능을 향상할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-648">It can also improve the performance of the group creation process by moving comparisons of the grouping properties from the sort of the full collection to the sort of the groups.</span></span>

<span data-ttu-id="9bae0-649">그룹 정렬을 지원하기 위해 새 <xref:System.ComponentModel.GroupDescription.SortDescriptions%2A?displayProperty=nameWithType> 및 <xref:System.ComponentModel.GroupDescription.CustomSort%2A?displayProperty=nameWithType> 속성에서 <xref:System.ComponentModel.GroupDescription> 개체에 의해 생성되는 그룹 컬렉션을 정렬하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-649">To support group sorting, the new <xref:System.ComponentModel.GroupDescription.SortDescriptions%2A?displayProperty=nameWithType> and <xref:System.ComponentModel.GroupDescription.CustomSort%2A?displayProperty=nameWithType> properties describe how to sort the collection of groups produced by the <xref:System.ComponentModel.GroupDescription> object.</span></span> <span data-ttu-id="9bae0-650">이 방법은 동일하게 명명된 <xref:System.Windows.Data.ListCollectionView> 속성에서 데이터 항목을 정렬하는 방법을 설명하는 방식과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-650">This is analogous to the way the identically named <xref:System.Windows.Data.ListCollectionView> properties describe how to sort the data items.</span></span>

<span data-ttu-id="9bae0-651"><xref:System.Windows.Data.PropertyGroupDescription> 클래스의 새로운 두 정적 속성인 <xref:System.Windows.Data.PropertyGroupDescription.CompareNameAscending%2A> 및 <xref:System.Windows.Data.PropertyGroupDescription.CompareNameDescending%2A>은 가장 일반적인 경우에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-651">Two new static properties of the <xref:System.Windows.Data.PropertyGroupDescription> class,  <xref:System.Windows.Data.PropertyGroupDescription.CompareNameAscending%2A> and <xref:System.Windows.Data.PropertyGroupDescription.CompareNameDescending%2A>, can be used for the most common cases.</span></span>

<span data-ttu-id="9bae0-652">예를 들어 다음 XAML은 데이터를 연령별로 그룹화하고, 연령 그룹을 오름차순으로 정렬한 다음 각 연령 그룹 내의 항목을 성별로 그룹화합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-652">For example, the following XAML groups data by age, sort the age groups in ascending order, and group the items within each age group by last name.</span></span>

```xaml
<GroupDescriptions>
     <PropertyGroupDescription
         PropertyName="Age"
         CustomSort=
              "{x:Static PropertyGroupDescription.CompareNamesAscending}"/>
     </PropertyGroupDescription>
</GroupDescriptions>

<SortDescriptions>
     <SortDescription PropertyName="LastName"/>
</SortDescriptions>
```

<span data-ttu-id="9bae0-653">**터치 키보드 지원**</span><span class="sxs-lookup"><span data-stu-id="9bae0-653">**Touch keyboard support**</span></span>

<span data-ttu-id="9bae0-654">터치 키보드 지원을 사용하면 텍스트 입력을 수행할 수 있는 컨트롤을 통해 터치 입력을 수신할 때 Windows 10의 터치 키보드를 자동으로 호출하거나 해제하여 WPF 애플리케이션에서 포커스를 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-654">Touch keyboard support enables focus tracking in WPF applications by automatically invoking and dismissing the touch Keyboard in Windows 10 when the touch input is received by a control that can take textual input.</span></span>

<span data-ttu-id="9bae0-655">이전 버전 .NET Framework의 WPF 애플리케이션에서는 포커스 추적을 사용하려면 WPF 펜/터치 제스처 지원을 사용하지 않도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-655">In previous versions of .NET Framework, WPF applications can't opt into the focus tracking without disabling WPF pen/touch gesture support.</span></span> <span data-ttu-id="9bae0-656">따라서 WPF 애플리케이션에서는 전체 WPF 터치 지원을 선택하거나 Windows 마우스 승격을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-656">As a result, WPF applications must choose between full WPF touch support or rely on Windows mouse promotion.</span></span>

<span data-ttu-id="9bae0-657">**모니터별 DPI**</span><span class="sxs-lookup"><span data-stu-id="9bae0-657">**Per-monitor DPI**</span></span>

<span data-ttu-id="9bae0-658">최근에 확산되는 높은 DPI 및 하이브리드 DPI 환경을 WPF 앱에 지원하기 위해 .NET Framework 4.6.2의 WPF에서는 모니터별 인식을 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-658">To support the recent proliferation of high-DPI and hybrid-DPI environments for WPF apps, WPF in .NET Framework 4.6.2 enables per-monitor awareness.</span></span> <span data-ttu-id="9bae0-659">모니터별 DPI를 인식하도록 WPF 앱을 설정하는 방법에 대한 자세한 내용은 GitHub의 [samples and developer guide](https://github.com/Microsoft/WPF-Samples/tree/master/PerMonitorDPI)(샘플 및 개발자 가이드)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9bae0-659">See the [samples and developer guide](https://github.com/Microsoft/WPF-Samples/tree/master/PerMonitorDPI) on GitHub for more information about how to enable your WPF app to become per-monitor DPI aware.</span></span>

<span data-ttu-id="9bae0-660">이전 버전의.NET Framework에서는 WPF 앱은 시스템 DPI를 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-660">In previous versions of .NET Framework, WPF apps are system-DPI aware.</span></span> <span data-ttu-id="9bae0-661">즉, 애플리케이션의 UI는 앱이 렌더링되는 모니터의 DPI에 따라 OS에 의해 적절하게 확장됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-661">In other words, the application's UI is scaled by the OS as appropriate, depending on the DPI of the monitor on which the app is rendered.</span></span>

<span data-ttu-id="9bae0-662">.NET Framework 4.6.2에서 실행 중인 앱의 경우 다음과 같이 애플리케이션 구성 파일의 [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) 섹션에 구성 문을 추가하여 WPF 앱에서 모니터별 DPI 변경을 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-662">For apps running under .NET Framework 4.6.2, you can disable per-monitor DPI changes in WPF apps by adding a configuration statement to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of your application configuration file, as follows:</span></span>

```xml
<runtime>
   <AppContextSwitchOverrides value="Switch.System.Windows.DoNotScaleForDpiChanges=false"/>
</runtime>
```

<a name="WF462"></a>

### <a name="windows-workflow-foundation-wf"></a><span data-ttu-id="9bae0-663">Windows WF(Workflow Foundation)</span><span class="sxs-lookup"><span data-stu-id="9bae0-663">Windows Workflow Foundation (WF)</span></span>

<span data-ttu-id="9bae0-664">.NET Framework 4.6.2에서 Windows Workflow Foundation이 다음과 같은 영역에서 향상되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-664">In .NET Framework 4.6.2, Windows Workflow Foundation has been enhanced in the following area:</span></span>

<span data-ttu-id="9bae0-665">**다시 호스트된 WF 디자이너에서 C# 식 및 IntelliSense 지원**</span><span class="sxs-lookup"><span data-stu-id="9bae0-665">**Support for C# expressions and IntelliSense in the Rehosted WF Designer**</span></span>

<span data-ttu-id="9bae0-666">.NET Framework 4.5 이상에서 WF는 Visual Studio 디자이너와 코드 워크플로 모두에서 C# 식을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-666">Starting with .NET Framework 4.5, WF supports C# expressions in both the Visual Studio Designer and in code workflows.</span></span> <span data-ttu-id="9bae0-667">다시 호스트된 워크플로 디자이너는 Visual Studio 외부 애플리케이션(예: WPF)에서 워크플로 디자이너가 위치할 수 있도록 해주는 WF의 주요 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-667">The Rehosted Workflow Designer is a key feature of WF that allows for the Workflow Designer to be in an application outside Visual Studio (for example, in WPF).</span></span>  <span data-ttu-id="9bae0-668">Windows Workflow Foundation을 사용하면 다시 호스트된 워크플로 디자이너에서 C# 식 및 IntelliSense를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-668">Windows Workflow Foundation provides the ability to support C# expressions and IntelliSense in the Rehosted Workflow Designer.</span></span> <span data-ttu-id="9bae0-669">자세한 내용은 [Windows Workflow Foundation 블로그](/archive/blogs/workflowteam/building-c-expressions-support-and-intellisense-in-the-rehosted-workflow-designer)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9bae0-669">For more information, see the [Windows Workflow Foundation blog](/archive/blogs/workflowteam/building-c-expressions-support-and-intellisense-in-the-rehosted-workflow-designer).</span></span>

<span data-ttu-id="9bae0-670">`Availability of IntelliSense when a customer rebuilds a workflow project from Visual Studio` 4.6.2 이전 버전의 .NET Framework에서는 고객이 Visual Studio에서 워크플로 프로젝트를 다시 작성할 때 WF 디자이너 IntelliSense가 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-670">`Availability of IntelliSense when a customer rebuilds a workflow project from Visual Studio` In versions of the .NET Framework prior to 4.6.2, WF Designer IntelliSense is broken when a customer rebuilds a workflow project from Visual Studio.</span></span> <span data-ttu-id="9bae0-671">프로젝트가 빌드되면 워크플로 형식을 디자이너에서 찾을 수 없으므로 IntelliSense의 누락된 워크플로 형식에 대한 경고가 **오류 목록** 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-671">While the project build is successful, the workflow types are not found on the designer, and warnings from IntelliSense for the missing workflow types appear in the **Error List** window.</span></span> <span data-ttu-id="9bae0-672">.NET Framework 4.6.2에서는 이 문제를 해결하고 IntelliSense를 사용할 수 있도록 해줍니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-672">.NET Framework 4.6.2 addresses this issue and makes IntelliSense available.</span></span>

<span data-ttu-id="9bae0-673">**워크플로 추적 기능이 설정된 Workflow V1 애플리케이션을 이제 FIPS 모드로 실행 가능**</span><span class="sxs-lookup"><span data-stu-id="9bae0-673">**Workflow V1 applications with Workflow Tracking on now run under FIPS-mode**</span></span>

<span data-ttu-id="9bae0-674">이제 FIPS 호환성 모드를 사용하는 컴퓨터에서 워크플로 추적이 설정된 워크플로 버전 1 스타일 애플리케이션을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-674">Machines with FIPS Compliance Mode enabled can now successfully run a workflow Version 1-style application with Workflow tracking on.</span></span> <span data-ttu-id="9bae0-675">이 시나리오를 사용하려면 app.config 파일을 다음과 같이 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-675">To enable this scenario, you must make the following change to your app.config file:</span></span>

```xml
<add key="microsoft:WorkflowRuntime:FIPSRequired" value="true" />
```

<span data-ttu-id="9bae0-676">이 시나리오를 사용하지 않도록 설정한 경우 애플리케이션을 실행하면 계속해서 예외가 발생하고 “이 구현은 Windows Platform FIPS 유효성을 검사한 암호화 알고리즘의 일부가 아닙니다.”라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-676">If this scenario is not enabled, running the application continues to generate an exception with the message, "This implementation is not part of the Windows Platform FIPS validated cryptographic algorithms."</span></span>

<span data-ttu-id="9bae0-677">**Visual Studio Workflow Designer에서 동적 업데이트를 사용할 때 워크플로 기능 향상**</span><span class="sxs-lookup"><span data-stu-id="9bae0-677">**Workflow Improvements when using Dynamic Update with Visual Studio Workflow Designer**</span></span>

<span data-ttu-id="9bae0-678">워크플로 디자이너, 순서도 활동 디자이너 및 기타 워크플로 활동 디자이너는 이제 <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=nameWithType> 메서드를 호출한 이후에 저장된 워크플로를 로드하여 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-678">The Workflow Designer, FlowChart Activity Designer, and other Workflow Activity Designers now successfully load and display workflows that have been saved after calling  the <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="9bae0-679">.NET Framework 4.6.2 이전 버전의 .NET Framework에서는 <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=nameWithType> 호출 후에 저장된 워크플로에 대한 XAML 파일을 Visual Studio에서 로드하면 다음과 같은 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-679">In versions of the .NET Framework before .NET Framework 4.6.2, loading a XAML file in Visual Studio for a workflow that has been saved after calling <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=nameWithType> can result in the following issues:</span></span>

- <span data-ttu-id="9bae0-680">워크플로 디자이너에서 XAML 파일을 올바르게 로드할 수 없습니다(<xref:System.Activities.Presentation.ViewState.ViewStateData.Id%2A?displayProperty=nameWithType>가 줄의 끝에 있는 경우).</span><span class="sxs-lookup"><span data-stu-id="9bae0-680">The Workflow Designer can't load the XAML file correctly (when the <xref:System.Activities.Presentation.ViewState.ViewStateData.Id%2A?displayProperty=nameWithType> is at the end of the line).</span></span>

- <span data-ttu-id="9bae0-681">순서도 활동 디자이너 또는 기타 워크플로 활동 디자이너는 연결된 속성 값과 달리 모든 개체를 기본 위치에 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-681">Flowchart Activity Designer or other Workflow Activity Designers may display all objects in their default locations as opposed to attached property values.</span></span>

<a name="clickonce-1"></a>

### <a name="clickonce"></a><span data-ttu-id="9bae0-682">ClickOnce</span><span class="sxs-lookup"><span data-stu-id="9bae0-682">ClickOnce</span></span>

<span data-ttu-id="9bae0-683">ClickOnce는 이미 지원되는 1.0 프로토콜 외에 TLS 1.1 및 TLS 1.2를 지원하도록 업데이트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-683">ClickOnce has been updated to support TLS 1.1 and TLS 1.2 in addition to the 1.0 protocol, which it already supports.</span></span> <span data-ttu-id="9bae0-684">ClickOnce는 필요한 프로토콜을 자동으로 검색하므로, TLS 1.1 및 1.2 지원하기 위해 ClickOnce 애플리케이션에서 별도의 단계를 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-684">ClickOnce automatically detects which protocol is required; no extra steps within the ClickOnce application are required to enable TLS 1.1 and 1.2 support.</span></span>

<a name="UWPConvert"></a>

### <a name="converting-windows-forms-and-wpf-apps-to--uwp-apps"></a><span data-ttu-id="9bae0-685">Windows Forms 및 WPF 앱을 UWP 앱으로 변환</span><span class="sxs-lookup"><span data-stu-id="9bae0-685">Converting Windows Forms and WPF apps to  UWP apps</span></span>

<span data-ttu-id="9bae0-686">이제 Windows에서는 기존 Windows 데스크톱 앱(예: WPF 및 Windows Forms 앱)을 UWP(유니버설 Windows 플랫폼)로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-686">Windows now offers capabilities to bring existing Windows desktop apps, including WPF and Windows Forms apps, to the Universal Windows Platform (UWP).</span></span> <span data-ttu-id="9bae0-687">이 기술은 기존 코드 베이스를 UWP로 점차적으로 마이그레이션하여 앱을 모든 Windows 10 디바이스로 가져옴으로써 브리지 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-687">This technology acts as a bridge by enabling you to gradually migrate your existing code base to UWP, thereby bringing your app to all Windows 10 devices.</span></span>

<span data-ttu-id="9bae0-688">변환된 데스크톱 앱은 UWP 앱의 ID와 비슷한 앱 ID를 얻습니다. 이 ID를 사용하여 UWP API에 액세스하여 라이브 타일, 알림 등과 같은 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-688">Converted desktop apps gain an app identity similar to the app identity of UWP apps, which makes UWP APIs accessible to enable features such as Live Tiles and notifications.</span></span> <span data-ttu-id="9bae0-689">앱은 이전과 동일하게 작동하고 완전히 신뢰할 수 있는 앱으로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-689">The app continues to behave as before and runs as a full trust app.</span></span> <span data-ttu-id="9bae0-690">앱이 변환되면 기존 완전 신뢰 프로세스에 앱 컨테이너 프로세스를 추가하여 적응형 사용자 인터페이스를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-690">Once the app is converted, an app container process can be added to the existing full trust process to add an adaptive user interface.</span></span> <span data-ttu-id="9bae0-691">모든 기능을 앱 컨테이너 프로세스로 이동한 후 완전 신뢰 프로세스를 제거하고 모든 Windows 10 디바이스에서 새 UWP 앱을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-691">When all functionality is moved to the app container process, the full trust process can be removed and the new UWP app can be made available to all Windows 10 devices.</span></span>

<a name="Debug462"></a>

### <a name="debugging-improvements"></a><span data-ttu-id="9bae0-692">디버깅 기능 향상</span><span class="sxs-lookup"><span data-stu-id="9bae0-692">Debugging improvements</span></span>

<span data-ttu-id="9bae0-693">단일 소스 코드 줄에서 `null`인 변수를 확인할 수 있도록 <xref:System.NullReferenceException>이 throw될 때 추가 분석을 수행하도록 .NET Framework 4.6.2에서 ‘비관리형 디버깅 API’가 개선되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-693">The *unmanaged debugging API* has been enhanced in .NET Framework 4.6.2 to perform additional analysis when a <xref:System.NullReferenceException> is thrown so that it is possible to determine which variable in a single line of source code is `null`.</span></span>   <span data-ttu-id="9bae0-694">이 시나리오를 지원하기 위해 관리되지 않는 디버깅 API에 다음 API를 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-694">To support this scenario, the following APIs have been added to the unmanaged debugging API.</span></span>

- <span data-ttu-id="9bae0-695">[ICorDebugCode4](../unmanaged-api/debugging/icordebugcode4-interface.md), [ICorDebugVariableHome](../unmanaged-api/debugging/icordebugvariablehome-interface.md) 및 [ICorDebugVariableHomeEnum](../unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) 인터페이스: 관리되는 변수의 네이티브 홈을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-695">The [ICorDebugCode4](../unmanaged-api/debugging/icordebugcode4-interface.md), [ICorDebugVariableHome](../unmanaged-api/debugging/icordebugvariablehome-interface.md), and [ICorDebugVariableHomeEnum](../unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) interfaces, which expose the native homes of managed variables.</span></span> <span data-ttu-id="9bae0-696">이렇게 하면 <xref:System.NullReferenceException>가 발생할 경우 디버거에서 일부 코드 흐름 분석을 수행하고 거꾸로 살펴보면서 네이티브 위치 `null`에 해당하는 관리되는 변수를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-696">This enables debuggers to do some code flow analysis when a  <xref:System.NullReferenceException> occurs and to work backwards to determine the managed variable that corresponds to the native location that was `null`.</span></span>

- <span data-ttu-id="9bae0-697">[ICorDebugType2::GetTypeID](../unmanaged-api/debugging/icordebugtype2-gettypeid-method.md) 메서드는 ICorDebugType을 [COR_TYPEID](../unmanaged-api/debugging/cor-typeid-structure.md)에 매핑하여 디버거가 ICorDebugType 인스턴스 없이 [COR_TYPEID](../unmanaged-api/debugging/cor-typeid-structure.md)를 가져올 수 있도록 해줍니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-697">The [ICorDebugType2::GetTypeID](../unmanaged-api/debugging/icordebugtype2-gettypeid-method.md) method provides a mapping for ICorDebugType to [COR_TYPEID](../unmanaged-api/debugging/cor-typeid-structure.md), which allows the debugger to obtain a [COR_TYPEID](../unmanaged-api/debugging/cor-typeid-structure.md) without an instance of the ICorDebugType.</span></span> <span data-ttu-id="9bae0-698">그런 다음 [COR_TYPEID](../unmanaged-api/debugging/cor-typeid-structure.md)의 기존 API를 사용하여 형식의 클래스 레이아웃을 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-698">Existing APIs on [COR_TYPEID](../unmanaged-api/debugging/cor-typeid-structure.md) can then be used to determine the class layout of the type.</span></span>

<a name="v461"></a>

## <a name="whats-new-in-net-framework-461"></a><span data-ttu-id="9bae0-699">.NET Framework 4.6.1의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="9bae0-699">What's new in .NET Framework 4.6.1</span></span>

<span data-ttu-id="9bae0-700">.NET Framework 4.6.1에는 다음 영역의 새 기능이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-700">.NET Framework 4.6.1 includes new features in the following areas:</span></span>

- [<span data-ttu-id="9bae0-701">암호화</span><span class="sxs-lookup"><span data-stu-id="9bae0-701">Cryptography</span></span>](#Crypto)

- [<span data-ttu-id="9bae0-702">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="9bae0-702">ADO.NET</span></span>](#ADO.NET461)

- [<span data-ttu-id="9bae0-703">WPF(Windows Presentation Foundation)</span><span class="sxs-lookup"><span data-stu-id="9bae0-703">Windows Presentation Foundation (WPF)</span></span>](#WPF461)

- [<span data-ttu-id="9bae0-704">Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="9bae0-704">Windows Workflow Foundation</span></span>](#WWF461)

- [<span data-ttu-id="9bae0-705">프로파일링</span><span class="sxs-lookup"><span data-stu-id="9bae0-705">Profiling</span></span>](#Profile461)

- [<span data-ttu-id="9bae0-706">NGen</span><span class="sxs-lookup"><span data-stu-id="9bae0-706">NGen</span></span>](#NGEN461)

<span data-ttu-id="9bae0-707">.NET Framework 4.6.1에 대한 자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bae0-707">For more information on .NET Framework 4.6.1, see the following topics:</span></span>

- [<span data-ttu-id="9bae0-708">.NET Framework 4.6.1 변경 내용 목록</span><span class="sxs-lookup"><span data-stu-id="9bae0-708">.NET Framework 4.6.1 list of changes</span></span>](https://github.com/Microsoft/dotnet/blob/master/releases/net461/dotnet461-changes.md)

- [<span data-ttu-id="9bae0-709">4.6.1의 애플리케이션 호환성</span><span class="sxs-lookup"><span data-stu-id="9bae0-709">Application Compatibility in 4.6.1</span></span>](../migration-guide/application-compatibility.md)

- <span data-ttu-id="9bae0-710">[.NET Framework API 차이점](https://github.com/Microsoft/dotnet/blob/master/releases/net461/dotnet461-api-changes.md)(GitHub에서)</span><span class="sxs-lookup"><span data-stu-id="9bae0-710">[.NET Framework API diff](https://github.com/Microsoft/dotnet/blob/master/releases/net461/dotnet461-api-changes.md) (on GitHub)</span></span>

<a name="Crypto"></a>

### <a name="cryptography-support-for-x509-certificates-containing-ecdsa"></a><span data-ttu-id="9bae0-711">암호화: ECDSA를 포함하는 X509 인증서 지원</span><span class="sxs-lookup"><span data-stu-id="9bae0-711">Cryptography: Support for X509 certificates containing ECDSA</span></span>

<span data-ttu-id="9bae0-712">.NET Framework 4.6에는 x509 인증서를 위한 RSACng 지원이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-712">.NET Framework 4.6 added RSACng support for X509 certificates.</span></span> <span data-ttu-id="9bae0-713">.NET Framework 4.6.1에는 ECDSA(타원 곡선 디지털 서명 알고리즘) X509 인증서에 대한 지원이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-713">.NET Framework 4.6.1 adds support for ECDSA (Elliptic Curve Digital Signature Algorithm) X509 certificates.</span></span>

<span data-ttu-id="9bae0-714">ECDSA는 RSA보다 더 향상된 성능과 더 안전한 암호화 알고리즘을 제공하므로 TLS(전송 계층 보안) 성능 및 확장성 면에서 최고의 선택이 될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-714">ECDSA offers better performance and is a more secure cryptography algorithm than RSA, providing an excellent choice where Transport Layer Security (TLS) performance and scalability is a concern.</span></span> <span data-ttu-id="9bae0-715">.NET Framework 구현은 기존 Windows 기능으로 호출을 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-715">The .NET Framework implementation wraps calls into existing Windows functionality.</span></span>

<span data-ttu-id="9bae0-716">다음 예제 코드에서는 .NET Framework 4.6.1에 포함된 ECDSA  X509 인증서에 대한 새 지원을 사용하여 바이트 스트림을 위한 서명을 쉽게 생성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-716">The following example code shows how easy it is to generate a signature for a byte stream by using the new  support for ECDSA  X509 certificates included in .NET Framework 4.6.1.</span></span>

[!code-csharp[whatsnew.461.crypto#1](~/samples/snippets/csharp/VS_Snippets_CLR/whatsnew.461.crypto/cs/Code46.cs#1)]
[!code-vb[whatsnew.461.crypto#1](~/samples/snippets/visualbasic/VS_Snippets_CLR/whatsnew.461.crypto/vb/Code461.vb#1)]

<span data-ttu-id="9bae0-717">다음은 .NET Framework 4.6에서 서명을 생성하는 데 필요한 코드에 표시된 대비를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-717">This offers a marked contrast to the code needed to generate a signature in .NET Framework 4.6.</span></span>

[!code-csharp[whatsnew.461.crypto#2](~/samples/snippets/csharp/VS_Snippets_CLR/whatsnew.461.crypto/cs/Code46.cs#2)]
[!code-vb[whatsnew.461.crypto#2](~/samples/snippets/visualbasic/VS_Snippets_CLR/whatsnew.461.crypto/vb/Code46.vb#2)]

<a name="ADO.NET461"></a>

### <a name="adonet"></a><span data-ttu-id="9bae0-718">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="9bae0-718">ADO.NET</span></span>

<span data-ttu-id="9bae0-719">ADO.NET에는 다음이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-719">The following have been added to ADO.NET:</span></span>

<span data-ttu-id="9bae0-720">**하드웨어로 보호된 키에 대해 Always Encrypted 지원**</span><span class="sxs-lookup"><span data-stu-id="9bae0-720">**Always Encrypted support for hardware protected keys**</span></span>

<span data-ttu-id="9bae0-721">ADO.NET은 이제 상시 암호화 열 마스터 키를 HSM(하드웨어 보안 모듈)에 고유하게 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-721">ADO.NET now supports storing Always Encrypted column master keys natively in Hardware Security Modules (HSMs).</span></span> <span data-ttu-id="9bae0-722">이 지원을 통해 고객은 사용자 지정 열 마스터 키 저장소 공급자를 작성하고 애플리케이션에 등록하지 않고도 HSM에 저장된 비동기 키를 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-722">With this support, customers can leverage asymmetric keys stored in HSMs without having to write custom column master key store providers and registering them in applications.</span></span>

<span data-ttu-id="9bae0-723">HSM에 저장된 열 마스터 키로 보호된 상시 암호화 데이터에 액세스하려면 고객이 HSM 공급업체에서 제공한 CSP 공급자 또는 CNG 키 저장소 공급자를 앱 서버 또는 클라이언트 컴퓨터에 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-723">Customers need to install the HSM vendor-provided CSP provider or CNG key store providers on the app servers or client computers in order to access Always Encrypted data protected with column master keys stored in a HSM.</span></span>

<span data-ttu-id="9bae0-724">**AlwaysOn의 <xref:System.Data.SqlClient.SqlConnectionStringBuilder.MultiSubnetFailover%2A> 연결 동작 개선**</span><span class="sxs-lookup"><span data-stu-id="9bae0-724">**Improved <xref:System.Data.SqlClient.SqlConnectionStringBuilder.MultiSubnetFailover%2A> connection behavior for AlwaysOn**</span></span>

<span data-ttu-id="9bae0-725">SqlClient는 이제 자동으로 AlwaysOn AG(가용성 그룹)에 대한 더 빠른 연결을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-725">SqlClient now automatically provides faster connections to an AlwaysOn Availability Group (AG).</span></span> <span data-ttu-id="9bae0-726">애플리케이션이 다른 서브넷의 AlwaysOn AG(가용성 그룹)에 연결되었는지 투명하게 감지하고 현재 활성 서버를 신속하게 검색하여 서버에 대한 연결을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-726">It transparently detects whether your application is connecting to an AlwaysOn availability group (AG) on a different subnet and quickly discovers the current active server and provides a connection to the server.</span></span> <span data-ttu-id="9bae0-727">이 릴리스 전에는 AlwaysOn 가용성 그룹에 연결되었음을 나타내기 위해 애플리케이션에서 `"MultisubnetFailover=true"`를 포함하도록 연결 문자열을 설정해야 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-727">Prior to this release, an application had to set the connection string to include `"MultisubnetFailover=true"` to indicate that it was connecting to an AlwaysOn Availability Group.</span></span> <span data-ttu-id="9bae0-728">연결 키워드를 `true`로 설정하지 않은 경우 애플리케이션에서 AlwaysOn 가용성 그룹에 연결하는 동안 시간 초과가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-728">Without setting the connection keyword to `true`, an application might experience a timeout while connecting to an AlwaysOn Availability Group.</span></span> <span data-ttu-id="9bae0-729">이 릴리스에서는 더 이상 애플리케이션에서 <xref:System.Data.SqlClient.SqlConnectionStringBuilder.MultiSubnetFailover%2A>를 `true`로 설정할 필요가 *없습니다*.</span><span class="sxs-lookup"><span data-stu-id="9bae0-729">With this release, an application does *not* need to set <xref:System.Data.SqlClient.SqlConnectionStringBuilder.MultiSubnetFailover%2A> to `true` anymore.</span></span> <span data-ttu-id="9bae0-730">Always On 가용성 그룹의 SqlClient 지원에 대한 자세한 내용은 [고가용성 및 재해 복구에 대한 SqlClient 지원](../data/adonet/sql/sqlclient-support-for-high-availability-disaster-recovery.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9bae0-730">For more information about SqlClient support for Always On Availability Groups, see [SqlClient Support for High Availability, Disaster Recovery](../data/adonet/sql/sqlclient-support-for-high-availability-disaster-recovery.md).</span></span>

<a name="WPF461"></a>

### <a name="windows-presentation-foundation-wpf"></a><span data-ttu-id="9bae0-731">WPF(Windows Presentation Foundation)</span><span class="sxs-lookup"><span data-stu-id="9bae0-731">Windows Presentation Foundation (WPF)</span></span>

<span data-ttu-id="9bae0-732">Windows Presentation Foundation에는 많은 향상된 기능 및 변경 내용이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-732">Windows Presentation Foundation includes a number of improvements and changes.</span></span>

<span data-ttu-id="9bae0-733">**향상된 성능**</span><span class="sxs-lookup"><span data-stu-id="9bae0-733">**Improved performance**</span></span>

<span data-ttu-id="9bae0-734">.NET Framework 4.6.1에서 터치 이벤트를 발생시킬 때의 지연이 수정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-734">The delay in firing touch events has been fixed in .NET Framework 4.6.1.</span></span> <span data-ttu-id="9bae0-735">또한 빠른 입력 중 <xref:System.Windows.Controls.RichTextBox> 컨트롤에 입력한 내용이 더 이상 렌더링 스레드에 연결되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-735">In addition, typing in a <xref:System.Windows.Controls.RichTextBox> control no longer ties up the render thread during fast input.</span></span>

<span data-ttu-id="9bae0-736">**향상된 맞춤법 검사**</span><span class="sxs-lookup"><span data-stu-id="9bae0-736">**Spell checking improvements**</span></span>

<span data-ttu-id="9bae0-737">Windows 8.1 이상 버전에서는 추가 언어 맞춤법 검사에 대한 운영 체제 지원을 사용하도록 WPF의 맞춤법 검사기 기능이 업데이트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-737">The spell checker in WPF has been updated on Windows 8.1 and later versions to leverage operating system support for spell-checking additional languages.</span></span>  <span data-ttu-id="9bae0-738">Windows 8.1 이전의 Windows 버전에 대해서는 기능이 변경되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-738">There is no change in functionality on Windows versions prior to Windows 8.1.</span></span>

<span data-ttu-id="9bae0-739">이전 버전의 .NET Framework와 마찬가지로, 다음 순서에 따라 정보를 검색하여 <xref:System.Windows.Controls.TextBox> 컨트롤 또는 <xref:System.Windows.Controls.RichTextBox> 블록의 언어를 감지합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-739">As in previous versions of .NET Framework, the language for a <xref:System.Windows.Controls.TextBox> control ora <xref:System.Windows.Controls.RichTextBox> block is detected by looking for information in the following order:</span></span>

- <span data-ttu-id="9bae0-740">`xml:lang`(있는 경우)</span><span class="sxs-lookup"><span data-stu-id="9bae0-740">`xml:lang`, if it is present.</span></span>

- <span data-ttu-id="9bae0-741">현재 입력 언어</span><span class="sxs-lookup"><span data-stu-id="9bae0-741">Current input language.</span></span>

- <span data-ttu-id="9bae0-742">현재 스레드 문화권</span><span class="sxs-lookup"><span data-stu-id="9bae0-742">Current thread culture.</span></span>

<span data-ttu-id="9bae0-743">WPF의 언어 지원에 대한 자세한 내용은 [.NET Framework 4.6.1 기능에 대한 WPF 블로그 게시물](https://devblogs.microsoft.com/wpf/wpf-in-net-4-6-1/)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bae0-743">For more information on language support in WPF, see the [WPF blog post on .NET Framework 4.6.1 features](https://devblogs.microsoft.com/wpf/wpf-in-net-4-6-1/).</span></span>

<span data-ttu-id="9bae0-744">**사용자 단위 사용자 지정 사전에 대한 추가 지원**</span><span class="sxs-lookup"><span data-stu-id="9bae0-744">**Additional support for per-user custom dictionaries**</span></span>

<span data-ttu-id="9bae0-745">.NET Framework 4.6.1에서 WPF는 전역으로 등록된 사용자 지정 사전을 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-745">In .NET Framework 4.6.1, WPF recognizes custom dictionaries that are registered globally.</span></span> <span data-ttu-id="9bae0-746">컨트롤 단위로 등록하는 기능 외에 이 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-746">This capability is available in addition to the ability to register them per-control.</span></span>

<span data-ttu-id="9bae0-747">WPF 이전 버전에서는 사용자 지정 사전에서 제외된 단어 및 자동 고침 목록을 인식하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-747">In previous versions of WPF, custom dictionaries did not recognize Excluded Words and AutoCorrect lists.</span></span> <span data-ttu-id="9bae0-748">Windows 8.1 및 Windows 10에서는 `%AppData%\Microsoft\Spelling\<language tag>` 디렉터리에 저장할 수 있는 파일을 사용하여 이러한 기능이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-748">They are supported on Windows 8.1 and Windows 10 through the use of files that can be placed under the `%AppData%\Microsoft\Spelling\<language tag>` directory.</span></span>  <span data-ttu-id="9bae0-749">이러한 파일에 적용되는 규칙은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-749">The following rules apply to these files:</span></span>

- <span data-ttu-id="9bae0-750">파일의 확장명은 .dic(추가된 단어용), .exc(제외된 단어용) 또는 .acl(자동 고침용)입니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-750">The files should have extensions of .dic (for added words), .exc (for excluded words), or .acl (for AutoCorrect).</span></span>

- <span data-ttu-id="9bae0-751">파일은 BOM(바이트 순서 표시)으로 시작하는 UTF-16 LE 일반 텍스트여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-751">The files should be UTF-16 LE plaintext that starts with the Byte Order Mark (BOM).</span></span>

- <span data-ttu-id="9bae0-752">각 줄은 단어(추가되거나 제외된 단어 목록의 단어) 또는 단어가 세로 막대(“&#124;”)로 구분된 자동 고침 쌍(자동 고침 단어 목록)으로 구성되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-752">Each line should consist of a word (in the added and excluded word lists), or an autocorrect pair with the words separated by a vertical bar ("&#124;") (in the AutoCorrect word list).</span></span>

- <span data-ttu-id="9bae0-753">이러한 파일은 읽기 전용으로 간주되며 시스템에 의해 수정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-753">These files are considered read-only and are not modified by the system.</span></span>

> [!NOTE]
> <span data-ttu-id="9bae0-754">이러한 새 파일 형식은 WPF 맞춤법 검사 API에 의해 직접 지원되지 않으며 애플리케이션에서 WPF에 제공된 사용자 지정 사전은 계속 .lex 파일을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-754">These new file-formats are not directly supported by the WPF spell checking APIs, and the custom dictionaries supplied to WPF in applications should continue to use .lex files.</span></span>

<span data-ttu-id="9bae0-755">**샘플**</span><span class="sxs-lookup"><span data-stu-id="9bae0-755">**Samples**</span></span>

<span data-ttu-id="9bae0-756">[Microsoft/WPF 샘플](https://github.com/Microsoft/WPF-Samples) GitHub 리포지토리에는 여러 가지 WPF 샘플이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-756">There are a number of WPF samples on the [Microsoft/WPF-Samples](https://github.com/Microsoft/WPF-Samples) GitHub repository.</span></span> <span data-ttu-id="9bae0-757">끌어오기 요청을 보내거나 [GitHub 문제](https://github.com/Microsoft/WPF-Samples/issues)를 열어 샘플 개선에 참여해 주세요.</span><span class="sxs-lookup"><span data-stu-id="9bae0-757">Help us improve our samples by sending us a pull-request or opening a [GitHub issue](https://github.com/Microsoft/WPF-Samples/issues).</span></span>

<span data-ttu-id="9bae0-758">**DirectX 확장**</span><span class="sxs-lookup"><span data-stu-id="9bae0-758">**DirectX extensions**</span></span>

<span data-ttu-id="9bae0-759">WPF에는 DX10 및 Dx11 콘텐츠와 쉽게 상호 운용할 수 있는 <xref:System.Windows.Interop.D3DImage>의 새 구현을 제공하는 [NuGet 패키지](https://www.nuget.org/packages/Microsoft.Wpf.Interop.DirectX-x86/)가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-759">WPF includes a [NuGet package](https://www.nuget.org/packages/Microsoft.Wpf.Interop.DirectX-x86/) that provides new implementations of <xref:System.Windows.Interop.D3DImage> that make it easy for you to interoperate with DX10 and Dx11 content.</span></span> <span data-ttu-id="9bae0-760">이 패키지의 코드는 오픈 소스로 [GitHub](https://github.com/Microsoft/WPFDXInterop)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-760">The code for this package has been open sourced and is available [on GitHub](https://github.com/Microsoft/WPFDXInterop).</span></span>

<a name="WWF461"></a>

### <a name="windows-workflow-foundation-transactions"></a><span data-ttu-id="9bae0-761">Windows Workflow Foundation: 의</span><span class="sxs-lookup"><span data-stu-id="9bae0-761">Windows Workflow Foundation: Transactions</span></span>

<span data-ttu-id="9bae0-762"><xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A?displayProperty=nameWithType> 메서드는 이제 MSDTC 이외의 분산 트랜잭션 관리자를 사용하여 트랜잭션을 승격할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-762">The <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A?displayProperty=nameWithType> method can now use a distributed transaction manager other than MSDTC to promote the transaction.</span></span> <span data-ttu-id="9bae0-763">이 작업을 수행하려면 GUID 트랜잭션 프로모터 식별자를 새 <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%28System.Transactions.IPromotableSinglePhaseNotification%2CSystem.Guid%29?displayProperty=nameWithType> 오버로드로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-763">You do this by specifying a GUID transaction promoter identifier to the  new <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%28System.Transactions.IPromotableSinglePhaseNotification%2CSystem.Guid%29?displayProperty=nameWithType> overload .</span></span> <span data-ttu-id="9bae0-764">이 작업이 성공한 경우 트랜잭션 기능이 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-764">If this operation is successful, there are limitations placed on the capabilities of the transaction.</span></span> <span data-ttu-id="9bae0-765">비 MSDTC 트랜잭션 프로모터가 등록된 경우 다음 메서드는 MSDTC로의 승격이 필요하므로 <xref:System.Transactions.TransactionPromotionException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-765">Once a non-MSDTC transaction promoter is enlisted, the following methods throw a <xref:System.Transactions.TransactionPromotionException> because these methods require promotion to MSDTC:</span></span>

- <xref:System.Transactions.Transaction.EnlistDurable%2A?displayProperty=nameWithType>

- <xref:System.Transactions.TransactionInterop.GetDtcTransaction%2A?displayProperty=nameWithType>

- <xref:System.Transactions.TransactionInterop.GetExportCookie%2A?displayProperty=nameWithType>

- <xref:System.Transactions.TransactionInterop.GetTransmitterPropagationToken%2A?displayProperty=nameWithType>

<span data-ttu-id="9bae0-766">비 MSDTC 트랜잭션 프로모터가 등록된 경우 향후 정의된 프로토콜을 사용하여 지속적인 인리스트먼트에 사용되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-766">Once a non-MSDTC transaction promoter is enlisted, it must be used for future durable enlistments by using protocols that it defines.</span></span> <span data-ttu-id="9bae0-767">트랜잭션 프로모터의 <xref:System.Guid>는 <xref:System.Transactions.Transaction.PromoterType%2A> 속성을 사용하여 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-767">The <xref:System.Guid> of the transaction promoter can be obtained by using the <xref:System.Transactions.Transaction.PromoterType%2A> property.</span></span> <span data-ttu-id="9bae0-768">트랜잭션이 승격될 때 트랜잭션 프로모터는 승격된 토큰을 나타내는 <xref:System.Byte> 배열을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-768">When the transaction promotes, the transaction promoter provides a <xref:System.Byte> array that represents the promoted token.</span></span> <span data-ttu-id="9bae0-769">애플리케이션에서는 <xref:System.Transactions.Transaction.GetPromotedToken%2A> 메서드를 사용하여 비 MSDTC 승격된 트랜잭션에 대한 승격된 토큰을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-769">An application can obtain the promoted token for a non-MSDTC promoted transaction with the <xref:System.Transactions.Transaction.GetPromotedToken%2A> method.</span></span>

<span data-ttu-id="9bae0-770">승격 작업을 완료하려면 새 <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%28System.Transactions.IPromotableSinglePhaseNotification%2CSystem.Guid%29?displayProperty=nameWithType> 오버로드 사용자가 특정 호출 시퀀스를 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-770">Users of the new <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%28System.Transactions.IPromotableSinglePhaseNotification%2CSystem.Guid%29?displayProperty=nameWithType> overload must follow a specific call sequence in order for the promotion operation to complete successfully.</span></span> <span data-ttu-id="9bae0-771">이러한 규칙은 메서드 설명서에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-771">These rules are documented in the method's documentation.</span></span>

<a name="Profile461"></a>

### <a name="profiling"></a><span data-ttu-id="9bae0-772">프로파일링</span><span class="sxs-lookup"><span data-stu-id="9bae0-772">Profiling</span></span>

<span data-ttu-id="9bae0-773">관리되지 않는 프로파일링 API가 다음과 같이 개선되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-773">The unmanaged profiling API has been enhanced as follows:</span></span>

- <span data-ttu-id="9bae0-774">[ICorProfilerInfo7](../unmanaged-api/profiling/icorprofilerinfo7-interface.md) 인터페이스에서 PDB 액세스에 대한 지원 개선</span><span class="sxs-lookup"><span data-stu-id="9bae0-774">Better support for accessing PDBs in the [ICorProfilerInfo7](../unmanaged-api/profiling/icorprofilerinfo7-interface.md) interface.</span></span>

  <span data-ttu-id="9bae0-775">ASP.NET Core에서는 Roslyn에 의해 어셈블리가 메모리 내에서 컴파일되는 경우가 더 많아지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-775">In ASP.NET Core, it is becoming much more common for assemblies to be compiled in-memory by Roslyn.</span></span> <span data-ttu-id="9bae0-776">프로파일링 도구를 만드는 개발자에게 있어 이는 지금까지 디스크에 serialize되던 PDB가 더 이상 존재하지 않는다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-776">For developers making profiling tools, this means that PDBs that historically were serialized on disk may no longer be present.</span></span> <span data-ttu-id="9bae0-777">프로파일러 도구는 종종 코드 검사 또는 줄 단위 성능 분석 등의 작업을 위해 PDB를 사용하여 코드를 다시 소스 줄에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-777">Profiler tools often use PDBs to map code back to source lines for tasks such as code coverage or line-by-line performance analysis.</span></span> <span data-ttu-id="9bae0-778">[ICorProfilerInfo7](../unmanaged-api/profiling/icorprofilerinfo7-interface.md) 인터 페이스는 [ICorProfilerInfo7::GetInMemorySymbolsLength](../unmanaged-api/profiling/icorprofilerinfo7-getinmemorysymbolslength-method.md)와 [ICorProfilerInfo7::ReadInMemorySymbols](../unmanaged-api/profiling/icorprofilerinfo7-readinmemorysymbols.md)의 두 가지 새로운 메서드를 포함합니다. 이 인터페이스에는 이제 메모리 내 PDB 데이터에 대한 액세스 권한과 함께 이러한 프로파일러 도구를 제공하는 새 메서드가 포함됩니다. 새 API를 사용하면 프로파일러가 메모리 내 PDB 콘텐츠를 바이트 배열로 가져온 다음 처리하거나 디스크로 직렬화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-778">The [ICorProfilerInfo7](../unmanaged-api/profiling/icorprofilerinfo7-interface.md) interface now includes two new methods, [ICorProfilerInfo7::GetInMemorySymbolsLength](../unmanaged-api/profiling/icorprofilerinfo7-getinmemorysymbolslength-method.md) and [ICorProfilerInfo7::ReadInMemorySymbols](../unmanaged-api/profiling/icorprofilerinfo7-readinmemorysymbols.md), to provide these profiler tools with access to the in-memory PDB data, By using the new APIs, a profiler can obtain the contents of an in-memory PDB as a byte array and then process it or serialize it to disk.</span></span>

- <span data-ttu-id="9bae0-779">ICorProfiler 인터페이스를 사용하여 계측 개선</span><span class="sxs-lookup"><span data-stu-id="9bae0-779">Better instrumentation with the ICorProfiler interface.</span></span>

  <span data-ttu-id="9bae0-780">동적 계측을 위해 `ICorProfiler` API의 ReJit 기능을 사용하는 프로파일러는 이제 일부 메타데이터를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-780">Profilers that are using the `ICorProfiler` APIs ReJit functionality for dynamic instrumentation can now modify some metadata.</span></span> <span data-ttu-id="9bae0-781">이전에는 이러한 도구를 사용하여 언제든지 IL을 계측할 수 있었지만 메타데이터는 모듈 로드 시에만 수정할 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-781">Previously such tools could instrument IL at any time, but metadata could only be modified at module load time.</span></span> <span data-ttu-id="9bae0-782">IL은 메타데이터를 참조하므로 수행할 수 있는 계측 종류에 한계가 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-782">Because IL refers to metadata, this limited the kinds of instrumentation that could be done.</span></span> <span data-ttu-id="9bae0-783">모듈 로드 후의 메타데이터 하위 집합 편집을 지원하기 위해 [ICorProfilerInfo7::ApplyMetaData](../unmanaged-api/profiling/icorprofilerinfo7-applymetadata-method.md) 메서드를 추가하고 특히, 새 `AssemblyRef`, `TypeRef`, `TypeSpec`, `MemberRef`, `MemberSpec` 및 `UserString` 레코드를 추가하여 이러한 제한을 일부 상향했습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-783">We have lifted some of those limits by adding the [ICorProfilerInfo7::ApplyMetaData](../unmanaged-api/profiling/icorprofilerinfo7-applymetadata-method.md) method to support a subset of metadata edits after the module loads, in particular by adding new `AssemblyRef`, `TypeRef`, `TypeSpec`, `MemberRef`, `MemberSpec`, and `UserString` records.</span></span> <span data-ttu-id="9bae0-784">이 변경을 통해 즉시 계측의 범위가 더 넓어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-784">This change makes a much broader range of on-the-fly instrumentation possible.</span></span>

<a name="NGEN461"></a>

### <a name="native-image-generator-ngen-pdbs"></a><span data-ttu-id="9bae0-785">NGEN(네이티브 이미지 생성기) PDB</span><span class="sxs-lookup"><span data-stu-id="9bae0-785">Native Image Generator (NGEN) PDBs</span></span>

<span data-ttu-id="9bae0-786">머신 간 이벤트 추적을 사용하면 고객이 머신 A에서 프로그램을 프로파일링하고 소스 줄 매핑을 사용하여 머신 B에서 프로파일링 데이터를 확인할 수 있습니다. 이전 버전의 .NET Framework에서는 사용자가 프로파일링된 머신의 모든 모듈 및 네이티브 이미지를 IL PDB가 포함된 분석 머신으로 복사하여 소스-네이티브 매핑을 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-786">Cross-machine event tracing allows customers to profile a program on Machine A and look at the profiling data with source line mapping on Machine B. Using previous versions of .NET Framework, the user would copy all the modules and native images from the profiled machine to the analysis machine that contains the IL PDB to create the source-to-native mapping.</span></span> <span data-ttu-id="9bae0-787">이 프로세스는 휴대폰 애플리케이션 등 비교적 파일이 작은 경우에는 잘 작동하지만 데스크톱 시스템에서는 파일이 매우 커질 수 있으며 복사하는 데 많은 시간이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-787">While this process may work well when the files are relatively small, such as for phone applications, the files can be very large on desktop systems and require significant time to copy.</span></span>

<span data-ttu-id="9bae0-788">Ngen PDB를 사용하면 NGen이 IL PDB에 대한 종속성 없이 IL-네이티브 매핑이 포함된 PDB를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-788">With Ngen PDBs, NGen can create a PDB that contains the IL-to-native mapping without a dependency on the IL PDB.</span></span> <span data-ttu-id="9bae0-789">시스템 간 이벤트 추적 시나리오에서는 시스템 A에서 생성된 네이티브 이미지 PDB를 시스템 B로 복사하고 [Debug Interface Access API](/visualstudio/debugger/debug-interface-access/debug-interface-access-sdk-reference)를 사용하여 IL PDB의 소스-IL 매핑 및 네이티브 이미지 PDB의 IL-네이티브 매핑을 읽기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-789">In our cross-machine event tracing scenario, all that is needed is to copy the native image PDB that is generated by Machine A to Machine B and to use [Debug Interface Access APIs](/visualstudio/debugger/debug-interface-access/debug-interface-access-sdk-reference) to read the IL PDB's source-to-IL mapping and the native image PDB's IL-to-native mapping.</span></span> <span data-ttu-id="9bae0-790">두 매핑을 함께 사용하면 소스-네이티브 매핑이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-790">Combining both mappings provides a source-to-native mapping.</span></span> <span data-ttu-id="9bae0-791">네이티브 이미지 PDB는 모든 모듈 및 네이티브 이미지보다 훨씬 작으므로 시스템 A에서 시스템 B로 복사하는 프로세스가 훨씬 빨라집니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-791">Since the native image PDB is much smaller than all the modules and native images, the process of copying from Machine A to Machine B is much faster.</span></span>

<a name="v46"></a>

## <a name="whats-new-in-net-2015"></a><span data-ttu-id="9bae0-792">.NET 2015의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="9bae0-792">What's new in .NET 2015</span></span>

<span data-ttu-id="9bae0-793">.NET 2015에서는 .NET Framework 4.6 및 .NET Core가 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-793">.NET 2015 introduces .NET Framework 4.6 and .NET Core.</span></span> <span data-ttu-id="9bae0-794">일부 새로운 기능은 둘 다에 적용되고 기타 기능은 .NET Framework 4.6 또는 .NET Core 중 하나와 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-794">Some new features apply to both, and other features are specific to .NET Framework 4.6 or .NET Core.</span></span>

- <span data-ttu-id="9bae0-795">**ASP.NET Core**</span><span class="sxs-lookup"><span data-stu-id="9bae0-795">**ASP.NET Core**</span></span>

  <span data-ttu-id="9bae0-796">.NET 2015에는 최신 클라우드 기반 앱을 빌드하기 위한 린(lean) .NET 구현인 ASP.NET Core가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-796">.NET 2015 includes ASP.NET Core, which is a lean .NET implementation for building modern cloud-based apps.</span></span> <span data-ttu-id="9bae0-797">ASP.NET Core는 모듈식이므로 애플리케이션에 필요한 기능만 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-797">ASP.NET Core is modular so you can include only those features that are needed in your application.</span></span> <span data-ttu-id="9bae0-798">IIS에서 호스트되거나 사용자 지정 프로세스에서 자체 호스트될 수 있으며 동일한 서버에서 다양한 .NET Framework 버전으로 앱을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-798">It can be hosted on IIS or self-hosted in a custom process, and you can run apps with different versions of the .NET Framework on the same server.</span></span> <span data-ttu-id="9bae0-799">클라우드 배포용으로 설계된 새 환경 구성 시스템도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-799">It includes a new environment configuration system that is designed for cloud deployment.</span></span>

  <span data-ttu-id="9bae0-800">MVC, Web API 및 웹 페이지가 MVC 6이라는 단일 프레임워크로 통합됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-800">MVC, Web API, and Web Pages are unified into a single framework called MVC 6.</span></span> <span data-ttu-id="9bae0-801">Visual Studio 2015 이상의 도구를 통해 ASP.NET Core 앱을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-801">You build ASP.NET Core apps through tools in Visual Studio 2015 or later.</span></span> <span data-ttu-id="9bae0-802">기존 애플리케이션도 새로운 .NET Framework에서 작동하지만 MVC 6 또는 SignalR 3을 사용하는 앱을 빌드하려면 Visual Studio 2015 이상의 프로젝트 시스템을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-802">Your existing applications will work on the new .NET Framework; however to build an app that uses MVC 6 or SignalR 3, you must use the project system in Visual Studio 2015 or later.</span></span>

  <span data-ttu-id="9bae0-803">자세한 내용은 [ASP.NET Core](/aspnet/core/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bae0-803">For information, see [ASP.NET Core](/aspnet/core/).</span></span>

- <span data-ttu-id="9bae0-804">**ASP.NET 업데이트**</span><span class="sxs-lookup"><span data-stu-id="9bae0-804">**ASP.NET Updates**</span></span>

  - <span data-ttu-id="9bae0-805">**비동기 응답 플러시를 위한 작업 기반 API**</span><span class="sxs-lookup"><span data-stu-id="9bae0-805">**Task-based API for Asynchronous Response Flushing**</span></span>

    <span data-ttu-id="9bae0-806">이제 ASP.NET이 비동기 응답 플러시에 대한 간단한 작업 기반 API인 <xref:System.Web.HttpResponse.FlushAsync%2A?displayProperty=nameWithType>를 제공합니다. 이를 통해 해당 언어의 `async/await` 지원을 사용하여 응답을 비동기적으로 플러시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-806">ASP.NET now provides a simple task-based API for asynchronous response flushing, <xref:System.Web.HttpResponse.FlushAsync%2A?displayProperty=nameWithType>, that allows responses to be flushed asynchronously by using your language's `async/await` support.</span></span>

  - <span data-ttu-id="9bae0-807">**모델 바인딩의 태스크 반환 메서드 지원**</span><span class="sxs-lookup"><span data-stu-id="9bae0-807">**Model binding supports task-returning methods**</span></span>

    <span data-ttu-id="9bae0-808">.NET Framework 4.5에 ASP.NET이 Web Forms 페이지 및 사용자 정의 컨트롤에서 CRUD 기반 데이터 작업으로 확장 가능하고 코드 중심의 접근이 가능하도록 모델 바인딩 기능을 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-808">In .NET Framework 4.5, ASP.NET added the Model Binding feature that enabled an extensible, code-focused approach to CRUD-based data operations in Web Forms pages and user controls.</span></span> <span data-ttu-id="9bae0-809">이제 모델 바인딩 시스템이 <xref:System.Threading.Tasks.Task>를 반환하는 모델 바인딩 메서드를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-809">The Model Binding system now supports <xref:System.Threading.Tasks.Task>-returning model binding methods.</span></span> <span data-ttu-id="9bae0-810">이 기능으로 Web Forms 개발자가 Entity Framework를 포함하여 새 버전의 ORM을 사용하는 경우 간편한 데이터 바인딩 시스템과 함께 비동기의 확장성 이점을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-810">This feature allows Web Forms developers to get the scalability benefits of async with the ease of the data-binding system when using newer versions of ORMs, including the Entity Framework.</span></span>

    <span data-ttu-id="9bae0-811">비동기 모델 바인딩은 `aspnet:EnableAsyncModelBinding` 구성 설정으로 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-811">Async model binding is controlled by the `aspnet:EnableAsyncModelBinding` configuration setting.</span></span>

    ```xml
    <appSettings>
        <add key=" aspnet:EnableAsyncModelBinding" value="true|false" />
    </appSettings>
    ```

    <span data-ttu-id="9bae0-812">.NET Framework 4.6을 대상으로 하는 앱에서는 기본적으로 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-812">On apps the target .NET Framework 4.6, it defaults to `true`.</span></span> <span data-ttu-id="9bae0-813">이전 버전의 .NET Framework를 대상으로 하고 .NET Framework 4.6에서 실행되는 앱에서는 기본적으로 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-813">On apps running on .NET Framework 4.6 that target an earlier version of .NET Framework, it is `false` by default.</span></span> <span data-ttu-id="9bae0-814">구성을 `true`로 설정하여 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-814">It can be enabled by setting the configuration setting to `true`.</span></span>

  - <span data-ttu-id="9bae0-815">**HTTP/2 지원(Windows 10)**</span><span class="sxs-lookup"><span data-stu-id="9bae0-815">**HTTP/2 Support (Windows 10)**</span></span>

    <span data-ttu-id="9bae0-816">[HTTP/2](https://www.wikipedia.org/wiki/HTTP/2)는 더 나은 연결 사용률(클라이언트와 서버 간 왕복 횟수 감소)을 제공하여 사용자의 웹 페이지 로딩 대기 시간을 줄여주는 새 버전의 HTTP 프로토콜입니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-816">[HTTP/2](https://www.wikipedia.org/wiki/HTTP/2) is a new version of the HTTP protocol that provides much better connection utilization (fewer round-trips between client and server), resulting in lower latency web page loading for users.</span></span>  <span data-ttu-id="9bae0-817">이 프로토콜은 단일 환경의 일부로 요청되는 여러 아티팩트에 최적화되었으므로 웹 페이지(서비스 대비)가 HTTP/2에서 가장 많은 혜택을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-817">Web pages (as opposed to services) benefit the most from HTTP/2, since the protocol optimizes for multiple artifacts being requested as part of a single experience.</span></span> <span data-ttu-id="9bae0-818">.NET Framework 4.6의 ASP.NET에는 HTTP/2 지원이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-818">HTTP/2 support has been added to ASP.NET in .NET Framework 4.6.</span></span> <span data-ttu-id="9bae0-819">여러 레이어에 네트워킹 기능이 있기 때문에 HTTP/2를 사용하려면 Windows, IIS 및 ASP.NET에 새로운 기능이 필요했습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-819">Because networking functionality exists at multiple layers, new features were required in Windows, in IIS, and in ASP.NET to enable HTTP/2.</span></span> <span data-ttu-id="9bae0-820">ASP.NET과 함께 HTTP/2를 사용하려면 Windows 10에서 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-820">You must be running on Windows 10 to use HTTP/2 with ASP.NET.</span></span>

    <span data-ttu-id="9bae0-821">또한 HTTP/2는 <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> API를 사용하는 Windows 10 UWP(유니버설 Windows 플랫폼) 앱에서 지원되며 기본적으로 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-821">HTTP/2 is also supported and on by default for Windows 10 Universal Windows Platform (UWP) apps that use the <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> API.</span></span>

    <span data-ttu-id="9bae0-822">ASP.NET 애플리케이션의 [PUSH_PROMISE](https://httpwg.github.io/http2-spec/#PUSH_PROMISE) 기능 사용 방법을 제공하기 위해 두 개의 오버로드(<xref:System.Web.HttpResponse.PushPromise%28System.String%29> 및 <xref:System.Web.HttpResponse.PushPromise%28System.String%2CSystem.String%2CSystem.Collections.Specialized.NameValueCollection%29>)와 함께 새 메서드가 <xref:System.Web.HttpResponse> 클래스에 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-822">In order to provide a way to use the [PUSH_PROMISE](https://httpwg.github.io/http2-spec/#PUSH_PROMISE) feature in ASP.NET applications, a new method with two overloads, <xref:System.Web.HttpResponse.PushPromise%28System.String%29> and <xref:System.Web.HttpResponse.PushPromise%28System.String%2CSystem.String%2CSystem.Collections.Specialized.NameValueCollection%29>, has been added to the <xref:System.Web.HttpResponse> class.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9bae0-823">ASP.NET Core는 HTTP/2를 지원하는 반면 PUSH PROMISE 기능에 대한 지원은 아직 추가되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-823">While ASP.NET Core supports HTTP/2, support for the PUSH PROMISE feature has not yet been added.</span></span>

    <span data-ttu-id="9bae0-824">브라우저와 웹 서버(Windows의 IIS)가 모든 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-824">The browser and the web server (IIS on Windows) do all the work.</span></span> <span data-ttu-id="9bae0-825">사용자를 위해 직접 힘든 작업을 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-825">You don't have to do any heavy-lifting for your users.</span></span>

    <span data-ttu-id="9bae0-826">대부분의 [주요 브라우저가 HTTP/2를 지원](https://www.wikipedia.org/wiki/HTTP/2)하므로 서버에서 지원할 경우 HTTP/2 지원은 사용자에게 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-826">Most of the [major browsers support HTTP/2](https://www.wikipedia.org/wiki/HTTP/2), so it's likely that your users will benefit from HTTP/2 support if your server supports it.</span></span>

  - <span data-ttu-id="9bae0-827">**토큰 바인딩 프로토콜 지원**</span><span class="sxs-lookup"><span data-stu-id="9bae0-827">**Support for the Token Binding Protocol**</span></span>

    <span data-ttu-id="9bae0-828">Microsoft 및 Google은 [토큰 바인딩 프로토콜](https://github.com/TokenBinding/Internet-Drafts)이라는 새로운 인증 방식을 위해 협력해 왔습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-828">Microsoft and Google have been collaborating on a new approach to authentication, called the [Token Binding Protocol](https://github.com/TokenBinding/Internet-Drafts).</span></span> <span data-ttu-id="9bae0-829">전제 조건은 브라우저 캐시의 인증 토큰이 도난당해 범죄자가 암호나 기타 권한 있는 정보 없이도 보안 리소스(예: 은행 계좌)에 액세스하는 데 이용될 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-829">The premise is that authentication tokens (in your browser cache) can be stolen and used by criminals to access otherwise secure resources (for example, your bank account) without requiring your password or any other privileged knowledge.</span></span> <span data-ttu-id="9bae0-830">새 프로토콜은 이 문제를 완화시키기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-830">The new protocol aims to mitigate this problem.</span></span>

    <span data-ttu-id="9bae0-831">토큰 바인딩 프로토콜은 Windows 10에서 브라우저 기능으로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-831">The Token Binding Protocol will be implemented in Windows 10 as a browser feature.</span></span> <span data-ttu-id="9bae0-832">인증 토큰이 정당한 것으로 검증되도록 ASP.NET 앱이 프로토콜에 참여합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-832">ASP.NET apps will participate in the protocol, so that authentication tokens are validated to be legitimate.</span></span> <span data-ttu-id="9bae0-833">클라이언트와 서버 구현은 프로토콜에 의해 지정된 엔드투엔드 보호를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-833">The client and the server implementations establish the end-to-end protection specified by the protocol.</span></span>

  - <span data-ttu-id="9bae0-834">**임의 문자열 해시 알고리즘**</span><span class="sxs-lookup"><span data-stu-id="9bae0-834">**Randomized string hash algorithms**</span></span>

    <span data-ttu-id="9bae0-835">.NET Framework 4.5에서는 [임의 문자열 해시 알고리즘](../configure-apps/file-schema/runtime/userandomizedstringhashalgorithm-element.md)이 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-835">.NET Framework 4.5 introduced a [randomized string hash algorithm](../configure-apps/file-schema/runtime/userandomizedstringhashalgorithm-element.md).</span></span> <span data-ttu-id="9bae0-836">그러나 일부 ASP.NET 기능이 안정적인 해시 코드에 종속되어 있어 ASP.NET에서는 지원하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-836">However, it was not supported by ASP.NET because of some ASP.NET features depended on a stable hash code.</span></span> <span data-ttu-id="9bae0-837">이제 .NET Framework 4.6에서 임의 문자열 해시 알고리즘을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-837">In .NET Framework 4.6, randomized string hash algorithms are now supported.</span></span> <span data-ttu-id="9bae0-838">이 기능을 사용하려면 `aspnet:UseRandomizedStringHashAlgorithm` 구성 설정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-838">To enable this feature, use the `aspnet:UseRandomizedStringHashAlgorithm` config setting.</span></span>

    ```xml
    <appSettings>
        <add key="aspnet:UseRandomizedStringHashAlgorithm" value="true|false" />
    </appSettings>
    ```

- <span data-ttu-id="9bae0-839">**ADO.NET**</span><span class="sxs-lookup"><span data-stu-id="9bae0-839">**ADO.NET**</span></span>

  <span data-ttu-id="9bae0-840">ADO .NET은 이제 SQL Server 2016 CTP2(Community Technology Preview 2)에서 제공되는 상시 암호화 기능을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-840">ADO .NET now supports the Always Encrypted feature available in SQL Server 2016 Community Technology Preview 2 (CTP2).</span></span> <span data-ttu-id="9bae0-841">Always Encrypted를 사용하면 SQL Server는 암호화된 데이터에 대해 작업을 수행할 수 있으며 무엇보다도, 암호화 키는 서버가 아니라 고객의 신뢰할 수 있는 환경 내에서 애플리케이션과 함께 상주합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-841">With Always Encrypted, SQL Server can perform operations on encrypted data, and best of all the encryption key resides with the application inside the customer's trusted environment and not on the server.</span></span> <span data-ttu-id="9bae0-842">Always Encrypted는 DBA가 일반 텍스트 데이터에 액세스할 수 없도록 고객 데이터를 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-842">Always Encrypted secures customer data so DBAs do not have access to plain text data.</span></span> <span data-ttu-id="9bae0-843">데이터 암호화 및 암호 해독은 드라이버 수준에서 투명하게 이루어지며 기존 애플리케이션에 대한 변경을 최소화합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-843">Encryption and decryption of data happens transparently at the driver level, minimizing changes that have to be made to existing applications.</span></span> <span data-ttu-id="9bae0-844">자세한 내용은 [상시 암호화(데이터베이스 엔진)](/sql/relational-databases/security/encryption/always-encrypted-database-engine) 및 [상시 암호화(클라이언트 개발)](/sql/relational-databases/security/encryption/always-encrypted-client-development)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9bae0-844">For details, see [Always Encrypted (Database Engine)](/sql/relational-databases/security/encryption/always-encrypted-database-engine) and [Always Encrypted (client development)](/sql/relational-databases/security/encryption/always-encrypted-client-development).</span></span>

- <span data-ttu-id="9bae0-845">**관리 코드에 대한 64비트 JIT 컴파일러**</span><span class="sxs-lookup"><span data-stu-id="9bae0-845">**64-bit JIT Compiler for managed code**</span></span>

  <span data-ttu-id="9bae0-846">.NET Framework 4.6에는 새 버전의64비트 JIT 컴파일러(원래 코드 이름은 RyuJIT)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-846">.NET Framework 4.6 features a new version of the 64-bit JIT compiler (originally code-named RyuJIT).</span></span> <span data-ttu-id="9bae0-847">새로운 64비트 컴파일러는 이전 64비트 JIT 컴파일러보다 훨씬 향상된 성능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-847">The new 64-bit compiler provides significant performance improvements over the older 64-bit JIT compiler.</span></span> <span data-ttu-id="9bae0-848">새로운 64비트 컴파일러는 .NET Framework 4.6에서 실행되는 64비트 프로세스에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-848">The new 64-bit compiler is enabled for 64-bit processes running on top of .NET Framework 4.6.</span></span> <span data-ttu-id="9bae0-849">앱이 64비트 또는 AnyCPU로 컴파일되고 64비트 운영 체제에서 실행되는 경우 해당 앱은 64비트 프로세스에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-849">Your app will run in a 64-bit process if it is compiled as 64-bit or AnyCPU and is running on a 64-bit operating system.</span></span> <span data-ttu-id="9bae0-850">새 컴파일러로 전환할 때 무슨 조치를 취했는지 투명하게 알 수 있으면 동작을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-850">While care has been taken to make the transition to the new compiler as transparent as possible, changes in behavior are possible.</span></span>

  <span data-ttu-id="9bae0-851">또한 새로운 64비트 JIT 컴파일러에는 하드웨어 SIMD 가속 기능이 있으므로 <xref:System.Numerics> 네임스페이스의 SIMD 사용 형식과 함께 사용하면 성능이 현저히 향상될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-851">The new 64-bit JIT compiler also includes hardware SIMD acceleration features when coupled with SIMD-enabled types in the <xref:System.Numerics> namespace, which can yield good performance improvements.</span></span>

- <span data-ttu-id="9bae0-852">**어셈블리 로더 기능 향상**</span><span class="sxs-lookup"><span data-stu-id="9bae0-852">**Assembly loader improvements**</span></span>

  <span data-ttu-id="9bae0-853">이제 어셈블리 로더가 해당 NGEN 이미지를 로드한 후 IL 어셈블리를 언로드하여 보다 효율적으로 메모리를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-853">The assembly loader now uses memory more efficiently by unloading IL assemblies after a corresponding NGEN image is loaded.</span></span> <span data-ttu-id="9bae0-854">이 변경으로 가상 메모리가 감소됩니다. 특히 큰 32비트 앱(예: Visual Studio)에 대해 효과적이며 실제 메모리도 절약됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-854">This change decreases virtual memory, which is particularly beneficial for large 32-bit apps (such as Visual Studio), and also saves physical memory.</span></span>

- <span data-ttu-id="9bae0-855">**기본 클래스 라이브러리 변경 내용**</span><span class="sxs-lookup"><span data-stu-id="9bae0-855">**Base class library changes**</span></span>

  <span data-ttu-id="9bae0-856">주요 시나리오를 사용할 수 있도록 많은 API가 .NET Framework 4.6에 새로 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-856">Many new APIs have been added around to .NET Framework 4.6 to enable key scenarios.</span></span> <span data-ttu-id="9bae0-857">변경 및 추가된 내용은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-857">These include the following changes and additions:</span></span>

  - <span data-ttu-id="9bae0-858">**IReadOnlyCollection\<T> 구현**</span><span class="sxs-lookup"><span data-stu-id="9bae0-858">**IReadOnlyCollection\<T> implementations**</span></span>

    <span data-ttu-id="9bae0-859">추가 컬렉션이 <xref:System.Collections.Generic.IReadOnlyCollection%601>(예: <xref:System.Collections.Generic.Queue%601> 및 <xref:System.Collections.Generic.Stack%601>)을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-859">Additional collections implement <xref:System.Collections.Generic.IReadOnlyCollection%601> such as <xref:System.Collections.Generic.Queue%601> and <xref:System.Collections.Generic.Stack%601>.</span></span>

  - <span data-ttu-id="9bae0-860">**CultureInfo.CurrentCulture 및 CultureInfo.CurrentUICulture**</span><span class="sxs-lookup"><span data-stu-id="9bae0-860">**CultureInfo.CurrentCulture and CultureInfo.CurrentUICulture**</span></span>

    <span data-ttu-id="9bae0-861">이제 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType> 및 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=nameWithType> 속성이 읽기 전용이 아니라 읽기/쓰기입니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-861">The <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType> and <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=nameWithType> properties are now read-write rather than read-only.</span></span> <span data-ttu-id="9bae0-862">이러한 속성에 새 <xref:System.Globalization.CultureInfo> 개체를 할당하면 `Thread.CurrentThread.CurrentCulture` 속성으로 정의된 현재 스레드 문화권과 `Thread.CurrentThread.CurrentUICulture` 속성으로 정의된 현재 UI 스레드 문화권도 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-862">If you assign a new <xref:System.Globalization.CultureInfo> object to these properties, the current thread culture defined by the `Thread.CurrentThread.CurrentCulture` property and the current UI thread culture defined by the `Thread.CurrentThread.CurrentUICulture` properties also change.</span></span>

  - <span data-ttu-id="9bae0-863">**GC(가비지 수집) 향상**</span><span class="sxs-lookup"><span data-stu-id="9bae0-863">**Enhancements to garbage collection (GC)**</span></span>

    <span data-ttu-id="9bae0-864">이제 <xref:System.GC> 클래스에 <xref:System.GC.TryStartNoGCRegion%2A> 및 <xref:System.GC.EndNoGCRegion%2A> 메서드가 포함되었습니다. 두 메서드를 사용하면 중요 경로를 실행하는 동안 가비지 수집을 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-864">The <xref:System.GC> class now includes <xref:System.GC.TryStartNoGCRegion%2A> and <xref:System.GC.EndNoGCRegion%2A> methods that allow you to disallow garbage collection during the execution of a critical path.</span></span>

    <span data-ttu-id="9bae0-865"><xref:System.GC.Collect%28System.Int32%2CSystem.GCCollectionMode%2CSystem.Boolean%2CSystem.Boolean%29?displayProperty=nameWithType> 메서드의 새 오버로드를 통해 소형 개체 힙과 대형 개체 힙을 모두 정리 및 압축할지, 아니면 정리만 할지 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-865">A new overload of the <xref:System.GC.Collect%28System.Int32%2CSystem.GCCollectionMode%2CSystem.Boolean%2CSystem.Boolean%29?displayProperty=nameWithType> method allows you to control whether both the small object heap and the large object heap are swept and compacted or swept only.</span></span>

  - <span data-ttu-id="9bae0-866">**SIMD 사용 형식**</span><span class="sxs-lookup"><span data-stu-id="9bae0-866">**SIMD-enabled types**</span></span>

    <span data-ttu-id="9bae0-867">이제 <xref:System.Numerics> 네임스페이스에 많은 SIMD 사용 형식(예: <xref:System.Numerics.Matrix3x2>, <xref:System.Numerics.Matrix4x4>, <xref:System.Numerics.Plane>, <xref:System.Numerics.Quaternion>, <xref:System.Numerics.Vector2>, <xref:System.Numerics.Vector3>, <xref:System.Numerics.Vector4>)이 포함되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-867">The <xref:System.Numerics> namespace now includes a number of SIMD-enabled types, such as <xref:System.Numerics.Matrix3x2>, <xref:System.Numerics.Matrix4x4>, <xref:System.Numerics.Plane>, <xref:System.Numerics.Quaternion>, <xref:System.Numerics.Vector2>, <xref:System.Numerics.Vector3>, and <xref:System.Numerics.Vector4>.</span></span>

    <span data-ttu-id="9bae0-868">또한 새로운 64비트 JIT 컴파일러에는 하드웨어 SIMD 가속 기능이 있으므로 SIMD 사용 형식과 새 64비트 JIT 컴파일러를 함께 사용하면 성능이 현저히 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-868">Because the new 64-bit JIT compiler also includes hardware SIMD acceleration features, there are especially significant performance improvements when using the SIMD-enabled types with the new 64-bit JIT compiler.</span></span>

  - <span data-ttu-id="9bae0-869">**암호화 업데이트**</span><span class="sxs-lookup"><span data-stu-id="9bae0-869">**Cryptography updates**</span></span>

    <span data-ttu-id="9bae0-870"><xref:System.Security.Cryptography?displayProperty=nameWithType> API가 [Windows CNG 암호화 API](/windows/desktop/SecCNG/cng-reference)를 지원하도록 업데이트되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-870">The <xref:System.Security.Cryptography?displayProperty=nameWithType> API is being updated to support the [Windows CNG cryptography APIs](/windows/desktop/SecCNG/cng-reference).</span></span> <span data-ttu-id="9bae0-871">이전 버전의 .NET Framework는 <xref:System.Security.Cryptography?displayProperty=nameWithType> 구현의 기반으로 [이전 버전의 Windows 암호화 API](/windows/desktop/SecCrypto/cryptography-portal)를 전적으로 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-871">Previous versions of the .NET Framework have relied entirely on an [earlier version of the Windows Cryptography APIs](/windows/desktop/SecCrypto/cryptography-portal) as the basis for the <xref:System.Security.Cryptography?displayProperty=nameWithType> implementation.</span></span> <span data-ttu-id="9bae0-872">CNG API는 특정 범주의 앱에 중요한 [최신 암호화 알고리즘](/windows/desktop/SecCNG/cng-features#suite-b-support)을 지원하기 때문에 CNG API에 대한 지원 요청을 받았습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-872">We have had requests to support the CNG API, since it supports [modern cryptography algorithms](/windows/desktop/SecCNG/cng-features#suite-b-support), which are important for certain categories of apps.</span></span>

    <span data-ttu-id="9bae0-873">.NET Framework 4.6에는 Windows CNG 암호화 API를 지원하는 다음과 같은 새로운 향상 기능이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-873">.NET Framework 4.6 includes the following new enhancements to support the Windows CNG cryptography APIs:</span></span>

    - <span data-ttu-id="9bae0-874">X509 인증서에 대한 일련의 확장 메서드(`System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey(System.Security.Cryptography.X509Certificates.X509Certificate2)` 및 `System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey(System.Security.Cryptography.X509Certificates.X509Certificate2)`) - 가능한 경우 CAPI 기반 구현 대신 CNG 기반 구현을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-874">A set of extension methods for X509 Certificates, `System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey(System.Security.Cryptography.X509Certificates.X509Certificate2)` and `System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey(System.Security.Cryptography.X509Certificates.X509Certificate2)`, that return a CNG-based implementation rather than a CAPI-based implementation when possible.</span></span> <span data-ttu-id="9bae0-875">(일부 스마트 카드 등에는 여전히 CAPI가 필요하며 API가 대체(fallback) 처리합니다.)</span><span class="sxs-lookup"><span data-stu-id="9bae0-875">(Some smartcards, etc., still require CAPI, and the APIs handle the fallback).</span></span>

    - <span data-ttu-id="9bae0-876"><xref:System.Security.Cryptography.RSACng?displayProperty=nameWithType> 클래스 - RSA 알고리즘의 CNG 구현을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-876">The <xref:System.Security.Cryptography.RSACng?displayProperty=nameWithType> class, which provides a CNG implementation of the RSA algorithm.</span></span>

    - <span data-ttu-id="9bae0-877">RSA API에 대한 향상 기능 - 일반 작업에 더 이상 캐스팅이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-877">Enhancements to the RSA API so that common actions no longer require casting.</span></span> <span data-ttu-id="9bae0-878">예를 들어 <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> 개체를 사용하여 데이터를 암호화하려면 이전 버전의 .NET Framework에서 다음과 같은 코드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-878">For example, encrypting data using an <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> object requires code like the following in previous versions of .NET Framework.</span></span>

      [!code-csharp[WhatsNew.Casting#1](~/samples/snippets/csharp/VS_Snippets_CLR/whatsnew.casting/cs/program.cs#1)]
      [!code-vb[WhatsNew.Casting#1](~/samples/snippets/visualbasic/VS_Snippets_CLR/whatsnew.casting/vb/module1.vb#1)]

      <span data-ttu-id="9bae0-879">.NET Framework 4.6에서 새로운 암호화 API를 사용하는 코드는 캐스팅을 방지하기 위해 다음과 같이 다시 작성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-879">Code that uses the new cryptography APIs in .NET Framework 4.6 can be rewritten as follows to avoid the cast.</span></span>

      [!code-csharp[WhatsNew.Casting#2](~/samples/snippets/csharp/VS_Snippets_CLR/whatsnew.casting/cs/program.cs#2)]
      [!code-vb[WhatsNew.Casting#2](~/samples/snippets/visualbasic/VS_Snippets_CLR/whatsnew.casting/vb/module1.vb#2)]

  - <span data-ttu-id="9bae0-880">**UNIX 시간으로/UNIX 시간에서 날짜 및 시간 변환 지원**</span><span class="sxs-lookup"><span data-stu-id="9bae0-880">**Support for converting dates and times to or from Unix time**</span></span>

    <span data-ttu-id="9bae0-881">다음 새 메서드가 <xref:System.DateTimeOffset> 구조에 추가되어 UNIX 시간으로/UNIX 시간에서 날짜 및 시간 변환을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-881">The following new methods have been added to the <xref:System.DateTimeOffset> structure to support converting date and time values to or from Unix time:</span></span>

    - <xref:System.DateTimeOffset.FromUnixTimeSeconds%2A?displayProperty=nameWithType>

    - <xref:System.DateTimeOffset.FromUnixTimeMilliseconds%2A?displayProperty=nameWithType>

    - <xref:System.DateTimeOffset.ToUnixTimeSeconds%2A?displayProperty=nameWithType>

    - <xref:System.DateTimeOffset.ToUnixTimeMilliseconds%2A?displayProperty=nameWithType>

  - <span data-ttu-id="9bae0-882">**호환성 스위치**</span><span class="sxs-lookup"><span data-stu-id="9bae0-882">**Compatibility switches**</span></span>

    <span data-ttu-id="9bae0-883"><xref:System.AppContext> 클래스는 라이브러리 작성자가 사용자에게 새로운 기능에 대한 균일한 옵트아웃(opt out) 메커니즘을 제공할 수 있게 해주는 새 호환성 기능을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-883">The <xref:System.AppContext> class adds a new compatibility feature that enables library writers to provide a uniform opt-out mechanism for new functionality for their users.</span></span> <span data-ttu-id="9bae0-884">옵트아웃(opt out) 요청을 전달하기 위해 구성 요소 간에 느슨하게 결합된 계약을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-884">It establishes a loosely coupled contract between components in order to communicate an opt-out request.</span></span> <span data-ttu-id="9bae0-885">이 기능은 일반적으로 기존 기능이 변경될 때 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-885">This capability is typically important when a change is made to existing functionality.</span></span> <span data-ttu-id="9bae0-886">반대로, 새로운 기능에 대한 암시적 옵트인(opt in)은 이미 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-886">Conversely, there is already an implicit opt-in for new functionality.</span></span>

    <span data-ttu-id="9bae0-887"><xref:System.AppContext>에서는 라이브러리가 호환성 스위치를 정의 및 노출하는 반면, 라이브러리에 종속된 코드가 해당 스위치를 설정하여 라이브러리 동작에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-887">With <xref:System.AppContext>, libraries define and expose compatibility switches, while code that depends on them can set those switches to affect the library behavior.</span></span> <span data-ttu-id="9bae0-888">기본적으로 라이브러리는 새로운 기능을 제공하며 스위치가 설정된 경우에만 변경합니다(즉, 이전 기능 제공).</span><span class="sxs-lookup"><span data-stu-id="9bae0-888">By default, libraries provide the new functionality, and they only alter it (that is, they provide the previous functionality) if the switch is set.</span></span>

    <span data-ttu-id="9bae0-889">애플리케이션(또는 라이브러리)은 종속 라이브러리가 정의하는 스위치 값(항상 <xref:System.Boolean> 값)을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-889">An application (or a library) can declare the value of a switch (which is always a <xref:System.Boolean> value) that a dependent library defines.</span></span> <span data-ttu-id="9bae0-890">스위치는 암시적으로 항상 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-890">The switch is always implicitly `false`.</span></span> <span data-ttu-id="9bae0-891">스위치를 `true`로 설정하면 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-891">Setting the switch to `true` enables it.</span></span> <span data-ttu-id="9bae0-892">스위치를 명시적으로 `false`로 설정하면 새 동작이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-892">Explicitly setting the switch to `false` provides the new behavior.</span></span>

    ```csharp
    AppContext.SetSwitch("Switch.AmazingLib.ThrowOnException", true);
    ```

    ```vb
    AppContext.SetSwitch("Switch.AmazingLib.ThrowOnException", True)
    ```

    <span data-ttu-id="9bae0-893">라이브러리는 소비자가 스위치 값을 선언했는지 확인한 다음 적절하게 동작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-893">The library must check if a consumer has declared the value of the switch and then appropriately act on it.</span></span>

    ```csharp
    if (!AppContext.TryGetSwitch("Switch.AmazingLib.ThrowOnException", out shouldThrow))
    {
        // This is the case where the switch value was not set by the application.
        // The library can choose to get the value of shouldThrow by other means.
        // If no overrides nor default values are specified, the value should be 'false'.
        // A false value implies the latest behavior.
    }

    // The library can use the value of shouldThrow to throw exceptions or not.
    if (shouldThrow)
    {
        // old code
    }
    else
    {
        // new code
    }
    ```

    ```vb
    If Not AppContext.TryGetSwitch("Switch.AmazingLib.ThrowOnException", shouldThrow) Then
        ' This is the case where the switch value was not set by the application.
        ' The library can choose to get the value of shouldThrow by other means.
        ' If no overrides nor default values are specified, the value should be 'false'.
        ' A false value implies the latest behavior.
    End If

    ' The library can use the value of shouldThrow to throw exceptions or not.
    If shouldThrow Then
        ' old code
    Else
        ' new code
    End If
    ```

    <span data-ttu-id="9bae0-894">라이브러리에 의해 노출되는 공식 계약이므로 스위치에 대해 일관된 형식을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-894">It's beneficial to use a consistent format for switches, since they are a formal contract exposed by a library.</span></span> <span data-ttu-id="9bae0-895">다음은 두 가지 명확한 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-895">The following are two obvious formats.</span></span>

    - <span data-ttu-id="9bae0-896">*Switch*. *namespace*. *switchname*</span><span class="sxs-lookup"><span data-stu-id="9bae0-896">*Switch*. *namespace*. *switchname*</span></span>

    - <span data-ttu-id="9bae0-897">*Switch*. *library*. *switchname*</span><span class="sxs-lookup"><span data-stu-id="9bae0-897">*Switch*. *library*. *switchname*</span></span>

  - <span data-ttu-id="9bae0-898">**TAP(작업 기반 비동기 패턴) 변경 내용**</span><span class="sxs-lookup"><span data-stu-id="9bae0-898">**Changes to the task-based asynchronous pattern (TAP)**</span></span>

    <span data-ttu-id="9bae0-899">.NET Framework 4.6을 대상으로 하는 앱의 경우 <xref:System.Threading.Tasks.Task> 및 <xref:System.Threading.Tasks.Task%601> 개체가 호출 스레드의 문화권과 UI 문화권을 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-899">For apps that target .NET Framework 4.6, <xref:System.Threading.Tasks.Task> and <xref:System.Threading.Tasks.Task%601> objects inherit the culture and UI culture of the calling thread.</span></span> <span data-ttu-id="9bae0-900">이전 버전의 .NET Framework를 대상으로 하거나 특정 버전의 .NET Framework를 대상으로 하지 않는 앱의 동작은 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-900">The behavior of apps that target previous versions of .NET Framework, or that do not target a specific version of .NET Framework, is unaffected.</span></span> <span data-ttu-id="9bae0-901">자세한 내용은 <xref:System.Globalization.CultureInfo> 클래스 항목의 “문화권 및 작업 기반 비동기 작업” 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bae0-901">For more information, see the "Culture and task-based asynchronous operations" section of the <xref:System.Globalization.CultureInfo> class topic.</span></span>

    <span data-ttu-id="9bae0-902"><xref:System.Threading.AsyncLocal%601?displayProperty=nameWithType> 클래스를 사용하여 `async` 메서드와 같은 지정된 비동기 제어 흐름의 로컬 앰비언트 데이터를 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-902">The <xref:System.Threading.AsyncLocal%601?displayProperty=nameWithType> class allows you to represent ambient data that is local to a given asynchronous control flow, such as an `async` method.</span></span> <span data-ttu-id="9bae0-903">스레드 간에 데이터를 유지하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-903">It can be used to persist data across threads.</span></span> <span data-ttu-id="9bae0-904"><xref:System.Threading.AsyncLocal%601.Value%2A?displayProperty=nameWithType> 속성이 명시적으로 변경되거나 스레드가 컨텍스트 전환을 발생시켜 앰비언트 데이터가 변경될 때마다 알림을 표시하는 콜백 메서드를 정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-904">You can also define a callback method that is notified whenever the ambient data changes either because the <xref:System.Threading.AsyncLocal%601.Value%2A?displayProperty=nameWithType> property was explicitly changed, or because the thread encountered a context transition.</span></span>

    <span data-ttu-id="9bae0-905">3개의 편리한 메서드(<xref:System.Threading.Tasks.Task.CompletedTask%2A?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Task.FromCanceled%2A?displayProperty=nameWithType> 및 <xref:System.Threading.Tasks.Task.FromException%2A?displayProperty=nameWithType>)가 작업 기반 비동기 패턴(TAP)에 추가되어 특정 상태에서 완료된 작업을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-905">Three convenience methods, <xref:System.Threading.Tasks.Task.CompletedTask%2A?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Task.FromCanceled%2A?displayProperty=nameWithType>, and <xref:System.Threading.Tasks.Task.FromException%2A?displayProperty=nameWithType>, have been added to the task-based asynchronous pattern (TAP) to return completed tasks in a particular state.</span></span>

    <span data-ttu-id="9bae0-906">이제 <xref:System.IO.Pipes.NamedPipeClientStream> 클래스가 새 <xref:System.IO.Pipes.NamedPipeClientStream.ConnectAsync%2A>와의 비동기 통신을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-906">The <xref:System.IO.Pipes.NamedPipeClientStream> class now supports asynchronous communication with its new <xref:System.IO.Pipes.NamedPipeClientStream.ConnectAsync%2A>.</span></span> <span data-ttu-id="9bae0-907">메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-907">method.</span></span>

  - <span data-ttu-id="9bae0-908">**EventSource에서 이벤트 로그에 쓰기 지원**</span><span class="sxs-lookup"><span data-stu-id="9bae0-908">**EventSource now supports writing to the Event log**</span></span>

    <span data-ttu-id="9bae0-909">이제 <xref:System.Diagnostics.Tracing.EventSource> 클래스를 사용하여 관리 또는 작동 메시지를 이벤트 로그와 컴퓨터에 만들어진 모든 기존 ETW 세션에 기록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-909">You now can use the <xref:System.Diagnostics.Tracing.EventSource> class to log administrative or operational messages to the event log, in addition to any existing ETW sessions created on the machine.</span></span> <span data-ttu-id="9bae0-910">과거에는 이 기능을 위해 Microsoft.Diagnostics.Tracing.EventSource NuGet 패키지를 사용해야 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-910">In the past, you had to use the Microsoft.Diagnostics.Tracing.EventSource NuGet package for this functionality.</span></span> <span data-ttu-id="9bae0-911">이제 이 기능이 .NET Framework 4.6에 기본 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-911">This functionality is now built-into .NET Framework 4.6.</span></span>

    <span data-ttu-id="9bae0-912">NuGet 패키지 및 .NET Framework 4.6이 다음 기능으로 업데이트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-912">Both the NuGet package and .NET Framework 4.6 have been updated with the following features:</span></span>

    - <span data-ttu-id="9bae0-913">**동적 이벤트**</span><span class="sxs-lookup"><span data-stu-id="9bae0-913">**Dynamic events**</span></span>

      <span data-ttu-id="9bae0-914">이벤트 메서드를 만들지 않고 "즉시" 정의된 이벤트를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-914">Allows events defined "on the fly" without creating event methods.</span></span>

    - <span data-ttu-id="9bae0-915">**풍부한 페이로드**</span><span class="sxs-lookup"><span data-stu-id="9bae0-915">**Rich payloads**</span></span>

      <span data-ttu-id="9bae0-916">기본 형식뿐만 아니라 특별하게 특성이 정의된 클래스 및 배열이 페이로드로 전달될 수 있도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-916">Allows specially attributed classes and arrays as well as primitive types to be passed as a payload</span></span>

    - <span data-ttu-id="9bae0-917">**작업 추적**</span><span class="sxs-lookup"><span data-stu-id="9bae0-917">**Activity tracking**</span></span>

      <span data-ttu-id="9bae0-918">시작과 중지 이벤트에서 현재 활성 중인 모든 작업을 나타내는 ID를 사용하여 이러한 이벤트 사이에서 발생하는 이벤트에 태그를 지정하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-918">Causes Start and Stop events to tag events between them with an ID that represents all currently active activities.</span></span>

    <span data-ttu-id="9bae0-919">이러한 기능을 지원하기 위해 오버로드된 <xref:System.Diagnostics.Tracing.EventSource.Write%2A> 메서드가 <xref:System.Diagnostics.Tracing.EventSource> 클래스에 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-919">To support these features, the overloaded <xref:System.Diagnostics.Tracing.EventSource.Write%2A> method has been added to the <xref:System.Diagnostics.Tracing.EventSource> class.</span></span>

- <span data-ttu-id="9bae0-920">**WPF(Windows Presentation Foundation)**</span><span class="sxs-lookup"><span data-stu-id="9bae0-920">**Windows Presentation Foundation (WPF)**</span></span>

  - <span data-ttu-id="9bae0-921">**HDPI 기능 향상**</span><span class="sxs-lookup"><span data-stu-id="9bae0-921">**HDPI improvements**</span></span>

    <span data-ttu-id="9bae0-922">이제 WPF의 HDPI 지원이 .NET Framework 4.6에서 더욱 향상되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-922">HDPI support in WPF is now better in .NET Framework 4.6.</span></span> <span data-ttu-id="9bae0-923">테두리가 있는 컨트롤에 클리핑 인스턴스를 줄이기 위해 레이아웃 반올림을 변경했습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-923">Changes have been made to layout rounding to reduce instances of clipping in controls with borders.</span></span> <span data-ttu-id="9bae0-924">기본적으로 이 기능은 <xref:System.Runtime.Versioning.TargetFrameworkAttribute>가 .NET 4.6으로 설정될 때에만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-924">By default, this feature is enabled only if your <xref:System.Runtime.Versioning.TargetFrameworkAttribute> is set to .NET 4.6.</span></span>  <span data-ttu-id="9bae0-925">이전 버전의 프레임워크를 대상으로 하지만 .NET Framework 4.6에서 실행되는 애플리케이션은 app.config 파일의 [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) 섹션에 다음 줄을 추가하여 새 동작을 옵트인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-925">Applications that target earlier versions of the framework but are running on .NET Framework 4.6 can opt in to the new behavior by adding the following line to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of the app.config file:</span></span>

    ```xml
    <AppContextSwitchOverrides
    value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=false"
    />
    ```

    <span data-ttu-id="9bae0-926">이제 서로 다른 DPI 설정(다중 DPI 설치)을 사용하여 여러 대의 모니터에 걸쳐 있는 WPF 창이 블랙아웃 영역 없이 완전하게 렌더링됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-926">WPF windows straddling multiple monitors with different DPI settings (Multi-DPI setup) are now completely rendered without blacked-out regions.</span></span> <span data-ttu-id="9bae0-927">이 새로운 동작을 사용하지 않으려면 app.config 파일의 `<appSettings>` 섹션에 다음 줄을 추가하여 옵트아웃(opt out)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-927">You can opt out of this behavior by adding the following line to the `<appSettings>` section of the app.config file to disable this new behavior:</span></span>

    ```xml
    <add key="EnableMultiMonitorDisplayClipping" value="true"/>
    ```

    <span data-ttu-id="9bae0-928">DPI 설정에 따라 오른쪽 커서를 자동으로 로딩하는 지원이 <xref:System.Windows.Input.Cursor?displayProperty=nameWithType>에 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-928">Support for automatically loading the right cursor based on DPI setting has been added to  <xref:System.Windows.Input.Cursor?displayProperty=nameWithType>.</span></span>

  - <span data-ttu-id="9bae0-929">**터치 기능 향상**</span><span class="sxs-lookup"><span data-stu-id="9bae0-929">**Touch is better**</span></span>

    <span data-ttu-id="9bae0-930">고객이 터치 시 예기치 않은 동작이 발생한다고 [Connect](https://connect.microsoft.com/VisualStudio/feedback/details/903760/)에 신고한 문제가 .NET Framework 4.6에서 해결되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-930">Customer reports on [Connect](https://connect.microsoft.com/VisualStudio/feedback/details/903760/) that touch produces unpredictable behavior have been addressed in .NET Framework 4.6.</span></span> <span data-ttu-id="9bae0-931">이제 Windows 스토어 애플리케이션 및 WPF 애플리케이션에 대한 두 번 탭하기 임계값이 Windows 8.1 이상 버전에서 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-931">The double tap threshold for Windows Store applications and WPF applications is now the same in Windows 8.1 and above.</span></span>

  - <span data-ttu-id="9bae0-932">**투명한 자식 창 지원**</span><span class="sxs-lookup"><span data-stu-id="9bae0-932">**Transparent child window support**</span></span>

    <span data-ttu-id="9bae0-933">.NET Framework 4.6의 WPF는 Windows 8.1 이상 버전에서 투명한 자식 창을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-933">WPF in .NET Framework 4.6 supports transparent child windows in Windows 8.1 and above.</span></span> <span data-ttu-id="9bae0-934">이를 통해 최상위 창에서 사각형이 아닌 투명한 자식 창을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-934">This allows you to create non-rectangular and transparent child windows in your top-level windows.</span></span> <span data-ttu-id="9bae0-935"><xref:System.Windows.Interop.HwndSourceParameters.UsesPerPixelTransparency%2A?displayProperty=nameWithType> 속성을 `true`로 설정하여 이 기능을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-935">You can enable this feature by setting the <xref:System.Windows.Interop.HwndSourceParameters.UsesPerPixelTransparency%2A?displayProperty=nameWithType> property to `true`.</span></span>

- <span data-ttu-id="9bae0-936">**WCF(Windows Communication Foundation)**</span><span class="sxs-lookup"><span data-stu-id="9bae0-936">**Windows Communication Foundation (WCF)**</span></span>

  - <span data-ttu-id="9bae0-937">**SSL 지원**</span><span class="sxs-lookup"><span data-stu-id="9bae0-937">**SSL support**</span></span>

    <span data-ttu-id="9bae0-938">이제 WCF가 전송 보안 및 클라이언트 인증으로 NetTcp를 사용할 때 SSL 3.0 및 TLS 1.0뿐만 아니라 SSL 버전 TLS 1.1 및 TLS 1.2를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-938">WCF now supports SSL version TLS 1.1 and TLS 1.2, in addition to SSL 3.0 and TLS 1.0, when using NetTcp with transport security and client authentication.</span></span> <span data-ttu-id="9bae0-939">이제 사용할 프로토콜을 선택하거나 이전의 안정성이 낮은 프로토콜을 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-939">It is now possible to select which protocol to use, or to disable old lesser secure protocols.</span></span> <span data-ttu-id="9bae0-940">이 작업을 수행하려면 <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A> 속성을 설정하거나 구성 파일에 다음을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-940">This can be done either by setting the <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A> property or by adding the following to a configuration file.</span></span>

    ```xml
    <netTcpBinding>
        <binding>
          <security mode= "None|Transport|Message|TransportWithMessageCredential" >
              <transport clientCredentialType="None|Windows|Certificate"
                        protectionLevel="None|Sign|EncryptAndSign"
                        sslProtocols="Ssl3|Tls1|Tls11|Tls12">
                </transport>
          </security>
        </binding>
    </netTcpBinding>
    ```

  - <span data-ttu-id="9bae0-941">**다른 HTTP 연결을 사용하여 메시지 전송**</span><span class="sxs-lookup"><span data-stu-id="9bae0-941">**Sending messages using different HTTP connections**</span></span>

    <span data-ttu-id="9bae0-942">이제 WCF를 사용하여 사용자가 특정 메시지를 다른 기본 HTTP 연결을 사용하여 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-942">WCF now allows users to ensure certain messages are sent using different underlying HTTP connections.</span></span> <span data-ttu-id="9bae0-943">여기에는 두 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-943">There are two ways to do this:</span></span>

    - <span data-ttu-id="9bae0-944">**연결 그룹 이름의 접두사 사용**</span><span class="sxs-lookup"><span data-stu-id="9bae0-944">**Using a connection group name prefix**</span></span>

      <span data-ttu-id="9bae0-945">사용자가 WCF에서 연결 그룹 이름의 접두사로 사용할 문자열을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-945">Users can specify a string that WCF will use as a prefix for the connection group name.</span></span> <span data-ttu-id="9bae0-946">서로 다른 접두사를 가진 두 메시지는 서로 다른 기본 HTTP 연결을 사용하여 보내집니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-946">Two messages with different prefixes are sent using different underlying HTTP connections.</span></span> <span data-ttu-id="9bae0-947">키/값 쌍을 메시지의 <xref:System.ServiceModel.Channels.Message.Properties%2A?displayProperty=nameWithType> 속성에 추가하여 접두사를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-947">You set the prefix by adding a key/value pair to the message's <xref:System.ServiceModel.Channels.Message.Properties%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="9bae0-948">키는 "HttpTransportConnectionGroupNamePrefix"이며 값은 원하는 접두사입니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-948">The key is "HttpTransportConnectionGroupNamePrefix"; the value is the desired prefix.</span></span>

    - <span data-ttu-id="9bae0-949">**다른 채널 팩터리 사용**</span><span class="sxs-lookup"><span data-stu-id="9bae0-949">**Using different channel factories**</span></span>

      <span data-ttu-id="9bae0-950">사용자는 서로 다른 채널 팩터리로 만들어진 채널을 사용하여 보낸 메시지가 서로 다른 기본 HTTP 연결을 사용하도록 하는 기능을 사용하도록 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-950">Users can also enable a feature that ensures that messages sent using channels created by different channel factories will use different underlying HTTP connections.</span></span> <span data-ttu-id="9bae0-951">이 기능을 사용하려면 사용자가 다음 `appSetting`을 `true`로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-951">To enable this feature, users must set the following `appSetting` to `true`:</span></span>

      ```xml
      <appSettings>
          <add key="wcf:httpTransportBinding:useUniqueConnectionPoolPerFactory" value="true" />
      </appSettings>
      ```

- <span data-ttu-id="9bae0-952">**WWF(Windows Workflow Foundation)**</span><span class="sxs-lookup"><span data-stu-id="9bae0-952">**Windows Workflow Foundation (WWF)**</span></span>

  <span data-ttu-id="9bae0-953">이제 요청 시간이 초과되기 전에 처리 중인 “비 프로토콜” 책갈피가 있을 때 워크플로 서비스가 순서가 잘못된 작업 요청을 유지하는 시간을 초 단위로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-953">You can now specify the number of seconds a workflow service will hold on to an out-of-order operation request when there is an outstanding "non-protocol" bookmark before timing out the request.</span></span> <span data-ttu-id="9bae0-954">“비 프로토콜” 책갈피는 처리 중인 수신 작업에 관련되지 않은 책갈피입니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-954">A "non-protocol" bookmark is a bookmark that is not related to outstanding Receive activities.</span></span> <span data-ttu-id="9bae0-955">일부 작업은 구현되는 과정에서 비 프로토콜 책갈피를 만들기 때문에 비 프로토콜 책갈피가 있는지 정확히 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-955">Some activities create non-protocol bookmarks within their implementation, so it may not be obvious that a non-protocol bookmark exists.</span></span> <span data-ttu-id="9bae0-956">여기에는 상태 및 선택이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-956">These include State and Pick.</span></span> <span data-ttu-id="9bae0-957">따라서 워크플로 서비스를 상태 컴퓨터를 사용하여 구현하거나 선택 작업을 포함하여 구현한 경우 대부분 비 프로토콜 책갈피가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-957">So if you have a workflow service implemented with a state machine or containing a Pick activity, you will most likely have non-protocol bookmarks.</span></span> <span data-ttu-id="9bae0-958">app.config 파일의 `appSettings` 섹션에 다음과 같은 줄을 추가하여 간격을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-958">You specify the interval by adding a line like the following to the `appSettings` section of your app.config file:</span></span>

  ```xml
  <add key="microsoft:WorkflowServices:FilterResumeTimeoutInSeconds" value="60"/>
  ```

  <span data-ttu-id="9bae0-959">기본값은 60초입니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-959">The default value is 60 seconds.</span></span> <span data-ttu-id="9bae0-960">`value`가 0으로 설정되면 순서가 잘못된 요청은 다음과 같은 텍스트의 오류로 인해 즉시 거부됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-960">If `value` is set to 0, out-of-order requests are immediately rejected with a fault with text that looks like this:</span></span>

  ```console
  Operation 'Request3|{http://tempuri.org/}IService' on service instance with identifier '2b0667b6-09c8-4093-9d02-f6c67d534292' cannot be performed at this time. Please ensure that the operations are performed in the correct order and that the binding in use provides ordered delivery guarantees.
  ```

  <span data-ttu-id="9bae0-961">순서가 잘못된 작업 메시지를 수신하고 비 프로토콜 책갈피가 없다면 동일한 메시지를 수신한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-961">This is the same message that you receive if an out-of-order operation message is received and there are no non-protocol bookmarks.</span></span>

  <span data-ttu-id="9bae0-962">`FilterResumeTimeoutInSeconds` 요소의 값이 0이 아니고 비 프로토콜 책갈피가 있으며 시간 제한 간격이 만료된 경우 시간 초과 메시지와 함께 작업이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-962">If the value of the `FilterResumeTimeoutInSeconds` element is non-zero, there are non-protocol bookmarks, and the timeout interval expires, the operation fails with a timeout message.</span></span>

- <span data-ttu-id="9bae0-963">**트랜잭션**</span><span class="sxs-lookup"><span data-stu-id="9bae0-963">**Transactions**</span></span>

  <span data-ttu-id="9bae0-964">이제 <xref:System.Transactions.TransactionException>에서 파생된 예외를 발생시킨 트랜잭션의 분산 트랜잭션 식별자를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-964">You can now include the distributed transaction identifier for the transaction that has caused an exception derived from <xref:System.Transactions.TransactionException> to be thrown.</span></span> <span data-ttu-id="9bae0-965">이렇게 하려면 app.config 파일의 `appSettings` 섹션에 다음 키를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-965">You do this by adding the following key to the `appSettings` section of your app.config file:</span></span>

  ```xml
  <add key="Transactions:IncludeDistributedTransactionIdInExceptionMessage" value="true"/>
  ```

  <span data-ttu-id="9bae0-966">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-966">The default value is `false`.</span></span>

- <span data-ttu-id="9bae0-967">**네트워킹**</span><span class="sxs-lookup"><span data-stu-id="9bae0-967">**Networking**</span></span>

  - <span data-ttu-id="9bae0-968">**소켓 재사용**</span><span class="sxs-lookup"><span data-stu-id="9bae0-968">**Socket reuse**</span></span>

    <span data-ttu-id="9bae0-969">Windows 10에는 새로운 확장성 높은 네트워킹 알고리즘이 있습니다. 이 알고리즘을 통해 아웃바운드 TCP 연결에 대한 로컬 포트를 재사용하여 컴퓨터 리소스를 효과적으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-969">Windows 10 includes a new high-scalability networking algorithm that makes better use of machine resources by reusing local ports for outbound TCP connections.</span></span> <span data-ttu-id="9bae0-970">.NET Framework 4.6은 새 알고리즘을 지원하므로 .NET 앱이 새 동작을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-970">.NET Framework 4.6 supports the new algorithm, enabling .NET apps to take advantage of the new behavior.</span></span> <span data-ttu-id="9bae0-971">이전 버전의 Windows에는 인위적인 동시 연결 제한(일반적으로 동적 포트 범위의 기본 크기는 16,384임)이 있었습니다. 이는 부하 상태에서 포트 소모를 발생시켜 서비스의 확장성을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-971">In previous versions of Windows, there was an artificial concurrent connection limit (typically 16,384, the default size of the dynamic port range), which could limit the scalability of a service by causing port exhaustion when under load.</span></span>

    <span data-ttu-id="9bae0-972">.NET Framework 4.6에는 다음 두 개의 API가 추가되어 포트를 재사용할 수 있습니다. 이를 통해 동시 연결 시 64KB 제한을 효과적으로 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-972">In .NET Framework 4.6, two APIs have been added to enable port reuse, which effectively removes the 64 KB limit on concurrent connections:</span></span>

    - <span data-ttu-id="9bae0-973"><xref:System.Net.Sockets.SocketOptionName?displayProperty=nameWithType> 열거형 값</span><span class="sxs-lookup"><span data-stu-id="9bae0-973">The <xref:System.Net.Sockets.SocketOptionName?displayProperty=nameWithType> enumeration value.</span></span>

    - <span data-ttu-id="9bae0-974"><xref:System.Net.ServicePointManager.ReusePort%2A?displayProperty=nameWithType> 속성</span><span class="sxs-lookup"><span data-stu-id="9bae0-974">The <xref:System.Net.ServicePointManager.ReusePort%2A?displayProperty=nameWithType> property.</span></span>

    <span data-ttu-id="9bae0-975">기본적으로 `HKLM\SOFTWARE\Microsoft\.NETFramework\v4.0.30319` 레지스트리 키의 `HWRPortReuseOnSocketBind` 값이 0x1로 설정되지 않는 한 <xref:System.Net.ServicePointManager.ReusePort%2A?displayProperty=nameWithType> 속성은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-975">By default, the <xref:System.Net.ServicePointManager.ReusePort%2A?displayProperty=nameWithType> property is `false` unless the `HWRPortReuseOnSocketBind` value of the `HKLM\SOFTWARE\Microsoft\.NETFramework\v4.0.30319` registry key is set to 0x1.</span></span> <span data-ttu-id="9bae0-976">HTTP 연결에 로컬 포트를 재사용하려면 <xref:System.Net.ServicePointManager.ReusePort%2A?displayProperty=nameWithType> 속성을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-976">To enable local port reuse on HTTP connections, set the <xref:System.Net.ServicePointManager.ReusePort%2A?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="9bae0-977">이렇게 하면 <xref:System.Net.Http.HttpClient> 및 <xref:System.Net.HttpWebRequest>에서 나가는 모든 TCP 소켓 연결이 새 Windows 10 소켓 옵션인 [SO_REUSE_UNICASTPORT](/windows/desktop/WinSock/sol-socket-socket-options)를 사용하여 로컬 포트를 재사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-977">This causes all outgoing TCP socket connections from <xref:System.Net.Http.HttpClient> and <xref:System.Net.HttpWebRequest> to use a new Windows 10 socket option, [SO_REUSE_UNICASTPORT](/windows/desktop/WinSock/sol-socket-socket-options), that enables local port reuse.</span></span>

    <span data-ttu-id="9bae0-978">소켓 전용 애플리케이션을 작성하는 개발자가 <xref:System.Net.Sockets.Socket.SetSocketOption%2A?displayProperty=nameWithType>과 같은 메서드를 호출할 때 <xref:System.Net.Sockets.SocketOptionName?displayProperty=nameWithType> 옵션을 지정하면 아웃바운드 소켓이 바인딩하는 동안 로컬 포트를 재사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-978">Developers writing a sockets-only application can specify the <xref:System.Net.Sockets.SocketOptionName?displayProperty=nameWithType> option when calling a method such as <xref:System.Net.Sockets.Socket.SetSocketOption%2A?displayProperty=nameWithType> so that outbound sockets reuse local ports during binding.</span></span>

  - <span data-ttu-id="9bae0-979">**국제 도메인 이름 및 PunyCode 지원**</span><span class="sxs-lookup"><span data-stu-id="9bae0-979">**Support for international domain names and PunyCode**</span></span>

    <span data-ttu-id="9bae0-980">새 속성 <xref:System.Uri.IdnHost%2A>가 <xref:System.Uri> 클래스에 추가되어 국제 도메인 이름 및 PunyCode를 더욱 효과적으로 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-980">A new property, <xref:System.Uri.IdnHost%2A>, has been added to the <xref:System.Uri> class to better support international domain names and PunyCode.</span></span>

- <span data-ttu-id="9bae0-981">**Windows Forms 컨트롤 크기 조정.**</span><span class="sxs-lookup"><span data-stu-id="9bae0-981">**Resizing in Windows Forms controls.**</span></span>

  <span data-ttu-id="9bae0-982">.NET Framework 4.6에서는 이 기능이 <xref:System.Windows.Forms.DomainUpDown>, <xref:System.Windows.Forms.NumericUpDown>, <xref:System.Windows.Forms.DataGridViewComboBoxColumn>, <xref:System.Windows.Forms.DataGridViewColumn> 및 <xref:System.Windows.Forms.ToolStripSplitButton> 형식과 <xref:System.Drawing.Design.UITypeEditor>를 그릴 때 사용되는 <xref:System.Drawing.Design.PaintValueEventArgs.Bounds%2A> 속성으로 지정된 사각형을 포함하도록 확장되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-982">This feature has been expanded in .NET Framework 4.6 to include the <xref:System.Windows.Forms.DomainUpDown>, <xref:System.Windows.Forms.NumericUpDown>, <xref:System.Windows.Forms.DataGridViewComboBoxColumn>, <xref:System.Windows.Forms.DataGridViewColumn> and <xref:System.Windows.Forms.ToolStripSplitButton> types and the rectangle specified by the <xref:System.Drawing.Design.PaintValueEventArgs.Bounds%2A> property used when drawing a <xref:System.Drawing.Design.UITypeEditor>.</span></span>

  <span data-ttu-id="9bae0-983">이 기능은 옵트인 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-983">This is an opt-in feature.</span></span> <span data-ttu-id="9bae0-984">이 기능을 사용하려면 아래와 같이 애플리케이션 구성 파일(app.config)에서 `EnableWindowsFormsHighDpiAutoResizing` 요소를 `true`로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-984">To enable it, set the `EnableWindowsFormsHighDpiAutoResizing` element to `true` in the application configuration (app.config) file:</span></span>

  ```xml
  <appSettings>
      <add key="EnableWindowsFormsHighDpiAutoResizing" value="true" />
  </appSettings>
  ```

- <span data-ttu-id="9bae0-985">**코드 페이지 인코딩 지원**</span><span class="sxs-lookup"><span data-stu-id="9bae0-985">**Support for code page encodings**</span></span>

  <span data-ttu-id="9bae0-986">.NET Core에서는 주로 유니코드 인코딩을 지원하며, 기본적으로 코드 페이지 인코딩에 대한 제한된 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-986">.NET Core primarily supports the Unicode encodings and by default provides limited support for code page encodings.</span></span> <span data-ttu-id="9bae0-987"><xref:System.Text.Encoding.RegisterProvider%2A?displayProperty=nameWithType> 메서드로 코드 페이지 인코딩을 등록하여 .NET Framework에서 사용할 수 있지만 .Net Core에서 지원되지 않는 코드 페이지 인코딩에 대한 지원을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-987">You can add support for code page encodings available in .NET Framework but unsupported in .NET Core by registering code page encodings with the <xref:System.Text.Encoding.RegisterProvider%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="9bae0-988">자세한 내용은 <xref:System.Text.CodePagesEncodingProvider?displayProperty=nameWithType>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bae0-988">For more information, see <xref:System.Text.CodePagesEncodingProvider?displayProperty=nameWithType>.</span></span>

- <span data-ttu-id="9bae0-989">**.NET 네이티브**</span><span class="sxs-lookup"><span data-stu-id="9bae0-989">**.NET Native**</span></span>

  <span data-ttu-id="9bae0-990">.NET Core를 대상으로 하며 C# 또는 Visual Basic으로 작성된 Windows 10용 앱은 IL이 아니라 네이티브 코드로 앱을 컴파일하는 새 기술을 이용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-990">Windows apps for Windows 10 that target .NET Core and are written in C# or Visual Basic can take advantage of a new technology that compiles apps to native code rather than IL.</span></span> <span data-ttu-id="9bae0-991">이렇게 생성된 앱은 시작 및 실행 시간이 훨씬 더 빠릅니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-991">They produce apps characterized by faster startup and execution times.</span></span> <span data-ttu-id="9bae0-992">자세한 내용은 [.NET 네이티브로 앱 컴파일](../net-native/index.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9bae0-992">For more information, see [Compiling Apps with .NET Native](../net-native/index.md).</span></span> <span data-ttu-id="9bae0-993">JIT 컴파일 및 NGEN 둘 다와의 차이점 및 코드에 미치는 영향을 검사하는 .NET 네이티브의 개요는 [.NET 네이티브 및 컴파일](../net-native/net-native-and-compilation.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9bae0-993">For an overview of .NET Native that examines how it differs from both JIT compilation and NGEN and what that means for your code, see [.NET Native and Compilation](../net-native/net-native-and-compilation.md).</span></span>

  <span data-ttu-id="9bae0-994">Visual Studio 2015 이상으로 컴파일하는 경우 앱은 기본적으로 네이티브 코드로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-994">Your apps are compiled to native code by default when you compile them with Visual Studio 2015 or later.</span></span> <span data-ttu-id="9bae0-995">자세한 내용은 [.NET 네이티브 시작](../net-native/getting-started-with-net-native.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9bae0-995">For more information, see [Getting Started with .NET Native](../net-native/getting-started-with-net-native.md).</span></span>

  <span data-ttu-id="9bae0-996">.NET 네이티브 앱 디버그를 지원하기 위해 다양한 인터페이스 및 열거형이 관리되지 않는 디버깅 API에 새로 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-996">To support debugging .NET Native apps, a number of new interfaces and enumerations have been added to the unmanaged debugging API.</span></span> <span data-ttu-id="9bae0-997">자세한 내용은 [디버깅(관리되지 않는 API 참조)](../unmanaged-api/debugging/index.md) 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9bae0-997">For more information, see the [Debugging (Unmanaged API Reference)](../unmanaged-api/debugging/index.md) topic.</span></span>

- <span data-ttu-id="9bae0-998">**오픈 소스 .NET Framework 패키지**</span><span class="sxs-lookup"><span data-stu-id="9bae0-998">**Open-source .NET Framework packages**</span></span>

  <span data-ttu-id="9bae0-999">이제 .NET Core 패키지(예: 변경할 수 없는 컬렉션, [SIMD API](https://www.nuget.org/packages/Microsoft.Bcl.Simd)) 및 네트워킹 API(예: <xref:System.Net.Http> 네임스페이스에 있는 API)를 [GitHub](https://github.com/)에서 오픈 소스 패키지로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-999">.NET Core packages such as the immutable collections, [SIMD APIs](https://www.nuget.org/packages/Microsoft.Bcl.Simd), and networking APIs such as those found in the <xref:System.Net.Http> namespace are now available as open-source packages on [GitHub](https://github.com/).</span></span> <span data-ttu-id="9bae0-1000">코드 액세스 방법은 [GitHub의 .NET](https://github.com/dotnet/runtime)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1000">To access the code, see [.NET on GitHub](https://github.com/dotnet/runtime).</span></span> <span data-ttu-id="9bae0-1001">자세한 내용과 이러한 패키지에 기여하는 방법은 [.NET 소개](../../core/introduction.md), [GitHub의 .NET 홈페이지](https://github.com/dotnet/home)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1001">For more information and how to contribute to these packages, see [Introduction to .NET](../../core/introduction.md), [.NET Home Page on GitHub](https://github.com/dotnet/home).</span></span>

<a name="v452"></a>

## <a name="whats-new-in-net-framework-452"></a><span data-ttu-id="9bae0-1002">.NET Framework 4.5.2의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="9bae0-1002">What's new in .NET Framework 4.5.2</span></span>

- <span data-ttu-id="9bae0-1003">**ASP.NET 앱을 위한 새 API.**</span><span class="sxs-lookup"><span data-stu-id="9bae0-1003">**New APIs for ASP.NET apps.**</span></span> <span data-ttu-id="9bae0-1004">새로운 <xref:System.Web.HttpResponse.AddOnSendingHeaders%2A?displayProperty=nameWithType> 및 <xref:System.Web.HttpResponseBase.AddOnSendingHeaders%2A?displayProperty=nameWithType> 메서드를 통해, 응답이 클라이언트 앱에 플러시되고 있을 때 응답 헤더와 상태 코드를 검사 및 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1004">The new <xref:System.Web.HttpResponse.AddOnSendingHeaders%2A?displayProperty=nameWithType> and <xref:System.Web.HttpResponseBase.AddOnSendingHeaders%2A?displayProperty=nameWithType> methods let you inspect and modify response headers and status code as the response is being flushed to the client app.</span></span> <span data-ttu-id="9bae0-1005">이러한 메서드는 <xref:System.Web.HttpApplication.PreSendRequestHeaders> 및 <xref:System.Web.HttpApplication.PreSendRequestContent> 이벤트 대신 사용할 수 있으며 더욱 효율적이고 신뢰할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1005">Consider using these methods instead of the <xref:System.Web.HttpApplication.PreSendRequestHeaders> and <xref:System.Web.HttpApplication.PreSendRequestContent> events; they are more efficient and reliable.</span></span>

  <span data-ttu-id="9bae0-1006"><xref:System.Web.Hosting.HostingEnvironment.QueueBackgroundWorkItem%2A?displayProperty=nameWithType> 메서드를 사용하면 소형 백그라운드 작업 항목을 예약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1006">The <xref:System.Web.Hosting.HostingEnvironment.QueueBackgroundWorkItem%2A?displayProperty=nameWithType> method lets you schedule small background work items.</span></span> <span data-ttu-id="9bae0-1007">ASP.NET는 이러한 항목을 추적하여 모든 백그라운드 작업 항목이 완료될 때까지는 IIS가 작업자 프로세스를 갑자기 종료하지 못하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1007">ASP.NET tracks these items and prevents IIS from abruptly terminating the worker process until all background work items have completed.</span></span> <span data-ttu-id="9bae0-1008">ASP.NET 관리되는 앱 도메인 외부에서는 이 메서드를 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1008">This method can't be called outside an ASP.NET managed app domain.</span></span>

  <span data-ttu-id="9bae0-1009">새로운 <xref:System.Web.HttpResponse.HeadersWritten?displayProperty=nameWithType> 및 <xref:System.Web.HttpResponseBase.HeadersWritten?displayProperty=nameWithType> 속성은 응답 헤더가 작성되어 있는지 여부를 나타내는 부울 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1009">The new <xref:System.Web.HttpResponse.HeadersWritten?displayProperty=nameWithType> and <xref:System.Web.HttpResponseBase.HeadersWritten?displayProperty=nameWithType> properties return Boolean values that indicate whether the response headers have been written.</span></span> <span data-ttu-id="9bae0-1010">이러한 속성을 사용하면 <xref:System.Web.HttpResponse.StatusCode%2A?displayProperty=nameWithType>(헤더가 작성되어 있으면 예외를 throw) 등의 API를 성공적으로 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1010">You can use these properties to make sure that calls to APIs such as <xref:System.Web.HttpResponse.StatusCode%2A?displayProperty=nameWithType> (which throw exceptions if the headers have been written) will succeed.</span></span>

- <span data-ttu-id="9bae0-1011">**Windows Forms 컨트롤 크기 조정.**</span><span class="sxs-lookup"><span data-stu-id="9bae0-1011">**Resizing in Windows Forms controls.**</span></span> <span data-ttu-id="9bae0-1012">이 기능은 확장되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1012">This feature has been expanded.</span></span> <span data-ttu-id="9bae0-1013">시스템 DPI 설정을 사용하여 다음과 같은 추가 컨트롤의 구성 요소 크기를 조정할 수 있습니다(예: 콤보 상자의 드롭다운 화살표).</span><span class="sxs-lookup"><span data-stu-id="9bae0-1013">You can now use the system DPI setting to resize components of the following additional controls (for example, the drop-down arrow in combo boxes):</span></span>

  - <xref:System.Windows.Forms.ComboBox>
  - <xref:System.Windows.Forms.ToolStripComboBox>
  - <xref:System.Windows.Forms.ToolStripMenuItem>
  - <xref:System.Windows.Forms.Cursor>
  - <xref:System.Windows.Forms.DataGridView>
  - <xref:System.Windows.Forms.DataGridViewComboBoxColumn>

  <span data-ttu-id="9bae0-1014">이 기능은 옵트인 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1014">This is an opt-in feature.</span></span> <span data-ttu-id="9bae0-1015">이 기능을 사용하려면 아래와 같이 애플리케이션 구성 파일(app.config)에서 `EnableWindowsFormsHighDpiAutoResizing` 요소를 `true`로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1015">To enable it, set the `EnableWindowsFormsHighDpiAutoResizing` element to `true` in the application configuration (app.config) file:</span></span>

  ```xml
  <appSettings>
      <add key="EnableWindowsFormsHighDpiAutoResizing" value="true" />
  </appSettings>
  ```

- <span data-ttu-id="9bae0-1016">**새 워크플로 기능.**</span><span class="sxs-lookup"><span data-stu-id="9bae0-1016">**New workflow feature.**</span></span> <span data-ttu-id="9bae0-1017"><xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A> 메서드를 사용하여 <xref:System.Transactions.IPromotableSinglePhaseNotification> 인터페이스를 구현하는 리소스 관리자는 새로운 <xref:System.Transactions.Transaction.PromoteAndEnlistDurable%2A?displayProperty=nameWithType> 메서드를 통해 다음을 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1017">A resource manager that's using the <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A> method (and therefore implementing the <xref:System.Transactions.IPromotableSinglePhaseNotification> interface) can use the new <xref:System.Transactions.Transaction.PromoteAndEnlistDurable%2A?displayProperty=nameWithType> method to request the following:</span></span>

  - <span data-ttu-id="9bae0-1018">트랜잭션을 MSDTC(Microsoft Distributed Transaction Coordinator) 트랜잭션으로 승격합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1018">Promote the transaction to a Microsoft Distributed Transaction Coordinator (MSDTC) transaction.</span></span>

  - <span data-ttu-id="9bae0-1019"><xref:System.Transactions.IPromotableSinglePhaseNotification>을 단일 단계 커밋이 지원되는 견고한 인리스트먼트인 <xref:System.Transactions.ISinglePhaseNotification>으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1019">Replace <xref:System.Transactions.IPromotableSinglePhaseNotification> with an <xref:System.Transactions.ISinglePhaseNotification>, which is a durable enlistment that supports single phase commits.</span></span>

  <span data-ttu-id="9bae0-1020">이 기능은 동일한 앱 도메인 내에서 수행할 수 있으며 승격 수행을 위해 MSDTC와 상호 작용하기 위한 관리되지 않는 코드가 추가로 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1020">This can be done within the same app domain, and doesn't require any extra unmanaged code to interact with MSDTC to perform the promotion.</span></span> <span data-ttu-id="9bae0-1021">새 메서드는 승격 가능한 인리스트먼트에 의해 구현되는 <xref:System.Transactions.IPromotableSinglePhaseNotification>`Promote` 메서드에 대한 <xref:System.Transactions?displayProperty=nameWithType>의 호출이 해결되지 않은 경우에만 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1021">The new method can be called only when there's an outstanding call from <xref:System.Transactions?displayProperty=nameWithType> to the <xref:System.Transactions.IPromotableSinglePhaseNotification>`Promote` method that's implemented by the promotable enlistment.</span></span>

- <span data-ttu-id="9bae0-1022">**프로파일링 기능 향상.**</span><span class="sxs-lookup"><span data-stu-id="9bae0-1022">**Profiling improvements.**</span></span> <span data-ttu-id="9bae0-1023">다음과 같은 관리되지 않는 새로운 프로파일링 API를 통해 더욱 강력한 프로파일링 기능이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1023">The following new unmanaged profiling APIs provide more robust profiling:</span></span>

  - [<span data-ttu-id="9bae0-1024">COR_PRF_ASSEMBLY_REFERENCE_INFO 구조체</span><span class="sxs-lookup"><span data-stu-id="9bae0-1024">COR_PRF_ASSEMBLY_REFERENCE_INFO Structure</span></span>](../unmanaged-api/profiling/cor-prf-assembly-reference-info-structure.md)
  - [<span data-ttu-id="9bae0-1025">COR_PRF_HIGH_MONITOR 열거형</span><span class="sxs-lookup"><span data-stu-id="9bae0-1025">COR_PRF_HIGH_MONITOR Enumeration</span></span>](../unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md)
  - [<span data-ttu-id="9bae0-1026">GetAssemblyReferences 메서드</span><span class="sxs-lookup"><span data-stu-id="9bae0-1026">GetAssemblyReferences Method</span></span>](../unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)
  - [<span data-ttu-id="9bae0-1027">GetEventMask2 메서드</span><span class="sxs-lookup"><span data-stu-id="9bae0-1027">GetEventMask2 Method</span></span>](../unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md)
  - [<span data-ttu-id="9bae0-1028">SetEventMask2 메서드</span><span class="sxs-lookup"><span data-stu-id="9bae0-1028">SetEventMask2 Method</span></span>](../unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)
  - [<span data-ttu-id="9bae0-1029">AddAssemblyReference 메서드</span><span class="sxs-lookup"><span data-stu-id="9bae0-1029">AddAssemblyReference Method</span></span>](../unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)

  <span data-ttu-id="9bae0-1030">이전 `ICorProfiler` 구현에서는 종속 어셈블리에 대한 지연 로딩이 지원되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1030">Previous `ICorProfiler` implementations supported lazy loading of dependent assemblies.</span></span> <span data-ttu-id="9bae0-1031">새로운 프로파일링 API의 경우 프로파일러에 의해 삽입된 종속 어셈블리는 앱이 완전히 초기화된 후에 로드되는 것이 아니라 즉시 로드할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1031">The new profiling APIs require dependent assemblies that are injected by the profiler to be loadable immediately, instead of being loaded after the app is fully initialized.</span></span> <span data-ttu-id="9bae0-1032">기존 `ICorProfiler` API 사용자에게는 이 변경 내용이 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1032">This change doesn't affect users of the existing `ICorProfiler` APIs.</span></span>

- <span data-ttu-id="9bae0-1033">**디버깅 기능 향상.**</span><span class="sxs-lookup"><span data-stu-id="9bae0-1033">**Debugging improvements.**</span></span> <span data-ttu-id="9bae0-1034">다음과 같은 관리되지 않는 새로운 디버깅 API를 통해 프로파일러와 더욱 완벽하게 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1034">The following new unmanaged debugging APIs provide better integration with a profiler.</span></span> <span data-ttu-id="9bae0-1035">덤프 디버깅 시 컴파일러 ReJIT 요청에 의해 생성된 로컬 변수 및 코드뿐 아니라 프로파일러가 삽입한 메타데이터를 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1035">You can now access metadata inserted by the profiler as well as local variables and code produced by compiler ReJIT requests when dump debugging.</span></span>

  - [<span data-ttu-id="9bae0-1036">SetWriteableMetadataUpdateMode 메서드</span><span class="sxs-lookup"><span data-stu-id="9bae0-1036">SetWriteableMetadataUpdateMode Method</span></span>](../unmanaged-api/debugging/icordebugprocess7-setwriteablemetadataupdatemode-method.md)
  - [<span data-ttu-id="9bae0-1037">EnumerateLocalVariablesEx 메서드</span><span class="sxs-lookup"><span data-stu-id="9bae0-1037">EnumerateLocalVariablesEx Method</span></span>](../unmanaged-api/debugging/icordebugilframe4-enumeratelocalvariablesex-method.md)
  - [<span data-ttu-id="9bae0-1038">GetLocalVariableEx 메서드</span><span class="sxs-lookup"><span data-stu-id="9bae0-1038">GetLocalVariableEx Method</span></span>](../unmanaged-api/debugging/icordebugilframe4-getlocalvariableex-method.md)
  - [<span data-ttu-id="9bae0-1039">GetCodeEx 메서드</span><span class="sxs-lookup"><span data-stu-id="9bae0-1039">GetCodeEx Method</span></span>](../unmanaged-api/debugging/icordebugilframe4-getcodeex-method.md)
  - [<span data-ttu-id="9bae0-1040">GetActiveReJitRequestILCode 메서드</span><span class="sxs-lookup"><span data-stu-id="9bae0-1040">GetActiveReJitRequestILCode Method</span></span>](../unmanaged-api/debugging/icordebugfunction3-getactiverejitrequestilcode-method.md)
  - [<span data-ttu-id="9bae0-1041">GetInstrumentedILMap 메서드</span><span class="sxs-lookup"><span data-stu-id="9bae0-1041">GetInstrumentedILMap Method</span></span>](../unmanaged-api/debugging/icordebugilcode2-getinstrumentedilmap-method.md)

- <span data-ttu-id="9bae0-1042">**이벤트 추적 변경 내용.**</span><span class="sxs-lookup"><span data-stu-id="9bae0-1042">**Event tracing changes.**</span></span> <span data-ttu-id="9bae0-1043">.NET Framework 4.5.2에서는 대형 노출 영역에 대해 out-of-process로 실행되는 ETW(Windows용 이벤트 추적) 기반 작업 추적이 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1043">.NET Framework 4.5.2 enables out-of-process, Event Tracing for Windows (ETW)-based activity tracing for a larger surface area.</span></span> <span data-ttu-id="9bae0-1044">이를 통해 APM(고급 전원 관리) 공급업체는 스레드 간의 각 요청 및 작업에 대한 비용을 정확하게 추적하는 간단한 도구를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1044">This enables Advanced Power Management (APM) vendors to provide lightweight tools that accurately track the costs of individual requests and activities that cross threads.</span></span>  <span data-ttu-id="9bae0-1045">이러한 이벤트는 ETW 컨트롤러에 의해 활성화된 경우에만 발생되므로 이전에 작성된 ETW 코드나 비활성화된 ETW로 실행된 코드에는 변경 내용이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1045">These events are raised only when ETW controllers enable them; therefore, the changes don't affect previously written ETW code or code that runs with ETW disabled.</span></span>

- <span data-ttu-id="9bae0-1046">**트랜잭션을 승격하고 지속적인 인리스트먼트로 변환**</span><span class="sxs-lookup"><span data-stu-id="9bae0-1046">**Promoting a transaction and converting it to a durable enlistment**</span></span>

  <span data-ttu-id="9bae0-1047"><xref:System.Transactions.Transaction.PromoteAndEnlistDurable%2A?displayProperty=nameWithType>은 .NET Framework 4.5.2 및 4.6에 추가된 새로운 API입니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1047"><xref:System.Transactions.Transaction.PromoteAndEnlistDurable%2A?displayProperty=nameWithType> is a new API added to .NET Framework 4.5.2 and 4.6:</span></span>

  ```csharp
  [System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name = "FullTrust")]
  public Enlistment PromoteAndEnlistDurable(Guid resourceManagerIdentifier,
                                            IPromotableSinglePhaseNotification promotableNotification,
                                            ISinglePhaseNotification enlistmentNotification,
                                            EnlistmentOptions enlistmentOptions)
  ```

  ```vb
  <System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name:="FullTrust")>
  public Function PromoteAndEnlistDurable(resourceManagerIdentifier As Guid,
                                          promotableNotification As IPromotableSinglePhaseNotification,
                                          enlistmentNotification As ISinglePhaseNotification,
                                          enlistmentOptions As EnlistmentOptions) As Enlistment
  ```

  <span data-ttu-id="9bae0-1048">이 메서드는 <xref:System.Transactions.ITransactionPromoter.Promote%2A?displayProperty=nameWithType> 메서드에 대한 응답으로 <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A?displayProperty=nameWithType>가 이전에 만든 인리스트먼트에 의해 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1048">The method may be used by an enlistment that was previously created by <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A?displayProperty=nameWithType> in response to the <xref:System.Transactions.ITransactionPromoter.Promote%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="9bae0-1049">트랜잭션에서 MSDTC 트랜잭션으로 수준을 올리고, 수준을 올릴 수 있는 인리스트먼트를 지속적인 인리스트먼트로 “변환”하도록 `System.Transactions`에게 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1049">It asks `System.Transactions` to promote the transaction to an MSDTC transaction and to "convert" the promotable enlistment to a durable enlistment.</span></span> <span data-ttu-id="9bae0-1050">이 메서드가 성공적으로 완료되면 `System.Transactions`이 <xref:System.Transactions.IPromotableSinglePhaseNotification> 인터페이스를 더 이상 참조하지 않습니다. 향후 모든 알림은 제공된 <xref:System.Transactions.ISinglePhaseNotification> 인터페이스에 도착하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1050">After this method completes successfully, the <xref:System.Transactions.IPromotableSinglePhaseNotification> interface will no longer be referenced by `System.Transactions`, and any future notifications will arrive on the provided <xref:System.Transactions.ISinglePhaseNotification> interface.</span></span> <span data-ttu-id="9bae0-1051">해당 인리스트먼트는 지속적인 인리스트먼트로 작동해야 하며 트랜잭션 로깅 및 복구를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1051">The enlistment in question must act as a durable enlistment, supporting transaction logging and recovery.</span></span> <span data-ttu-id="9bae0-1052">자세한 내용은 <xref:System.Transactions.Transaction.EnlistDurable%2A?displayProperty=nameWithType>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1052">Refer to <xref:System.Transactions.Transaction.EnlistDurable%2A?displayProperty=nameWithType> for details.</span></span> <span data-ttu-id="9bae0-1053">또한 인리스트먼트는 <xref:System.Transactions.ISinglePhaseNotification>을 지원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1053">In addition, the enlistment must support <xref:System.Transactions.ISinglePhaseNotification>.</span></span>  <span data-ttu-id="9bae0-1054">이 메서드는 <xref:System.Transactions.ITransactionPromoter.Promote%2A?displayProperty=nameWithType> 호출을 처리하는 동안에 *만* 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1054">This method can *only* be called while processing an <xref:System.Transactions.ITransactionPromoter.Promote%2A?displayProperty=nameWithType> call.</span></span> <span data-ttu-id="9bae0-1055">그렇지 않은 경우 <xref:System.Transactions.TransactionException> 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1055">If that is not the case, a <xref:System.Transactions.TransactionException> exception is thrown.</span></span>

<a name="v451"></a>

## <a name="whats-new-in-net-framework-451"></a><span data-ttu-id="9bae0-1056">.NET Framework 4.5.1의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="9bae0-1056">What's new in .NET Framework 4.5.1</span></span>

<span data-ttu-id="9bae0-1057">**2014년 4월 업데이트** :</span><span class="sxs-lookup"><span data-stu-id="9bae0-1057">**April 2014 updates** :</span></span>

- <span data-ttu-id="9bae0-1058">[Visual Studio 2013 업데이트 2](https://go.microsoft.com/fwlink/p/?LinkId=393658)에는 이식 가능한 클래스 라이브러리 템플릿에 대한 업데이트가 포함되어 다음과 같은 시나리오가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1058">[Visual Studio 2013 Update 2](https://go.microsoft.com/fwlink/p/?LinkId=393658) includes updates to the Portable Class Library templates to support these scenarios:</span></span>

  - <span data-ttu-id="9bae0-1059">Windows 8.1, Windows Phone 8.1 및 Windows Phone Silverlight 8.1을 대상으로 하는 이식 가능한 라이브러리에서 Windows 런타임 API를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1059">You can use Windows Runtime APIs in portable libraries that target Windows 8.1, Windows Phone 8.1, and Windows Phone Silverlight 8.1.</span></span>

  - <span data-ttu-id="9bae0-1060">Windows 8.1 또는 Windows Phone 8.1을 대상으로 하는 경우 XAML(Windows.UI.XAML 형식)을 이식 가능한 라이브러리에 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1060">You can include XAML (Windows.UI.XAML types) in portable libraries when you target Windows 8.1 or Windows Phone 8.1.</span></span> <span data-ttu-id="9bae0-1061">다음과 같은 XAML 템플릿이 지원됩니다.  빈 페이지, 리소스 사전, 템플릿 컨트롤 및 사용자 정의 컨트롤</span><span class="sxs-lookup"><span data-stu-id="9bae0-1061">The following XAML templates are supported:  Blank Page, Resource Dictionary, Templated Control, and User Control.</span></span>

  - <span data-ttu-id="9bae0-1062">Windows 8.1 및 Windows Phone 8.1 대상의 스토어 앱에서 사용할 이식 가능한 Windows 런타임 구성 요소(.winmd 파일)를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1062">You can create a portable Windows Runtime component (.winmd file) for use in Store apps that target Windows 8.1 and Windows Phone 8.1.</span></span>

  - <span data-ttu-id="9bae0-1063">이식 가능한 클래스 라이브러리처럼 대상을 다시 Windows 스토어 또는 Windows Phone 스토어 클래스 라이브러리를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1063">You can retarget a Windows Store or Windows Phone Store class library like a Portable Class Library.</span></span>

  <span data-ttu-id="9bae0-1064">이러한 변경 내용에 대한 자세한 내용은 [이식 가능한 클래스 라이브러리](../cross-platform/portable-class-library.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1064">For more information about these changes, see [Portable Class Library](../cross-platform/portable-class-library.md).</span></span>

- <span data-ttu-id="9bae0-1065">이제 Windows 앱 빌드 및 배포를 위한 미리 컴파일 기술인 .NET Native에 대한 설명서가 .NET Framework 콘텐츠 집합에 포함되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1065">The .NET Framework content set now includes documentation for .NET Native, which is a precompilation technology for building and deploying Windows apps.</span></span> <span data-ttu-id="9bae0-1066">.NET Native는 앱을 중간 언어가 아닌 네이티브 코드로 직접 컴파일하여 더 나은 성능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1066">.NET Native compiles your apps directly to native code, rather than to intermediate language (IL), for better performance.</span></span> <span data-ttu-id="9bae0-1067">자세한 내용은 [.NET 네이티브로 앱 컴파일](../net-native/index.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1067">For details, see [Compiling Apps with .NET Native](../net-native/index.md).</span></span>

- <span data-ttu-id="9bae0-1068">[.NET Framework 참조 소스](https://referencesource.microsoft.com/)에서는 새로운 검색 환경과 향상된 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1068">The [.NET Framework Reference Source](https://referencesource.microsoft.com/) provides a new browsing experience and enhanced functionality.</span></span> <span data-ttu-id="9bae0-1069">온라인에서 .NET Framework 소스 코드를 검색하여, [참조를 다운로드](https://referencesource.microsoft.com/download.html)해 오프라인에서 살펴보고, 디버그 시 소스(패치 및 업데이트 포함)를 단계별로 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1069">You can now browse through the .NET Framework source code online, [download the reference](https://referencesource.microsoft.com/download.html) for offline viewing, and step through the sources (including patches and updates) during debugging.</span></span> <span data-ttu-id="9bae0-1070">자세한 내용은 블로그 항목 [.NET 참조 소스의 새로운 디자인](https://devblogs.microsoft.com/dotnet/a-new-look-for-net-reference-source/)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1070">For more information, see the blog entry [A new look for .NET Reference Source](https://devblogs.microsoft.com/dotnet/a-new-look-for-net-reference-source/).</span></span>

<span data-ttu-id="9bae0-1071">.NET Framework 4.5.1에서 기본 클래스의 새로운 기능 및 향상된 기능은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1071">New features and enhancements in the base classes in .NET Framework 4.5.1 include:</span></span>

- <span data-ttu-id="9bae0-1072">어셈블리에 대한 자동 바인딩 리디렉션.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1072">Automatic binding redirection for assemblies.</span></span> <span data-ttu-id="9bae0-1073">Visual Studio 2013부터는 .NET Framework 4.5.1을 대상으로 하는 앱을 컴파일할 때 앱 또는 해당 구성 요소가 동일한 어셈블리의 여러 버전을 참조할 경우 앱 구성 파일에 바인딩 리디렉션을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1073">Starting with Visual Studio 2013, when you compile an app that targets .NET Framework 4.5.1, binding redirects may be added to the app configuration file if your app or its components reference multiple versions of the same assembly.</span></span> <span data-ttu-id="9bae0-1074">또한 이전 버전의 .NET Framework를 대상으로 하는 프로젝트에 대해 이 기능을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1074">You can also enable this feature for projects that target older versions of .NET Framework.</span></span> <span data-ttu-id="9bae0-1075">자세한 내용은 [방법: 자동 바인딩 리디렉션 사용 설정 및 해제](../configure-apps/how-to-enable-and-disable-automatic-binding-redirection.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1075">For more information, see [How to: Enable and Disable Automatic Binding Redirection](../configure-apps/how-to-enable-and-disable-automatic-binding-redirection.md).</span></span>

- <span data-ttu-id="9bae0-1076">진단 정보를 수집하여 개발자가 서버 및 클라우드 애플리케이션의 성능을 향상시키는 기능.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1076">Ability to collect diagnostics information to help developers improve the performance of server and cloud applications.</span></span> <span data-ttu-id="9bae0-1077">자세한 내용은 <xref:System.Diagnostics.Tracing.EventSource.WriteEventWithRelatedActivityId%2A> 클래스의 <xref:System.Diagnostics.Tracing.EventSource.WriteEventWithRelatedActivityIdCore%2A> 및 <xref:System.Diagnostics.Tracing.EventSource> 메서드를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1077">For more information, see the <xref:System.Diagnostics.Tracing.EventSource.WriteEventWithRelatedActivityId%2A> and <xref:System.Diagnostics.Tracing.EventSource.WriteEventWithRelatedActivityIdCore%2A> methods in the <xref:System.Diagnostics.Tracing.EventSource> class.</span></span>

- <span data-ttu-id="9bae0-1078">가비지 수집 동안 LOH(대형 개체 힙)를 명시적으로 압축하는 기능.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1078">Ability to explicitly compact the large object heap (LOH) during garbage collection.</span></span> <span data-ttu-id="9bae0-1079">자세한 내용은 <xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode%2A?displayProperty=nameWithType> 속성을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1079">For more information, see the <xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode%2A?displayProperty=nameWithType> property.</span></span>

- <span data-ttu-id="9bae0-1080">.NET Framework 업데이트를 통해 ASP.NET 응용 프로그램 일시 중단, 멀티 코어 JIT 개선 및 빠른 응용 프로그램 시작 등의 추가적인 성능 개선.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1080">Additional performance improvements such as ASP.NET app suspension, multi-core JIT improvements, and faster app startup after a .NET Framework update.</span></span> <span data-ttu-id="9bae0-1081">자세한 내용은 [.NET Framework 4.5.1 알림](https://devblogs.microsoft.com/dotnet/announcing-the-net-framework-4-5-1-preview/) 및 [ASP.NET 응용 프로그램 일시 중단](https://devblogs.microsoft.com/dotnet/asp-net-app-suspend-responsive-shared-net-web-hosting/) 블로그 게시물을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1081">For details, see the [.NET Framework 4.5.1 announcement](https://devblogs.microsoft.com/dotnet/announcing-the-net-framework-4-5-1-preview/) and the [ASP.NET app suspend](https://devblogs.microsoft.com/dotnet/asp-net-app-suspend-responsive-shared-net-web-hosting/) blog post.</span></span>

<span data-ttu-id="9bae0-1082">Windows Forms의 향상된 기능은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1082">Improvements to Windows Forms include:</span></span>

- <span data-ttu-id="9bae0-1083">Windows Forms 컨트롤 크기 조정.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1083">Resizing in Windows Forms controls.</span></span> <span data-ttu-id="9bae0-1084">앱의 애플리케이션 구성 파일(app.config)의 항목을 선택하여 시스템 DPI 설정으로 컨트롤 구성 요소(예: 속성 표에 표시되는 아이콘)의 크기를 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1084">You can use the system DPI setting to resize components of controls (for example, the icons that appear in a property grid) by opting in with an entry in the application configuration file (app.config) for your app.</span></span> <span data-ttu-id="9bae0-1085">이 기능은 현재 다음과 같은 Windows Forms 컨트롤에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1085">This feature is currently supported in the following Windows Forms controls:</span></span>

  - <xref:System.Windows.Forms.PropertyGrid>
  - <xref:System.Windows.Forms.TreeView>
  - <span data-ttu-id="9bae0-1086"><xref:System.Windows.Forms.DataGridView>의 일부 구성 요소(그 밖에 지원되는 컨트롤에 대해서는 [4.5.2의 새 기능](#v452) 참조)</span><span class="sxs-lookup"><span data-stu-id="9bae0-1086">Some aspects of the <xref:System.Windows.Forms.DataGridView> (see [new features in 4.5.2](#v452) for additional controls supported)</span></span>

  <span data-ttu-id="9bae0-1087">이 기능을 사용하려면 다음과 같이 새로운 \<appSettings> 요소를 구성 파일(app.config)에 추가하여 `EnableWindowsFormsHighDpiAutoResizing` 요소를 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1087">To enable this feature, add a new \<appSettings> element to the configuration file (app.config) and set the `EnableWindowsFormsHighDpiAutoResizing` element to `true`:</span></span>

  ```xml
  <appSettings>
      <add key="EnableWindowsFormsHighDpiAutoResizing" value="true" />
  </appSettings>
  ```

<span data-ttu-id="9bae0-1088">Visual Studio 2013의 .NET Framework 응용 프로그램 디버깅 시 개선된 기능은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1088">Improvements when debugging your .NET Framework apps in Visual Studio 2013 include:</span></span>

- <span data-ttu-id="9bae0-1089">Visual Studio 디버거에서 값 반환.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1089">Return values in the Visual Studio debugger.</span></span> <span data-ttu-id="9bae0-1090">Visual Studio 2013에서 관리되는 응용 프로그램을 디버깅하면 자동 창에 메서드에 대한 반환 형식 및 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1090">When you debug a managed app in Visual Studio 2013, the Autos window displays return types and values for methods.</span></span> <span data-ttu-id="9bae0-1091">이 정보는 데스크톱, Windows 스토어 및 Windows Phone 응용 프로그램에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1091">This information is available for desktop, Windows Store, and Windows Phone apps.</span></span> <span data-ttu-id="9bae0-1092">자세한 내용은 [메서드 호출의 반환 값 검사](/previous-versions/visualstudio/visual-studio-2013/dn323257(v=vs.120))를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1092">For more information, see [Examine return values of method calls](/previous-versions/visualstudio/visual-studio-2013/dn323257(v=vs.120)).</span></span>

- <span data-ttu-id="9bae0-1093">64비트 응용 프로그램의 편집하며 계속하기.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1093">Edit and Continue for 64-bit apps.</span></span> <span data-ttu-id="9bae0-1094">Visual Studio 2013은 데스크톱, Windows 스토어 및 Windows Phone용 64비트 관리되는 응용 프로그램의 편집하며 계속하기 기능을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1094">Visual Studio 2013 supports the Edit and Continue feature for 64-bit managed apps for desktop, Windows Store, and Windows Phone.</span></span> <span data-ttu-id="9bae0-1095">기존 제한은 32비트 응용 프로그램과 64비트 응용 프로그램에서 그대로 적용됩니다. [지원되는 코드 변경 내용(C#)](/visualstudio/debugger/supported-code-changes-csharp) 문서의 마지막 섹션을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1095">The existing limitations remain in effect for both 32-bit and 64-bit apps (see the last section of the [Supported Code Changes (C#)](/visualstudio/debugger/supported-code-changes-csharp) article).</span></span>

- <span data-ttu-id="9bae0-1096">비동기 인식 디버깅.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1096">Async-aware debugging.</span></span> <span data-ttu-id="9bae0-1097">Visual Studio 2013에서 비동기 응용 프로그램을 더 쉽게 디버깅하기 위해 호출 스택은 컴파일러에서 제공된 인프라 코드를 숨겨 비동기 프로그래밍을 지원하고, 논리 프로그램 실행을 보다 명확하게 반영할 수 있도록 논리 부모 프레임의 체인을 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1097">To make it easier to debug asynchronous apps in Visual Studio 2013, the call stack hides the infrastructure code provided by compilers to support asynchronous programming, and also chains in logical parent frames so you can follow logical program execution more clearly.</span></span> <span data-ttu-id="9bae0-1098">병렬 작업 창은 작업 창으로 대체되고 특정 중단점과 관련된 작업을 표시하며 응용 프로그램에서 현재 활성 상태이거나 예약된 다른 작업도 모두 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1098">A Tasks window replaces the Parallel Tasks window and displays tasks that relate to a particular breakpoint, and also displays any other tasks that are currently active or scheduled in the app.</span></span> <span data-ttu-id="9bae0-1099">이 기능에 대한 자세한 내용을 [.NET Framework 4.5.1 알림](https://devblogs.microsoft.com/dotnet/announcing-the-net-framework-4-5-1-preview/)의 "비동기 인식 디버깅" 섹션에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1099">You can read about this feature in the "Async-aware debugging" section of the [.NET Framework 4.5.1 announcement](https://devblogs.microsoft.com/dotnet/announcing-the-net-framework-4-5-1-preview/).</span></span>

- <span data-ttu-id="9bae0-1100">Windows 런타임 구성 요소에 대한 예외 지원 향상.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1100">Better exception support for Windows Runtime components.</span></span> <span data-ttu-id="9bae0-1101">Windows 8.1에서는 다른 언어 간에도 예외의 원인인 오류에 대한 정보를 Windows 스토어 응용 프로그램에서 발생시킨 예외에 보존합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1101">In Windows 8.1, exceptions that arise from Windows Store apps preserve information about the error that caused the exception, even across language boundaries.</span></span> <span data-ttu-id="9bae0-1102">이 기능에 대한 자세한 내용을 [.NET Framework 4.5.1 알림](https://devblogs.microsoft.com/dotnet/announcing-the-net-framework-4-5-1-preview/)의 "Windows 스토어 앱 개발" 섹션에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1102">You can read about this feature in the "Windows Store app development" section of the [.NET Framework 4.5.1 announcement](https://devblogs.microsoft.com/dotnet/announcing-the-net-framework-4-5-1-preview/).</span></span>

<span data-ttu-id="9bae0-1103">Visual Studio 2013부터 [관리되는 프로필 기반 최적화 도구(Mpgo.exe)](../tools/mpgo-exe-managed-profile-guided-optimization-tool.md)를 사용하여 Windows 8.x 스토어 앱과 데스크톱 앱을 최적화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1103">Starting with Visual Studio 2013, you can use the [Managed Profile Guided Optimization Tool (Mpgo.exe)](../tools/mpgo-exe-managed-profile-guided-optimization-tool.md) to optimize Windows 8.x Store apps as well as desktop apps.</span></span>

<span data-ttu-id="9bae0-1104">ASP.NET 4.5.1의 새로운 기능은 [Visual Studio 2013용 ASP.NET 및 Web Tools 릴리스 정보](/aspnet/visual-studio/overview/2013/release-notes)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1104">For new features in ASP.NET 4.5.1, see [ASP.NET and Web Tools for Visual Studio 2013 Release Notes](/aspnet/visual-studio/overview/2013/release-notes).</span></span>

<a name="v45"></a>

## <a name="whats-new-in-net-framework-45"></a><span data-ttu-id="9bae0-1105">.NET Framework 4.5의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="9bae0-1105">What's new in .NET Framework 4.5</span></span>

### <a name="base-classes"></a><span data-ttu-id="9bae0-1106">기본 클래스</span><span class="sxs-lookup"><span data-stu-id="9bae0-1106">Base classes</span></span>

- <span data-ttu-id="9bae0-1107">배포 시 .NET Framework 4 애플리케이션을 감지하고 닫아 시스템 다시 시작 횟수를 줄이는 기능.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1107">Ability to reduce system restarts by detecting and closing .NET Framework 4 applications during deployment.</span></span> <span data-ttu-id="9bae0-1108">[.NET Framework 4.5를 설치하는 동안 시스템 다시 시작 줄이기](../deployment/reducing-system-restarts.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1108">See [Reducing System Restarts During .NET Framework 4.5 Installations](../deployment/reducing-system-restarts.md).</span></span>

- <span data-ttu-id="9bae0-1109">64비트 플랫폼에서 2GB보다 큰 배열 지원.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1109">Support for arrays that are larger than 2 gigabytes (GB) on 64-bit platforms.</span></span> <span data-ttu-id="9bae0-1110">애플리케이션 구성 파일에서 이 기능을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1110">This feature can be enabled in the application configuration file.</span></span> <span data-ttu-id="9bae0-1111">개체 크기와 배열 크기에 대한 기타 제한을 나열하는 [\<gcAllowVeryLargeObjects> 요소](../configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1111">See the [\<gcAllowVeryLargeObjects> element](../configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md), which also lists other restrictions on object size and array size.</span></span>

- <span data-ttu-id="9bae0-1112">서버에 대한 백그라운드 가비지 수집을 통해 성능 향상.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1112">Better performance through background garbage collection for servers.</span></span> <span data-ttu-id="9bae0-1113">사용자가 .NET Framework 4.5에서 서버 가비지 수집을 사용하면 백그라운드 가비지 수집을 사용하도록 자동으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1113">When you use server garbage collection in .NET Framework 4.5, background garbage collection is automatically enabled.</span></span> <span data-ttu-id="9bae0-1114">[가비지 컬렉션 기본 사항](../../standard/garbage-collection/fundamentals.md) 항목의 백그라운드 서버 가비지 컬렉션 섹션을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1114">See the Background Server Garbage Collection section of the [Fundamentals of Garbage Collection](../../standard/garbage-collection/fundamentals.md) topic.</span></span>

- <span data-ttu-id="9bae0-1115">애플리케이션 성능 개선을 위해 다중 코어 프로세서에서 선택적으로 사용 가능한 백그라운드 JIT(Just-In-Time) 컴파일.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1115">Background just-in-time (JIT) compilation, which is optionally available on multi-core processors to improve application performance.</span></span> <span data-ttu-id="9bae0-1116"><xref:System.Runtime.ProfileOptimization>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1116">See <xref:System.Runtime.ProfileOptimization>.</span></span>

- <span data-ttu-id="9bae0-1117">정규식 엔진이 시간 초과되기 전에 정규식 해결을 시도하는 시간을 제한하는 기능. <xref:System.Text.RegularExpressions.Regex.MatchTimeout%2A?displayProperty=nameWithType> 속성을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1117">Ability to limit how long the regular expression engine will attempt to resolve a regular expression before it times out. See the <xref:System.Text.RegularExpressions.Regex.MatchTimeout%2A?displayProperty=nameWithType> property.</span></span>

- <span data-ttu-id="9bae0-1118">애플리케이션 도메인에 대한 기본 문화권을 정의하는 기능.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1118">Ability to define the default culture for an application domain.</span></span> <span data-ttu-id="9bae0-1119"><xref:System.Globalization.CultureInfo> 클래스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1119">See the <xref:System.Globalization.CultureInfo> class.</span></span>

- <span data-ttu-id="9bae0-1120">콘솔에서 유니코드(UTF-16) 인코딩 지원.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1120">Console support for Unicode (UTF-16) encoding.</span></span> <span data-ttu-id="9bae0-1121"><xref:System.Console> 클래스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1121">See the <xref:System.Console> class.</span></span>

- <span data-ttu-id="9bae0-1122">문화권 문자열 순서 지정 및 비교 데이터의 버전 관리 지원.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1122">Support for versioning of cultural string ordering and comparison data.</span></span> <span data-ttu-id="9bae0-1123"><xref:System.Globalization.SortVersion> 클래스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1123">See the <xref:System.Globalization.SortVersion> class.</span></span>

- <span data-ttu-id="9bae0-1124">리소스 검색 시 성능 향상.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1124">Better performance when retrieving resources.</span></span> <span data-ttu-id="9bae0-1125">[리소스 패키징 및 배포](../resources/packaging-and-deploying-resources-in-desktop-apps.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1125">See [Packaging and Deploying Resources](../resources/packaging-and-deploying-resources-in-desktop-apps.md).</span></span>

- <span data-ttu-id="9bae0-1126">압축 파일의 크기를 줄이기 위해 zip 압축 기능 개선.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1126">Zip compression improvements to reduce the size of a compressed file.</span></span> <span data-ttu-id="9bae0-1127"><xref:System.IO.Compression?displayProperty=nameWithType> 네임스페이스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1127">See the <xref:System.IO.Compression?displayProperty=nameWithType> namespace.</span></span>

- <span data-ttu-id="9bae0-1128"><xref:System.Reflection.Context.CustomReflectionContext> 클래스를 통해 기본 리플렉션 동작을 재정의하도록 리플렉션 컨텍스트를 사용자 지정하는 기능</span><span class="sxs-lookup"><span data-stu-id="9bae0-1128">Ability to customize a reflection context to override default reflection behavior through the <xref:System.Reflection.Context.CustomReflectionContext> class.</span></span>

- <span data-ttu-id="9bae0-1129">Windows 8에서 <xref:System.Globalization.IdnMapping?displayProperty=nameWithType> 클래스 사용 시 IDNA(Internationalizing Domain Names in Applications) 표준의 2008 버전 지원</span><span class="sxs-lookup"><span data-stu-id="9bae0-1129">Support for the 2008 version of the Internationalized Domain Names in Applications (IDNA) standard when the <xref:System.Globalization.IdnMapping?displayProperty=nameWithType> class is used  on Windows 8.</span></span>

- <span data-ttu-id="9bae0-1130">.NET Framework가 Windows 8에서 사용되면 유니코드 6.0을 구현하는 문자열 비교가 운영 체제에 위임됨.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1130">Delegation of string comparison to the operating system, which implements Unicode 6.0, when the .NET Framework is used on Windows 8.</span></span> <span data-ttu-id="9bae0-1131">다른 플랫폼에서 실행되는 경우 유니코드 5.x를 구현하는 자체 문자열 비교 데이터가 .NET Framework에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1131">When running on other platforms, the .NET Framework includes its own string comparison data, which implements Unicode 5.x.</span></span> <span data-ttu-id="9bae0-1132"><xref:System.String> 클래스 및 <xref:System.Globalization.SortVersion> 클래스의 설명 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1132">See the <xref:System.String> class and the Remarks section of the <xref:System.Globalization.SortVersion> class.</span></span>

- <span data-ttu-id="9bae0-1133">애플리케이션 도메인 단위로 문자열에 대한 해시 코드를 계산하는 기능.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1133">Ability to compute the hash codes for strings on a per application domain basis.</span></span> <span data-ttu-id="9bae0-1134">[\<UseRandomizedStringHashAlgorithm> 요소](../configure-apps/file-schema/runtime/userandomizedstringhashalgorithm-element.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1134">See [\<UseRandomizedStringHashAlgorithm> Element](../configure-apps/file-schema/runtime/userandomizedstringhashalgorithm-element.md).</span></span>

- <span data-ttu-id="9bae0-1135">형식 리플렉션이 <xref:System.Type> 및 <xref:System.Reflection.TypeInfo> 클래스 사이의 분할 지원.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1135">Type reflection support split between <xref:System.Type> and <xref:System.Reflection.TypeInfo> classes.</span></span> <span data-ttu-id="9bae0-1136">[Windows 스토어 앱에 대한 .NET Framework의 리플렉션](../reflection-and-codedom/reflection-for-windows-store-apps.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1136">See [Reflection in the .NET Framework for Windows Store Apps](../reflection-and-codedom/reflection-for-windows-store-apps.md).</span></span>

### <a name="managed-extensibility-framework-mef"></a><span data-ttu-id="9bae0-1137">MEF(Managed Extensibility Framework)</span><span class="sxs-lookup"><span data-stu-id="9bae0-1137">Managed Extensibility Framework (MEF)</span></span>

<span data-ttu-id="9bae0-1138">.NET Framework 4.5의 MEF(Managed Extensibility Framework)는 다음과 같은 새로운 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1138">In .NET Framework 4.5, the Managed Extensibility Framework (MEF) provides the following new features:</span></span>

- <span data-ttu-id="9bae0-1139">제네릭 형식 지원</span><span class="sxs-lookup"><span data-stu-id="9bae0-1139">Support for generic types.</span></span>

- <span data-ttu-id="9bae0-1140">특성이 아닌 명명 규칙을 기반으로 파트를 만들 수 있는 규칙 기반 프로그래밍 모델</span><span class="sxs-lookup"><span data-stu-id="9bae0-1140">Convention-based programming model that enables you to create parts based on naming conventions rather than attributes.</span></span>

- <span data-ttu-id="9bae0-1141">다중 범위</span><span class="sxs-lookup"><span data-stu-id="9bae0-1141">Multiple scopes.</span></span>

- <span data-ttu-id="9bae0-1142">Windows 8.x 스토어 앱을 만들 때 사용할 수 있는 MEF의 하위 집합.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1142">A subset of MEF that you can use when you create Windows 8.x Store apps.</span></span> <span data-ttu-id="9bae0-1143">이 하위 집합은 NuGet 갤러리에서 [다운로드 가능 패키지](https://www.nuget.org/packages/Microsoft.Composition)로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1143">This subset is available as a [downloadable package](https://www.nuget.org/packages/Microsoft.Composition) from the NuGet Gallery.</span></span> <span data-ttu-id="9bae0-1144">패키지를 설치하려면 Visual Studio에서 프로젝트를 열고 **프로젝트** 메뉴에서 **NuGet 패키지 관리** 를 선택한 후 `Microsoft.Composition` 패키지를 온라인으로 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1144">To install the package, open your project in Visual Studio, choose **Manage NuGet Packages** from the **Project** menu, and search online for the `Microsoft.Composition` package.</span></span>

<span data-ttu-id="9bae0-1145">자세한 내용은 [MEF(관리되는 확장성 프레임워크 개요)](../mef/index.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1145">For more information, see [Managed Extensibility Framework (MEF)](../mef/index.md).</span></span>

### <a name="asynchronous-file-operations"></a><span data-ttu-id="9bae0-1146">비동기 파일 작업</span><span class="sxs-lookup"><span data-stu-id="9bae0-1146">Asynchronous file operations</span></span>

<span data-ttu-id="9bae0-1147">.NET Framework 4.5에서는 C# 및 Visual Basic 언어에 새로운 비동기 기능이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1147">In .NET Framework 4.5, new asynchronous features were added to the C# and Visual Basic languages.</span></span> <span data-ttu-id="9bae0-1148">이러한 기능은 비동기 작업을 수행하는 작업 기반 모델을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1148">These features add a task-based model for performing asynchronous operations.</span></span> <span data-ttu-id="9bae0-1149">이 새로운 모델을 사용하려면 I/O 클래스에서 비동기 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1149">To use this new model, use the asynchronous methods in the I/O classes.</span></span> <span data-ttu-id="9bae0-1150">[비동기 파일 I/O](../../standard/io/asynchronous-file-i-o.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1150">See [Asynchronous File I/O](../../standard/io/asynchronous-file-i-o.md).</span></span>

<a name="tools"></a>

### <a name="tools"></a><span data-ttu-id="9bae0-1151">도구</span><span class="sxs-lookup"><span data-stu-id="9bae0-1151">Tools</span></span>

<span data-ttu-id="9bae0-1152">.NET Framework 4.5에서 리소스 파일 생성기(Resgen.exe)를 사용하면 .NET Framework 어셈블리에 포함된 .resources 파일에서 Windows 8.x 스토어 앱에 사용할 .resw 파일을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1152">In .NET Framework 4.5, Resource File Generator (Resgen.exe) enables you to create a .resw file for use in Windows 8.x Store apps from a .resources file embedded in a .NET Framework assembly.</span></span> <span data-ttu-id="9bae0-1153">자세한 내용은 [Resgen.exe(리소스 파일 생성기)](../tools/resgen-exe-resource-file-generator.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1153">For more information, see [Resgen.exe (Resource File Generator)](../tools/resgen-exe-resource-file-generator.md).</span></span>

<span data-ttu-id="9bae0-1154">관리되는 프로필 기반 최적화(Mpgo.exe)를 사용하면 네이티브 이미지 어셈블리를 최적화하여 애플리케이션 시작 시간, 메모리 사용률(작업 집합 크기) 및 처리량을 개선할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1154">Managed Profile Guided Optimization (Mpgo.exe) enables you to improve application startup time, memory utilization (working set size), and throughput by optimizing native image assemblies.</span></span> <span data-ttu-id="9bae0-1155">명령줄 도구는 네이티브 이미지 애플리케이션 어셈블리에 대한 프로필 데이터를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1155">The command-line tool generates profile data for native image application assemblies.</span></span> <span data-ttu-id="9bae0-1156">[Mpgo.exe(관리되는 프로필 기반 최적화 도구)](../tools/mpgo-exe-managed-profile-guided-optimization-tool.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1156">See [Mpgo.exe (Managed Profile Guided Optimization Tool)](../tools/mpgo-exe-managed-profile-guided-optimization-tool.md).</span></span> <span data-ttu-id="9bae0-1157">Visual Studio 2013부터 Mpgo.exe를 사용하여 Windows 8.x 스토어 앱과 데스크톱 앱을 최적화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1157">Starting with Visual Studio 2013, you can use Mpgo.exe to optimize Windows 8.x Store apps as well as desktop apps.</span></span>

<a name="parallel"></a>

### <a name="parallel-computing"></a><span data-ttu-id="9bae0-1158">병렬 컴퓨팅</span><span class="sxs-lookup"><span data-stu-id="9bae0-1158">Parallel computing</span></span>

<span data-ttu-id="9bae0-1159">.NET Framework 4.5는 병렬 컴퓨팅을 위한 몇 가지 새로운 기능과 향상된 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1159">.NET Framework 4.5 provides several new features and improvements for parallel computing.</span></span> <span data-ttu-id="9bae0-1160">여기에는 성능 향상, 제어 강화, 비동기 프로그래밍에 대한 지원 개선, 새 데이터 흐름 라이브러리 및 병렬 디버깅 및 성능 분석에 대한 지원 개선이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1160">These include improved performance, increased control, improved support for asynchronous programming, a new dataflow library, and improved support for parallel debugging and performance analysis.</span></span> <span data-ttu-id="9bae0-1161">.NET 블로그에서 병렬 프로그래밍에 대한 항목인 [.NET 4.5의 새로운 병렬 처리 기능](https://devblogs.microsoft.com/pfxteam/whats-new-for-parallelism-in-net-4-5/)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1161">See the entry [What's New for Parallelism in .NET 4.5](https://devblogs.microsoft.com/pfxteam/whats-new-for-parallelism-in-net-4-5/) in the Parallel Programming with .NET blog.</span></span>

<a name="web"></a>

### <a name="web"></a><span data-ttu-id="9bae0-1162">웹</span><span class="sxs-lookup"><span data-stu-id="9bae0-1162">Web</span></span>

<span data-ttu-id="9bae0-1163">ASP.NET 4.5 및 4.5.1은 Web Forms, WebSocket 지원, 비동기 처리기, 성능 향상 및 기타 많은 기능을 바인딩하는 모델을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1163">ASP.NET 4.5 and 4.5.1 add model binding for Web Forms, WebSocket support, asynchronous handlers, performance enhancements, and many other features.</span></span> <span data-ttu-id="9bae0-1164">자세한 내용은 다음 자료를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1164">For more information, see the following resources:</span></span>

- <span data-ttu-id="9bae0-1165">[ASP.NET 4.5 및 Visual Studio 2012](/previous-versions/aspnet/hh420390(v=vs.110))</span><span class="sxs-lookup"><span data-stu-id="9bae0-1165">[ASP.NET 4.5 and Visual Studio 2012](/previous-versions/aspnet/hh420390(v=vs.110))</span></span>

- [<span data-ttu-id="9bae0-1166">Visual Studio 2013용 ASP.NET 및 Web Tools 릴리스 정보</span><span class="sxs-lookup"><span data-stu-id="9bae0-1166">ASP.NET and Web Tools for Visual Studio 2013 Release Notes</span></span>](/aspnet/visual-studio/overview/2013/release-notes)

### <a name="networking"></a><span data-ttu-id="9bae0-1167">네트워킹 <a name="networking"></a></span><span class="sxs-lookup"><span data-stu-id="9bae0-1167">Networking <a name="networking"></a></span></span>

<span data-ttu-id="9bae0-1168">.NET Framework 4.5에서는 HTTP 애플리케이션의 새로운 프로그래밍 인터페이스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1168">.NET Framework 4.5 provides a new programming interface for HTTP applications.</span></span> <span data-ttu-id="9bae0-1169">자세한 내용은 새로운 <xref:System.Net.Http?displayProperty=nameWithType> 및 <xref:System.Net.Http.Headers?displayProperty=nameWithType> 네임스페이스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1169">For more information, see the new <xref:System.Net.Http?displayProperty=nameWithType> and <xref:System.Net.Http.Headers?displayProperty=nameWithType> namespaces.</span></span>

<span data-ttu-id="9bae0-1170">기존의 <xref:System.Net.HttpListener> 및 관련 클래스를 사용하여 WebSocket 연결을 허용하고 이와 상호 작용하는 새로운 프로그래밍 인터페이스 지원도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1170">Support is also included for a new programming interface for accepting and interacting with a WebSocket connection by using the existing <xref:System.Net.HttpListener> and related classes.</span></span> <span data-ttu-id="9bae0-1171">자세한 내용은 새로운 <xref:System.Net.WebSockets> 네임스페이스 및 <xref:System.Net.HttpListener> 클래스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1171">For more information, see the new <xref:System.Net.WebSockets> namespace and the <xref:System.Net.HttpListener> class.</span></span>

<span data-ttu-id="9bae0-1172">또한 .NET Framework 4.5에는 다음 네트워킹 개선 사항이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1172">In addition, .NET Framework 4.5 includes the following networking improvements:</span></span>

- <span data-ttu-id="9bae0-1173">RFC 규격 URI 지원.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1173">RFC-compliant URI support.</span></span> <span data-ttu-id="9bae0-1174">자세한 내용은 <xref:System.Uri> 및 관련 클래스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1174">For more information, see <xref:System.Uri> and related classes.</span></span>

- <span data-ttu-id="9bae0-1175">IDN(Internationalized Domain Name) 구문 분석 지원.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1175">Support for Internationalized Domain Name (IDN) parsing.</span></span> <span data-ttu-id="9bae0-1176">자세한 내용은 <xref:System.Uri> 및 관련 클래스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1176">For more information, see <xref:System.Uri> and related classes.</span></span>

- <span data-ttu-id="9bae0-1177">EAI(Email Address Internationalization) 지원.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1177">Support for Email Address Internationalization (EAI).</span></span> <span data-ttu-id="9bae0-1178">자세한 내용은 <xref:System.Net.Mail> 네임스페이스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1178">For more information, see the <xref:System.Net.Mail> namespace.</span></span>

- <span data-ttu-id="9bae0-1179">IPv6 지원 개선.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1179">Improved IPv6 support.</span></span> <span data-ttu-id="9bae0-1180">자세한 내용은 <xref:System.Net.NetworkInformation> 네임스페이스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1180">For more information, see the <xref:System.Net.NetworkInformation> namespace.</span></span>

- <span data-ttu-id="9bae0-1181">이중 모드 소켓 지원.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1181">Dual-mode socket support.</span></span> <span data-ttu-id="9bae0-1182">자세한 내용은 <xref:System.Net.Sockets.Socket> 및 <xref:System.Net.Sockets.TcpListener> 클래스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1182">For more information, see the <xref:System.Net.Sockets.Socket> and <xref:System.Net.Sockets.TcpListener> classes.</span></span>

<a name="client"></a>

### <a name="windows-presentation-foundation-wpf"></a><span data-ttu-id="9bae0-1183">WPF(Windows Presentation Foundation)</span><span class="sxs-lookup"><span data-stu-id="9bae0-1183">Windows Presentation Foundation (WPF)</span></span>

<span data-ttu-id="9bae0-1184">.NET Framework 4.5의 WPF(Windows Presentation Foundation)에서 변경되고 개선된 영역은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1184">In .NET Framework 4.5, Windows Presentation Foundation (WPF) contains changes and improvements in the following areas:</span></span>

- <span data-ttu-id="9bae0-1185">빠른 실행 도구 모음, 애플리케이션 메뉴 및 탭을 호스팅하는 리본 사용자 인터페이스 구현에 사용할 수 있는 새로운 <xref:System.Windows.Controls.Ribbon.Ribbon> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="9bae0-1185">The new <xref:System.Windows.Controls.Ribbon.Ribbon> control, which enables you to implement a ribbon user interface that hosts a Quick Access Toolbar, Application Menu, and tabs.</span></span>

- <span data-ttu-id="9bae0-1186">동기 및 비동기 데이터 유효성 검사를 지원하는 새로운 <xref:System.ComponentModel.INotifyDataErrorInfo> 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9bae0-1186">The new <xref:System.ComponentModel.INotifyDataErrorInfo> interface, which supports synchronous and asynchronous data validation.</span></span>

- <span data-ttu-id="9bae0-1187"><xref:System.Windows.Controls.VirtualizingPanel> 및 <xref:System.Windows.Threading.Dispatcher> 클래스의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="9bae0-1187">New features for the <xref:System.Windows.Controls.VirtualizingPanel> and <xref:System.Windows.Threading.Dispatcher> classes.</span></span>

- <span data-ttu-id="9bae0-1188">그룹화된 큰 데이터 집합을 표시하고 UI가 아닌 스레드에서 컬렉션에 액세스할 때의 성능 개선</span><span class="sxs-lookup"><span data-stu-id="9bae0-1188">Improved performance when displaying large sets of grouped data, and by accessing collections on non-UI threads.</span></span>

- <span data-ttu-id="9bae0-1189">정적 속성에 대한 데이터 바인딩, <xref:System.Reflection.ICustomTypeProvider> 인터페이스를 구현하는 사용자 지정 형식에 대한 데이터 바인딩 및 바인딩 식에서 데이터 바인딩 정보 검색</span><span class="sxs-lookup"><span data-stu-id="9bae0-1189">Data binding to static properties, data binding to custom types that implement the <xref:System.Reflection.ICustomTypeProvider> interface, and retrieval of data binding information from a binding expression.</span></span>

- <span data-ttu-id="9bae0-1190">값이 변경될 때(라이브 셰이핑) 데이터의 위치 변경</span><span class="sxs-lookup"><span data-stu-id="9bae0-1190">Repositioning of data as the values change (live shaping).</span></span>

- <span data-ttu-id="9bae0-1191">항목 컨테이너에 대한 데이터 컨텍스트 연결을 해제할지 여부를 확인하는 기능</span><span class="sxs-lookup"><span data-stu-id="9bae0-1191">Ability to check whether the data context for an item container is disconnected.</span></span>

- <span data-ttu-id="9bae0-1192">속성 변경과 데이터 소스 업데이트 간에 경과되어야 하는 시간을 설정하는 기능</span><span class="sxs-lookup"><span data-stu-id="9bae0-1192">Ability to set the amount of time that should elapse between property changes and data source updates.</span></span>

- <span data-ttu-id="9bae0-1193">취약한 이벤트 패턴을 구현하기 위한 지원 개선.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1193">Improved support for implementing weak event patterns.</span></span> <span data-ttu-id="9bae0-1194">또한 이벤트가 태그 확장을 수락할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1194">Also, events can now accept markup extensions.</span></span>

<a name="windows_communication_foundation"></a>

### <a name="windows-communication-foundation-wcf"></a><span data-ttu-id="9bae0-1195">WCF(Windows Communication Foundation)</span><span class="sxs-lookup"><span data-stu-id="9bae0-1195">Windows Communication Foundation (WCF)</span></span>

<span data-ttu-id="9bae0-1196">.NET Framework 4.5에서 WCF(Windows Communication Foundation) 애플리케이션을 더 쉽게 작성하고 유지 관리할 수 있도록 다음 기능이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1196">In .NET Framework 4.5, the following features have been added to make it simpler to write and maintain Windows Communication Foundation (WCF) applications:</span></span>

- <span data-ttu-id="9bae0-1197">생성된 구성 파일의 단순화</span><span class="sxs-lookup"><span data-stu-id="9bae0-1197">Simplification of generated configuration files.</span></span>

- <span data-ttu-id="9bae0-1198">계약 중심 개발 지원</span><span class="sxs-lookup"><span data-stu-id="9bae0-1198">Support for contract-first development.</span></span>

- <span data-ttu-id="9bae0-1199">ASP.NET 호환성 모드를 더 쉽게 구성하는 기능</span><span class="sxs-lookup"><span data-stu-id="9bae0-1199">Ability to configure ASP.NET compatibility mode more easily.</span></span>

- <span data-ttu-id="9bae0-1200">기본 전송 속성 값을 변경하여 값을 설정해야 할 가능성을 줄임</span><span class="sxs-lookup"><span data-stu-id="9bae0-1200">Changes in default transport property values to reduce the likelihood that you will have to set them.</span></span>

- <span data-ttu-id="9bae0-1201"><xref:System.Xml.XmlDictionaryReaderQuotas> 클래스를 업데이트하여 XML 사전 판독기에 대해 수동으로 할당량을 구성해야 할 가능성을 줄임</span><span class="sxs-lookup"><span data-stu-id="9bae0-1201">Updates to the <xref:System.Xml.XmlDictionaryReaderQuotas> class to reduce the likelihood that you will have to manually configure quotas for XML dictionary readers.</span></span>

- <span data-ttu-id="9bae0-1202">Visual Studio에서 빌드 프로세스의 일부로 WCF 구성 파일의 유효성 검사를 실시하여 애플리케이션 실행 전에 구성 오류를 검색할 수 있도록 함</span><span class="sxs-lookup"><span data-stu-id="9bae0-1202">Validation of WCF configuration files by Visual Studio as part of the build process, so you can detect configuration errors before you run your application.</span></span>

- <span data-ttu-id="9bae0-1203">새로운 비동기 스트리밍 지원</span><span class="sxs-lookup"><span data-stu-id="9bae0-1203">New asynchronous streaming support.</span></span>

- <span data-ttu-id="9bae0-1204">새 HTTPS 프로토콜 매핑을 사용하면 간단하게 IIS(인터넷 정보 서비스)로 HTTPS에서 엔드포인트를 표시할 수 있음</span><span class="sxs-lookup"><span data-stu-id="9bae0-1204">New HTTPS protocol mapping to make it easier to expose an endpoint over HTTPS with Internet Information Services (IIS).</span></span>

- <span data-ttu-id="9bae0-1205">서비스 URL에 `?singleWSDL`을 추가하여 단일 WSDL 문서에서 메타데이터를 생성하는 기능</span><span class="sxs-lookup"><span data-stu-id="9bae0-1205">Ability to generate metadata in a single WSDL document by appending `?singleWSDL` to the service URL.</span></span>

- <span data-ttu-id="9bae0-1206">Websocket이 포트 80 및 443에서 완벽한 양방향 통신을 지원하며 성능 특성은 TCP 전송과 유사함</span><span class="sxs-lookup"><span data-stu-id="9bae0-1206">Websockets support to enable true bidirectional communication over ports 80 and 443 with performance characteristics similar to the TCP transport.</span></span>

- <span data-ttu-id="9bae0-1207">코드에서 서비스 구성 지원</span><span class="sxs-lookup"><span data-stu-id="9bae0-1207">Support for configuring services in code.</span></span>

- <span data-ttu-id="9bae0-1208">XML 편집기 도구 설명</span><span class="sxs-lookup"><span data-stu-id="9bae0-1208">XML Editor tooltips.</span></span>

- <span data-ttu-id="9bae0-1209"><xref:System.ServiceModel.ChannelFactory> 캐싱 지원</span><span class="sxs-lookup"><span data-stu-id="9bae0-1209"><xref:System.ServiceModel.ChannelFactory> caching support.</span></span>

- <span data-ttu-id="9bae0-1210">이진 인코더 압축 지원</span><span class="sxs-lookup"><span data-stu-id="9bae0-1210">Binary encoder compression support.</span></span>

- <span data-ttu-id="9bae0-1211">개발자가 "실행 후 제거" 메시징을 사용하는 서비스를 작성할 수 있는 UDP 전송 지원.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1211">Support for a UDP transport that enables developers to write services that use "fire and forget" messaging.</span></span> <span data-ttu-id="9bae0-1212">클라이언트는 서비스에 메시지를 보내고 서비스에서 응답을 기대하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1212">A client sends a message to a service and expects no response from the service.</span></span>

- <span data-ttu-id="9bae0-1213">HTTP 전송 및 전송 보안 사용 시 단일 WCF 엔드포인트에 대한 여러 인증 모드를 지원하는 기능</span><span class="sxs-lookup"><span data-stu-id="9bae0-1213">Ability to support multiple authentication modes on a single WCF endpoint when using the HTTP transport and transport security.</span></span>

- <span data-ttu-id="9bae0-1214">IDN(Internationalized Domain Name)을 사용하는 WCF 서비스 지원</span><span class="sxs-lookup"><span data-stu-id="9bae0-1214">Support for WCF services that use internationalized domain names (IDNs).</span></span>

<span data-ttu-id="9bae0-1215">자세한 내용은 [Windows Communication Foundation의 새로운 기능](../wcf/whats-new.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1215">For more information, see [What's New in Windows Communication Foundation](../wcf/whats-new.md).</span></span>

<a name="windows_workflow_foundation"></a>

### <a name="windows-workflow-foundation-wf"></a><span data-ttu-id="9bae0-1216">Windows WF(Workflow Foundation)</span><span class="sxs-lookup"><span data-stu-id="9bae0-1216">Windows Workflow Foundation (WF)</span></span>

<span data-ttu-id="9bae0-1217">.NET Framework 4.5의 Windows WF(Windows Workflow Foundation)에 몇 가지 새로운 기능이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1217">In .NET Framework 4.5, several new features were added to Windows Workflow Foundation (WF), including:</span></span>

- <span data-ttu-id="9bae0-1218">상태 머신 워크플로가 .NET Framework 4.0.1([.NET Framework 4 플랫폼 업데이트 1](/archive/blogs/endpoint/microsoft-net-framework-4-platform-update-1))의 일부로 처음 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1218">State machine workflows, which were first introduced as part of .NET Framework 4.0.1 ([.NET Framework 4 Platform Update 1](/archive/blogs/endpoint/microsoft-net-framework-4-platform-update-1)).</span></span> <span data-ttu-id="9bae0-1219">이 업데이트에는 개발자가 상태 시스템 워크플로를 만들 수 있도록 하는 몇 가지 새로운 클래스와 활동이 포함되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1219">This update included several new classes and activities that enabled developers to create state machine workflows.</span></span> <span data-ttu-id="9bae0-1220">이러한 클래스와 활동은 다음을 포함하도록 .NET Framework 4.5에 대해 업데이트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1220">These classes and activities were updated for .NET Framework 4.5 to include:</span></span>

  - <span data-ttu-id="9bae0-1221">상태에 중단점을 설정하는 기능</span><span class="sxs-lookup"><span data-stu-id="9bae0-1221">The ability to set breakpoints on states.</span></span>

  - <span data-ttu-id="9bae0-1222">Workflow Designer에서 전환을 복사하여 붙여 넣는 기능</span><span class="sxs-lookup"><span data-stu-id="9bae0-1222">The ability to copy and paste transitions in the workflow designer.</span></span>

  - <span data-ttu-id="9bae0-1223">공유 트리거 전환 작성을 위한 디자이너 지원</span><span class="sxs-lookup"><span data-stu-id="9bae0-1223">Designer support for shared trigger transition creation.</span></span>

  - <span data-ttu-id="9bae0-1224"><xref:System.Activities.Statements.StateMachine>, <xref:System.Activities.Statements.State> 및 <xref:System.Activities.Statements.Transition>을 포함하는 상태 시스템 워크플로를 만들기 위한 활동</span><span class="sxs-lookup"><span data-stu-id="9bae0-1224">Activities for creating state machine workflows, including: <xref:System.Activities.Statements.StateMachine>, <xref:System.Activities.Statements.State>, and <xref:System.Activities.Statements.Transition>.</span></span>

- <span data-ttu-id="9bae0-1225">다음과 같은 향상된 Workflow Designer 기능</span><span class="sxs-lookup"><span data-stu-id="9bae0-1225">Enhanced Workflow Designer features such as the following:</span></span>

  - <span data-ttu-id="9bae0-1226">Visual Studio의 **빠른 찾기** 및 **파일에서 찾기** 등의 향상된 워크플로 검색 기능</span><span class="sxs-lookup"><span data-stu-id="9bae0-1226">Enhanced workflow search capabilities in Visual Studio, including **Quick Find** and **Find in Files**.</span></span>

  - <span data-ttu-id="9bae0-1227">컨테이너 활동에 두 번째 자식 활동이 추가될 때 Sequence 활동을 자동으로 생성하고 두 활동 모두를 Sequence 활동에 포함하는 기능</span><span class="sxs-lookup"><span data-stu-id="9bae0-1227">Ability to automatically create a Sequence activity when a second child activity is added to a container activity, and to include both activities in the Sequence activity.</span></span>

  - <span data-ttu-id="9bae0-1228">스크롤 막대를 사용하지 않고 워크플로의 보이는 부분을 변경할 수 있는 이동 기능 지원</span><span class="sxs-lookup"><span data-stu-id="9bae0-1228">Panning support, which enables the visible portion of a workflow to be changed without using the scroll bars.</span></span>

  - <span data-ttu-id="9bae0-1229">트리 스타일 개요 뷰에서 워크플로의 구성 요소를 보여 주는 새로운 **문서 개요** 뷰. 이 **문서 개요** 뷰에서 구성 요소를 선택할 수 있음</span><span class="sxs-lookup"><span data-stu-id="9bae0-1229">A new **Document Outline** view that shows the components of a workflow in a tree-style outline view and lets you select a component in the **Document Outline** view.</span></span>

  - <span data-ttu-id="9bae0-1230">활동에 주석을 추가하는 기능</span><span class="sxs-lookup"><span data-stu-id="9bae0-1230">Ability to add annotations to activities.</span></span>

  - <span data-ttu-id="9bae0-1231">Workflow Designer를 사용하여 활동 대리자를 정의하고 사용하는 기능</span><span class="sxs-lookup"><span data-stu-id="9bae0-1231">Ability to define and consume activity delegates by using the workflow designer.</span></span>

  - <span data-ttu-id="9bae0-1232">상태 시스템과 순서도 워크플로에서 활동 및 전환의 자동 연결 및 자동 삽입</span><span class="sxs-lookup"><span data-stu-id="9bae0-1232">Auto-connect and auto-insert for activities and transitions in state machine and flowchart workflows.</span></span>

- <span data-ttu-id="9bae0-1233">XAML 파일의 단일 요소에 워크플로의 뷰 상태 정보가 스토리지되므로 뷰 상태 정보를 쉽게 찾아 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1233">Storage of the view state information for a workflow in a single element in the XAML file, so you can easily locate and edit the view state information.</span></span>

- <span data-ttu-id="9bae0-1234">자식 활동이 지속되지 않도록 하는 NoPersistScope 컨테이너 활동</span><span class="sxs-lookup"><span data-stu-id="9bae0-1234">A NoPersistScope container activity to prevent child activities from persisting.</span></span>

- <span data-ttu-id="9bae0-1235">C# 식에 대한 지원</span><span class="sxs-lookup"><span data-stu-id="9bae0-1235">Support for C# expressions:</span></span>

  - <span data-ttu-id="9bae0-1236">Visual Basic을 사용하는 워크플로 프로젝트에서는 Visual Basic 식을 사용하고, C# 워크플로 프로젝트에서는 C# 식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1236">Workflow projects that use Visual Basic will use Visual Basic expressions, and C# workflow projects will use C# expressions.</span></span>

  - <span data-ttu-id="9bae0-1237">Visual Studio 2010에서 만들어지고 Visual Basic 식이 있는 C# 워크플로 프로젝트는 C# 식을 사용하는 C# 워크플로 프로젝트와 호환됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1237">C# workflow projects that were created in Visual Studio 2010 and that have Visual Basic expressions are compatible with C# workflow projects that use C# expressions.</span></span>

- <span data-ttu-id="9bae0-1238">버전 관리 향상</span><span class="sxs-lookup"><span data-stu-id="9bae0-1238">Versioning enhancements:</span></span>

  - <span data-ttu-id="9bae0-1239">지속되는 워크플로 인스턴스와 해당 워크플로 정의 사이에 매핑을 제공하는 새로운 <xref:System.Activities.WorkflowIdentity> 클래스</span><span class="sxs-lookup"><span data-stu-id="9bae0-1239">The new  <xref:System.Activities.WorkflowIdentity> class, which provides a mapping between a persisted workflow instance and its workflow definition.</span></span>

  - <span data-ttu-id="9bae0-1240"><xref:System.ServiceModel.Activities.WorkflowServiceHost>를 포함하여 같은 호스트에서 여러 워크플로 버전을 side-by-side로 실행</span><span class="sxs-lookup"><span data-stu-id="9bae0-1240">Side-by-side execution of multiple workflow versions in the same host, including <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span>

  - <span data-ttu-id="9bae0-1241">동적 업데이트에서 지속된 워크플로 인스턴스의 정의를 수정할 수 있는 기능</span><span class="sxs-lookup"><span data-stu-id="9bae0-1241">In Dynamic Update, the ability to modify the definition of a persisted workflow instance.</span></span>

- <span data-ttu-id="9bae0-1242">기존 서비스 계약과 일치하도록 자동 생성 활동에 대한 지원을 제공하는 계약 중심 워크플로 서비스 개발</span><span class="sxs-lookup"><span data-stu-id="9bae0-1242">Contract-first workflow service development, which provides support for automatically generating activities to match an existing service contract.</span></span>

<span data-ttu-id="9bae0-1243">자세한 내용은 [Windows Workflow Foundation의 새로운 기능](../windows-workflow-foundation/whats-new-in-wf-in-dotnet.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1243">For more information, see [What's New in Windows Workflow Foundation](../windows-workflow-foundation/whats-new-in-wf-in-dotnet.md).</span></span>

<a name="tailored"></a>

### <a name="net-for-windows-8x-store-apps"></a><span data-ttu-id="9bae0-1244">Windows 8.x 스토어 앱용 .NET</span><span class="sxs-lookup"><span data-stu-id="9bae0-1244">.NET for Windows 8.x Store apps</span></span>

<span data-ttu-id="9bae0-1245">Windows 8.x 스토어 앱은 특정 폼 팩터용으로 설계되었으며 Windows 운영 체제의 강력한 기능을 활용합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1245">Windows 8.x Store apps are designed for specific form factors and leverage the power of the Windows operating system.</span></span> <span data-ttu-id="9bae0-1246">.NET Framework 4.5 또는 4.5.1의 하위 집합은 C# 또는 Visual Basic을 사용하여 Windows용 Windows 8.x 스토어 앱을 빌드하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1246">A subset of .NET Framework 4.5 or 4.5.1 is available for building Windows 8.x Store apps for Windows by using C# or Visual Basic.</span></span> <span data-ttu-id="9bae0-1247">이 하위 집합을 Windows 8.x 스토어 앱용 .NET이라고 하며 [개요](/previous-versions/windows/apps/br230302(v=vs.140))에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1247">This subset is called .NET for Windows 8.x Store apps and is discussed in an [overview](/previous-versions/windows/apps/br230302(v=vs.140)).</span></span>

### <a name="portable-class-libraries"></a><span data-ttu-id="9bae0-1248">이식 가능한 클래스 라이브러리 <a name="portable"></a></span><span class="sxs-lookup"><span data-stu-id="9bae0-1248">Portable Class Libraries <a name="portable"></a></span></span>

<span data-ttu-id="9bae0-1249">Visual Studio 2012 및 이후 버전의 이식 가능한 클래스 라이브러리 프로젝트를 사용하여 여러 .NET Framework 플랫폼에서 작동하는 관리되는 어셈블리를 작성하고 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1249">The Portable Class Library project in Visual Studio 2012 (and later versions) enables you to write and build managed assemblies that work on multiple .NET Framework platforms.</span></span> <span data-ttu-id="9bae0-1250">이식 가능한 클래스 라이브러리 프로젝트를 사용하여 대상 플랫폼(예: Windows Phone 및 Windows 8.x 스토어 앱용 .NET)을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1250">Using a Portable Class Library project, you choose the platforms (such as Windows Phone and .NET for Windows 8.x Store apps) to target.</span></span> <span data-ttu-id="9bae0-1251">프로젝트에서 사용할 수 있는 형식 및 멤버는 이러한 플랫폼에서 공용 형식 및 멤버로 자동으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1251">The available types and members in your project are automatically restricted to the common types and members across these platforms.</span></span> <span data-ttu-id="9bae0-1252">자세한 내용은 [이식 가능한 클래스 라이브러리](../cross-platform/portable-class-library.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9bae0-1252">For more information, see [Portable Class Library](../cross-platform/portable-class-library.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9bae0-1253">참조</span><span class="sxs-lookup"><span data-stu-id="9bae0-1253">See also</span></span>

- [<span data-ttu-id="9bae0-1254">.NET Framework 및 번외 릴리스</span><span class="sxs-lookup"><span data-stu-id="9bae0-1254">The .NET Framework and Out-of-Band Releases</span></span>](../get-started/the-net-framework-and-out-of-band-releases.md)
- [<span data-ttu-id="9bae0-1255">.NET Framework에서 내게 필요한 옵션의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="9bae0-1255">What's new in accessibility in .NET Framework</span></span>](whats-new-in-accessibility.md)
- [<span data-ttu-id="9bae0-1256">Visual Studio 2019의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="9bae0-1256">What's New in Visual Studio 2019</span></span>](/visualstudio/ide/whats-new-visual-studio-2019)
- [<span data-ttu-id="9bae0-1257">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="9bae0-1257">ASP.NET</span></span>](/aspnet)
- [<span data-ttu-id="9bae0-1258">Visual Studio의 새로운 C++ 기능</span><span class="sxs-lookup"><span data-stu-id="9bae0-1258">What's New for C++ in Visual Studio</span></span>](/cpp/what-s-new-for-visual-cpp-in-visual-studio)
