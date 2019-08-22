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
ms.openlocfilehash: b2e31dee4f5aff2bf6cedf5c4e9ca235695b0a53
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659091"
---
# <a name="specifiedpickupdirectory-element-network-settings"></a><span data-ttu-id="c0c72-102">\<specifiedPickupDirectory > 요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="c0c72-102">\<specifiedPickupDirectory> Element (Network Settings)</span></span>
<span data-ttu-id="c0c72-103">SMTP (Simple Mail Transport Protocol) 서버에 대 한 로컬 디렉터리를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0c72-103">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>  
  
 <span data-ttu-id="c0c72-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="c0c72-104">\<configuration></span></span>  
<span data-ttu-id="c0c72-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="c0c72-105">\<system.net></span></span>  
<span data-ttu-id="c0c72-106">\<mailSettings></span><span class="sxs-lookup"><span data-stu-id="c0c72-106">\<mailSettings></span></span>  
<span data-ttu-id="c0c72-107">\<smtp></span><span class="sxs-lookup"><span data-stu-id="c0c72-107">\<smtp></span></span>  
<span data-ttu-id="c0c72-108">\<specifiedPickupDirectory></span><span class="sxs-lookup"><span data-stu-id="c0c72-108">\<specifiedPickupDirectory></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0c72-109">구문</span><span class="sxs-lookup"><span data-stu-id="c0c72-109">Syntax</span></span>  
  
```xml  
<specifiedPickupDirectory  
  pickupDirectoryLocation="directory"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c0c72-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c0c72-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c0c72-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c0c72-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c0c72-112">특성</span><span class="sxs-lookup"><span data-stu-id="c0c72-112">Attributes</span></span>  
  
|<span data-ttu-id="c0c72-113">특성</span><span class="sxs-lookup"><span data-stu-id="c0c72-113">Attribute</span></span>|<span data-ttu-id="c0c72-114">설명</span><span class="sxs-lookup"><span data-stu-id="c0c72-114">Description</span></span>|  
|---------------|-----------------|  
|`pickupDirectoryLocation`|<span data-ttu-id="c0c72-115">응용 프로그램이 나중에 SMTP 서버에서 처리할 전자 메일을 저장 하는 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="c0c72-115">The directory where applications save email for later processing by the SMTP server.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c0c72-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c0c72-116">Child Elements</span></span>  
 <span data-ttu-id="c0c72-117">없음</span><span class="sxs-lookup"><span data-stu-id="c0c72-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c0c72-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c0c72-118">Parent Elements</span></span>  
  
|<span data-ttu-id="c0c72-119">요소</span><span class="sxs-lookup"><span data-stu-id="c0c72-119">Element</span></span>|<span data-ttu-id="c0c72-120">Description</span><span class="sxs-lookup"><span data-stu-id="c0c72-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c0c72-121">\<smtp > 요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="c0c72-121">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="c0c72-122">SMTP (Simple Mail Transport Protocol) 메일 전송 옵션을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0c72-122">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c0c72-123">설명</span><span class="sxs-lookup"><span data-stu-id="c0c72-123">Remarks</span></span>  
 <span data-ttu-id="c0c72-124">`specifiedPickupDirectory` 특성은 애플리케이션이 SMTP 서버에서 처리할 수 있도록 메일 메시지를 저장하는 디렉터리를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c0c72-124">The `specifiedPickupDirectory` attribute sets the directory where applications save mail messages to be processed by the SMTP server.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c0c72-125">예제</span><span class="sxs-lookup"><span data-stu-id="c0c72-125">Example</span></span>  
 <span data-ttu-id="c0c72-126">다음 예에서는 c:\maildrop을 메일 픽업 디렉터리로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0c72-126">The following example specifies c:\maildrop as the mail pickup directory.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c0c72-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="c0c72-127">See also</span></span>

- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSpecifiedPickupDirectoryElement?displayProperty=nameWithType>
- [<span data-ttu-id="c0c72-128">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="c0c72-128">Network Settings Schema</span></span>](index.md)
