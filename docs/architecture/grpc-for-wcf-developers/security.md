---
title: GRPC 응용 프로그램의 보안-WCF 개발자를 위한 gRPC
description: GRPC의 호출 및 채널 인증 및 권한 부여에 대 한 개요입니다.
ms.date: 09/02/2019
ms.openlocfilehash: d5804ad5de4a834eb81b90fa1ea7a61969a0b42f
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503413"
---
# <a name="security-in-grpc-applications"></a><span data-ttu-id="f8a0a-103">gRPC 애플리케이션의 보안</span><span class="sxs-lookup"><span data-stu-id="f8a0a-103">Security in gRPC applications</span></span>

<span data-ttu-id="f8a0a-104">모든 실제 시나리오에서는 응용 프로그램 및 서비스를 보호 하는 것이 필수적입니다.</span><span class="sxs-lookup"><span data-stu-id="f8a0a-104">In any real-world scenario, securing applications and services is essential.</span></span> <span data-ttu-id="f8a0a-105">보안은 다음과 같은 세 가지 주요 영역을 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="f8a0a-105">Security covers three key areas:</span></span> 

* <span data-ttu-id="f8a0a-106">악의적인 해커가 가로채기를 방지 하기 위해 네트워크 트래픽을 암호화 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8a0a-106">Encrypting network traffic to prevent malicious hackers from intercepting it.</span></span>
* <span data-ttu-id="f8a0a-107">클라이언트 및 서버를 인증 하 여 id 및 신뢰를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8a0a-107">Authenticating clients and servers to establish identity and trust.</span></span>
* <span data-ttu-id="f8a0a-108">클라이언트에 게 시스템에 대 한 액세스를 제어 하 고 id를 기준으로 권한을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8a0a-108">Authorizing clients to control access to systems and apply permissions based on identity.</span></span>

> [!NOTE]
> <span data-ttu-id="f8a0a-109">*인증은* 클라이언트 또는 서버의 id를 설정 하는 것과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8a0a-109">*Authentication* is concerned with establishing the identity of a client or server.</span></span> <span data-ttu-id="f8a0a-110">*권한 부여* 는 클라이언트에 리소스에 대 한 액세스 권한이 있는지 여부를 확인 하거나 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8a0a-110">*Authorization* is concerned with determining whether a client has permission to access a resource or issue a command.</span></span>

<span data-ttu-id="f8a0a-111">이 장에서는 ASP.NET Core에 대 한 gRPC의 인증 및 권한 부여에 대 한 기능을 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="f8a0a-111">This chapter will cover the facilities for authentication and authorization in gRPC for ASP.NET Core.</span></span> <span data-ttu-id="f8a0a-112">TLS 암호화 된 연결을 통해 네트워크 보안에 대해서도 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8a0a-112">It will also discuss network security through TLS encrypted connections.</span></span>

## <a name="wcf-authentication-and-authorization"></a><span data-ttu-id="f8a0a-113">WCF 인증 및 권한 부여</span><span class="sxs-lookup"><span data-stu-id="f8a0a-113">WCF authentication and authorization</span></span>

<span data-ttu-id="f8a0a-114">WCF (Windows Communication Foundation)에서 인증 및 권한 부여는 사용 되는 전송 및 바인딩에 따라 서로 다른 방식으로 처리 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f8a0a-114">In Windows Communication Foundation (WCF), authentication and authorization were handled in different ways, depending on the transports and bindings being used.</span></span> <span data-ttu-id="f8a0a-115">WCF는 다양 한 WS\* 보안 표준을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8a0a-115">WCF supported various WS-\* security standards.</span></span> <span data-ttu-id="f8a0a-116">또한 Windows 시스템 간에 IIS 또는 NetTCP 서비스에서 실행 되는 HTTP 서비스에 대 한 Windows 인증이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8a0a-116">It also supported Windows authentication for HTTP services running in IIS or NetTCP services between Windows systems.</span></span>

## <a name="grpc-authentication-and-authorization"></a><span data-ttu-id="f8a0a-117">gRPC 인증 및 권한 부여</span><span class="sxs-lookup"><span data-stu-id="f8a0a-117">gRPC authentication and authorization</span></span>

<span data-ttu-id="f8a0a-118">gRPC 인증 및 권한 부여는 두 가지 수준에서 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8a0a-118">gRPC authentication and authorization works on two levels:</span></span>

