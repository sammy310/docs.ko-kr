---
title: GRPC 응용 프로그램의 보안 - WCF 개발자를 위한 gRPC
description: gRPC의 통화 및 채널 인증 및 권한 부여 개요.
ms.date: 09/02/2019
ms.openlocfilehash: 70cbf441bbc1b299b997f7d1f02bcd2bf7fde60c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147817"
---
# <a name="security-in-grpc-applications"></a><span data-ttu-id="13257-103">gRPC 애플리케이션의 보안</span><span class="sxs-lookup"><span data-stu-id="13257-103">Security in gRPC applications</span></span>

<span data-ttu-id="13257-104">모든 실제 시나리오에서 응용 프로그램 및 서비스를 보호하는 것은 필수적입니다.</span><span class="sxs-lookup"><span data-stu-id="13257-104">In any real-world scenario, securing applications and services is essential.</span></span> <span data-ttu-id="13257-105">보안은 세 가지 주요 영역을 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="13257-105">Security covers three key areas:</span></span>

* <span data-ttu-id="13257-106">악의적인 해커가 네트워크 트래픽을 가로채는 것을 방지하기 위해 네트워크 트래픽을 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="13257-106">Encrypting network traffic to prevent malicious hackers from intercepting it.</span></span>
* <span data-ttu-id="13257-107">ID와 신뢰를 구축하기 위해 클라이언트와 서버를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="13257-107">Authenticating clients and servers to establish identity and trust.</span></span>
* <span data-ttu-id="13257-108">클라이언트가 시스템에 대한 액세스를 제어하고 ID를 기반으로 권한을 적용할 수 있도록 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="13257-108">Authorizing clients to control access to systems and apply permissions based on identity.</span></span>

> [!NOTE]
> <span data-ttu-id="13257-109">*인증은* 클라이언트 또는 서버의 ID를 설정하는 데 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="13257-109">*Authentication* is concerned with establishing the identity of a client or server.</span></span> <span data-ttu-id="13257-110">*권한 부여는* 클라이언트가 리소스에 액세스하거나 명령을 발급할 수 있는 권한이 있는지 여부를 결정하는 데 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="13257-110">*Authorization* is concerned with determining whether a client has permission to access a resource or issue a command.</span></span>

<span data-ttu-id="13257-111">이 장에서는 ASP.NET 코어에 대한 gRPC의 인증 및 권한 부여 기능을 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="13257-111">This chapter will cover the facilities for authentication and authorization in gRPC for ASP.NET Core.</span></span> <span data-ttu-id="13257-112">또한 TLS 암호화 된 연결을 통해 네트워크 보안에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="13257-112">It will also discuss network security through TLS encrypted connections.</span></span>

## <a name="wcf-authentication-and-authorization"></a><span data-ttu-id="13257-113">WCF 인증 및 권한 부여</span><span class="sxs-lookup"><span data-stu-id="13257-113">WCF authentication and authorization</span></span>

<span data-ttu-id="13257-114">WCF(Windows 통신 재단)에서는 사용 중인 전송 및 바인딩에 따라 인증 및 권한 부여가 여러 가지 방식으로 처리되었습니다.</span><span class="sxs-lookup"><span data-stu-id="13257-114">In Windows Communication Foundation (WCF), authentication and authorization were handled in different ways, depending on the transports and bindings being used.</span></span> <span data-ttu-id="13257-115">WCF는 다양한\* WS-보안 표준을 지원했습니다.</span><span class="sxs-lookup"><span data-stu-id="13257-115">WCF supported various WS-\* security standards.</span></span> <span data-ttu-id="13257-116">또한 Windows 시스템 간에 IIS 또는 NetTCP 서비스에서 실행되는 HTTP 서비스에 대한 Windows 인증을 지원했습니다.</span><span class="sxs-lookup"><span data-stu-id="13257-116">It also supported Windows authentication for HTTP services running in IIS or NetTCP services between Windows systems.</span></span>

## <a name="grpc-authentication-and-authorization"></a><span data-ttu-id="13257-117">gRPC 인증 및 권한 부여</span><span class="sxs-lookup"><span data-stu-id="13257-117">gRPC authentication and authorization</span></span>

<span data-ttu-id="13257-118">gRPC 인증 및 권한 부여는 다음 두 가지 수준에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="13257-118">gRPC authentication and authorization works on two levels:</span></span>

