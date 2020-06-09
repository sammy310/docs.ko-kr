---
title: '방법: 신뢰할 수 있는 세션 내에서 메시지 보안'
ms.date: 03/30/2017
ms.assetid: aee33e50-936f-4486-9ca8-c1520c19a62d
ms.openlocfilehash: 306d0f96b5163fe5c24d270b4b9a7c1d3f499e7e
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596957"
---
# <a name="how-to-secure-messages-within-reliable-sessions"></a><span data-ttu-id="957e2-102">방법: 신뢰할 수 있는 세션 내에서 메시지 보안</span><span class="sxs-lookup"><span data-stu-id="957e2-102">How to: Secure Messages within Reliable Sessions</span></span>

<span data-ttu-id="957e2-103">이 항목에서는 기본적이지는 않지만 신뢰할 수 있는 세션을 지원하는 시스템 제공 바인딩 중 하나를 사용하여 이러한 세션 내에서 교환된 메시지의 메시지 수준 보안을 사용하도록 설정하는 데 필요한 단계에 대해 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="957e2-103">This topic outlines the steps required to enable message-level security for messages exchanged within a reliable session using one of the system-provided bindings that support such a session, but not by default.</span></span> <span data-ttu-id="957e2-104">코드를 사용 하 여 명령적으로 또는 구성 파일에서 선언적으로 안전 하 고 신뢰할 수 있는 세션을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="957e2-104">Enable a secure, reliable session either imperatively by using code or declaratively in the configuration file.</span></span> <span data-ttu-id="957e2-105">이 절차에서는 클라이언트와 서비스 구성 파일을 사용하여 안전하고 신뢰할 수 있는 세션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="957e2-105">This procedure uses the client and service configuration files to enable the secure, reliable session.</span></span>

<span data-ttu-id="957e2-106">이 절차는 다음 세 가지 주요 작업으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="957e2-106">This procedure consists of the following three key tasks:</span></span>

1. <span data-ttu-id="957e2-107">클라이언트 및 서비스가 신뢰할 수 있는 세션 내에서 메시지를 교환하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="957e2-107">Specify that the client and service exchange messages within a reliable session.</span></span>

1. <span data-ttu-id="957e2-108">신뢰할 수 있는 세션 내에서 메시지 수준 보안이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="957e2-108">Require message-level security within the reliable session.</span></span>

1. <span data-ttu-id="957e2-109">클라이언트가 서비스에서 인증받는 데 사용해야 하는 클라이언트 자격 증명 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="957e2-109">Specify the client credential type that the client must use to be authenticated with the service.</span></span>

<span data-ttu-id="957e2-110">첫 번째 작업에서는 끝점 구성 요소에 `bindingConfiguration` 이라는 바인딩 구성 (이 예제에서는)을 참조 하는 특성이 포함 되어 있다는 것이 중요 합니다 `MessageSecurity` .</span><span class="sxs-lookup"><span data-stu-id="957e2-110">It's important in the first task that the endpoint configuration element contain a `bindingConfiguration` attribute that references a binding configuration named (in this example) `MessageSecurity`.</span></span> <span data-ttu-id="957e2-111">[**\<binding>**](../../configure-apps/file-schema/wcf/bindings.md)그런 다음 구성 요소는 요소의 특성을로 설정 하 여 신뢰할 수 있는 세션을 사용 하도록이 이름을 참조 합니다 `enabled` [**\<reliableSession>**](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90)) `true` .</span><span class="sxs-lookup"><span data-stu-id="957e2-111">The [**\<binding>**](../../configure-apps/file-schema/wcf/bindings.md) configuration element then references this name to enable reliable sessions by setting the `enabled` attribute of the [**\<reliableSession>**](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90)) element to `true`.</span></span> <span data-ttu-id="957e2-112">`ordered` 특성을 `true`로 설정하여 신뢰할 수 있는 세션 내에서 순서가 지정된 배달 보증을 사용하는 것이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="957e2-112">You can require that the ordered delivery assurances are available within a reliable session by setting the `ordered` attribute to `true`.</span></span>

<span data-ttu-id="957e2-113">이 구성 프로시저가 기반으로 하는 예제의 원본 복사본은 [WS 신뢰할](../samples/ws-reliable-session.md)수 있는 세션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="957e2-113">For the source copy of the example on which this configuration procedure is based, see the [WS Reliable Session](../samples/ws-reliable-session.md).</span></span>

<span data-ttu-id="957e2-114">두 번째 작업의 주요 항목은 `mode` **\<security>** **\<binding>** 클라이언트 및 서비스의 요소에 포함 된 요소의 특성을로 설정 하 여 수행 됩니다 `Message` .</span><span class="sxs-lookup"><span data-stu-id="957e2-114">The essential items of the second task are accomplished by setting the `mode` attribute of the **\<security>** element contained in the **\<binding>** element of the client and service to `Message`.</span></span>

