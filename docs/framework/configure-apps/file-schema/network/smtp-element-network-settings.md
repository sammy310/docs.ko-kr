---
title: <smtp> 요소(네트워크 설정)
description: <smtp>네트워크 설정 요소는 .NET Framework에서 전자 메일을 보내기 위한 배달 형식, 배달 방법 및 보낸 사람 주소를 구성 합니다.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp
- http://schemas.microsoft.com/.NetConfiguration/v2.0#smtp
helpviewer_keywords:
- <smtp> element
- smtp element
ms.assetid: 220b0329-e384-4e0c-86b4-0945ad17efd9
ms.openlocfilehash: 58f496b4a07f7d5531df897dd54bb6176111f1c4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91178322"
---
# <a name="smtp-element-network-settings"></a><span data-ttu-id="839cb-103">\<smtp> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="839cb-103">\<smtp> Element (Network Settings)</span></span>

<span data-ttu-id="839cb-104">전자 메일을 보내기 위한 배달 형식, 배달 방법 및 보낸 사람 주소를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="839cb-104">Configures the delivery format, delivery method, and from address for sending emails.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<smtp>**
  
## <a name="syntax"></a><span data-ttu-id="839cb-105">구문</span><span class="sxs-lookup"><span data-stu-id="839cb-105">Syntax</span></span>  
  
```xml  
<smtp  
  deliveryFormat="format"  
  deliveryMethod="method"  
  from="from address">
    <specifiedPickupDirectory>...</specifiedPickupDirectory>  
    <network>...</network>  
</smtp>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="839cb-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="839cb-106">Attributes and Elements</span></span>  

 <span data-ttu-id="839cb-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="839cb-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="839cb-108">특성</span><span class="sxs-lookup"><span data-stu-id="839cb-108">Attributes</span></span>  
  
|<span data-ttu-id="839cb-109">attribute</span><span class="sxs-lookup"><span data-stu-id="839cb-109">Attribute</span></span>|<span data-ttu-id="839cb-110">설명</span><span class="sxs-lookup"><span data-stu-id="839cb-110">Description</span></span>|  
|---------------|-----------------|  
|`deliveryFormat`|<span data-ttu-id="839cb-111">보내는 전자 메일의 배달 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="839cb-111">Specifies the delivery format for outgoing emails.</span></span> <span data-ttu-id="839cb-112">허용 가능한 값은 SevenBit와 International입니다.</span><span class="sxs-lookup"><span data-stu-id="839cb-112">Acceptable values are SevenBit and International.</span></span>|  
|`deliveryMethod`|<span data-ttu-id="839cb-113">전자 메일에 대 한 배달 방법을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="839cb-113">Specifies the delivery method for emails.</span></span> <span data-ttu-id="839cb-114">허용 되는 값은 Network, PickupDirectoryFromIis 및 SpecifiedPickupDirectory입니다.</span><span class="sxs-lookup"><span data-stu-id="839cb-114">Acceptable values are Network, PickupDirectoryFromIis, and SpecifiedPickupDirectory.</span></span>|  
|`from`|<span data-ttu-id="839cb-115">보내는 전자 메일의 보낸 사람 주소를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="839cb-115">Specifies the from address for outgoing emails.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="839cb-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="839cb-116">Child Elements</span></span>  
  
|<span data-ttu-id="839cb-117">attribute</span><span class="sxs-lookup"><span data-stu-id="839cb-117">Attribute</span></span>|<span data-ttu-id="839cb-118">설명</span><span class="sxs-lookup"><span data-stu-id="839cb-118">Description</span></span>|  
|---------------|-----------------|  
|`specifiedPickupDirectory`|<span data-ttu-id="839cb-119">SMTP (Simple Mail Transport Protocol) 서버에 대 한 로컬 디렉터리를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="839cb-119">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>|  
|`network`|<span data-ttu-id="839cb-120">외부 SMTP 서버에 대 한 네트워크 옵션을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="839cb-120">Configures the network options for an external SMTP server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="839cb-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="839cb-121">Parent Elements</span></span>  
  
|<span data-ttu-id="839cb-122">**요소**</span><span class="sxs-lookup"><span data-stu-id="839cb-122">**Element**</span></span>|<span data-ttu-id="839cb-123">**설명**</span><span class="sxs-lookup"><span data-stu-id="839cb-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="839cb-124">\<mailSettings> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="839cb-124">\<mailSettings> Element (Network Settings)</span></span>](mailsettings-element-network-settings.md)|<span data-ttu-id="839cb-125">메일 전송 옵션을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="839cb-125">Configures mail sending options.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="839cb-126">예제</span><span class="sxs-lookup"><span data-stu-id="839cb-126">Example</span></span>  

 <span data-ttu-id="839cb-127">다음 예에서는 기본 네트워크 자격 증명을 사용 하 여 전자 메일을 보낼 적절 한 SMTP 매개 변수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="839cb-127">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="839cb-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="839cb-128">See also</span></span>

- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpDeliveryFormat>
- <xref:System.Net.Mail.SmtpDeliveryMethod>
- [<span data-ttu-id="839cb-129">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="839cb-129">Network Settings Schema</span></span>](index.md)
