---
title: <net.pipe>
ms.date: 03/30/2017
ms.assetid: 6a0f0318-f8f6-466c-9fae-199d7274a82e
ms.openlocfilehash: d070b822cefeef3c281d5b0e47411f4c624dd83f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204608"
---
# \<net.pipe>

<span data-ttu-id="7aa6b-102">명명된 파이프 연결의 수명을 관리하고 명명된 파이프을 통해 수신되는 활성화 요청을 처리하는 Named Pipe Activation Service의 구성 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-102">Specifies configuration settings for the Named Pipe Activation Service, which manages the lifetime of the named pipe connection, and handles activation requests that arrive over named pipes.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<net.pipe>**  
  
## <a name="syntax"></a><span data-ttu-id="7aa6b-103">구문</span><span class="sxs-lookup"><span data-stu-id="7aa6b-103">Syntax</span></span>  
  
```xml  
<configuration>
  <system.serviceModel.activation>
    <net.pipe maxPendingAccepts="Integer"
              maxPendingConnections="Integer"
              receiveTimeout="TimeSpan">
      <allowAccounts>
        <!-- LocalSystem account -->
        <add securityIdentifier="S-1-5-18" />
        <!-- LocalService account -->
        <add securityIdentifier="S-1-5-19" />
        <!-- Administrators account -->
        <add securityIdentifier="S-1-5-20" />
        <!-- Network Service account -->
        <add securityIdentifier="S-1-5-32-544" />
        <!-- IIS_IUSRS account (Vista only) -->
        <add securityIdentifier="S-1-5-32-568" />
      </allowAccounts>
    </net.pipe>
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="type"></a><span data-ttu-id="7aa6b-104">형식</span><span class="sxs-lookup"><span data-stu-id="7aa6b-104">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7aa6b-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="7aa6b-105">Attributes and Elements</span></span>  

 <span data-ttu-id="7aa6b-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7aa6b-107">특성</span><span class="sxs-lookup"><span data-stu-id="7aa6b-107">Attributes</span></span>  
  
|<span data-ttu-id="7aa6b-108">attribute</span><span class="sxs-lookup"><span data-stu-id="7aa6b-108">Attribute</span></span>|<span data-ttu-id="7aa6b-109">설명</span><span class="sxs-lookup"><span data-stu-id="7aa6b-109">Description</span></span>|  
|---------------|-----------------|  
|`maxPendingAccepts`|<span data-ttu-id="7aa6b-110">공유 서비스에 대한 수신 엔드포인트에서 동시에 수용할 수 있는 활성 스레드의 최대 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-110">An integer that specifies the maximum outstanding concurrent accepting threads on the listening endpoint for the sharing service.</span></span> <span data-ttu-id="7aa6b-111">기본값은 2입니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-111">The default is 2.</span></span>|  
|`maxPendingConnections`|<span data-ttu-id="7aa6b-112">디스패치를 대기할 수 있는 최대 연결 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-112">An integer that specifies the maximum number of connections that can wait for dispatch.</span></span> <span data-ttu-id="7aa6b-113">기본값은 100입니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-113">The default is 100.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="7aa6b-114">프레이밍 데이터를 읽고 내부 연결에서 연결 디스패치를 수행하는 데 대한 제한 시간을 지정하는 <xref:System.TimeSpan>입니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-114">A <xref:System.TimeSpan> that specifies the timeout for reading the framing data and performing connection dispatching from the underlining connections.</span></span> <span data-ttu-id="7aa6b-115">기본값은 "00:00:10"입니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-115">The default is "00:00:10"</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7aa6b-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="7aa6b-116">Child Elements</span></span>  
  
|<span data-ttu-id="7aa6b-117">요소</span><span class="sxs-lookup"><span data-stu-id="7aa6b-117">Element</span></span>|<span data-ttu-id="7aa6b-118">설명</span><span class="sxs-lookup"><span data-stu-id="7aa6b-118">Description</span></span>|  
|-------------|-----------------|  
|[\<allowAccounts>](allowaccounts.md)|<span data-ttu-id="7aa6b-119">`securityIdentifier`WCF 서비스를 호스팅하고 공유 서비스에 대 한 연결 액세스 권한이 부여 된 프로세스의 사용자 계정을 지정 하는 특성을 포함 하는 구성 요소 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-119">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7aa6b-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="7aa6b-120">Parent Elements</span></span>  
  
|<span data-ttu-id="7aa6b-121">요소</span><span class="sxs-lookup"><span data-stu-id="7aa6b-121">Element</span></span>|<span data-ttu-id="7aa6b-122">설명</span><span class="sxs-lookup"><span data-stu-id="7aa6b-122">Description</span></span>|  
|-------------|-----------------|  
|[\<system.serviceModel.activation>](system-servicemodel-activation.md)|<span data-ttu-id="7aa6b-123">수신기 프로세스 SMSvcHost.exe에 대한 구성 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-123">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7aa6b-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7aa6b-124">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection>
