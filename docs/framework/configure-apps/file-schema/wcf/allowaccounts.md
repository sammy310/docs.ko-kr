---
description: 다음에 대해 자세히 알아보세요. <allowAccounts>
title: <allowAccounts>
ms.date: 03/30/2017
ms.assetid: 166923a9-a8ac-478f-92f9-529d9667f3a6
ms.openlocfilehash: 5211d694e5318faf0cfc31b404764acb405bd096
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99749989"
---
# \<allowAccounts>

<span data-ttu-id="a9a1e-102">Windows Communication Foundation (WCF) 서비스를 호스팅하고 공유 서비스에 대 한 연결 액세스 권한이 부여 된 프로세스의 사용자 계정을 지정 하는 구성 요소 컬렉션을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9a1e-102">Contains a collection of configuration elements that specify user accounts for processes that host Windows Communication Foundation (WCF) services, and are granted connection access to the sharing service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<net.pipe>**](net-pipe.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<allowAccounts>**  
  
## <a name="syntax"></a><span data-ttu-id="a9a1e-103">구문</span><span class="sxs-lookup"><span data-stu-id="a9a1e-103">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a9a1e-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="a9a1e-104">Attributes and Elements</span></span>  

 <span data-ttu-id="a9a1e-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a9a1e-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a9a1e-106">특성</span><span class="sxs-lookup"><span data-stu-id="a9a1e-106">Attributes</span></span>  

 <span data-ttu-id="a9a1e-107">없음</span><span class="sxs-lookup"><span data-stu-id="a9a1e-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a9a1e-108">자식 요소</span><span class="sxs-lookup"><span data-stu-id="a9a1e-108">Child Elements</span></span>  
  
|<span data-ttu-id="a9a1e-109">attribute</span><span class="sxs-lookup"><span data-stu-id="a9a1e-109">Attribute</span></span>|<span data-ttu-id="a9a1e-110">설명</span><span class="sxs-lookup"><span data-stu-id="a9a1e-110">Description</span></span>|  
|---------------|-----------------|  
|[\<add>](add-of-allowaccounts.md)|<span data-ttu-id="a9a1e-111">WCF 서비스를 호스팅하고 공유 서비스에 대 한 연결 액세스 권한이 부여 된 프로세스에 대 한 사용자 계정을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9a1e-111">Adds a user account for processes that host WCF services, and are granted connection access to the sharing service</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a9a1e-112">부모 요소</span><span class="sxs-lookup"><span data-stu-id="a9a1e-112">Parent Elements</span></span>  
  
|<span data-ttu-id="a9a1e-113">요소</span><span class="sxs-lookup"><span data-stu-id="a9a1e-113">Element</span></span>|<span data-ttu-id="a9a1e-114">설명</span><span class="sxs-lookup"><span data-stu-id="a9a1e-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a9a1e-115">[\<net.pipe>](net-pipe.md) 또는 [\<net.tcp>](net-tcp.md)</span><span class="sxs-lookup"><span data-stu-id="a9a1e-115">[\<net.pipe>](net-pipe.md) or [\<net.tcp>](net-tcp.md)</span></span>|<span data-ttu-id="a9a1e-116">Net Pipe 또는 TCP 공유 서비스의 구성 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a9a1e-116">Specifies configuration settings for the Net Pipe or TCP sharing services.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a9a1e-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a9a1e-117">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
