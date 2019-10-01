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
ms.openlocfilehash: 2105a6dd25a7f6e5e4c1ce286be7f60beae1dca0
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697603"
---
# <a name="smtp-element-network-settings"></a><span data-ttu-id="9b3b6-102">\<smtp > 요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="9b3b6-102">\<smtp> Element (Network Settings)</span></span>
<span data-ttu-id="9b3b6-103">전자 메일을 보내기 위한 배달 형식, 배달 방법 및 보낸 사람 주소를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b3b6-103">Configures the delivery format, delivery method, and from address for sending emails.</span></span>  
  
[<span data-ttu-id="9b3b6-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="9b3b6-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="9b3b6-105">&nbsp; @ no__t-1[ **@no__t -4c.net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="9b3b6-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="9b3b6-106">&nbsp; @ no__t-1 @ no__t-2[ **\<mailSettings >** ](mailsettings-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="9b3b6-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)</span></span>  
<span data-ttu-id="9b3b6-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t @ no__t-4 @ no__t-5 **\<smtp >**</span><span class="sxs-lookup"><span data-stu-id="9b3b6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<smtp>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b3b6-108">구문</span><span class="sxs-lookup"><span data-stu-id="9b3b6-108">Syntax</span></span>  
  
```xml  
<smtp  
  deliveryFormat="format"  
  deliveryMethod="method"  
  from="from address">
    <specifiedPickupDirectory>...</specifiedPickupDirectory>  
    <network>...</network>  
</smtp>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9b3b6-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="9b3b6-109">Attributes and Elements</span></span>  
 <span data-ttu-id="9b3b6-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9b3b6-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9b3b6-111">특성</span><span class="sxs-lookup"><span data-stu-id="9b3b6-111">Attributes</span></span>  
  
|<span data-ttu-id="9b3b6-112">특성</span><span class="sxs-lookup"><span data-stu-id="9b3b6-112">Attribute</span></span>|<span data-ttu-id="9b3b6-113">설명</span><span class="sxs-lookup"><span data-stu-id="9b3b6-113">Description</span></span>|  
|---------------|-----------------|  
|`deliveryFormat`|<span data-ttu-id="9b3b6-114">보내는 전자 메일의 배달 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b3b6-114">Specifies the delivery format for outgoing emails.</span></span> <span data-ttu-id="9b3b6-115">허용 가능한 값은 SevenBit와 International입니다.</span><span class="sxs-lookup"><span data-stu-id="9b3b6-115">Acceptable values are SevenBit and International.</span></span>|  
|`deliveryMethod`|<span data-ttu-id="9b3b6-116">전자 메일에 대 한 배달 방법을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b3b6-116">Specifies the delivery method for emails.</span></span> <span data-ttu-id="9b3b6-117">허용 되는 값은 Network, PickupDirectoryFromIis 및 SpecifiedPickupDirectory입니다.</span><span class="sxs-lookup"><span data-stu-id="9b3b6-117">Acceptable values are Network, PickupDirectoryFromIis, and SpecifiedPickupDirectory.</span></span>|  
|`from`|<span data-ttu-id="9b3b6-118">보내는 전자 메일의 보낸 사람 주소를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b3b6-118">Specifies the from address for outgoing emails.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9b3b6-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="9b3b6-119">Child Elements</span></span>  
  
|<span data-ttu-id="9b3b6-120">특성</span><span class="sxs-lookup"><span data-stu-id="9b3b6-120">Attribute</span></span>|<span data-ttu-id="9b3b6-121">설명</span><span class="sxs-lookup"><span data-stu-id="9b3b6-121">Description</span></span>|  
|---------------|-----------------|  
|`specifiedPickupDirectory`|<span data-ttu-id="9b3b6-122">SMTP (Simple Mail Transport Protocol) 서버에 대 한 로컬 디렉터리를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b3b6-122">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>|  
|`network`|<span data-ttu-id="9b3b6-123">외부 SMTP 서버에 대 한 네트워크 옵션을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b3b6-123">Configures the network options for an external SMTP server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9b3b6-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="9b3b6-124">Parent Elements</span></span>  
  
|<span data-ttu-id="9b3b6-125">**요소**</span><span class="sxs-lookup"><span data-stu-id="9b3b6-125">**Element**</span></span>|<span data-ttu-id="9b3b6-126">**설명**</span><span class="sxs-lookup"><span data-stu-id="9b3b6-126">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="9b3b6-127">\<mailSettings> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="9b3b6-127">\<mailSettings> Element (Network Settings)</span></span>](mailsettings-element-network-settings.md)|<span data-ttu-id="9b3b6-128">메일 전송 옵션을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b3b6-128">Configures mail sending options.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="9b3b6-129">예제</span><span class="sxs-lookup"><span data-stu-id="9b3b6-129">Example</span></span>  
 <span data-ttu-id="9b3b6-130">다음 예에서는 기본 네트워크 자격 증명을 사용 하 여 전자 메일을 보낼 적절 한 SMTP 매개 변수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b3b6-130">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9b3b6-131">참조</span><span class="sxs-lookup"><span data-stu-id="9b3b6-131">See also</span></span>

- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpDeliveryFormat>
- <xref:System.Net.Mail.SmtpDeliveryMethod>
- [<span data-ttu-id="9b3b6-132">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="9b3b6-132">Network Settings Schema</span></span>](index.md)
