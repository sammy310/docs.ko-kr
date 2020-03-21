---
title: <specifiedPickupDirectory> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#specifiedPickupDirectory
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp/specifiedPickupDirectory
helpviewer_keywords:
- specifiedPickupDirectory element
- <specifiedPickupDirectory> element
ms.assetid: 0121f49d-bff2-4bc6-af06-f1628dcd61f1
ms.openlocfilehash: 4b0cbaf9a7bfe2a9b1610811f4201253d219a6b2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154610"
---
# <a name="specifiedpickupdirectory-element-network-settings"></a><span data-ttu-id="96f94-102">\<specified픽업디렉터> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="96f94-102">\<specifiedPickupDirectory> Element (Network Settings)</span></span>
<span data-ttu-id="96f94-103">SMTP(단순 메일 전송 프로토콜) 서버에 대한 로컬 디렉터리를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="96f94-103">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>  
  
<span data-ttu-id="96f94-104">[**\<구성>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="96f94-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="96f94-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="96f94-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="96f94-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<메일 설정>**](mailsettings-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="96f94-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)</span></span>\
<span data-ttu-id="96f94-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<smtp>**](smtp-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="96f94-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<smtp>**](smtp-element-network-settings.md)</span></span>\
<span data-ttu-id="96f94-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<지정픽업 디렉터리>**</span><span class="sxs-lookup"><span data-stu-id="96f94-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<specifiedPickupDirectory>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96f94-109">구문</span><span class="sxs-lookup"><span data-stu-id="96f94-109">Syntax</span></span>  
  
```xml  
<specifiedPickupDirectory  
  pickupDirectoryLocation="directory"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="96f94-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="96f94-110">Attributes and Elements</span></span>  
 <span data-ttu-id="96f94-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="96f94-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="96f94-112">특성</span><span class="sxs-lookup"><span data-stu-id="96f94-112">Attributes</span></span>  
  
|<span data-ttu-id="96f94-113">attribute</span><span class="sxs-lookup"><span data-stu-id="96f94-113">Attribute</span></span>|<span data-ttu-id="96f94-114">Description</span><span class="sxs-lookup"><span data-stu-id="96f94-114">Description</span></span>|  
|---------------|-----------------|  
|`pickupDirectoryLocation`|<span data-ttu-id="96f94-115">응용 프로그램이 SMTP 서버에서 나중에 처리하기 위해 전자 메일을 저장하는 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="96f94-115">The directory where applications save email for later processing by the SMTP server.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="96f94-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="96f94-116">Child Elements</span></span>  
 <span data-ttu-id="96f94-117">없음</span><span class="sxs-lookup"><span data-stu-id="96f94-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="96f94-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="96f94-118">Parent Elements</span></span>  
  
|<span data-ttu-id="96f94-119">요소</span><span class="sxs-lookup"><span data-stu-id="96f94-119">Element</span></span>|<span data-ttu-id="96f94-120">Description</span><span class="sxs-lookup"><span data-stu-id="96f94-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="96f94-121">\<smtp> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="96f94-121">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="96f94-122">간단한 메일 전송 프로토콜(SMTP) 메일 전송 옵션을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="96f94-122">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="96f94-123">설명</span><span class="sxs-lookup"><span data-stu-id="96f94-123">Remarks</span></span>  
 <span data-ttu-id="96f94-124">`specifiedPickupDirectory` 특성은 애플리케이션이 SMTP 서버에서 처리할 수 있도록 메일 메시지를 저장하는 디렉터리를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="96f94-124">The `specifiedPickupDirectory` attribute sets the directory where applications save mail messages to be processed by the SMTP server.</span></span>  
  
## <a name="example"></a><span data-ttu-id="96f94-125">예제</span><span class="sxs-lookup"><span data-stu-id="96f94-125">Example</span></span>  
 <span data-ttu-id="96f94-126">다음 예제는 c:\maildrop을 메일 픽업 디렉터리로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="96f94-126">The following example specifies c:\maildrop as the mail pickup directory.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="SpecifiedPickupDirectory">  
        <specifiedPickupDirectory  
          pickupDirectoryLocation="c:\maildrop"  
        />  
      </smtp>  
    </mailSettings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="96f94-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="96f94-127">See also</span></span>

- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSpecifiedPickupDirectoryElement?displayProperty=nameWithType>
- [<span data-ttu-id="96f94-128">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="96f94-128">Network Settings Schema</span></span>](index.md)
