---
description: 다음에 대해 자세히 알아보세요. <privacyNoticeAt>
title: <privacyNoticeAt>
ms.date: 03/30/2017
ms.assetid: 4cc96942-4eb9-4241-b2fd-45aa239915e8
ms.openlocfilehash: 2e38d43becd783cc50afba5a029d3ab9905ec15a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99683504"
---
# \<privacyNoticeAt>

<span data-ttu-id="354ab-102">`wsFederationHttp` 바인딩에 사용되는 개인 정보 알림을 지정하는 구성 요소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="354ab-102">Represents a configuration element that specifies a privacy notice used in `wsFederationHttp` binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<privacyNotice>**  
  
## <a name="syntax"></a><span data-ttu-id="354ab-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="354ab-103">Syntax</span></span>  
  
```xml  
<privacyNotice url="String"
               version="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="354ab-104">Type</span><span class="sxs-lookup"><span data-stu-id="354ab-104">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="354ab-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="354ab-105">Attributes and Elements</span></span>  

 <span data-ttu-id="354ab-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="354ab-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="354ab-107">특성</span><span class="sxs-lookup"><span data-stu-id="354ab-107">Attributes</span></span>  
  
|<span data-ttu-id="354ab-108">attribute</span><span class="sxs-lookup"><span data-stu-id="354ab-108">Attribute</span></span>|<span data-ttu-id="354ab-109">설명</span><span class="sxs-lookup"><span data-stu-id="354ab-109">Description</span></span>|  
|---------------|-----------------|  
|`url`|<span data-ttu-id="354ab-110">개인 정보 알림이 있는 URI를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="354ab-110">A string that specifies the URI at which the privacy notice is located.</span></span>|  
|`version`|<span data-ttu-id="354ab-111">이 개인 정보 알림의 버전을 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="354ab-111">An integer that specifies the version of this privacy notice.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="354ab-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="354ab-112">Child Elements</span></span>  

 <span data-ttu-id="354ab-113">없음</span><span class="sxs-lookup"><span data-stu-id="354ab-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="354ab-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="354ab-114">Parent Elements</span></span>  
  
|<span data-ttu-id="354ab-115">요소</span><span class="sxs-lookup"><span data-stu-id="354ab-115">Element</span></span>|<span data-ttu-id="354ab-116">설명</span><span class="sxs-lookup"><span data-stu-id="354ab-116">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="354ab-117">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="354ab-117">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="354ab-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="354ab-118">See also</span></span>

- <xref:System.ServiceModel.Configuration.PrivacyNoticeElement>
- <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="354ab-119">바인딩</span><span class="sxs-lookup"><span data-stu-id="354ab-119">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="354ab-120">바인딩 확장명</span><span class="sxs-lookup"><span data-stu-id="354ab-120">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="354ab-121">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="354ab-121">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
