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
ms.sourcegitcommit: 0a798a7e9680e2d0a5a81a3eaa203870ea782883
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/03/2020
ms.locfileid: "79154610"
---
# <a name="specifiedpickupdirectory-element-network-settings"></a><span data-ttu-id="62e68-102">\<specifiedPickupDirectory> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="62e68-102">\<specifiedPickupDirectory> Element (Network Settings)</span></span>
<span data-ttu-id="62e68-103">SMTP (Simple Mail Transport Protocol) 서버에 대 한 로컬 디렉터리를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="62e68-103">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<smtp>**](smtp-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<specifiedPickupDirectory>**  
  
## <a name="syntax"></a><span data-ttu-id="62e68-104">구문</span><span class="sxs-lookup"><span data-stu-id="62e68-104">Syntax</span></span>  
  
```xml  
<specifiedPickupDirectory  
  pickupDirectoryLocation="directory"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="62e68-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="62e68-105">Attributes and Elements</span></span>  
 <span data-ttu-id="62e68-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="62e68-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="62e68-107">특성</span><span class="sxs-lookup"><span data-stu-id="62e68-107">Attributes</span></span>  
  
|<span data-ttu-id="62e68-108">특성</span><span class="sxs-lookup"><span data-stu-id="62e68-108">Attribute</span></span>|<span data-ttu-id="62e68-109">Description</span><span class="sxs-lookup"><span data-stu-id="62e68-109">Description</span></span>|  
|---------------|-----------------|  
|`pickupDirectoryLocation`|<span data-ttu-id="62e68-110">응용 프로그램이 나중에 SMTP 서버에서 처리할 전자 메일을 저장 하는 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="62e68-110">The directory where applications save email for later processing by the SMTP server.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="62e68-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="62e68-111">Child Elements</span></span>  
 <span data-ttu-id="62e68-112">없음</span><span class="sxs-lookup"><span data-stu-id="62e68-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="62e68-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="62e68-113">Parent Elements</span></span>  
  
|<span data-ttu-id="62e68-114">요소</span><span class="sxs-lookup"><span data-stu-id="62e68-114">Element</span></span>|<span data-ttu-id="62e68-115">Description</span><span class="sxs-lookup"><span data-stu-id="62e68-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="62e68-116">\<smtp>요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="62e68-116">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="62e68-117">SMTP (Simple Mail Transport Protocol) 메일 전송 옵션을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="62e68-117">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62e68-118">설명</span><span class="sxs-lookup"><span data-stu-id="62e68-118">Remarks</span></span>  
 <span data-ttu-id="62e68-119">`specifiedPickupDirectory` 특성은 애플리케이션이 SMTP 서버에서 처리할 수 있도록 메일 메시지를 저장하는 디렉터리를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="62e68-119">The `specifiedPickupDirectory` attribute sets the directory where applications save mail messages to be processed by the SMTP server.</span></span>  
  
## <a name="example"></a><span data-ttu-id="62e68-120">예제</span><span class="sxs-lookup"><span data-stu-id="62e68-120">Example</span></span>  
 <span data-ttu-id="62e68-121">다음 예에서는 c:\maildrop을 메일 픽업 디렉터리로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="62e68-121">The following example specifies c:\maildrop as the mail pickup directory.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="62e68-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="62e68-122">See also</span></span>

- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSpecifiedPickupDirectoryElement?displayProperty=nameWithType>
- [<span data-ttu-id="62e68-123">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="62e68-123">Network Settings Schema</span></span>](index.md)
