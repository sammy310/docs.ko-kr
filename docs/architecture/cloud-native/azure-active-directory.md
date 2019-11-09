---
title: Azure Active Directory
description: Azure 용 클라우드 네이티브 .NET 앱 설계 | Azure Active Directory
ms.date: 06/30/2019
ms.openlocfilehash: 207043507a9052c47683383a98cef6417a1a2740
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2019
ms.locfileid: "73840732"
---
# <a name="azure-active-directory"></a><span data-ttu-id="1299e-103">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="1299e-103">Azure Active Directory</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="1299e-104">Azure AD (Microsoft Azure Active Directory)는 id 및 액세스 관리를 서비스로 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1299e-104">Microsoft Azure Active Directory (Azure AD) offers identity and access management as a service.</span></span> <span data-ttu-id="1299e-105">고객은 사용자를 구성 하 고 유지 관리 하는 데 사용할 수 있는 사용자, 해당 정보에 액세스할 수 있는 사람, 해당 정보에 액세스할 수 있는 사용자, 앱에 액세스할 수 있는 사람을 구성 하 고 유지 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="1299e-105">Customers use it to configure and maintain who users are, what information to store about them, who can access that information, who can manage it, and what apps can access it.</span></span> <span data-ttu-id="1299e-106">AAD는이를 사용 하도록 구성 된 응용 프로그램에 대 한 사용자를 인증 하 여 SSO (Single Sign-On) 환경을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1299e-106">AAD can authenticate users for applications configured to use it, providing a single sign-on (SSO) experience.</span></span> <span data-ttu-id="1299e-107">자체에서 사용 하거나 온-프레미스에서 실행 되는 Windows AD와 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1299e-107">It can be used on its own or be integrated with Windows AD running on premises.</span></span>

<span data-ttu-id="1299e-108">Azure AD는 클라우드 용으로 작성 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1299e-108">Azure AD is built for the cloud.</span></span> <span data-ttu-id="1299e-109">LDAP를 사용 하는 Windows AD와 달리 REST 기반 Graph API 및 OData 구문을 사용 하는 클라우드 기본 id 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="1299e-109">It's truly a cloud-native identity solution that uses a REST-based Graph API and OData syntax for queries, unlike Windows AD, which uses LDAP.</span></span> <span data-ttu-id="1299e-110">온-프레미스 Active Directory는 Id 동기화 서비스를 사용 하 여 사용자 특성을 클라우드에 동기화 하 여 모든 인증을 클라우드에서 Azure AD를 사용 하 여 수행할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1299e-110">On premises Active Directory can sync user attributes to the cloud using Identity Sync Services, allowing all authentication to take place in the cloud using Azure AD.</span></span> <span data-ttu-id="1299e-111">또는 ADFS를 통해 로컬 Active Directory로 다시 전달 하 여 온-프레미스에서 Windows AD를 통해 인증을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1299e-111">Alternately, authentication can be configured via Connect to pass back to local Active Directory via ADFS to be completed by Windows AD on premises.</span></span>

<span data-ttu-id="1299e-112">Azure AD는 온-프레미스에서 호스트 되는 응용 프로그램에 대 한 SSO를 제공 하는 데 사용 되는 회사 브랜드 로그인 화면, 다중 팩터리 인증 및 클라우드 기반 응용 프로그램 프록시를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="1299e-112">Azure AD supports company branded sign-in screens, multi-factory authentication, and cloud-based application proxies that are used to provide SSO for applications hosted on premises.</span></span> <span data-ttu-id="1299e-113">다양 한 종류의 보안 보고 및 경고 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1299e-113">It offers different kinds of security reporting and alert capabilities.</span></span>

## <a name="references"></a><span data-ttu-id="1299e-114">참조 항목</span><span class="sxs-lookup"><span data-stu-id="1299e-114">References</span></span>

- [<span data-ttu-id="1299e-115">Microsoft id 플랫폼</span><span class="sxs-lookup"><span data-stu-id="1299e-115">Microsoft identity platform</span></span>](https://docs.microsoft.com/azure/active-directory/develop/)

>[!div class="step-by-step"]
><span data-ttu-id="1299e-116">[이전](authentication-authorization.md)
>[다음](identity-server.md)</span><span class="sxs-lookup"><span data-stu-id="1299e-116">[Previous](authentication-authorization.md)
[Next](identity-server.md)</span></span>
