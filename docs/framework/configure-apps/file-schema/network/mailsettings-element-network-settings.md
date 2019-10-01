---
title: <mailSettings> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#mailSettings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings
helpviewer_keywords:
- mailSettings element
- <mailSettings> element
ms.assetid: 54f0f153-17e5-4f49-afdc-deadb940c9c1
ms.openlocfilehash: fb4c8844ed3eb13af483c214d659090c0c563c33
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698071"
---
# <a name="mailsettings-element-network-settings"></a><span data-ttu-id="bde16-102">\<mailSettings > 요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="bde16-102">\<mailSettings> Element (Network Settings)</span></span>
<span data-ttu-id="bde16-103">메일 전송 옵션을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="bde16-103">Configures mail sending options.</span></span>  

[<span data-ttu-id="bde16-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="bde16-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="bde16-105">&nbsp; @ no__t-1[ **@no__t -4c.net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="bde16-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="bde16-106">&nbsp; @ no__t-1 @ no__t-2 **\<mailSettings >**</span><span class="sxs-lookup"><span data-stu-id="bde16-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<mailSettings>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bde16-107">구문</span><span class="sxs-lookup"><span data-stu-id="bde16-107">Syntax</span></span>  
  
```xml  
<mailSettings>
  <smtp>...</smtp>  
</mailSettings>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bde16-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="bde16-108">Attributes and Elements</span></span>  
 <span data-ttu-id="bde16-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bde16-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bde16-110">특성</span><span class="sxs-lookup"><span data-stu-id="bde16-110">Attributes</span></span>  
 <span data-ttu-id="bde16-111">없음</span><span class="sxs-lookup"><span data-stu-id="bde16-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="bde16-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="bde16-112">Child Elements</span></span>  
  
|<span data-ttu-id="bde16-113">특성</span><span class="sxs-lookup"><span data-stu-id="bde16-113">Attribute</span></span>|<span data-ttu-id="bde16-114">설명</span><span class="sxs-lookup"><span data-stu-id="bde16-114">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="bde16-115">\<smtp > 요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="bde16-115">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="bde16-116">간단한 메일 전송 프로토콜 옵션을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="bde16-116">Configures Simple Mail Transport Protocol options.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bde16-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="bde16-117">Parent Elements</span></span>  
  
|<span data-ttu-id="bde16-118">**요소**</span><span class="sxs-lookup"><span data-stu-id="bde16-118">**Element**</span></span>|<span data-ttu-id="bde16-119">**설명**</span><span class="sxs-lookup"><span data-stu-id="bde16-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="bde16-120">\<system.Net> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="bde16-120">\<system.Net> Element (Network Settings)</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="bde16-121">.NET Framework의 네트워크 연결 방법을 지정하는 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="bde16-121">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="bde16-122">예제</span><span class="sxs-lookup"><span data-stu-id="bde16-122">Example</span></span>  
 <span data-ttu-id="bde16-123">다음 예에서는 기본 네트워크 자격 증명을 사용 하 여 전자 메일을 보낼 적절 한 SMTP 매개 변수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bde16-123">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="Network">  
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
  
## <a name="see-also"></a><span data-ttu-id="bde16-124">참조</span><span class="sxs-lookup"><span data-stu-id="bde16-124">See also</span></span>

- <xref:System.Net.Mail.SmtpClient>
- [<span data-ttu-id="bde16-125">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="bde16-125">Network Settings Schema</span></span>](index.md)
