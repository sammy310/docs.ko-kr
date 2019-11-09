---
title: GRPC 응용 프로그램의 보안-WCF 개발자를 위한 gRPC
description: GRPC의 호출 및 채널 인증 및 권한 부여에 대 한 개요입니다.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: d0b7ff5bef755c5eeb9b3c419dcda1cb75ac4031
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841374"
---
# <a name="security-in-grpc-applications"></a><span data-ttu-id="f03a3-103">gRPC 애플리케이션의 보안</span><span class="sxs-lookup"><span data-stu-id="f03a3-103">Security in gRPC applications</span></span>

<span data-ttu-id="f03a3-104">모든 실제 시나리오에서는 응용 프로그램 및 서비스를 보호 하는 것이 필수적입니다.</span><span class="sxs-lookup"><span data-stu-id="f03a3-104">In any real-world scenario, securing applications and services is essential.</span></span> <span data-ttu-id="f03a3-105">보안은 잘못 된 행위자가 가로챌 수 없도록 네트워크 트래픽 암호화의 세 가지 주요 영역을 다룹니다. 클라이언트 및 서버를 인증 하 여 id 및 트러스트 설정 클라이언트에서 시스템에 대 한 액세스를 제어 하 고 id를 기준으로 권한을 적용 하도록 권한을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="f03a3-105">Security covers three key areas: encrypting network traffic to prevent it from being intercepted by bad actors; authenticating clients and servers to establish identity and trust; and authorizing clients to control access to systems and apply permissions based on identity.</span></span>

> [!NOTE]
> <span data-ttu-id="f03a3-106">**인증은** 클라이언트 또는 서버의 id를 설정 하는 것과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f03a3-106">**Authentication** is concerned with establishing the identity of a client or server.</span></span> <span data-ttu-id="f03a3-107">**권한 부여** 는 클라이언트에 리소스에 대 한 액세스 권한이 있는지 여부를 확인 하거나 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f03a3-107">**Authorization** is concerned with determining whether a client has permission to access a resource or issue a command.</span></span>

<span data-ttu-id="f03a3-108">이 장에서는 ASP.NET Core에 대 한 gRPC의 인증 및 권한 부여 기능에 대해 설명 하 고 TLS 암호화 연결을 사용 하 여 네트워크 보안에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f03a3-108">This chapter will cover the facilities for authentication and authorization in gRPC for ASP.NET Core, and discuss network security using TLS encrypted connections.</span></span>

## <a name="wcf-authentication-and-authorization"></a><span data-ttu-id="f03a3-109">WCF 인증 및 권한 부여</span><span class="sxs-lookup"><span data-stu-id="f03a3-109">WCF authentication and authorization</span></span>

<span data-ttu-id="f03a3-110">WCF에서 인증 및 권한 부여는 사용 되는 전송 및 바인딩에 따라 서로 다른 방식으로 처리 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f03a3-110">In WCF, authentication and authorization were handled in different ways depending on the transports and bindings being used.</span></span> <span data-ttu-id="f03a3-111">WCF는 IIS에서 실행 되는 HTTP 서비스에 대 한 Windows 인증 및 Windows 시스템 간에 다양 한 WS\* 보안 표준 및 Windows 인증을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="f03a3-111">WCF supported various WS-\* security standards, as well as Windows authentication for HTTP services running in IIS or NetTCP services between Windows systems.</span></span>

## <a name="grpc-authentication-and-authorization"></a><span data-ttu-id="f03a3-112">gRPC 인증 및 권한 부여</span><span class="sxs-lookup"><span data-stu-id="f03a3-112">gRPC authentication and authorization</span></span>

<span data-ttu-id="f03a3-113">gRPC 인증 및 권한 부여는 두 수준에서 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="f03a3-113">gRPC authentication and authorization works on two levels.</span></span> <span data-ttu-id="f03a3-114">호출 수준 인증/권한 부여는 일반적으로 호출이 수행 될 때 메타 데이터에 적용 되는 토큰을 사용 하 여 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f03a3-114">Call-level authentication/authorization is usually handled using tokens that are applied in metadata when the call is made.</span></span> <span data-ttu-id="f03a3-115">채널 수준 인증은 연결 수준에서 적용 되는 클라이언트 인증서를 사용 하며, 채널의 모든 호출에 자동으로 적용 되는 호출 수준 인증/권한 부여 자격 증명을 포함할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f03a3-115">Channel-level authentication uses a client certificate that is applied at the connection level, and can also include call-level authentication/authorization credentials to be applied to every call on the channel automatically.</span></span> <span data-ttu-id="f03a3-116">이러한 메커니즘 중 하나 또는 둘 모두를 사용 하 여 서비스를 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f03a3-116">You can use either or both of these mechanisms to secure your service.</span></span>

