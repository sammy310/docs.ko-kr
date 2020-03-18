---
title: .NET Framework의 네트워크 프로그래밍
ms.date: 03/30/2017
helpviewer_keywords:
- Networking
- Internet
- Internet, .NET Framework Internet services
- Network Resources
ms.assetid: 8d455610-67a0-4fa8-a62f-7747064a9256
ms.openlocfilehash: 1e7f0123ab07fd4e83eea957b72bf79eeeecef2b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "74204689"
---
# <a name="network-programming-in-the-net-framework"></a><span data-ttu-id="1fc2c-102">.NET Framework의 네트워크 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="1fc2c-102">Network Programming in the .NET Framework</span></span>
<span data-ttu-id="1fc2c-103">Microsoft .NET Framework는 더 빠르고 쉽게 애플리케이션에 통합할 수 있는 계층적이고 확장 가능하며 관리되는 인터넷 서비스 구현을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1fc2c-103">The Microsoft .NET Framework provides a layered, extensible, and managed implementation of Internet services that can be quickly and easily integrated into your applications.</span></span> <span data-ttu-id="1fc2c-104">네트워크 애플리케이션은 플러그 가능한 프로토콜을 바탕으로 빌드하여 새 인터넷 프로토콜을 자동으로 이용하거나, Windows 소켓 인터페이스의 관리되는 구현을 사용하여 소켓 수준에서 네트워크 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1fc2c-104">Your network applications can build on pluggable protocols to automatically take advantage of new Internet protocols, or they can use a managed implementation of the Windows socket interface to work with the network on the socket level.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1fc2c-105">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="1fc2c-105">In This Section</span></span>  

 [<span data-ttu-id="1fc2c-106">플러그형 프로토콜 소개</span><span class="sxs-lookup"><span data-stu-id="1fc2c-106">Introducing Pluggable Protocols</span></span>](introducing-pluggable-protocols.md)  
 <span data-ttu-id="1fc2c-107">필요한 액세스 프로토콜에 관계없이 인터넷 리소스에 액세스하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1fc2c-107">Describes how to access an Internet resource without regard to the access protocol that it requires.</span></span>  
  
 [<span data-ttu-id="1fc2c-108">데이터 요청</span><span class="sxs-lookup"><span data-stu-id="1fc2c-108">Requesting Data</span></span>](requesting-data.md)  
 <span data-ttu-id="1fc2c-109">플러그 가능한 프로토콜을 사용하여 인터넷 리소스에 데이터를 업로드하고 이 리소스에서 데이터를 다운로드하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1fc2c-109">Explains how to use pluggable protocols to upload and download data from Internet resources.</span></span>  
  
 [<span data-ttu-id="1fc2c-110">플러그형 프로토콜 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="1fc2c-110">Programming Pluggable Protocols</span></span>](programming-pluggable-protocols.md)  
 <span data-ttu-id="1fc2c-111">플러그 가능한 프로토콜을 구현하기 위한 프로토콜별 클래스를 파생하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1fc2c-111">Explains how to derive protocol-specific classes to implement pluggable protocols.</span></span>  
  
 [<span data-ttu-id="1fc2c-112">애플리케이션 프로토콜 사용</span><span class="sxs-lookup"><span data-stu-id="1fc2c-112">Using Application Protocols</span></span>](using-application-protocols.md)  
 <span data-ttu-id="1fc2c-113">TCP, UDP, HTTP와 같은 네트워크 프로토콜을 이용하는 프로그래밍 애플리케이션을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1fc2c-113">Describes programming applications that take advantage of network protocols such as TCP, UDP, and HTTP.</span></span>  
  
 [<span data-ttu-id="1fc2c-114">인터넷 프로토콜 버전 6</span><span class="sxs-lookup"><span data-stu-id="1fc2c-114">Internet Protocol Version 6</span></span>](internet-protocol-version-6.md)  
 <span data-ttu-id="1fc2c-115">현재 버전의 인터넷 프로토콜 모음(IPv4)에 비해 인터넷 프로토콜 버전 6(IPv6)이 지닌 장점을 설명하고, IPv6 주소 지정, 라우팅 및 자동 구성, IPv6을 사용하거나 사용하지 않는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1fc2c-115">Describes the advantages of Internet Protocol version 6 (IPv6) over the current version of the Internet Protocol suite (IPv4), describes IPv6 addressing, routing and auto-configuration, and how to enable and disable IPv6.</span></span>  
  
 [<span data-ttu-id="1fc2c-116">인터넷 애플리케이션 구성</span><span class="sxs-lookup"><span data-stu-id="1fc2c-116">Configuring Internet Applications</span></span>](configuring-internet-applications.md)  
 <span data-ttu-id="1fc2c-117">.NET Framework 구성 파일을 사용하여 인터넷 애플리케이션을 구성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1fc2c-117">Explains how to use the .NET Framework configuration files to configure Internet applications.</span></span>  
  
 [<span data-ttu-id="1fc2c-118">.NET Framework의 네트워크 추적</span><span class="sxs-lookup"><span data-stu-id="1fc2c-118">Network Tracing in the .NET Framework</span></span>](network-tracing.md)  
 <span data-ttu-id="1fc2c-119">네트워크 추적을 사용하여 메서드 호출과 관리되는 애플리케이션에서 생성되는 네트워크 트래픽에 대한 정보를 얻는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1fc2c-119">Explains how to use network tracing to get information about method invocations and network traffic generated by a managed application.</span></span>  
  
 [<span data-ttu-id="1fc2c-120">네트워크 애플리케이션에 대한 캐시 관리</span><span class="sxs-lookup"><span data-stu-id="1fc2c-120">Cache Management for Network Applications</span></span>](cache-management-for-network-applications.md)  
 <span data-ttu-id="1fc2c-121"><xref:System.Net.WebClient?displayProperty=nameWithType>, <xref:System.Net.WebRequest?displayProperty=nameWithType>및 <xref:System.Net.HttpWebRequest?displayProperty=nameWithType> 클래스를 사용하는 애플리케이션에 대한 캐싱을 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1fc2c-121">Describes how to use caching for applications that use the <xref:System.Net.WebClient?displayProperty=nameWithType>, <xref:System.Net.WebRequest?displayProperty=nameWithType>, and <xref:System.Net.HttpWebRequest?displayProperty=nameWithType> classes.</span></span>  
  
 [<span data-ttu-id="1fc2c-122">네트워크 프로그래밍의 보안</span><span class="sxs-lookup"><span data-stu-id="1fc2c-122">Security in Network Programming</span></span>](security-in-network-programming.md)  
 <span data-ttu-id="1fc2c-123">표준 인터넷 보안 및 인증 기술을 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1fc2c-123">Describes how to use standard Internet security and authentication techniques.</span></span>  
  
 [<span data-ttu-id="1fc2c-124">System.Net 클래스에 대한 모범 사례</span><span class="sxs-lookup"><span data-stu-id="1fc2c-124">Best Practices for System.Net Classes</span></span>](best-practices-for-system-net-classes.md)  
 <span data-ttu-id="1fc2c-125">인터넷 애플리케이션을 최대한 활용하기 위한 팁과 트릭을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1fc2c-125">Provides tips and tricks for getting the most out of your Internet applications.</span></span>  
  
 [<span data-ttu-id="1fc2c-126">프록시를 통해 인터넷 액세스</span><span class="sxs-lookup"><span data-stu-id="1fc2c-126">Accessing the Internet Through a Proxy</span></span>](accessing-the-internet-through-a-proxy.md)  
 <span data-ttu-id="1fc2c-127">프록시를 구성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1fc2c-127">Describes how to configure proxies.</span></span>  
  
 [<span data-ttu-id="1fc2c-128">NetworkInformation</span><span class="sxs-lookup"><span data-stu-id="1fc2c-128">NetworkInformation</span></span>](networkinformation.md)  
 <span data-ttu-id="1fc2c-129">네트워크 이벤트, 변경 사항, 통계 및 속성에 대한 정보를 수집하는 방법을 설명하고, <xref:System.Net.NetworkInformation.Ping?displayProperty=nameWithType> 클래스를 사용하여 원격 호스트에 연결할 수 있는지 확인하는 방법도 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1fc2c-129">Describes how to gather information about network events, changes, statistics, and properties and also explains how to determine whether a remote host is reachable by using the <xref:System.Net.NetworkInformation.Ping?displayProperty=nameWithType> class.</span></span>  
  
 [<span data-ttu-id="1fc2c-130">버전 2.0에서 System.Uri 네임스페이스 변경 내용</span><span class="sxs-lookup"><span data-stu-id="1fc2c-130">Changes to the System.Uri namespace in Version 2.0</span></span>](changes-to-the-system-uri-namespace-in-version-2-0.md)  
 <span data-ttu-id="1fc2c-131">잘못된 동작을 수정하고 유용성을 향상하고 보안을 강화하기 위해 버전 2.0에서 <xref:System.Uri?displayProperty=nameWithType> 클래스에 대해 이루어진 여러 가지 변경 사항을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1fc2c-131">Describes several changes made to the <xref:System.Uri?displayProperty=nameWithType> class in Version 2.0 to fixed incorrect behavior, enhance usability, and enhance security.</span></span>  
  
 [<span data-ttu-id="1fc2c-132">System.Uri의 국가별 리소스 식별자 지원</span><span class="sxs-lookup"><span data-stu-id="1fc2c-132">International Resource Identifier Support in System.Uri</span></span>](international-resource-identifier-support-in-system-uri.md)  
 <span data-ttu-id="1fc2c-133">IRI(International Resource Identifier) 및 IDN(Internationalized Domain Name) 지원을 위해 버전 3.5, 3.0 SP1 및 2.0 SP1에서 <xref:System.Uri?displayProperty=nameWithType> 클래스에 대해 강화된 기능을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1fc2c-133">Describes enhancements to the <xref:System.Uri?displayProperty=nameWithType> class in Version 3.5, 3.0 SP1, and 2.0 SP1 for International Resource Identifier (IRI) and Internationalized Domain Name (IDN) support.</span></span>  
  
 [<span data-ttu-id="1fc2c-134">버전 3.5의 소켓 성능 향상</span><span class="sxs-lookup"><span data-stu-id="1fc2c-134">Socket Performance Enhancements in Version 3.5</span></span>](socket-performance-enhancements-in-version-3-5.md)  
 <span data-ttu-id="1fc2c-135">버전 3.5, 3.0 SP1 및 2.0 SP1에서 <xref:System.Net.Sockets.Socket?displayProperty=nameWithType> 클래스에 대해 강화된 여러 가지 기능을 설명하며, 이런 기능에서는 특수화된 고성능 소켓 애플리케이션에서 사용할 수 있는 대체 비동기 패턴을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1fc2c-135">Describes a set of enhancements to the <xref:System.Net.Sockets.Socket?displayProperty=nameWithType> class in Version 3.5, 3.0 SP1, and 2.0 SP1 that provide an alternative asynchronous pattern that can be used by specialized high-performance socket applications.</span></span>  
  
 [<span data-ttu-id="1fc2c-136">피어 이름 확인 프로토콜</span><span class="sxs-lookup"><span data-stu-id="1fc2c-136">Peer Name Resolution Protocol</span></span>](peer-name-resolution-protocol.md)  
 <span data-ttu-id="1fc2c-137">버전 3.5에서 PNRP(Peer Name Resolution Protocol), 서버가 없는 동적 이름 등록 및 이름 확인 프로토콜을 지원하기 위해 추가된 지원 기능을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1fc2c-137">Describes support added in Version 3.5 to support the Peer Name Resolution Protocol (PNRP), a serverless and dynamic name registration and name resolution protocol.</span></span> <span data-ttu-id="1fc2c-138">이런 새로운 기능은 <xref:System.Net.PeerToPeer?displayProperty=nameWithType> 네임스페이스에 의해 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="1fc2c-138">These new features are supported by the <xref:System.Net.PeerToPeer?displayProperty=nameWithType> namespace.</span></span>  
  
 [<span data-ttu-id="1fc2c-139">피어 투 피어 협업</span><span class="sxs-lookup"><span data-stu-id="1fc2c-139">Peer-to-Peer Collaboration</span></span>](peer-to-peer-collaboration.md)  
 <span data-ttu-id="1fc2c-140">PNRP를 기반으로 빌드되는 피어 투 피어 협업을 지원하기 위해 버전 3.5에 추가된 지원 기능을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1fc2c-140">Describes support added in Version 3.5 to support the Peer-to-Peer Collaboration that builds on PNRP.</span></span> <span data-ttu-id="1fc2c-141">이런 새로운 기능은 <xref:System.Net.PeerToPeer.Collaboration?displayProperty=nameWithType> 네임스페이스에 의해 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="1fc2c-141">These new features are supported by the <xref:System.Net.PeerToPeer.Collaboration?displayProperty=nameWithType> namespace.</span></span>  
  
 [<span data-ttu-id="1fc2c-142">버전 3.5 SP1에서 HttpWebRequest에 대한 NTLM 인증 변경 내용</span><span class="sxs-lookup"><span data-stu-id="1fc2c-142">Changes to NTLM authentication for HttpWebRequest in Version 3.5 SP1</span></span>](changes-to-ntlm-authentication-for-httpwebrequest-in-version-3-5-sp1.md)  
 <span data-ttu-id="1fc2c-143">버전 3.5 SP1에서 <xref:System.Net.HttpWebRequest?displayProperty=nameWithType>, <xref:System.Net.HttpListener?displayProperty=nameWithType>, <xref:System.Net.Security.NegotiateStream?displayProperty=nameWithType>및 System.Net 네임스페이스의 관련 클래스에 의해 통합 Windows 인증이 처리되는 방식에 영향을 미치는 보안 변경 사항을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1fc2c-143">Describes security changes made in Version 3.5 SP1 that affect how integrated Windows authentication is handled by the <xref:System.Net.HttpWebRequest?displayProperty=nameWithType>, <xref:System.Net.HttpListener?displayProperty=nameWithType>, <xref:System.Net.Security.NegotiateStream?displayProperty=nameWithType>, and related classes in the System.Net namespace.</span></span>  
  
 [<span data-ttu-id="1fc2c-144">확장된 보호를 사용하는 Windows 통합 인증</span><span class="sxs-lookup"><span data-stu-id="1fc2c-144">Integrated Windows Authentication with Extended Protection</span></span>](integrated-windows-authentication-with-extended-protection.md)  
 <span data-ttu-id="1fc2c-145"><xref:System.Net.HttpWebRequest?displayProperty=nameWithType>, <xref:System.Net.HttpListener?displayProperty=nameWithType>, <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>, <xref:System.Net.Security.SslStream?displayProperty=nameWithType>, <xref:System.Net.Security.NegotiateStream?displayProperty=nameWithType>, 그리고 <xref:System.Net?displayProperty=nameWithType> 및 관련 네임스페이스의 관련 클래스에 의해 통합 Windows 인증이 처리되는 방식에 영향을 미치는 확장된 보호를 위해 향상된 기능을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1fc2c-145">Describes enhancements for extended protection that affect how integrated Windows authentication is handled by the <xref:System.Net.HttpWebRequest?displayProperty=nameWithType>, <xref:System.Net.HttpListener?displayProperty=nameWithType>, <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>, <xref:System.Net.Security.SslStream?displayProperty=nameWithType>, <xref:System.Net.Security.NegotiateStream?displayProperty=nameWithType>, and related classes in the <xref:System.Net?displayProperty=nameWithType> and related namespaces.</span></span>  
  
 [<span data-ttu-id="1fc2c-146">IPv6 및 Teredo를 사용하는 NAT 통과</span><span class="sxs-lookup"><span data-stu-id="1fc2c-146">NAT Traversal using IPv6 and Teredo</span></span>](nat-traversal-using-ipv6-and-teredo.md)  
 <span data-ttu-id="1fc2c-147">IPv6 및 Teredo를 사용하여 NAT 통과를 지원하기 위해 <xref:System.Net?displayProperty=nameWithType>, <xref:System.Net.NetworkInformation?displayProperty=nameWithType>및 <xref:System.Net.Sockets?displayProperty=nameWithType> 네임스페이스에 추가된 향상된 기능을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1fc2c-147">Describes enhancements added to the <xref:System.Net?displayProperty=nameWithType>, <xref:System.Net.NetworkInformation?displayProperty=nameWithType>, and <xref:System.Net.Sockets?displayProperty=nameWithType> namespaces to support NAT traversal using IPv6 and Teredo.</span></span>  
  
 [<span data-ttu-id="1fc2c-148">Windows 스토어 앱에 대한 네트워크 격리</span><span class="sxs-lookup"><span data-stu-id="1fc2c-148">Network Isolation for Windows Store Apps</span></span>](network-isolation-for-windows-store-apps.md)  
 <span data-ttu-id="1fc2c-149"><xref:System.Net>, <xref:System.Net.Http> 및 <xref:System.Net.Http.Headers> 네임스페이스의 클래스가 Windows 8.x 스토어 앱에서 사용될 때 네트워크 격리가 미치는 영향을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1fc2c-149">Describes the impact of network isolation when classes in the <xref:System.Net>, <xref:System.Net.Http>, and <xref:System.Net.Http.Headers> namespaces are used in Windows 8.x Store apps.</span></span>  
  
 [<span data-ttu-id="1fc2c-150">네트워크 프로그래밍 샘플</span><span class="sxs-lookup"><span data-stu-id="1fc2c-150">Network Programming Samples</span></span>](network-programming-samples.md)  
 <span data-ttu-id="1fc2c-151"><xref:System.Net>, <xref:System.Net.Cache>, <xref:System.Net.Configuration>, <xref:System.Net.Mail>, <xref:System.Net.Mime>, <xref:System.Net.NetworkInformation>, <xref:System.Net.PeerToPeer>, <xref:System.Net.Security>, <xref:System.Net.Sockets> 네임스페이스의 클래스를 사용하는 다운로드 가능한 네트워크 프로그래밍 샘플에 대한 링크입니다.</span><span class="sxs-lookup"><span data-stu-id="1fc2c-151">Links to downloadable network programming samples that use classes in the <xref:System.Net>, <xref:System.Net.Cache>, <xref:System.Net.Configuration>, <xref:System.Net.Mail>, <xref:System.Net.Mime>, <xref:System.Net.NetworkInformation>, <xref:System.Net.PeerToPeer>, <xref:System.Net.Security>, <xref:System.Net.Sockets> namespaces.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="1fc2c-152">참조</span><span class="sxs-lookup"><span data-stu-id="1fc2c-152">Reference</span></span>  
 <xref:System.Net?displayProperty=nameWithType>  
 <span data-ttu-id="1fc2c-153">오늘날 네트워크에 사용되는 여러 프로토콜을 위한 간단한 프로그래밍 인터페이스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1fc2c-153">Provides a simple programming interface for many of the protocols used on networks today.</span></span> <span data-ttu-id="1fc2c-154">이 네임스페이스의 <xref:System.Net.WebRequest?displayProperty=nameWithType> 및 <xref:System.Net.WebResponse?displayProperty=nameWithType> 클래스는 플러그 가능한 프로토콜을 위한 기초입니다.</span><span class="sxs-lookup"><span data-stu-id="1fc2c-154">The <xref:System.Net.WebRequest?displayProperty=nameWithType> and <xref:System.Net.WebResponse?displayProperty=nameWithType> classes in this namespace are the basis for pluggable protocols.</span></span>  
  
 <xref:System.Net.Cache?displayProperty=nameWithType>  
 <span data-ttu-id="1fc2c-155"><xref:System.Net.WebRequest?displayProperty=nameWithType> 및 <xref:System.Net.HttpWebRequest?displayProperty=nameWithType> 클래스를 사용하여 얻은 리소스에 대한 캐시 정책을 정의하는 데 사용되는 형식과 열거형을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1fc2c-155">Defines the types and enumerations used to define cache policies for resources obtained using the <xref:System.Net.WebRequest?displayProperty=nameWithType> and <xref:System.Net.HttpWebRequest?displayProperty=nameWithType> classes.</span></span>  
  
 <xref:System.Net.Configuration?displayProperty=nameWithType>  
 <span data-ttu-id="1fc2c-156">애플리케이션에서 System.Net 네임스페이스에 대한 구성 설정을 프로그래밍 방식으로 액세스 및 업데이트하는 데 사용하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="1fc2c-156">Classes that applications use to programmatically access and update configuration settings for the System.Net namespaces.</span></span>  
  
 <xref:System.Net.Http?displayProperty=nameWithType>  
 <span data-ttu-id="1fc2c-157">최신 HTTP 애플리케이션의 프로그래밍 인터페이스를 제공하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="1fc2c-157">Classes that provides a programming interface for modern HTTP applications.</span></span>  
  
 <xref:System.Net.Http.Headers?displayProperty=nameWithType>  
 <span data-ttu-id="1fc2c-158"><xref:System.Net.Http?displayProperty=nameWithType> 네임스페이스에서 사용되는 HTTP 헤더의 컬렉션 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1fc2c-158">Provides support for collections of HTTP headers used by the <xref:System.Net.Http?displayProperty=nameWithType> namespace</span></span>  
  
 <xref:System.Net.Mail?displayProperty=nameWithType>  
 <span data-ttu-id="1fc2c-159">SMTP 프로토콜을 사용하여 메일을 작성하고 보내기 위한 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="1fc2c-159">Classes to compose and send mail using the SMTP protocol.</span></span>  
  
 <xref:System.Net.Mime?displayProperty=nameWithType>  
 <span data-ttu-id="1fc2c-160"><xref:System.Net.Mail?displayProperty=nameWithType> 네임스페이스의 클래스에 사용되는 MIME(Multipurpose Internet Mail Exchange) 헤더를 나타내는 데 사용되는 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1fc2c-160">Defines types that are used to represent Multipurpose Internet Mail Exchange (MIME) headers used by classes in the <xref:System.Net.Mail?displayProperty=nameWithType> namespace.</span></span>  
  
 <xref:System.Net.NetworkInformation?displayProperty=nameWithType>  
 <span data-ttu-id="1fc2c-161">네트워크 이벤트, 변경 사항, 통계 및 속성에 대한 정보를 프로그래밍 방식으로 수집하기 위한 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="1fc2c-161">Classes to programmatically gather information about network events, changes, statistics, and properties.</span></span>  
  
 <xref:System.Net.PeerToPeer?displayProperty=nameWithType>  
 <span data-ttu-id="1fc2c-162">개발자를 위한 PNRP(피어 이름 확인 프로토콜)의 관리되는 구현을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1fc2c-162">Provides a managed implementation of the Peer Name Resolution Protocol (PNRP) for developers.</span></span>  
  
 <xref:System.Net.PeerToPeer.Collaboration?displayProperty=nameWithType>  
 <span data-ttu-id="1fc2c-163">개발자를 위한 피어-투-피어 협업 인터페이스의 관리되는 구현을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1fc2c-163">Provides a managed implementation of the Peer-to-Peer Collaboration interface for developers.</span></span>  
  
 <xref:System.Net.Security?displayProperty=nameWithType>  
 <span data-ttu-id="1fc2c-164">호스트 간의 보안 통신을 위한 네트워크 스트림을 제공하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="1fc2c-164">Classes to provide network streams for secure communications between hosts.</span></span>  
  
 <xref:System.Net.Sockets?displayProperty=nameWithType>  
 <span data-ttu-id="1fc2c-165">네트워크 액세스를 제어해야 하는 개발자를 위한 Winsock(Windows 소켓) 인터페이스에 대해 관리되는 구현을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1fc2c-165">Provides a managed implementation of the Windows Sockets (Winsock) interface for developers who need to help control access to the network.</span></span>  
  
 <xref:System.Net.WebSockets?displayProperty=nameWithType>  
 <span data-ttu-id="1fc2c-166">개발자를 위한 WebSocket 인터페이스에 대해 관리되는 구현을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1fc2c-166">Provides a managed implementation of the WebSocket interface for developers.</span></span>  
  
 <xref:System.Uri?displayProperty=nameWithType>  
 <span data-ttu-id="1fc2c-167">URI(Uniform Resource Indentifier)의 개체 표현을 제공하며 URI 부분에 쉽게 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1fc2c-167">Provides an object representation of a uniform resource identifier (URI) and easy access to the parts of the URI.</span></span>  
  
 <xref:System.Security.Authentication.ExtendedProtection?displayProperty=nameWithType>  
 <span data-ttu-id="1fc2c-168">애플리케이션의 확장된 보호를 사용하여 인증을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="1fc2c-168">Provides support for authentication using extended protection for applications.</span></span>  
  
 <xref:System.Security.Authentication.ExtendedProtection.Configuration?displayProperty=nameWithType>  
 <span data-ttu-id="1fc2c-169">애플리케이션의 확장된 보호를 사용하여 인증 구성을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="1fc2c-169">Provides support for configuration of authentication using extended protection for applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fc2c-170">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1fc2c-170">See also</span></span>

- [<span data-ttu-id="1fc2c-171">.NET Framework를 사용한 TLS(전송 계층 보안) 모범 사례</span><span class="sxs-lookup"><span data-stu-id="1fc2c-171">Transport Layer Security (TLS) best practices with .NET Framework</span></span>](tls.md)
- [<span data-ttu-id="1fc2c-172">네트워크 프로그래밍 방법 항목</span><span class="sxs-lookup"><span data-stu-id="1fc2c-172">Network Programming How-to Topics</span></span>](network-programming-how-to-topics.md)
- [<span data-ttu-id="1fc2c-173">네트워크 프로그래밍 샘플</span><span class="sxs-lookup"><span data-stu-id="1fc2c-173">Network Programming Samples</span></span>](network-programming-samples.md)
- [<span data-ttu-id="1fc2c-174">HttpClient 샘플</span><span class="sxs-lookup"><span data-stu-id="1fc2c-174">HttpClient Sample</span></span>](https://code.msdn.microsoft.com/windowsapps/HttpClient-sample-55700664)
