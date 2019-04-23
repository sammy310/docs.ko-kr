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
ms.openlocfilehash: a459fee557285935c383dcfaf512c8a8a9aea570
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59099276"
---
# <a name="specifiedpickupdirectory-element-network-settings"></a><span data-ttu-id="b4d0a-102">\<specifiedPickupDirectory > 요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="b4d0a-102">\<specifiedPickupDirectory> Element (Network Settings)</span></span>
<span data-ttu-id="b4d0a-103">전송 프로토콜 SMTP (Simple Mail) 서버에 대 한 로컬 디렉터리를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="b4d0a-103">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>  
  
 <span data-ttu-id="b4d0a-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="b4d0a-104">\<configuration></span></span>  
<span data-ttu-id="b4d0a-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="b4d0a-105">\<system.net></span></span>  
<span data-ttu-id="b4d0a-106">\<mailSettings></span><span class="sxs-lookup"><span data-stu-id="b4d0a-106">\<mailSettings></span></span>  
<span data-ttu-id="b4d0a-107">\<smtp></span><span class="sxs-lookup"><span data-stu-id="b4d0a-107">\<smtp></span></span>  
<span data-ttu-id="b4d0a-108">\<specifiedPickupDirectory></span><span class="sxs-lookup"><span data-stu-id="b4d0a-108">\<specifiedPickupDirectory></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4d0a-109">구문</span><span class="sxs-lookup"><span data-stu-id="b4d0a-109">Syntax</span></span>  
  
```xml  
<specifiedPickupDirectory  
  pickupDirectoryLocation="directory"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b4d0a-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b4d0a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b4d0a-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b4d0a-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b4d0a-112">특성</span><span class="sxs-lookup"><span data-stu-id="b4d0a-112">Attributes</span></span>  
  
|<span data-ttu-id="b4d0a-113">특성</span><span class="sxs-lookup"><span data-stu-id="b4d0a-113">Attribute</span></span>|<span data-ttu-id="b4d0a-114">설명</span><span class="sxs-lookup"><span data-stu-id="b4d0a-114">Description</span></span>|  
|---------------|-----------------|  
|`pickupDirectoryLocation`|<span data-ttu-id="b4d0a-115">응용 프로그램에서 SMTP 서버에서 나중에 처리할 전자 메일을 저장할 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="b4d0a-115">The directory where applications save email for later processing by the SMTP server.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b4d0a-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b4d0a-116">Child Elements</span></span>  
 <span data-ttu-id="b4d0a-117">없음</span><span class="sxs-lookup"><span data-stu-id="b4d0a-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b4d0a-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b4d0a-118">Parent Elements</span></span>  
  
|<span data-ttu-id="b4d0a-119">요소</span><span class="sxs-lookup"><span data-stu-id="b4d0a-119">Element</span></span>|<span data-ttu-id="b4d0a-120">설명</span><span class="sxs-lookup"><span data-stu-id="b4d0a-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b4d0a-121">\<smtp > 요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="b4d0a-121">\<smtp> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|<span data-ttu-id="b4d0a-122">단순 메일 전송 프로토콜 (SMTP) 메일 보내기 옵션을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4d0a-122">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b4d0a-123">설명</span><span class="sxs-lookup"><span data-stu-id="b4d0a-123">Remarks</span></span>  
 <span data-ttu-id="b4d0a-124">`specifiedPickupDirectory` 특성은 응용 프로그램이 SMTP 서버에서 처리할 수 있도록 메일 메시지를 저장하는 디렉터리를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b4d0a-124">The `specifiedPickupDirectory` attribute sets the directory where applications save mail messages to be processed by the SMTP server.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b4d0a-125">예제</span><span class="sxs-lookup"><span data-stu-id="b4d0a-125">Example</span></span>  
 <span data-ttu-id="b4d0a-126">다음 예제에서는 메일 픽업 디렉터리로 c:\maildrop를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b4d0a-126">The following example specifies c:\maildrop as the mail pickup directory.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b4d0a-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="b4d0a-127">See also</span></span>

- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSpecifiedPickupDirectoryElement?displayProperty=nameWithType>
- [<span data-ttu-id="b4d0a-128">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="b4d0a-128">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
