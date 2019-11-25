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
ms.openlocfilehash: 4e8bf23ce39edadf80f019315c690b597b3d7361
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089228"
---
# <a name="mailsettings-element-network-settings"></a><span data-ttu-id="35ba2-102">\<mailSettings > 요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="35ba2-102">\<mailSettings> Element (Network Settings)</span></span>
<span data-ttu-id="35ba2-103">메일 전송 옵션을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="35ba2-103">Configures mail sending options.</span></span>  

<span data-ttu-id="35ba2-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="35ba2-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="35ba2-105">&nbsp;[ **\<.net >를**](system-net-element-network-settings.md) &nbsp;</span><span class="sxs-lookup"><span data-stu-id="35ba2-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="35ba2-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<mailSettings >**</span><span class="sxs-lookup"><span data-stu-id="35ba2-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<mailSettings>**</span></span>

## <a name="syntax"></a><span data-ttu-id="35ba2-107">구문</span><span class="sxs-lookup"><span data-stu-id="35ba2-107">Syntax</span></span>  
  
```xml  
<mailSettings>
  <smtp>...</smtp>  
</mailSettings>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="35ba2-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="35ba2-108">Attributes and Elements</span></span>  
 <span data-ttu-id="35ba2-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="35ba2-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="35ba2-110">특성</span><span class="sxs-lookup"><span data-stu-id="35ba2-110">Attributes</span></span>  
 <span data-ttu-id="35ba2-111">없음.</span><span class="sxs-lookup"><span data-stu-id="35ba2-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="35ba2-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="35ba2-112">Child Elements</span></span>  
  
|<span data-ttu-id="35ba2-113">특성</span><span class="sxs-lookup"><span data-stu-id="35ba2-113">Attribute</span></span>|<span data-ttu-id="35ba2-114">설명</span><span class="sxs-lookup"><span data-stu-id="35ba2-114">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="35ba2-115">\<smtp > 요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="35ba2-115">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="35ba2-116">간단한 메일 전송 프로토콜 옵션을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="35ba2-116">Configures Simple Mail Transport Protocol options.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="35ba2-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="35ba2-117">Parent Elements</span></span>  
  
|<span data-ttu-id="35ba2-118">**요소**</span><span class="sxs-lookup"><span data-stu-id="35ba2-118">**Element**</span></span>|<span data-ttu-id="35ba2-119">**설명**</span><span class="sxs-lookup"><span data-stu-id="35ba2-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="35ba2-120">\<system.Net> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="35ba2-120">\<system.Net> Element (Network Settings)</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="35ba2-121">.NET Framework의 네트워크 연결 방법을 지정하는 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="35ba2-121">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="35ba2-122">예제</span><span class="sxs-lookup"><span data-stu-id="35ba2-122">Example</span></span>  
 <span data-ttu-id="35ba2-123">다음 예에서는 기본 네트워크 자격 증명을 사용 하 여 전자 메일을 보낼 적절 한 SMTP 매개 변수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="35ba2-123">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="35ba2-124">참조</span><span class="sxs-lookup"><span data-stu-id="35ba2-124">See also</span></span>

- <xref:System.Net.Mail.SmtpClient>
- [<span data-ttu-id="35ba2-125">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="35ba2-125">Network Settings Schema</span></span>](index.md)
