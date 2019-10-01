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
ms.openlocfilehash: 47aa357dac8b6bf71ce8c391004af16f8c98e347
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697599"
---
# <a name="specifiedpickupdirectory-element-network-settings"></a><span data-ttu-id="7c6f1-102">\<specifiedPickupDirectory > 요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="7c6f1-102">\<specifiedPickupDirectory> Element (Network Settings)</span></span>
<span data-ttu-id="7c6f1-103">SMTP (Simple Mail Transport Protocol) 서버에 대 한 로컬 디렉터리를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c6f1-103">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>  
  
[<span data-ttu-id="7c6f1-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="7c6f1-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="7c6f1-105">&nbsp; @ no__t-1[ **@no__t -4c.net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="7c6f1-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="7c6f1-106">&nbsp; @ no__t-1 @ no__t-2[ **\<mailSettings >** ](mailsettings-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="7c6f1-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)</span></span>  
<span data-ttu-id="7c6f1-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t @ no__t-4 @ no__t-5[ **\<smtp >** ](smtp-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="7c6f1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<smtp>**](smtp-element-network-settings.md)</span></span>  
<span data-ttu-id="7c6f1-108">&nbsp; @ no__t-1 @ no__t @ no__t @ @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7 **\<specifiedPickupDirectory >**</span><span class="sxs-lookup"><span data-stu-id="7c6f1-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<specifiedPickupDirectory>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c6f1-109">구문</span><span class="sxs-lookup"><span data-stu-id="7c6f1-109">Syntax</span></span>  
  
```xml  
<specifiedPickupDirectory  
  pickupDirectoryLocation="directory"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7c6f1-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="7c6f1-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7c6f1-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7c6f1-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7c6f1-112">특성</span><span class="sxs-lookup"><span data-stu-id="7c6f1-112">Attributes</span></span>  
  
|<span data-ttu-id="7c6f1-113">특성</span><span class="sxs-lookup"><span data-stu-id="7c6f1-113">Attribute</span></span>|<span data-ttu-id="7c6f1-114">설명</span><span class="sxs-lookup"><span data-stu-id="7c6f1-114">Description</span></span>|  
|---------------|-----------------|  
|`pickupDirectoryLocation`|<span data-ttu-id="7c6f1-115">응용 프로그램이 나중에 SMTP 서버에서 처리할 전자 메일을 저장 하는 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="7c6f1-115">The directory where applications save email for later processing by the SMTP server.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7c6f1-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="7c6f1-116">Child Elements</span></span>  
 <span data-ttu-id="7c6f1-117">없음</span><span class="sxs-lookup"><span data-stu-id="7c6f1-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7c6f1-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="7c6f1-118">Parent Elements</span></span>  
  
|<span data-ttu-id="7c6f1-119">요소</span><span class="sxs-lookup"><span data-stu-id="7c6f1-119">Element</span></span>|<span data-ttu-id="7c6f1-120">설명</span><span class="sxs-lookup"><span data-stu-id="7c6f1-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7c6f1-121">\<smtp > 요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="7c6f1-121">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="7c6f1-122">SMTP (Simple Mail Transport Protocol) 메일 전송 옵션을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c6f1-122">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7c6f1-123">설명</span><span class="sxs-lookup"><span data-stu-id="7c6f1-123">Remarks</span></span>  
 <span data-ttu-id="7c6f1-124">`specifiedPickupDirectory` 특성은 애플리케이션이 SMTP 서버에서 처리할 수 있도록 메일 메시지를 저장하는 디렉터리를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7c6f1-124">The `specifiedPickupDirectory` attribute sets the directory where applications save mail messages to be processed by the SMTP server.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7c6f1-125">예제</span><span class="sxs-lookup"><span data-stu-id="7c6f1-125">Example</span></span>  
 <span data-ttu-id="7c6f1-126">다음 예에서는 c:\maildrop을 메일 픽업 디렉터리로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c6f1-126">The following example specifies c:\maildrop as the mail pickup directory.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7c6f1-127">참조</span><span class="sxs-lookup"><span data-stu-id="7c6f1-127">See also</span></span>

- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSpecifiedPickupDirectoryElement?displayProperty=nameWithType>
- [<span data-ttu-id="7c6f1-128">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="7c6f1-128">Network Settings Schema</span></span>](index.md)