* <span data-ttu-id="f8a0a-119">호출 수준 인증/권한 부여는 일반적으로 호출이 수행 될 때 메타 데이터에 적용 되는 토큰을 통해 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8a0a-119">Call-level authentication/authorization is usually handled through tokens that are applied in metadata when the call is made.</span></span> 
* <span data-ttu-id="f8a0a-120">채널 수준 인증은 연결 수준에서 적용 되는 클라이언트 인증서를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8a0a-120">Channel-level authentication uses a client certificate that's applied at the connection level.</span></span> <span data-ttu-id="f8a0a-121">채널의 모든 호출에 자동으로 적용 되는 호출 수준 인증/권한 부여 자격 증명을 포함할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8a0a-121">It can also include call-level authentication/authorization credentials to be applied to every call on the channel automatically.</span></span> 

<span data-ttu-id="f8a0a-122">이러한 메커니즘 중 하나 또는 둘 모두를 사용 하 여 서비스의 보안을 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8a0a-122">You can use either or both of these mechanisms to help secure your service.</span></span>

<span data-ttu-id="f8a0a-123">GRPC의 ASP.NET Core 구현은 대부분의 표준 ASP.NET Core 메커니즘을 통한 인증 및 권한 부여를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8a0a-123">The ASP.NET Core implementation of gRPC supports authentication and authorization through most of the standard ASP.NET Core mechanisms:</span></span>

- <span data-ttu-id="f8a0a-124">인증 호출</span><span class="sxs-lookup"><span data-stu-id="f8a0a-124">Call authentication</span></span>
  - <span data-ttu-id="f8a0a-125">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="f8a0a-125">Azure Active Directory</span></span>
  - <span data-ttu-id="f8a0a-126">IdentityServer</span><span class="sxs-lookup"><span data-stu-id="f8a0a-126">IdentityServer</span></span>
  - <span data-ttu-id="f8a0a-127">JWT 전달자 토큰</span><span class="sxs-lookup"><span data-stu-id="f8a0a-127">JWT Bearer Token</span></span>
  - <span data-ttu-id="f8a0a-128">OAuth 2.0</span><span class="sxs-lookup"><span data-stu-id="f8a0a-128">OAuth 2.0</span></span>
  - <span data-ttu-id="f8a0a-129">OpenID Connect</span><span class="sxs-lookup"><span data-stu-id="f8a0a-129">OpenID Connect</span></span>
  - <span data-ttu-id="f8a0a-130">WS-Federation</span><span class="sxs-lookup"><span data-stu-id="f8a0a-130">WS-Federation</span></span>
- <span data-ttu-id="f8a0a-131">채널 인증</span><span class="sxs-lookup"><span data-stu-id="f8a0a-131">Channel authentication</span></span>
  - <span data-ttu-id="f8a0a-132">클라이언트 인증서</span><span class="sxs-lookup"><span data-stu-id="f8a0a-132">Client certificate</span></span>

<span data-ttu-id="f8a0a-133">호출 인증 방법은 모두 *토큰*을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8a0a-133">The call authentication methods are all based on *tokens*.</span></span> <span data-ttu-id="f8a0a-134">유일한 차이점은 토큰을 생성 하는 방법과 ASP.NET Core 서비스에서 토큰의 유효성을 검사 하는 데 사용 되는 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="f8a0a-134">The only real difference is how the tokens are generated and the libraries that are used to validate the tokens in the ASP.NET Core service.</span></span>

<span data-ttu-id="f8a0a-135">자세한 내용은 [인증 및 권한 부여](/aspnet/core/grpc/authn-and-authz) 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f8a0a-135">For more information, see the [Authentication and authorization](/aspnet/core/grpc/authn-and-authz) article.</span></span>

> [!NOTE]
> <span data-ttu-id="f8a0a-136">TLS로 암호화 된 HTTP/2 연결에서 gRPC를 사용 하는 경우 채널 수준 인증을 사용 하지 않는 경우에도 클라이언트와 서버 간의 모든 트래픽이 암호화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8a0a-136">When you're using gRPC over a TLS-encrypted HTTP/2 connection, all traffic between clients and servers is encrypted, even if you don't use channel-level authentication.</span></span>

<span data-ttu-id="f8a0a-137">이 장에서는 gRPC 서비스에 통화 자격 증명과 채널 자격 증명을 적용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f8a0a-137">This chapter will show how to apply call credentials and channel credentials to a gRPC service.</span></span> <span data-ttu-id="f8a0a-138">또한 .NET Core gRPC 클라이언트의 자격 증명을 사용 하 여 서비스를 인증 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f8a0a-138">It will also show how to use credentials from a .NET Core gRPC client to authenticate with the service.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="f8a0a-139">[이전](client-libraries.md)
>[다음](call-credentials.md)</span><span class="sxs-lookup"><span data-stu-id="f8a0a-139">[Previous](client-libraries.md)
[Next](call-credentials.md)</span></span>
