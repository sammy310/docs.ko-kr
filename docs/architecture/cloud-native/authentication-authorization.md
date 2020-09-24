---
title: 클라우드 네이티브 앱의 인증 및 권한 부여
description: Azure 용 클라우드 네이티브 .NET 앱 설계 | 클라우드 네이티브 앱의 인증 및 권한 부여
ms.date: 05/13/2020
ms.openlocfilehash: bbd2df110dd7a7dc7363e9c07d87f1fa12f4e464
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91161141"
---
# <a name="authentication-and-authorization-in-cloud-native-apps"></a><span data-ttu-id="6deeb-103">클라우드 네이티브 앱의 인증 및 권한 부여</span><span class="sxs-lookup"><span data-stu-id="6deeb-103">Authentication and authorization in cloud-native apps</span></span>

<span data-ttu-id="6deeb-104">*인증은* 보안 주체의 id를 확인 하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="6deeb-104">*Authentication* is the process of determining the identity of a security principal.</span></span> <span data-ttu-id="6deeb-105">*권한 부여* 는 인증 된 보안 주체에 게 작업을 수행 하거나 리소스에 액세스할 수 있는 권한을 부여 하는 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="6deeb-105">*Authorization* is the act of granting an authenticated principal permission to perform an action or access a resource.</span></span> <span data-ttu-id="6deeb-106">경우에 따라 인증이 단축 되 `AuthN` 고 권한 부여가 짧아집니다 `AuthZ` .</span><span class="sxs-lookup"><span data-stu-id="6deeb-106">Sometimes authentication is shortened to `AuthN` and authorization is shortened to `AuthZ`.</span></span> <span data-ttu-id="6deeb-107">클라우드 네이티브 응용 프로그램은 오픈 HTTP 기반 프로토콜을 사용 하 여 모든 플랫폼 또는 장치에서 전 세계 어디에서 든 클라이언트와 응용 프로그램을 실행할 수 있기 때문에 보안 주체를 인증 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6deeb-107">Cloud-native applications need to rely on open HTTP-based protocols to authenticate security principals since both clients and applications could be running anywhere in the world on any platform or device.</span></span> <span data-ttu-id="6deeb-108">유일한 일반적인 요소는 HTTP입니다.</span><span class="sxs-lookup"><span data-stu-id="6deeb-108">The only common factor is HTTP.</span></span>

<span data-ttu-id="6deeb-109">대부분의 조직에서는 Active Directory Federation Services (ADFS)와 같은 로컬 인증 서비스를 계속 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6deeb-109">Many organizations still rely on local authentication services like Active Directory Federation Services (ADFS).</span></span> <span data-ttu-id="6deeb-110">이 접근 방식에서는 온-프레미스 인증 요구 사항에 대해 전통적으로 제공 되는 조직을 제공 하지만 클라우드 네이티브 응용 프로그램은 클라우드 용으로 특별히 설계 된 시스템을 활용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6deeb-110">While this approach has traditionally served organizations well for on premises authentication needs, cloud-native applications benefit from systems designed specifically for the cloud.</span></span> <span data-ttu-id="6deeb-111">최근 2019 영국 NCSC (국립 사이버 Security Center) 권고는 "Azure AD를 기본 인증 원본으로 사용 하는 조직이 ADFS와 비교 하 여 실제로 위험을 낮추는 것을 말합니다."</span><span class="sxs-lookup"><span data-stu-id="6deeb-111">A recent 2019 United Kingdom National Cyber Security Centre (NCSC) advisory states that "organizations using Azure AD as their primary authentication source will actually lower their risk compared to ADFS."</span></span> <span data-ttu-id="6deeb-112">[이 분석](https://oxfordcomputergroup.com/resources/o365-security-native-cloud-authentication/) 에서 설명 하는 몇 가지 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6deeb-112">Some reasons outlined in [this analysis](https://oxfordcomputergroup.com/resources/o365-security-native-cloud-authentication/) include:</span></span>

- <span data-ttu-id="6deeb-113">Microsoft 자격 증명 보호 기술의 전체 집합에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6deeb-113">Access to full set of Microsoft credential protection technologies.</span></span>
- <span data-ttu-id="6deeb-114">대부분의 조직에서는 Azure AD를 어느 정도까지 이미 의존 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6deeb-114">Most organizations are already relying on Azure AD to some extent.</span></span>
- <span data-ttu-id="6deeb-115">NTLM 해시를 이중으로 해시 하면 손상으로 인해 로컬 Active Directory에서 작동 하는 자격 증명이 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6deeb-115">Double hashing of NTLM hashes ensures compromise won't allow credentials that work in local Active Directory.</span></span>

## <a name="references"></a><span data-ttu-id="6deeb-116">참조</span><span class="sxs-lookup"><span data-stu-id="6deeb-116">References</span></span>

- [<span data-ttu-id="6deeb-117">인증 기본 사항</span><span class="sxs-lookup"><span data-stu-id="6deeb-117">Authentication basics</span></span>](/azure/active-directory/develop/authentication-scenarios)
- [<span data-ttu-id="6deeb-118">액세스 토큰 및 클레임</span><span class="sxs-lookup"><span data-stu-id="6deeb-118">Access tokens and claims</span></span>](/azure/active-directory/develop/access-tokens)
- [<span data-ttu-id="6deeb-119">온-프레미스 인증 서비스를 버릴 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6deeb-119">It may be time to ditch your on premises authentication services</span></span>](https://oxfordcomputergroup.com/resources/o365-security-native-cloud-authentication/)

>[!div class="step-by-step"]
><span data-ttu-id="6deeb-120">[이전](identity.md)
>[다음](azure-active-directory.md)</span><span class="sxs-lookup"><span data-stu-id="6deeb-120">[Previous](identity.md)
[Next](azure-active-directory.md)</span></span>
