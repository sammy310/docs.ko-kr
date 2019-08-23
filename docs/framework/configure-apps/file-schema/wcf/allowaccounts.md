---
title: <allowAccounts>
ms.date: 03/30/2017
ms.assetid: 166923a9-a8ac-478f-92f9-529d9667f3a6
ms.openlocfilehash: c62f29c53d807cab397ff09c6163d924a71ea319
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926606"
---
# <a name="allowaccounts"></a><span data-ttu-id="2761e-101">\<allowAccounts></span><span class="sxs-lookup"><span data-stu-id="2761e-101">\<allowAccounts></span></span>
<span data-ttu-id="2761e-102">Windows Communication Foundation (WCF) 서비스를 호스팅하고 공유 서비스에 대 한 연결 액세스 권한이 부여 된 프로세스의 사용자 계정을 지정 하는 구성 요소 컬렉션을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="2761e-102">Contains a collection of configuration elements that specify user accounts for processes that host Windows Communication Foundation (WCF) services, and are granted connection access to the sharing service.</span></span>  
  
 <span data-ttu-id="2761e-103">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="2761e-103">\<system.serviceModel.activation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2761e-104">구문</span><span class="sxs-lookup"><span data-stu-id="2761e-104">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2761e-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="2761e-105">Attributes and Elements</span></span>  
 <span data-ttu-id="2761e-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2761e-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2761e-107">특성</span><span class="sxs-lookup"><span data-stu-id="2761e-107">Attributes</span></span>  
 <span data-ttu-id="2761e-108">없음</span><span class="sxs-lookup"><span data-stu-id="2761e-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2761e-109">자식 요소</span><span class="sxs-lookup"><span data-stu-id="2761e-109">Child Elements</span></span>  
  
|<span data-ttu-id="2761e-110">특성</span><span class="sxs-lookup"><span data-stu-id="2761e-110">Attribute</span></span>|<span data-ttu-id="2761e-111">Description</span><span class="sxs-lookup"><span data-stu-id="2761e-111">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="2761e-112">\<add></span><span class="sxs-lookup"><span data-stu-id="2761e-112">\<add></span></span>](add-of-allowaccounts.md)|<span data-ttu-id="2761e-113">WCF 서비스를 호스팅하고 공유 서비스에 대 한 연결 액세스 권한이 부여 된 프로세스에 대 한 사용자 계정을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2761e-113">Adds a user account for processes that host WCF services, and are granted connection access to the sharing service</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2761e-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="2761e-114">Parent Elements</span></span>  
  
|<span data-ttu-id="2761e-115">요소</span><span class="sxs-lookup"><span data-stu-id="2761e-115">Element</span></span>|<span data-ttu-id="2761e-116">설명</span><span class="sxs-lookup"><span data-stu-id="2761e-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2761e-117">net.pipe > 또는 [ \<](net-pipe.md) [ net.tcp>\<](net-tcp.md)</span><span class="sxs-lookup"><span data-stu-id="2761e-117">[\<net.pipe>](net-pipe.md) or [\<net.tcp>](net-tcp.md)</span></span>|<span data-ttu-id="2761e-118">Net Pipe 또는 TCP 공유 서비스의 구성 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2761e-118">Specifies configuration settings for the Net Pipe or TCP sharing services.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2761e-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="2761e-119">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
