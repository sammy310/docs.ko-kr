---
title: 클라우드 네이티브 앱의 인증 및 권한 부여
description: Azure용 클라우드 네이티브 .NET 앱 설계 | 클라우드 네이티브 앱의 인증 및 권한 부여
ms.date: 03/02/2020
ms.openlocfilehash: 6261a0a72405bc1c984a04a7851aea4dd6664ddf
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805547"
---
# <a name="authentication-and-authorization-in-cloud-native-apps"></a><span data-ttu-id="1d52f-103">클라우드 네이티브 앱의 인증 및 권한 부여</span><span class="sxs-lookup"><span data-stu-id="1d52f-103">Authentication and authorization in cloud-native apps</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="1d52f-104">*인증은* 보안 주체의 ID를 확인하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="1d52f-104">*Authentication* is the process of determining the identity of a security principal.</span></span> <span data-ttu-id="1d52f-105">*권한 부여는* 작업을 수행하거나 리소스에 액세스할 수 있는 인증된 보안 주체 권한을 부여하는 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="1d52f-105">*Authorization* is the act of granting an authenticated principal permission to perform an action or access a resource.</span></span> <span data-ttu-id="1d52f-106">인증이 로 `AuthN` 단축되고 권한 부여가 `AuthZ`로 단축되는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d52f-106">Sometimes authentication is shortened to `AuthN` and authorization is shortened to `AuthZ`.</span></span> <span data-ttu-id="1d52f-107">클라우드 네이티브 응용 프로그램은 클라이언트와 응용 프로그램이 모든 플랫폼 또는 장치에서 전 세계 어디에서나 실행될 수 있기 때문에 보안 주체를 인증하기 위해 개방형 HTTP 기반 프로토콜에 의존해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d52f-107">Cloud-native applications need to rely on open HTTP-based protocols to authenticate security principals since both clients and applications could be running anywhere in the world on any platform or device.</span></span> <span data-ttu-id="1d52f-108">유일한 일반적인 요소는 HTTP입니다.</span><span class="sxs-lookup"><span data-stu-id="1d52f-108">The only common factor is HTTP.</span></span>

<span data-ttu-id="1d52f-109">많은 조직에서여전히 ADFS(Active Directory Federation 서비스)와 같은 로컬 인증 서비스에 의존하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d52f-109">Many organizations still rely on local authentication services like Active Directory Federation Services (ADFS).</span></span> <span data-ttu-id="1d52f-110">이 접근 방식은 전통적으로 조직에 온프레미스 인증 요구 사항에 적합했지만 클라우드 네이티브 응용 프로그램은 클라우드를 위해 특별히 설계된 시스템의 이점을 활용합니다.</span><span class="sxs-lookup"><span data-stu-id="1d52f-110">While this approach has traditionally served organizations well for on premises authentication needs, cloud-native applications benefit from systems designed specifically for the cloud.</span></span> <span data-ttu-id="1d52f-111">최근 2019년 영국 국가 사이버 보안 센터(NCSC) 권고에 따르면 "Azure AD를 기본 인증 소스로 사용하는 조직은 실제로 ADFS에 비해 위험을 낮출 수 있습니다."</span><span class="sxs-lookup"><span data-stu-id="1d52f-111">A recent 2019 United Kingdom National Cyber Security Centre (NCSC) advisory states that "organizations using Azure AD as their primary authentication source will actually lower their risk compared to ADFS."</span></span> <span data-ttu-id="1d52f-112">[이 분석에](https://oxfordcomputergroup.com/resources/o365-security-native-cloud-authentication/) 설명된 몇 가지 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1d52f-112">Some reasons outlined in [this analysis](https://oxfordcomputergroup.com/resources/o365-security-native-cloud-authentication/) include:</span></span>

- <span data-ttu-id="1d52f-113">전체 Microsoft 자격 증명 보호 기술 집합에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="1d52f-113">Access to full set of Microsoft credential protection technologies.</span></span>
- <span data-ttu-id="1d52f-114">대부분의 조직은 이미 Azure AD에 어느 정도 의존하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d52f-114">Most organizations are already relying on Azure AD to some extent.</span></span>
- <span data-ttu-id="1d52f-115">NTLM 해시를 두 번 해시하면 로컬 Active Directory에서 작동하는 자격 증명이 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d52f-115">Double hashing of NTLM hashes ensures compromise won't allow credentials that work in local Active Directory.</span></span>

## <a name="references"></a><span data-ttu-id="1d52f-116">참조</span><span class="sxs-lookup"><span data-stu-id="1d52f-116">References</span></span>

- [<span data-ttu-id="1d52f-117">인증 기본 사항</span><span class="sxs-lookup"><span data-stu-id="1d52f-117">Authentication basics</span></span>](https://docs.microsoft.com/azure/active-directory/develop/authentication-scenarios)
- [<span data-ttu-id="1d52f-118">토큰 및 클레임 액세스</span><span class="sxs-lookup"><span data-stu-id="1d52f-118">Access tokens and claims</span></span>](https://docs.microsoft.com/azure/active-directory/develop/access-tokens)
- [<span data-ttu-id="1d52f-119">온-프레미스 인증 서비스를 폐기할 때가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d52f-119">It may be time to ditch your on premises authentication services</span></span>](https://oxfordcomputergroup.com/resources/o365-security-native-cloud-authentication/)

>[!div class="step-by-step"]
><span data-ttu-id="1d52f-120">[이전](identity.md)
>[다음](azure-active-directory.md)</span><span class="sxs-lookup"><span data-stu-id="1d52f-120">[Previous](identity.md)
[Next](azure-active-directory.md)</span></span>
