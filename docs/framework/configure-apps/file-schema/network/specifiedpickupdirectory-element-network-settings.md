---
title: <specifiedPickupDirectory> 요소(네트워크 설정)
description: <specifiedPickupDirectory>네트워크 설정 요소는 .NET Framework의 SMTP 서버 옵션에 대 한 로컬 디렉터리를 구성 합니다.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#specifiedPickupDirectory
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp/specifiedPickupDirectory
helpviewer_keywords:
- specifiedPickupDirectory element
- <specifiedPickupDirectory> element
ms.assetid: 0121f49d-bff2-4bc6-af06-f1628dcd61f1
ms.openlocfilehash: f0c4c1845e9542d0f3b836ff03f16bdf2979ebd8
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504500"
---
# <a name="specifiedpickupdirectory-element-network-settings"></a><span data-ttu-id="aeccb-103">\<specifiedPickupDirectory> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="aeccb-103">\<specifiedPickupDirectory> Element (Network Settings)</span></span>
<span data-ttu-id="aeccb-104">SMTP (Simple Mail Transport Protocol) 서버에 대 한 로컬 디렉터리를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeccb-104">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<smtp>**](smtp-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<specifiedPickupDirectory>**  
  
## <a name="syntax"></a><span data-ttu-id="aeccb-105">구문</span><span class="sxs-lookup"><span data-stu-id="aeccb-105">Syntax</span></span>  
  
```xml  
<specifiedPickupDirectory  
  pickupDirectoryLocation="directory"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aeccb-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="aeccb-106">Attributes and Elements</span></span>  
 <span data-ttu-id="aeccb-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="aeccb-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aeccb-108">특성</span><span class="sxs-lookup"><span data-stu-id="aeccb-108">Attributes</span></span>  
  
|<span data-ttu-id="aeccb-109">특성</span><span class="sxs-lookup"><span data-stu-id="aeccb-109">Attribute</span></span>|<span data-ttu-id="aeccb-110">설명</span><span class="sxs-lookup"><span data-stu-id="aeccb-110">Description</span></span>|  
|---------------|-----------------|  
|`pickupDirectoryLocation`|<span data-ttu-id="aeccb-111">응용 프로그램이 나중에 SMTP 서버에서 처리할 전자 메일을 저장 하는 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="aeccb-111">The directory where applications save email for later processing by the SMTP server.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="aeccb-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="aeccb-112">Child Elements</span></span>  
 <span data-ttu-id="aeccb-113">없음</span><span class="sxs-lookup"><span data-stu-id="aeccb-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="aeccb-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="aeccb-114">Parent Elements</span></span>  
  
|<span data-ttu-id="aeccb-115">요소</span><span class="sxs-lookup"><span data-stu-id="aeccb-115">Element</span></span>|<span data-ttu-id="aeccb-116">설명</span><span class="sxs-lookup"><span data-stu-id="aeccb-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aeccb-117">\<smtp>요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="aeccb-117">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="aeccb-118">SMTP (Simple Mail Transport Protocol) 메일 전송 옵션을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeccb-118">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aeccb-119">설명</span><span class="sxs-lookup"><span data-stu-id="aeccb-119">Remarks</span></span>  
 <span data-ttu-id="aeccb-120">`specifiedPickupDirectory` 특성은 애플리케이션이 SMTP 서버에서 처리할 수 있도록 메일 메시지를 저장하는 디렉터리를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="aeccb-120">The `specifiedPickupDirectory` attribute sets the directory where applications save mail messages to be processed by the SMTP server.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aeccb-121">예제</span><span class="sxs-lookup"><span data-stu-id="aeccb-121">Example</span></span>  
 <span data-ttu-id="aeccb-122">다음 예에서는 c:\maildrop을 메일 픽업 디렉터리로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeccb-122">The following example specifies c:\maildrop as the mail pickup directory.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="aeccb-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="aeccb-123">See also</span></span>

- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSpecifiedPickupDirectoryElement?displayProperty=nameWithType>
- [<span data-ttu-id="aeccb-124">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="aeccb-124">Network Settings Schema</span></span>](index.md)