* <span data-ttu-id="13257-119">통화 수준 인증/권한 부여는 일반적으로 호출이 이루어질 때 메타데이터에 적용되는 토큰을 통해 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="13257-119">Call-level authentication/authorization is usually handled through tokens that are applied in metadata when the call is made.</span></span>
* <span data-ttu-id="13257-120">채널 수준 인증은 연결 수준에서 적용되는 클라이언트 인증서를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="13257-120">Channel-level authentication uses a client certificate that's applied at the connection level.</span></span> <span data-ttu-id="13257-121">또한 채널의 모든 통화에 자동으로 적용할 호출 수준 인증/권한 부여 자격 증명을 포함할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13257-121">It can also include call-level authentication/authorization credentials to be applied to every call on the channel automatically.</span></span>

<span data-ttu-id="13257-122">이러한 메커니즘 중 하나 또는 둘 다를 사용하여 서비스를 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13257-122">You can use either or both of these mechanisms to help secure your service.</span></span>

<span data-ttu-id="13257-123">gRPC의 ASP.NET 코어 구현은 대부분의 표준 ASP.NET 핵심 메커니즘을 통해 인증 및 권한 부여를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="13257-123">The ASP.NET Core implementation of gRPC supports authentication and authorization through most of the standard ASP.NET Core mechanisms:</span></span>

- <span data-ttu-id="13257-124">통화 인증</span><span class="sxs-lookup"><span data-stu-id="13257-124">Call authentication</span></span>
  - <span data-ttu-id="13257-125">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="13257-125">Azure Active Directory</span></span>
  - <span data-ttu-id="13257-126">아이덴티티 서버</span><span class="sxs-lookup"><span data-stu-id="13257-126">IdentityServer</span></span>
  - <span data-ttu-id="13257-127">JWT 베어러 토큰</span><span class="sxs-lookup"><span data-stu-id="13257-127">JWT Bearer Token</span></span>
  - <span data-ttu-id="13257-128">OAuth 2.0</span><span class="sxs-lookup"><span data-stu-id="13257-128">OAuth 2.0</span></span>
  - <span data-ttu-id="13257-129">OpenID Connect</span><span class="sxs-lookup"><span data-stu-id="13257-129">OpenID Connect</span></span>
  - <span data-ttu-id="13257-130">WS-Federation</span><span class="sxs-lookup"><span data-stu-id="13257-130">WS-Federation</span></span>
- <span data-ttu-id="13257-131">채널 인증</span><span class="sxs-lookup"><span data-stu-id="13257-131">Channel authentication</span></span>
  - <span data-ttu-id="13257-132">클라이언트 인증서</span><span class="sxs-lookup"><span data-stu-id="13257-132">Client certificate</span></span>

<span data-ttu-id="13257-133">호출 인증 메서드는 모두 토큰을 기반으로 *합니다.*</span><span class="sxs-lookup"><span data-stu-id="13257-133">The call authentication methods are all based on *tokens*.</span></span> <span data-ttu-id="13257-134">유일한 차이점은 토큰이 생성되는 방법과 ASP.NET Core 서비스에서 토큰의 유효성을 검사하는 데 사용되는 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="13257-134">The only real difference is how the tokens are generated and the libraries that are used to validate the tokens in the ASP.NET Core service.</span></span>

<span data-ttu-id="13257-135">자세한 내용은 인증 [및 권한 부여](/aspnet/core/grpc/authn-and-authz) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="13257-135">For more information, see the [Authentication and authorization](/aspnet/core/grpc/authn-and-authz) article.</span></span>

> [!NOTE]
> <span data-ttu-id="13257-136">TLS 암호화 된 HTTP/2 연결을 통해 gRPC를 사용하는 경우 채널 수준 인증을 사용하지 않더라도 클라이언트와 서버 간의 모든 트래픽이 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="13257-136">When you're using gRPC over a TLS-encrypted HTTP/2 connection, all traffic between clients and servers is encrypted, even if you don't use channel-level authentication.</span></span>

<span data-ttu-id="13257-137">이 장에서는 gRPC 서비스에 통화 자격 증명 및 채널 자격 증명을 적용하는 방법을 보여 줄 것입니다.</span><span class="sxs-lookup"><span data-stu-id="13257-137">This chapter will show how to apply call credentials and channel credentials to a gRPC service.</span></span> <span data-ttu-id="13257-138">또한 .NET Core gRPC 클라이언트의 자격 증명을 사용하여 서비스를 인증하는 방법도 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="13257-138">It will also show how to use credentials from a .NET Core gRPC client to authenticate with the service.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="13257-139">[이전](client-libraries.md)
>[다음](call-credentials.md)</span><span class="sxs-lookup"><span data-stu-id="13257-139">[Previous](client-libraries.md)
[Next](call-credentials.md)</span></span>
