---
description: '다음에 대 한 자세한 정보: <localClientSettings> 요소'
title: <localClientSettings> 요소
ms.date: 03/30/2017
ms.assetid: 4680ace5-f4e1-4fcb-b9d8-a4a4af5cd7ae
ms.openlocfilehash: 6393a460b5a58ab9bf7933df8643df3530da5f14
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802218"
---
# <a name="localclientsettings-element"></a><span data-ttu-id="d1cee-103">\<localClientSettings> 요소</span><span class="sxs-lookup"><span data-stu-id="d1cee-103">\<localClientSettings> element</span></span>

<span data-ttu-id="d1cee-104">이 바인딩에 대한 로컬 클라이언트의 보안 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d1cee-104">Specifies the security settings of a local client for this binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<localClientSettings>**  
  
## <a name="syntax"></a><span data-ttu-id="d1cee-105">구문</span><span class="sxs-lookup"><span data-stu-id="d1cee-105">Syntax</span></span>  
  
```xml  
<security>
   <localClientSettings cacheCookies="Boolean"
                        cookieRenewalThresholdPercentage="Integer"
                        detectReplays="Boolean"
                        maxClockSkew="TimeSpan"
                        maxCookieCachingTime="TimeSpan"
                        reconnectTransportOnFailure="Boolean"
                        replayCacheSize="Integer"
                        replayWindow="TimeSpan"
                        sessionKeyRenewalInterval="TimeSpan"
                        sessionKeyRolloverInterval="TimeSpan"
                        timestampValidityDuration="TimeSpan" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d1cee-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d1cee-106">Attributes and Elements</span></span>  

 <span data-ttu-id="d1cee-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d1cee-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d1cee-108">특성</span><span class="sxs-lookup"><span data-stu-id="d1cee-108">Attributes</span></span>  
  
|<span data-ttu-id="d1cee-109">attribute</span><span class="sxs-lookup"><span data-stu-id="d1cee-109">Attribute</span></span>|<span data-ttu-id="d1cee-110">설명</span><span class="sxs-lookup"><span data-stu-id="d1cee-110">Description</span></span>|  
|---------------|-----------------|  
|`cacheCookies`|<span data-ttu-id="d1cee-111">쿠키 캐싱 활성화 여부를 나타내는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d1cee-111">A Boolean value that specifies whether cookie caching is enabled.</span></span> <span data-ttu-id="d1cee-112">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="d1cee-112">The default is `false`.</span></span>|  
|`cookieRenewalThresholdPercentage`|<span data-ttu-id="d1cee-113">갱신할 수 있는 최대 쿠키 백분율을 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="d1cee-113">An integer that specifies the maximum percentage of cookies that can be renewed.</span></span> <span data-ttu-id="d1cee-114">이 값은 0 이상 100 이하여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1cee-114">This value should be between 0 and 100 inclusively.</span></span> <span data-ttu-id="d1cee-115">기본값은 90입니다.</span><span class="sxs-lookup"><span data-stu-id="d1cee-115">The default is 90.</span></span>|  
|`detectReplays`|<span data-ttu-id="d1cee-116">채널에 대한 재생 공격이 검색되어 자동으로 처리되는지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d1cee-116">A Boolean value that specifies whether replay attacks against the channel are detected and dealt with automatically.</span></span> <span data-ttu-id="d1cee-117">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="d1cee-117">The default is `false`.</span></span>|  
|`maxClockSkew`|<span data-ttu-id="d1cee-118">서로 통신하는 양쪽의 시스템 클록 간의 최대 시간 차이를 지정하는 <xref:System.TimeSpan>입니다.</span><span class="sxs-lookup"><span data-stu-id="d1cee-118">A <xref:System.TimeSpan> that specifies the maximum time difference between the system clocks of the two communicating parties.</span></span> <span data-ttu-id="d1cee-119">기본값은 "00:05:00"입니다.</span><span class="sxs-lookup"><span data-stu-id="d1cee-119">The default value is "00:05:00".</span></span><br /><br /> <span data-ttu-id="d1cee-120">이 값을 기본값으로 설정하면 수신자는 메시지를 받은 시간을 기준으로 보낸 시간 타임스탬프가 전후 5분 이내인 메시지를 수신 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="d1cee-120">When this value is set to the default, the receiver accepts messages with send-time time stamps up to 5 minutes later or earlier than the time the message was received.</span></span> <span data-ttu-id="d1cee-121">보낸 시간 테스트를 통과하지 못한 메시지는 거부됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1cee-121">Messages that do not pass the send-time test are rejected.</span></span> <span data-ttu-id="d1cee-122">이 설정은 `replayWindow` 특성과 함께 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1cee-122">This setting is used in conjunction with the `replayWindow` attribute.</span></span>|  
|`maxCookieCachingTime`|<span data-ttu-id="d1cee-123">쿠키의 최대 수명을 지정하는 <xref:System.TimeSpan>입니다.</span><span class="sxs-lookup"><span data-stu-id="d1cee-123">A <xref:System.TimeSpan> that specifies the maximum lifetime of cookies.</span></span> <span data-ttu-id="d1cee-124">기본값은 "10675199.02:48:05.4775807"입니다.</span><span class="sxs-lookup"><span data-stu-id="d1cee-124">The default value is "10675199.02:48:05.4775807".</span></span>|  
|`reconnectTransportOnFailure`|<span data-ttu-id="d1cee-125">WS-Reliable Messaging을 사용하는 연결에서 전송 실패 후 다시 연결을 시도할지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d1cee-125">A Boolean value that specifies whether connections using WS-Reliable messaging will attempt to reconnect after transport failures.</span></span> <span data-ttu-id="d1cee-126">기본값은 `true`로, 다시 연결이 무한히 시도된다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="d1cee-126">The default is `true`, which means that infinite attempts to reconnect are attempted.</span></span> <span data-ttu-id="d1cee-127">이 순환은 비활성 제한 시간이 초과되어야만 중단되며, 이 경우 채널에서 다시 연결할 수 없으면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1cee-127">The cycle is broken by the inactivity time-out, which causes the channel to throw an exception when it cannot be reconnected.</span></span>|  
|`replayCacheSize`|<span data-ttu-id="d1cee-128">재생 검색에 사용되는 캐시된 Nonce의 수를 지정하는 양의 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="d1cee-128">A positive integer that specifies the number of cached nonces used for replay detection.</span></span> <span data-ttu-id="d1cee-129">이 제한을 초과하면 가장 오래된 Nonce가 제거되고 새 메시지에 대해 새로운 Nonce가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="d1cee-129">If this limit is exceeded, the oldest nonce is removed and a new nonce is created for the new message.</span></span> <span data-ttu-id="d1cee-130">기본값은 500000입니다.</span><span class="sxs-lookup"><span data-stu-id="d1cee-130">The default value is 500000.</span></span>|  
|`replayWindow`|<span data-ttu-id="d1cee-131">개별 메시지 Nonce의 유효 기간을 지정하는 <xref:System.TimeSpan>입니다.</span><span class="sxs-lookup"><span data-stu-id="d1cee-131">A <xref:System.TimeSpan> that specifies the duration in which individual message nonces are valid.</span></span><br /><br /> <span data-ttu-id="d1cee-132">이 속성에서 지정한 시간이 지나면 이전에 보낸 메시지와 동일한 Nonce를 갖는 메시지는 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d1cee-132">After this duration, a message sent with the same nonce as the one sent before will not be accepted.</span></span> <span data-ttu-id="d1cee-133">이 특성은 `maxClockSkew` 특성과 함께 사용되어 재생 공격을 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="d1cee-133">This attribute is used in conjunction with the `maxClockSkew` attribute to prevent replay attacks.</span></span> <span data-ttu-id="d1cee-134">메시지 재생 창이 만료된 후에 공격자가 그 메시지를 재생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1cee-134">An attacker could replay a message after its replay window has expired.</span></span> <span data-ttu-id="d1cee-135">그러나 이 메시지는 `maxClockSkew` 테스트를 통과하지 못합니다. 해당 테스트는 메시지의 보낸 시간 타임스탬프가 메시지를 받은 시간보다 지정된 시간 이상으로 늦거나 빠르면 그 메시지를 거부합니다.</span><span class="sxs-lookup"><span data-stu-id="d1cee-135">This message, however, would fail the `maxClockSkew` test which rejects messages with send-time timestamps up to a specified time later or earlier than the time the message was received.</span></span>|  
|`sessionKeyRenewalInterval`|<span data-ttu-id="d1cee-136">개시자가 보안 세션을 위해 키를 갱신하는 시간 간격을 지정하는 <xref:System.TimeSpan>입니다.</span><span class="sxs-lookup"><span data-stu-id="d1cee-136">A <xref:System.TimeSpan> that specifies the duration after which the initiator will renew the key for the security session.</span></span> <span data-ttu-id="d1cee-137">기본값은 "10:00:00"입니다.</span><span class="sxs-lookup"><span data-stu-id="d1cee-137">The default is "10:00:00".</span></span>|  
|`sessionKeyRolloverInterval`|<span data-ttu-id="d1cee-138">키 갱신 중에 들어오는 메시지에서 이전 세션 키를 사용할 수 있는 시간 간격을 지정하는 <xref:System.TimeSpan>입니다.</span><span class="sxs-lookup"><span data-stu-id="d1cee-138">A <xref:System.TimeSpan> that specifies the time interval a previous session key is valid on incoming messages during a key renewal.</span></span> <span data-ttu-id="d1cee-139">기본값은 "00:05:00"입니다.</span><span class="sxs-lookup"><span data-stu-id="d1cee-139">The default is "00:05:00".</span></span><br /><br /> <span data-ttu-id="d1cee-140">키 갱신 중에 클라이언트와 서버는 반드시 사용 가능한 최신 키를 사용하여 메시지를 보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1cee-140">During key renewal, the client and server must always send messages using the most current available key.</span></span> <span data-ttu-id="d1cee-141">양쪽 모두 롤오버 시간이 만료될 때까지는 이전 세션 키를 사용하여 보안되는 메시지를 수락할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1cee-141">Both parties will accept incoming messages secured with the previous session key until the rollover time expires.</span></span>|  
|`timestampValidityDuration`|<span data-ttu-id="d1cee-142">타임스탬프의 유효 기간을 지정하는 <xref:System.TimeSpan>(양수)입니다.</span><span class="sxs-lookup"><span data-stu-id="d1cee-142">A positive <xref:System.TimeSpan> that specifies the duration in which a time stamp is valid.</span></span> <span data-ttu-id="d1cee-143">기본값은 "00:15:00"입니다.</span><span class="sxs-lookup"><span data-stu-id="d1cee-143">The default is "00:15:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d1cee-144">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d1cee-144">Child Elements</span></span>  

 <span data-ttu-id="d1cee-145">없음</span><span class="sxs-lookup"><span data-stu-id="d1cee-145">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d1cee-146">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d1cee-146">Parent Elements</span></span>  
  
|<span data-ttu-id="d1cee-147">요소</span><span class="sxs-lookup"><span data-stu-id="d1cee-147">Element</span></span>|<span data-ttu-id="d1cee-148">설명</span><span class="sxs-lookup"><span data-stu-id="d1cee-148">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-custombinding.md)|<span data-ttu-id="d1cee-149">사용자 지정 바인딩에 대한 보안 옵션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d1cee-149">Specifies the security options for a custom binding.</span></span>|  
|[\<secureConversationBootstrap>](secureconversationbootstrap.md)|<span data-ttu-id="d1cee-150">보안 대화 서비스 개시에 사용되는 기본값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d1cee-150">Specifies the default values used for initiating a secure conversation service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d1cee-151">설명</span><span class="sxs-lookup"><span data-stu-id="d1cee-151">Remarks</span></span>  

 <span data-ttu-id="d1cee-152">이 설정은 서비스의 보안 정책에서 파생되는 설정이 아니므로 로컬 설정에 속합니다.</span><span class="sxs-lookup"><span data-stu-id="d1cee-152">The settings are local in the sense that they are not settings derived from the security policy of the service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1cee-153">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d1cee-153">See also</span></span>

- <xref:System.ServiceModel.Configuration.LocalClientSecuritySettingsElement>
- <xref:System.ServiceModel.Configuration.SecurityElementBase.LocalClientSettings%2A>
- <xref:System.ServiceModel.Channels.SecurityBindingElement.LocalClientSettings%2A>
- <xref:System.ServiceModel.Channels.LocalClientSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="d1cee-154">바인딩</span><span class="sxs-lookup"><span data-stu-id="d1cee-154">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="d1cee-155">바인딩 확장명</span><span class="sxs-lookup"><span data-stu-id="d1cee-155">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="d1cee-156">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="d1cee-156">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [<span data-ttu-id="d1cee-157">방법: SecurityBindingElement를 사용하여 사용자 지정 바인딩 만들기</span><span class="sxs-lookup"><span data-stu-id="d1cee-157">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="d1cee-158">Custom Binding Security</span><span class="sxs-lookup"><span data-stu-id="d1cee-158">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
