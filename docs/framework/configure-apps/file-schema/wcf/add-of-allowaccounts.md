---
title: <allowAccounts>의 <add>
ms.date: 03/30/2017
ms.assetid: 763c7b1f-e7b0-4d99-a42c-4506fcb8da00
ms.openlocfilehash: 02654b8ab198a2b161b3044c1f3aa452761a6a4c
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398388"
---
# <a name="add-of-allowaccounts"></a><span data-ttu-id="b2340-102">\<allowAccounts>의 \<add></span><span class="sxs-lookup"><span data-stu-id="b2340-102">\<add> of \<allowAccounts></span></span>
<span data-ttu-id="b2340-103">WCF 서비스를 호스팅하고 공유 서비스에 대 한 연결 액세스 권한이 부여 된 프로세스의 사용자 계정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2340-103">Specifies a user account for processes that host WCF services, and are granted connection access to the sharing service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<net.pipe>**](net-pipe.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<allowAccounts>**](allowaccounts.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="b2340-104">구문</span><span class="sxs-lookup"><span data-stu-id="b2340-104">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b2340-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b2340-105">Attributes and Elements</span></span>  
 <span data-ttu-id="b2340-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b2340-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b2340-107">특성</span><span class="sxs-lookup"><span data-stu-id="b2340-107">Attributes</span></span>  
  
|<span data-ttu-id="b2340-108">attribute</span><span class="sxs-lookup"><span data-stu-id="b2340-108">Attribute</span></span>|<span data-ttu-id="b2340-109">Description</span><span class="sxs-lookup"><span data-stu-id="b2340-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b2340-110">securityIdentifier</span><span class="sxs-lookup"><span data-stu-id="b2340-110">securityIdentifier</span></span>|<span data-ttu-id="b2340-111">사용자 계정을 식별하는 데 사용하는 고유 식별자를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="b2340-111">A string that specifies a unique identifier used to identify a user account.</span></span> <span data-ttu-id="b2340-112">반환되는 기본값은 LocalSystem, Administrators, NS, LS 및 IIS_USRS입니다.</span><span class="sxs-lookup"><span data-stu-id="b2340-112">The default values are LocalSystem, Administrators, NS, LS, and IIS_USRS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b2340-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b2340-113">Child Elements</span></span>  
 <span data-ttu-id="b2340-114">없음</span><span class="sxs-lookup"><span data-stu-id="b2340-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b2340-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b2340-115">Parent Elements</span></span>  
  
|<span data-ttu-id="b2340-116">요소</span><span class="sxs-lookup"><span data-stu-id="b2340-116">Element</span></span>|<span data-ttu-id="b2340-117">Description</span><span class="sxs-lookup"><span data-stu-id="b2340-117">Description</span></span>|  
|-------------|-----------------|  
|[\<allowAccounts>](allowaccounts.md)|<span data-ttu-id="b2340-118">`securityIdentifier`WCF 서비스를 호스팅하고 공유 서비스에 대 한 연결 액세스 권한이 부여 된 프로세스의 사용자 계정을 지정 하는 특성을 포함 하는 구성 요소 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="b2340-118">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b2340-119">예제</span><span class="sxs-lookup"><span data-stu-id="b2340-119">Example</span></span>  
 <span data-ttu-id="b2340-120">다음 구성 예제에서는 사용자 계정에 대한 다섯 가지 기본 식별자를 이 컬렉션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b2340-120">The following configuration example adds the five default identifiers for user accounts to this collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b2340-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b2340-121">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
