---
title: <privacyNoticeAt>
ms.date: 03/30/2017
ms.assetid: 4cc96942-4eb9-4241-b2fd-45aa239915e8
ms.openlocfilehash: 2ff70d3a8636970434582e417e4549ab6b433fc1
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738769"
---
# \<privacyNoticeAt>
<span data-ttu-id="28ab5-101">`wsFederationHttp` 바인딩에 사용되는 개인 정보 알림을 지정하는 구성 요소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="28ab5-101">Represents a configuration element that specifies a privacy notice used in `wsFederationHttp` binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<privacyNotice>**  
  
## <a name="syntax"></a><span data-ttu-id="28ab5-102">구문</span><span class="sxs-lookup"><span data-stu-id="28ab5-102">Syntax</span></span>  
  
```xml  
<privacyNotice url="String"
               version="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="28ab5-103">Type</span><span class="sxs-lookup"><span data-stu-id="28ab5-103">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="28ab5-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="28ab5-104">Attributes and Elements</span></span>  
 <span data-ttu-id="28ab5-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="28ab5-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="28ab5-106">특성</span><span class="sxs-lookup"><span data-stu-id="28ab5-106">Attributes</span></span>  
  
|<span data-ttu-id="28ab5-107">attribute</span><span class="sxs-lookup"><span data-stu-id="28ab5-107">Attribute</span></span>|<span data-ttu-id="28ab5-108">Description</span><span class="sxs-lookup"><span data-stu-id="28ab5-108">Description</span></span>|  
|---------------|-----------------|  
|`url`|<span data-ttu-id="28ab5-109">개인 정보 알림이 있는 URI를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="28ab5-109">A string that specifies the URI at which the privacy notice is located.</span></span>|  
|`version`|<span data-ttu-id="28ab5-110">이 개인 정보 알림의 버전을 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="28ab5-110">An integer that specifies the version of this privacy notice.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="28ab5-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="28ab5-111">Child Elements</span></span>  
 <span data-ttu-id="28ab5-112">없음</span><span class="sxs-lookup"><span data-stu-id="28ab5-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="28ab5-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="28ab5-113">Parent Elements</span></span>  
  
|<span data-ttu-id="28ab5-114">요소</span><span class="sxs-lookup"><span data-stu-id="28ab5-114">Element</span></span>|<span data-ttu-id="28ab5-115">Description</span><span class="sxs-lookup"><span data-stu-id="28ab5-115">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="28ab5-116">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="28ab5-116">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="28ab5-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="28ab5-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.PrivacyNoticeElement>
- <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="28ab5-118">바인딩</span><span class="sxs-lookup"><span data-stu-id="28ab5-118">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="28ab5-119">바인딩 확장명</span><span class="sxs-lookup"><span data-stu-id="28ab5-119">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="28ab5-120">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="28ab5-120">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
