---
title: <allowAccounts>
ms.date: 03/30/2017
ms.assetid: 166923a9-a8ac-478f-92f9-529d9667f3a6
ms.openlocfilehash: 74b9d51b7400469c96fc9c8b36e4b0fb1d46969b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398412"
---
# \<allowAccounts>
<span data-ttu-id="414d4-101">Windows Communication Foundation (WCF) 서비스를 호스팅하고 공유 서비스에 대 한 연결 액세스 권한이 부여 된 프로세스의 사용자 계정을 지정 하는 구성 요소 컬렉션을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="414d4-101">Contains a collection of configuration elements that specify user accounts for processes that host Windows Communication Foundation (WCF) services, and are granted connection access to the sharing service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<net.pipe>**](net-pipe.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<allowAccounts>**  
  
## <a name="syntax"></a><span data-ttu-id="414d4-102">구문</span><span class="sxs-lookup"><span data-stu-id="414d4-102">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="414d4-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="414d4-103">Attributes and Elements</span></span>  
 <span data-ttu-id="414d4-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="414d4-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="414d4-105">특성</span><span class="sxs-lookup"><span data-stu-id="414d4-105">Attributes</span></span>  
 <span data-ttu-id="414d4-106">없음</span><span class="sxs-lookup"><span data-stu-id="414d4-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="414d4-107">자식 요소</span><span class="sxs-lookup"><span data-stu-id="414d4-107">Child Elements</span></span>  
  
|<span data-ttu-id="414d4-108">attribute</span><span class="sxs-lookup"><span data-stu-id="414d4-108">Attribute</span></span>|<span data-ttu-id="414d4-109">Description</span><span class="sxs-lookup"><span data-stu-id="414d4-109">Description</span></span>|  
|---------------|-----------------|  
|[\<add>](add-of-allowaccounts.md)|<span data-ttu-id="414d4-110">WCF 서비스를 호스팅하고 공유 서비스에 대 한 연결 액세스 권한이 부여 된 프로세스에 대 한 사용자 계정을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="414d4-110">Adds a user account for processes that host WCF services, and are granted connection access to the sharing service</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="414d4-111">부모 요소</span><span class="sxs-lookup"><span data-stu-id="414d4-111">Parent Elements</span></span>  
  
|<span data-ttu-id="414d4-112">요소</span><span class="sxs-lookup"><span data-stu-id="414d4-112">Element</span></span>|<span data-ttu-id="414d4-113">Description</span><span class="sxs-lookup"><span data-stu-id="414d4-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="414d4-114">[\<net.pipe>](net-pipe.md)디스크나[\<net.tcp>](net-tcp.md)</span><span class="sxs-lookup"><span data-stu-id="414d4-114">[\<net.pipe>](net-pipe.md) or [\<net.tcp>](net-tcp.md)</span></span>|<span data-ttu-id="414d4-115">Net Pipe 또는 TCP 공유 서비스의 구성 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="414d4-115">Specifies configuration settings for the Net Pipe or TCP sharing services.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="414d4-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="414d4-116">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