<span data-ttu-id="957e2-115">세 번째 작업의 필수 항목은 `clientCredentialType` **\<message>** **\<security>** 클라이언트 및 서비스의 요소에 포함 된 요소의 특성을로 설정 하 여 수행 됩니다 `Certificate` .</span><span class="sxs-lookup"><span data-stu-id="957e2-115">The essential items of the third task are accomplished by setting the `clientCredentialType` attribute of the **\<message>** element contained in the **\<security>** element of the client and service to `Certificate`.</span></span>

> [!NOTE]
> <span data-ttu-id="957e2-116">신뢰할 수 있는 세션에서 메시지 보안을 사용 하는 경우 첫 번째 오류 발생 시 예외를 throw 하는 대신 시간이 초과 될 때까지 신뢰할 수 있는 메시징에서 인증 되지 않은 클라이언트를 인증 합니다.</span><span class="sxs-lookup"><span data-stu-id="957e2-116">When using message security with reliable sessions, Reliable Messaging attempts to authenticate an unauthenticated client until a timeout occurs instead of throwing an exception upon first failure.</span></span>

### <a name="configure-the-service-with-a-wshttpbinding-to-use-a-reliable-session"></a><span data-ttu-id="957e2-117">신뢰할 수 있는 세션을 사용 하도록 WSHttpBinding으로 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="957e2-117">Configure the service with a WSHttpBinding to use a reliable session</span></span>

<span data-ttu-id="957e2-118">이 절차는 [방법: 신뢰할 수 있는 세션 내에서 메시지 교환](how-to-exchange-messages-within-a-reliable-session.md)에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="957e2-118">This procedure is described in [How to: Exchange Messages Within a Reliable Session](how-to-exchange-messages-within-a-reliable-session.md).</span></span>

### <a name="configure-the-client-with-a-wshttpbinding-to-use-a-reliable-session"></a><span data-ttu-id="957e2-119">신뢰할 수 있는 세션을 사용 하도록 WSHttpBinding으로 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="957e2-119">Configure the client with a WSHttpBinding to use a reliable session</span></span>

<span data-ttu-id="957e2-120">이 절차는 [방법: 신뢰할 수 있는 세션 내에서 메시지 교환](how-to-exchange-messages-within-a-reliable-session.md)에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="957e2-120">This procedure is described in [How to: Exchange Messages Within a Reliable Session](how-to-exchange-messages-within-a-reliable-session.md).</span></span>

### <a name="set-the-mode-and-clientcredentialtype-in-configuration"></a><span data-ttu-id="957e2-121">구성에서 모드 및 ClientCredentialType 설정</span><span class="sxs-lookup"><span data-stu-id="957e2-121">Set the mode and ClientCredentialType in configuration</span></span>

1. <span data-ttu-id="957e2-122">구성 파일의 요소에 적절 한 바인딩 요소를 추가 [**\<bindings>**](../../configure-apps/file-schema/wcf/bindings.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="957e2-122">Add an appropriate binding element to the [**\<bindings>**](../../configure-apps/file-schema/wcf/bindings.md) element of the configuration file.</span></span> <span data-ttu-id="957e2-123">다음 예제에서는 요소를 추가 합니다 [**\<wsHttpBinding>**](../../configure-apps/file-schema/wcf/wshttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="957e2-123">The following example adds a [**\<wsHttpBinding>**](../../configure-apps/file-schema/wcf/wshttpbinding.md) element.</span></span>

1. <span data-ttu-id="957e2-124">요소를 추가 하 **\<binding>** 고 해당 `name` 특성을 적절 한 값으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="957e2-124">Add a **\<binding>** element and set its `name` attribute to an appropriate value.</span></span> <span data-ttu-id="957e2-125">이 예에서는 이름을 사용 `MessageSecurity` 합니다.</span><span class="sxs-lookup"><span data-stu-id="957e2-125">The example uses the name `MessageSecurity`.</span></span>

1. <span data-ttu-id="957e2-126">요소를 추가 하 **\<security>** 고 `mode` 특성을로 설정 `Message` 합니다.</span><span class="sxs-lookup"><span data-stu-id="957e2-126">Add a **\<security>** element and set the `mode` attribute to `Message`.</span></span>

1. <span data-ttu-id="957e2-127">요소 내에 **\<security>** 요소를 추가 하 **\<message>** 고 특성을 `clientCredentialType` 로 설정 `Certificate` 합니다.</span><span class="sxs-lookup"><span data-stu-id="957e2-127">Within the **\<security>** element, add a **\<message>** element and set the `clientCredentialType` attribute to `Certificate`.</span></span>

```xml
<wsHttpBinding>
  <binding name="MessageSecurity">
    <security mode="Message">
      <message clientCredentialType="Certificate" />
    </security>
  </binding>
</wsHttpBinding>
```