<span data-ttu-id="f03a3-117">GRPC의 ASP.NET Core 구현에서는 대부분의 표준 ASP.NET Core 메커니즘을 사용 하 여 인증 및 권한 부여를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="f03a3-117">The ASP.NET Core implementation of gRPC supports authentication and authorization using most of the standard ASP.NET Core mechanisms:</span></span>

- <span data-ttu-id="f03a3-118">인증 호출</span><span class="sxs-lookup"><span data-stu-id="f03a3-118">Call authentication</span></span>
  - <span data-ttu-id="f03a3-119">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="f03a3-119">Azure Active Directory</span></span>
  - <span data-ttu-id="f03a3-120">IdentityServer</span><span class="sxs-lookup"><span data-stu-id="f03a3-120">IdentityServer</span></span>
  - <span data-ttu-id="f03a3-121">JWT 전달자 토큰</span><span class="sxs-lookup"><span data-stu-id="f03a3-121">JWT Bearer Token</span></span>
  - <span data-ttu-id="f03a3-122">OAuth 2.0</span><span class="sxs-lookup"><span data-stu-id="f03a3-122">OAuth 2.0</span></span>
  - <span data-ttu-id="f03a3-123">Openid connect 연결</span><span class="sxs-lookup"><span data-stu-id="f03a3-123">OpenID Connect</span></span>
  - <span data-ttu-id="f03a3-124">WS-Federation</span><span class="sxs-lookup"><span data-stu-id="f03a3-124">WS-Federation</span></span>
- <span data-ttu-id="f03a3-125">채널 인증</span><span class="sxs-lookup"><span data-stu-id="f03a3-125">Channel authentication</span></span>
  - <span data-ttu-id="f03a3-126">클라이언트 인증서</span><span class="sxs-lookup"><span data-stu-id="f03a3-126">Client Certificate</span></span>

<span data-ttu-id="f03a3-127">호출 인증 방법은 모두 *토큰*을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="f03a3-127">The call authentication methods are all based on *tokens*.</span></span> <span data-ttu-id="f03a3-128">유일한 차이점은 토큰을 생성 하는 방법과 ASP.NET Core 서비스에서 토큰의 유효성을 검사 하는 데 사용 되는 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="f03a3-128">The only real difference is how the token is generated and the libraries that are used to validate the tokens in the ASP.NET Core service.</span></span>

<span data-ttu-id="f03a3-129">자세한 내용은 [Microsoft Docs의 인증 및 권한 부여 설명서](https://docs.microsoft.com/aspnet/core/grpc/authn-and-authz?view=aspnetcore-3.0)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f03a3-129">For more information, see the [Authentication and authorization documentation on Microsoft Docs](https://docs.microsoft.com/aspnet/core/grpc/authn-and-authz?view=aspnetcore-3.0).</span></span>

> [!NOTE]
> <span data-ttu-id="f03a3-130">TLS로 암호화 된 HTTP/2 연결에서 gRPC를 사용할 때 채널 수준 인증을 사용 하지 않는 경우에도 클라이언트와 서버 간의 모든 트래픽이 암호화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f03a3-130">When using gRPC over a TLS-encrypted HTTP/2 connection, all traffic between clients and servers is encrypted, even if you don't use channel-level authentication.</span></span>

<span data-ttu-id="f03a3-131">이 장에서는 gRPC 서비스에 통화 자격 증명과 채널 자격 증명을 적용 하는 방법과 .NET Core gRPC 클라이언트의 자격 증명을 사용 하 여 서비스에 인증 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f03a3-131">This chapter will show how to apply call credentials and channel credentials to a gRPC service, and how to use credentials from a .NET Core gRPC client to authenticate with the service.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="f03a3-132">[이전](client-libraries.md)
>[다음](call-credentials.md)</span><span class="sxs-lookup"><span data-stu-id="f03a3-132">[Previous](client-libraries.md)
[Next](call-credentials.md)</span></span>
