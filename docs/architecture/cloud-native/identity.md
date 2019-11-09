---
title: 클레임
description: Azure 용 클라우드 네이티브 .NET 앱 설계 | 신분을
ms.date: 09/23/2019
ms.openlocfilehash: 4cc7c04bf323d2589777df466321f6801f511b6f
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2019
ms.locfileid: "73840348"
---
# <a name="identity"></a><span data-ttu-id="78c3a-103">클레임</span><span class="sxs-lookup"><span data-stu-id="78c3a-103">Identity</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="78c3a-104">대부분의 소프트웨어 응용 프로그램에는 해당 응용 프로그램을 호출 하는 사용자 또는 프로세스에 대 한 지식이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78c3a-104">Most software applications need to have some knowledge of the user or process that is calling them.</span></span> <span data-ttu-id="78c3a-105">응용 프로그램과 상호 작용 하는 사용자 또는 프로세스를 보안 주체 라고 하며 이러한 보안 주체를 인증 하 고 권한을 부여 하는 프로세스를 id 관리 또는 간단히 *id*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="78c3a-105">The user or process interacting with an application is known as a security principal, and the process of authenticating and authorizing these principals is known as identity management, or simply *identity*.</span></span> <span data-ttu-id="78c3a-106">간단한 응용 프로그램은 응용 프로그램 내에서 모든 id 관리를 포함할 수 있지만이 접근 방식은 많은 응용 프로그램 및 다양 한 종류의 보안 주체를 사용 하 여 제대로 확장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="78c3a-106">Simple applications may include all of their identity management within the application, but this approach doesn't scale well with many applications and many kinds of security principals.</span></span> <span data-ttu-id="78c3a-107">Windows에서는 Active Directory를 사용 하 여 중앙 집중식 인증 및 권한 부여를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="78c3a-107">Windows supports the use of Active Directory to provide centralized authentication and authorization.</span></span>

<!-- (insert figure showing Windows AD auth model) -->

<span data-ttu-id="78c3a-108">이 솔루션은 회사 네트워크 내에서 효과적 이지만 AD 도메인 외부에 있는 사용자 또는 응용 프로그램에서 사용 하도록 설계 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="78c3a-108">While this solution is effective within corporate networks, it isn't designed for use by users or applications that are outside of the AD domain.</span></span> <span data-ttu-id="78c3a-109">인터넷 기반 응용 프로그램 및 클라우드 네이티브 앱의 증가로 인해 보안 모델이 진화 했습니다.</span><span class="sxs-lookup"><span data-stu-id="78c3a-109">With the growth of Internet-based applications and the rise of cloud-native apps, security models have evolved.</span></span>

<span data-ttu-id="78c3a-110">오늘날의 클라우드 기본 id 모델에서는 아키텍처가 배포 되는 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="78c3a-110">In today's cloud-native identity model, architecture is assumed to be distributed.</span></span> <span data-ttu-id="78c3a-111">앱은 어디에서 나 배포할 수 있으며 어디에서 나 다른 앱과 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78c3a-111">Apps can be deployed anywhere and may communicate with other apps anywhere.</span></span> <span data-ttu-id="78c3a-112">클라이언트는 어디에서 나 이러한 앱과 통신할 수 있습니다. 실제로 클라이언트는 플랫폼과 장치를 조합 하 여 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78c3a-112">Clients may communicate with these apps from anywhere, and in fact, clients may consist of any combination of platforms and devices.</span></span> <span data-ttu-id="78c3a-113">클라우드 기본 id 솔루션은 오픈 표준을 활용 하 여 클라이언트의 보안 응용 프로그램 액세스를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="78c3a-113">Cloud-native identity solutions leverage open standards to achieve secure application access from clients.</span></span> <span data-ttu-id="78c3a-114">이러한 클라이언트는 Pc 또는 휴대폰의 사용자와 전 세계 어디에서 든 모든 소프트웨어 플랫폼을 실행 하는 셋톱 박스 및 IOT 장치에 이르기까지 다양 합니다.</span><span class="sxs-lookup"><span data-stu-id="78c3a-114">These clients range from human users on PCs or phones, to other apps hosted anywhere online, to set-top boxes and IOT devices running any software platform anywhere in the world.</span></span>

<span data-ttu-id="78c3a-115">최신 클라우드 네이티브 id 솔루션은 일반적으로 id가 결정 된 후 보안 주체에 게 STS (보안 토큰 서비스/서버)에서 발급 한 액세스 토큰을 활용 합니다.</span><span class="sxs-lookup"><span data-stu-id="78c3a-115">Modern cloud-native identity solutions typically leverage access tokens that are issued by a secure token service/server (STS) to a security principal once their identity is determined.</span></span> <span data-ttu-id="78c3a-116">액세스 토큰 (일반적으로 JWT (JSON Web Token))에는 보안 주체에 대 한 *클레임이* 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78c3a-116">The access token, typically a JSON Web Token (JWT), includes *claims* about the security principal.</span></span> <span data-ttu-id="78c3a-117">이러한 클레임에는 최소한 사용자의 id가 포함 되지만 응용 프로그램에서 보안 주체를 부여할 액세스 수준을 결정 하는 데 사용할 수 있는 추가 클레임이 포함 될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78c3a-117">These claims will minimally include the user's identity but may also include additional claims that can be used by applications to determine the level of access to grant the principal.</span></span>

<!-- (insert figure showing basic handshake involving a principal, an STS, and an app) -->

<span data-ttu-id="78c3a-118">일반적으로 STS는 주 서버 인증을 담당 합니다.</span><span class="sxs-lookup"><span data-stu-id="78c3a-118">Typically, the STS is only responsible for authenticating the principal.</span></span> <span data-ttu-id="78c3a-119">리소스에 대 한 액세스 수준을 결정 하는 것은 응용 프로그램의 다른 부분에 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78c3a-119">Determining their level of access to resources is left to other parts of the application.</span></span>

## <a name="references"></a><span data-ttu-id="78c3a-120">참조 항목</span><span class="sxs-lookup"><span data-stu-id="78c3a-120">References</span></span>

- [<span data-ttu-id="78c3a-121">Microsoft id 플랫폼</span><span class="sxs-lookup"><span data-stu-id="78c3a-121">Microsoft identity platform</span></span>](https://docs.microsoft.com/azure/active-directory/develop/)

>[!div class="step-by-step"]
><span data-ttu-id="78c3a-122">[이전](azure-monitor.md)
>[다음](authentication-authorization.md)</span><span class="sxs-lookup"><span data-stu-id="78c3a-122">[Previous](azure-monitor.md)
[Next](authentication-authorization.md)</span></span>
