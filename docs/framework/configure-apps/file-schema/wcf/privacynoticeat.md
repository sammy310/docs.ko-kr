---
title: <privacyNoticeAt>
ms.date: 03/30/2017
ms.assetid: 4cc96942-4eb9-4241-b2fd-45aa239915e8
ms.openlocfilehash: 5e772e23b21c566c906be854e33b924698dcf3e0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158710"
---
# \<privacyNoticeAt>

<span data-ttu-id="b0a81-101">`wsFederationHttp` 바인딩에 사용되는 개인 정보 알림을 지정하는 구성 요소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b0a81-101">Represents a configuration element that specifies a privacy notice used in `wsFederationHttp` binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<privacyNotice>**  
  
## <a name="syntax"></a><span data-ttu-id="b0a81-102">구문</span><span class="sxs-lookup"><span data-stu-id="b0a81-102">Syntax</span></span>  
  
```xml  
<privacyNotice url="String"
               version="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="b0a81-103">형식</span><span class="sxs-lookup"><span data-stu-id="b0a81-103">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b0a81-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b0a81-104">Attributes and Elements</span></span>  

 <span data-ttu-id="b0a81-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b0a81-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b0a81-106">특성</span><span class="sxs-lookup"><span data-stu-id="b0a81-106">Attributes</span></span>  
  
|<span data-ttu-id="b0a81-107">attribute</span><span class="sxs-lookup"><span data-stu-id="b0a81-107">Attribute</span></span>|<span data-ttu-id="b0a81-108">설명</span><span class="sxs-lookup"><span data-stu-id="b0a81-108">Description</span></span>|  
|---------------|-----------------|  
|`url`|<span data-ttu-id="b0a81-109">개인 정보 알림이 있는 URI를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="b0a81-109">A string that specifies the URI at which the privacy notice is located.</span></span>|  
|`version`|<span data-ttu-id="b0a81-110">이 개인 정보 알림의 버전을 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="b0a81-110">An integer that specifies the version of this privacy notice.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b0a81-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b0a81-111">Child Elements</span></span>  

 <span data-ttu-id="b0a81-112">없음</span><span class="sxs-lookup"><span data-stu-id="b0a81-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b0a81-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b0a81-113">Parent Elements</span></span>  
  
|<span data-ttu-id="b0a81-114">요소</span><span class="sxs-lookup"><span data-stu-id="b0a81-114">Element</span></span>|<span data-ttu-id="b0a81-115">설명</span><span class="sxs-lookup"><span data-stu-id="b0a81-115">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="b0a81-116">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b0a81-116">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b0a81-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b0a81-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.PrivacyNoticeElement>
- <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="b0a81-118">바인딩하</span><span class="sxs-lookup"><span data-stu-id="b0a81-118">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="b0a81-119">바인딩 확장명</span><span class="sxs-lookup"><span data-stu-id="b0a81-119">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="b0a81-120">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="b0a81-120">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
