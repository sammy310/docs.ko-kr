---
title: <mailSettings> 요소(네트워크 설정)
description: <mailSettings>네트워크 설정 요소는 .NET Framework의 메일 전송 옵션을 구성 합니다.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#mailSettings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings
helpviewer_keywords:
- mailSettings element
- <mailSettings> element
ms.assetid: 54f0f153-17e5-4f49-afdc-deadb940c9c1
ms.openlocfilehash: a146874acc21f52507b37b1751c648792e23c8bb
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158853"
---
# <a name="mailsettings-element-network-settings"></a><span data-ttu-id="b7a1c-103">\<mailSettings> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="b7a1c-103">\<mailSettings> Element (Network Settings)</span></span>

<span data-ttu-id="b7a1c-104">메일 전송 옵션을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7a1c-104">Configures mail sending options.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<mailSettings>**

## <a name="syntax"></a><span data-ttu-id="b7a1c-105">구문</span><span class="sxs-lookup"><span data-stu-id="b7a1c-105">Syntax</span></span>  
  
```xml  
<mailSettings>
  <smtp>...</smtp>  
</mailSettings>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b7a1c-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b7a1c-106">Attributes and Elements</span></span>  

 <span data-ttu-id="b7a1c-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b7a1c-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b7a1c-108">특성</span><span class="sxs-lookup"><span data-stu-id="b7a1c-108">Attributes</span></span>  

 <span data-ttu-id="b7a1c-109">없음</span><span class="sxs-lookup"><span data-stu-id="b7a1c-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b7a1c-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b7a1c-110">Child Elements</span></span>  
  
|<span data-ttu-id="b7a1c-111">attribute</span><span class="sxs-lookup"><span data-stu-id="b7a1c-111">Attribute</span></span>|<span data-ttu-id="b7a1c-112">설명</span><span class="sxs-lookup"><span data-stu-id="b7a1c-112">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="b7a1c-113">\<smtp> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="b7a1c-113">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="b7a1c-114">간단한 메일 전송 프로토콜 옵션을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7a1c-114">Configures Simple Mail Transport Protocol options.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b7a1c-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b7a1c-115">Parent Elements</span></span>  
  
|<span data-ttu-id="b7a1c-116">**요소**</span><span class="sxs-lookup"><span data-stu-id="b7a1c-116">**Element**</span></span>|<span data-ttu-id="b7a1c-117">**설명**</span><span class="sxs-lookup"><span data-stu-id="b7a1c-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="b7a1c-118">\<system.Net> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="b7a1c-118">\<system.Net> Element (Network Settings)</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="b7a1c-119">.NET Framework의 네트워크 연결 방법을 지정하는 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="b7a1c-119">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b7a1c-120">예제</span><span class="sxs-lookup"><span data-stu-id="b7a1c-120">Example</span></span>  

 <span data-ttu-id="b7a1c-121">다음 예에서는 기본 네트워크 자격 증명을 사용 하 여 전자 메일을 보낼 적절 한 SMTP 매개 변수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7a1c-121">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b7a1c-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b7a1c-122">See also</span></span>

- <xref:System.Net.Mail.SmtpClient>
- [<span data-ttu-id="b7a1c-123">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="b7a1c-123">Network Settings Schema</span></span>](index.md)
