---
title: <allowAccounts>의 <add>
ms.date: 03/30/2017
ms.assetid: 763c7b1f-e7b0-4d99-a42c-4506fcb8da00
ms.openlocfilehash: 1ed0b5025ab969c45d7440f2a209426c5c87f549
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920282"
---
# <a name="add-of-allowaccounts"></a><span data-ttu-id="85600-102">\<allowaccounts의 \<> 추가 ></span><span class="sxs-lookup"><span data-stu-id="85600-102">\<add> of \<allowAccounts></span></span>
<span data-ttu-id="85600-103">WCF 서비스를 호스팅하고 공유 서비스에 대 한 연결 액세스 권한이 부여 된 프로세스의 사용자 계정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="85600-103">Specifies a user account for processes that host WCF services, and are granted connection access to the sharing service.</span></span>  
  
 <span data-ttu-id="85600-104">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="85600-104">\<system.serviceModel.activation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85600-105">구문</span><span class="sxs-lookup"><span data-stu-id="85600-105">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="85600-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="85600-106">Attributes and Elements</span></span>  
 <span data-ttu-id="85600-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="85600-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="85600-108">특성</span><span class="sxs-lookup"><span data-stu-id="85600-108">Attributes</span></span>  
  
|<span data-ttu-id="85600-109">특성</span><span class="sxs-lookup"><span data-stu-id="85600-109">Attribute</span></span>|<span data-ttu-id="85600-110">Description</span><span class="sxs-lookup"><span data-stu-id="85600-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="85600-111">securityIdentifier</span><span class="sxs-lookup"><span data-stu-id="85600-111">securityIdentifier</span></span>|<span data-ttu-id="85600-112">사용자 계정을 식별하는 데 사용하는 고유 식별자를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="85600-112">A string that specifies a unique identifier used to identify a user account.</span></span> <span data-ttu-id="85600-113">반환되는 기본값은 LocalSystem, Administrators, NS, LS 및 IIS_USRS입니다.</span><span class="sxs-lookup"><span data-stu-id="85600-113">The default values are LocalSystem, Administrators, NS, LS, and IIS_USRS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="85600-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="85600-114">Child Elements</span></span>  
 <span data-ttu-id="85600-115">없음</span><span class="sxs-lookup"><span data-stu-id="85600-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="85600-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="85600-116">Parent Elements</span></span>  
  
|<span data-ttu-id="85600-117">요소</span><span class="sxs-lookup"><span data-stu-id="85600-117">Element</span></span>|<span data-ttu-id="85600-118">Description</span><span class="sxs-lookup"><span data-stu-id="85600-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="85600-119">\<allowAccounts></span><span class="sxs-lookup"><span data-stu-id="85600-119">\<allowAccounts></span></span>](allowaccounts.md)|<span data-ttu-id="85600-120">WCF 서비스를 호스팅하고 공유 서비스에 대 `securityIdentifier` 한 연결 액세스 권한이 부여 된 프로세스의 사용자 계정을 지정 하는 특성을 포함 하는 구성 요소 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="85600-120">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="85600-121">예제</span><span class="sxs-lookup"><span data-stu-id="85600-121">Example</span></span>  
 <span data-ttu-id="85600-122">다음 구성 예제에서는 사용자 계정에 대한 다섯 가지 기본 식별자를 이 컬렉션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="85600-122">The following configuration example adds the five default identifiers for user accounts to this collection.</span></span>  
  
```xml  
<allowAccounts>
  <!-- LocalSystem account -->
  <add securityIdentifier="S-1-5-18" />
  <!-- LocalService account -->
  <add securityIdentifier="S-1-5-19" />
  <!-- Administrators account -->
  <add securityIdentifier="S-1-5-20" />
  <!-- Network Service account -->
  <add securityIdentifier="S-1-5-32-544" />
  <!-- IIS_IUSRS account (Vista only) -->
  <add securityIdentifier="S-1-5-32-568" />
</allowAccounts>
```  
  
## <a name="see-also"></a><span data-ttu-id="85600-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="85600-123">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
