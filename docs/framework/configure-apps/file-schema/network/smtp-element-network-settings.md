---
title: <smtp> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp
- http://schemas.microsoft.com/.NetConfiguration/v2.0#smtp
helpviewer_keywords:
- <smtp> element
- smtp element
ms.assetid: 220b0329-e384-4e0c-86b4-0945ad17efd9
ms.openlocfilehash: 625c3cb82a8659c742b540724e5cf31be65a705e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "74089096"
---
# <a name="smtp-element-network-settings"></a><span data-ttu-id="6b652-102">\<smtp> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="6b652-102">\<smtp> Element (Network Settings)</span></span>
<span data-ttu-id="6b652-103">전자 메일을 보내기 위한 배달 형식, 배달 방법 및 보낸 사람 주소를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b652-103">Configures the delivery format, delivery method, and from address for sending emails.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<smtp>**
  
## <a name="syntax"></a><span data-ttu-id="6b652-104">구문</span><span class="sxs-lookup"><span data-stu-id="6b652-104">Syntax</span></span>  
  
```xml  
<smtp  
  deliveryFormat="format"  
  deliveryMethod="method"  
  from="from address">
    <specifiedPickupDirectory>...</specifiedPickupDirectory>  
    <network>...</network>  
</smtp>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6b652-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="6b652-105">Attributes and Elements</span></span>  
 <span data-ttu-id="6b652-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6b652-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6b652-107">특성</span><span class="sxs-lookup"><span data-stu-id="6b652-107">Attributes</span></span>  
  
|<span data-ttu-id="6b652-108">attribute</span><span class="sxs-lookup"><span data-stu-id="6b652-108">Attribute</span></span>|<span data-ttu-id="6b652-109">Description</span><span class="sxs-lookup"><span data-stu-id="6b652-109">Description</span></span>|  
|---------------|-----------------|  
|`deliveryFormat`|<span data-ttu-id="6b652-110">보내는 전자 메일의 배달 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b652-110">Specifies the delivery format for outgoing emails.</span></span> <span data-ttu-id="6b652-111">허용 가능한 값은 SevenBit와 International입니다.</span><span class="sxs-lookup"><span data-stu-id="6b652-111">Acceptable values are SevenBit and International.</span></span>|  
|`deliveryMethod`|<span data-ttu-id="6b652-112">전자 메일에 대 한 배달 방법을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b652-112">Specifies the delivery method for emails.</span></span> <span data-ttu-id="6b652-113">허용 되는 값은 Network, PickupDirectoryFromIis 및 SpecifiedPickupDirectory입니다.</span><span class="sxs-lookup"><span data-stu-id="6b652-113">Acceptable values are Network, PickupDirectoryFromIis, and SpecifiedPickupDirectory.</span></span>|  
|`from`|<span data-ttu-id="6b652-114">보내는 전자 메일의 보낸 사람 주소를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b652-114">Specifies the from address for outgoing emails.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6b652-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="6b652-115">Child Elements</span></span>  
  
|<span data-ttu-id="6b652-116">attribute</span><span class="sxs-lookup"><span data-stu-id="6b652-116">Attribute</span></span>|<span data-ttu-id="6b652-117">Description</span><span class="sxs-lookup"><span data-stu-id="6b652-117">Description</span></span>|  
|---------------|-----------------|  
|`specifiedPickupDirectory`|<span data-ttu-id="6b652-118">SMTP (Simple Mail Transport Protocol) 서버에 대 한 로컬 디렉터리를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b652-118">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>|  
|`network`|<span data-ttu-id="6b652-119">외부 SMTP 서버에 대 한 네트워크 옵션을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b652-119">Configures the network options for an external SMTP server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6b652-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="6b652-120">Parent Elements</span></span>  
  
|<span data-ttu-id="6b652-121">**요소**</span><span class="sxs-lookup"><span data-stu-id="6b652-121">**Element**</span></span>|<span data-ttu-id="6b652-122">**설명**</span><span class="sxs-lookup"><span data-stu-id="6b652-122">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="6b652-123">\<mailSettings>요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="6b652-123">\<mailSettings> Element (Network Settings)</span></span>](mailsettings-element-network-settings.md)|<span data-ttu-id="6b652-124">메일 전송 옵션을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b652-124">Configures mail sending options.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="6b652-125">예제</span><span class="sxs-lookup"><span data-stu-id="6b652-125">Example</span></span>  
 <span data-ttu-id="6b652-126">다음 예에서는 기본 네트워크 자격 증명을 사용 하 여 전자 메일을 보낼 적절 한 SMTP 매개 변수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b652-126">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="Network" deliveryFormat="SevenBit"  from="ben@contoso.com">  
        <network  
          host="localhost"  
          port="25"  
          defaultCredentials="true"  
        />  
      </smtp>  
    </mailSettings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6b652-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6b652-127">See also</span></span>

- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpDeliveryFormat>
- <xref:System.Net.Mail.SmtpDeliveryMethod>
- [<span data-ttu-id="6b652-128">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="6b652-128">Network Settings Schema</span></span>](index.md)
