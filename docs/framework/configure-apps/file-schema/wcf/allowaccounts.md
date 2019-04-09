---
title: <allowAccounts>
ms.date: 03/30/2017
ms.assetid: 166923a9-a8ac-478f-92f9-529d9667f3a6
ms.openlocfilehash: f9def3004b116afdc629de136cdfe0b0eb6e75c2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59102624"
---
# <a name="allowaccounts"></a><span data-ttu-id="adf0e-101">\<allowAccounts></span><span class="sxs-lookup"><span data-stu-id="adf0e-101">\<allowAccounts></span></span>
<span data-ttu-id="adf0e-102">사용자 호스트 하는 Windows Communication Foundation (WCF) 서비스 프로세스에 대 한 계정 및 공유 서비스에 대 한 연결 액세스를 부여 하는 지정 하는 구성 요소의 컬렉션을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="adf0e-102">Contains a collection of configuration elements that specify user accounts for processes that host Windows Communication Foundation (WCF) services, and are granted connection access to the sharing service.</span></span>  
  
 <span data-ttu-id="adf0e-103">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="adf0e-103">\<system.serviceModel.activation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="adf0e-104">구문</span><span class="sxs-lookup"><span data-stu-id="adf0e-104">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="adf0e-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="adf0e-105">Attributes and Elements</span></span>  
 <span data-ttu-id="adf0e-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="adf0e-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="adf0e-107">특성</span><span class="sxs-lookup"><span data-stu-id="adf0e-107">Attributes</span></span>  
 <span data-ttu-id="adf0e-108">없음</span><span class="sxs-lookup"><span data-stu-id="adf0e-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="adf0e-109">자식 요소</span><span class="sxs-lookup"><span data-stu-id="adf0e-109">Child Elements</span></span>  
  
|<span data-ttu-id="adf0e-110">특성</span><span class="sxs-lookup"><span data-stu-id="adf0e-110">Attribute</span></span>|<span data-ttu-id="adf0e-111">설명</span><span class="sxs-lookup"><span data-stu-id="adf0e-111">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="adf0e-112">\<add></span><span class="sxs-lookup"><span data-stu-id="adf0e-112">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowaccounts.md)|<span data-ttu-id="adf0e-113">WCF 서비스를 호스팅하고 공유 서비스에 대 한 연결 액세스 권한이 부여 된 프로세스에 대 한 사용자 계정을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="adf0e-113">Adds a user account for processes that host WCF services, and are granted connection access to the sharing service</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="adf0e-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="adf0e-114">Parent Elements</span></span>  
  
|<span data-ttu-id="adf0e-115">요소</span><span class="sxs-lookup"><span data-stu-id="adf0e-115">Element</span></span>|<span data-ttu-id="adf0e-116">설명</span><span class="sxs-lookup"><span data-stu-id="adf0e-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="adf0e-117">[\<net. pipe >](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md) 나 [ \<net.tcp >](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)</span><span class="sxs-lookup"><span data-stu-id="adf0e-117">[\<net.pipe>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md) or [\<net.tcp>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)</span></span>|<span data-ttu-id="adf0e-118">Net Pipe 또는 TCP 공유 서비스의 구성 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="adf0e-118">Specifies configuration settings for the Net Pipe or TCP sharing services.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="adf0e-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="adf0e-119">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
