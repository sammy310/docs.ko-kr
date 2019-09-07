---
title: <allowAccounts>의 <add>
ms.date: 03/30/2017
ms.assetid: 763c7b1f-e7b0-4d99-a42c-4506fcb8da00
ms.openlocfilehash: 02654b8ab198a2b161b3044c1f3aa452761a6a4c
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398388"
---
# <a name="add-of-allowaccounts"></a><span data-ttu-id="5168f-102">\<allowaccounts의 \<> 추가 ></span><span class="sxs-lookup"><span data-stu-id="5168f-102">\<add> of \<allowAccounts></span></span>
<span data-ttu-id="5168f-103">WCF 서비스를 호스팅하고 공유 서비스에 대 한 연결 액세스 권한이 부여 된 프로세스의 사용자 계정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5168f-103">Specifies a user account for processes that host WCF services, and are granted connection access to the sharing service.</span></span>  
  
<span data-ttu-id="5168f-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5168f-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5168f-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel-activation.md)</span><span class="sxs-lookup"><span data-stu-id="5168f-105">&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)</span></span>\
<span data-ttu-id="5168f-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<net.pipe >** ](net-pipe.md)</span><span class="sxs-lookup"><span data-stu-id="5168f-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<net.pipe>**](net-pipe.md)</span></span>\
<span data-ttu-id="5168f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<allowAccounts >** ](allowaccounts.md)</span><span class="sxs-lookup"><span data-stu-id="5168f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<allowAccounts>**](allowaccounts.md)</span></span>\
<span data-ttu-id="5168f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> 추가**</span><span class="sxs-lookup"><span data-stu-id="5168f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5168f-109">구문</span><span class="sxs-lookup"><span data-stu-id="5168f-109">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5168f-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="5168f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="5168f-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5168f-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5168f-112">특성</span><span class="sxs-lookup"><span data-stu-id="5168f-112">Attributes</span></span>  
  
|<span data-ttu-id="5168f-113">특성</span><span class="sxs-lookup"><span data-stu-id="5168f-113">Attribute</span></span>|<span data-ttu-id="5168f-114">Description</span><span class="sxs-lookup"><span data-stu-id="5168f-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5168f-115">securityIdentifier</span><span class="sxs-lookup"><span data-stu-id="5168f-115">securityIdentifier</span></span>|<span data-ttu-id="5168f-116">사용자 계정을 식별하는 데 사용하는 고유 식별자를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="5168f-116">A string that specifies a unique identifier used to identify a user account.</span></span> <span data-ttu-id="5168f-117">반환되는 기본값은 LocalSystem, Administrators, NS, LS 및 IIS_USRS입니다.</span><span class="sxs-lookup"><span data-stu-id="5168f-117">The default values are LocalSystem, Administrators, NS, LS, and IIS_USRS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5168f-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="5168f-118">Child Elements</span></span>  
 <span data-ttu-id="5168f-119">없음</span><span class="sxs-lookup"><span data-stu-id="5168f-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5168f-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="5168f-120">Parent Elements</span></span>  
  
|<span data-ttu-id="5168f-121">요소</span><span class="sxs-lookup"><span data-stu-id="5168f-121">Element</span></span>|<span data-ttu-id="5168f-122">Description</span><span class="sxs-lookup"><span data-stu-id="5168f-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5168f-123">\<allowAccounts></span><span class="sxs-lookup"><span data-stu-id="5168f-123">\<allowAccounts></span></span>](allowaccounts.md)|<span data-ttu-id="5168f-124">WCF 서비스를 호스팅하고 공유 서비스에 대 `securityIdentifier` 한 연결 액세스 권한이 부여 된 프로세스의 사용자 계정을 지정 하는 특성을 포함 하는 구성 요소 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="5168f-124">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="5168f-125">예제</span><span class="sxs-lookup"><span data-stu-id="5168f-125">Example</span></span>  
 <span data-ttu-id="5168f-126">다음 구성 예제에서는 사용자 계정에 대한 다섯 가지 기본 식별자를 이 컬렉션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5168f-126">The following configuration example adds the five default identifiers for user accounts to this collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5168f-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="5168f-127">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
