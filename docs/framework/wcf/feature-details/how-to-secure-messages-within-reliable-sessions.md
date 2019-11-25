---
title: '방법: 신뢰할 수 있는 세션 내에서 메시지 보안'
ms.date: 03/30/2017
ms.assetid: aee33e50-936f-4486-9ca8-c1520c19a62d
ms.openlocfilehash: edff27fe9649387c1922c34e72ef59d615e52b90
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141671"
---
# <a name="how-to-secure-messages-within-reliable-sessions"></a><span data-ttu-id="d959a-102">방법: 신뢰할 수 있는 세션 내에서 메시지 보안</span><span class="sxs-lookup"><span data-stu-id="d959a-102">How to: Secure Messages within Reliable Sessions</span></span>

<span data-ttu-id="d959a-103">이 항목에서는 기본적이지는 않지만 신뢰할 수 있는 세션을 지원하는 시스템 제공 바인딩 중 하나를 사용하여 이러한 세션 내에서 교환된 메시지의 메시지 수준 보안을 사용하도록 설정하는 데 필요한 단계에 대해 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d959a-103">This topic outlines the steps required to enable message-level security for messages exchanged within a reliable session using one of the system-provided bindings that support such a session, but not by default.</span></span> <span data-ttu-id="d959a-104">코드를 사용 하 여 명령적으로 또는 구성 파일에서 선언적으로 안전 하 고 신뢰할 수 있는 세션을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d959a-104">Enable a secure, reliable session either imperatively by using code or declaratively in the configuration file.</span></span> <span data-ttu-id="d959a-105">이 절차에서는 클라이언트와 서비스 구성 파일을 사용하여 안전하고 신뢰할 수 있는 세션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d959a-105">This procedure uses the client and service configuration files to enable the secure, reliable session.</span></span>

<span data-ttu-id="d959a-106">이 절차는 다음 세 가지 주요 작업으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d959a-106">This procedure consists of the following three key tasks:</span></span>

1. <span data-ttu-id="d959a-107">클라이언트 및 서비스가 신뢰할 수 있는 세션 내에서 메시지를 교환하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d959a-107">Specify that the client and service exchange messages within a reliable session.</span></span>

1. <span data-ttu-id="d959a-108">신뢰할 수 있는 세션 내에서 메시지 수준 보안이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d959a-108">Require message-level security within the reliable session.</span></span>

1. <span data-ttu-id="d959a-109">클라이언트가 서비스에서 인증받는 데 사용해야 하는 클라이언트 자격 증명 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d959a-109">Specify the client credential type that the client must use to be authenticated with the service.</span></span>

<span data-ttu-id="d959a-110">첫 번째 작업에서는 끝점 구성 요소에 이라는 바인딩 구성을 참조 하는 `bindingConfiguration` 특성 (이 예제에서는 `MessageSecurity`)이 포함 되어 있는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d959a-110">It's important in the first task that the endpoint configuration element contain a `bindingConfiguration` attribute that references a binding configuration named (in this example) `MessageSecurity`.</span></span> <span data-ttu-id="d959a-111">[ **\<바인딩 >** ](../../configure-apps/file-schema/wcf/bindings.md) 구성 요소는 [ **\<reliableSession >** ](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90)) 요소의 `enabled` 특성을 `true`로 설정 하 여 신뢰할 수 있는 세션을 사용 하도록이 이름을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="d959a-111">The [**\<binding>**](../../configure-apps/file-schema/wcf/bindings.md) configuration element then references this name to enable reliable sessions by setting the `enabled` attribute of the [**\<reliableSession>**](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90)) element to `true`.</span></span> <span data-ttu-id="d959a-112">`ordered` 특성을 `true`로 설정하여 신뢰할 수 있는 세션 내에서 순서가 지정된 배달 보증을 사용하는 것이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d959a-112">You can require that the ordered delivery assurances are available within a reliable session by setting the `ordered` attribute to `true`.</span></span>

<span data-ttu-id="d959a-113">이 구성 프로시저가 기반으로 하는 예제의 원본 복사본은 [WS 신뢰할](../../../../docs/framework/wcf/samples/ws-reliable-session.md)수 있는 세션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d959a-113">For the source copy of the example on which this configuration procedure is based, see the [WS Reliable Session](../../../../docs/framework/wcf/samples/ws-reliable-session.md).</span></span>

<span data-ttu-id="d959a-114">두 번째 작업의 필수 항목은 클라이언트 및 서비스의 **\<binding >** 요소에 포함 된 **\<security >** 요소의 `mode` 특성을 `Message`로 설정 하 여 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d959a-114">The essential items of the second task are accomplished by setting the `mode` attribute of the **\<security>** element contained in the **\<binding>** element of the client and service to `Message`.</span></span>

<span data-ttu-id="d959a-115">세 번째 작업의 필수 항목은 클라이언트 및 서비스의 **\<security >** 요소에 포함 된 **\<메시지 >** 요소의 `clientCredentialType` 특성을 `Certificate`로 설정 하 여 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d959a-115">The essential items of the third task are accomplished by setting the `clientCredentialType` attribute of the **\<message>** element contained in the **\<security>** element of the client and service to `Certificate`.</span></span>

> [!NOTE]
> <span data-ttu-id="d959a-116">신뢰할 수 있는 세션에서 메시지 보안을 사용 하는 경우 첫 번째 오류 발생 시 예외를 throw 하는 대신 시간이 초과 될 때까지 신뢰할 수 있는 메시징에서 인증 되지 않은 클라이언트를 인증 합니다.</span><span class="sxs-lookup"><span data-stu-id="d959a-116">When using message security with reliable sessions, Reliable Messaging attempts to authenticate an unauthenticated client until a timeout occurs instead of throwing an exception upon first failure.</span></span>

### <a name="configure-the-service-with-a-wshttpbinding-to-use-a-reliable-session"></a><span data-ttu-id="d959a-117">신뢰할 수 있는 세션을 사용 하도록 WSHttpBinding으로 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="d959a-117">Configure the service with a WSHttpBinding to use a reliable session</span></span>

<span data-ttu-id="d959a-118">이 절차는 [방법: 신뢰할 수 있는 세션 내에서 메시지 교환](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md)에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d959a-118">This procedure is described in [How to: Exchange Messages Within a Reliable Session](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md).</span></span>

### <a name="configure-the-client-with-a-wshttpbinding-to-use-a-reliable-session"></a><span data-ttu-id="d959a-119">신뢰할 수 있는 세션을 사용 하도록 WSHttpBinding으로 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="d959a-119">Configure the client with a WSHttpBinding to use a reliable session</span></span>

<span data-ttu-id="d959a-120">이 절차는 [방법: 신뢰할 수 있는 세션 내에서 메시지 교환](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md)에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d959a-120">This procedure is described in [How to: Exchange Messages Within a Reliable Session](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md).</span></span>

### <a name="set-the-mode-and-clientcredentialtype-in-configuration"></a><span data-ttu-id="d959a-121">구성에서 모드 및 ClientCredentialType 설정</span><span class="sxs-lookup"><span data-stu-id="d959a-121">Set the mode and ClientCredentialType in configuration</span></span>

1. <span data-ttu-id="d959a-122">구성 파일의 [ **\<bindings >** ](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) 요소에 적절 한 바인딩 요소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d959a-122">Add an appropriate binding element to the [**\<bindings>**](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) element of the configuration file.</span></span> <span data-ttu-id="d959a-123">다음 예제에서는 [ **\<wsHttpBinding >** ](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) 요소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d959a-123">The following example adds a [**\<wsHttpBinding>**](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) element.</span></span>

1. <span data-ttu-id="d959a-124">**\<binding >** 요소를 추가 하 고 해당 `name` 특성을 적절 한 값으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d959a-124">Add a **\<binding>** element and set its `name` attribute to an appropriate value.</span></span> <span data-ttu-id="d959a-125">이 예에서는 `MessageSecurity`이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d959a-125">The example uses the name `MessageSecurity`.</span></span>

1. <span data-ttu-id="d959a-126">**\<security >** 요소를 추가 하 고 `mode` 특성을 `Message`로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d959a-126">Add a **\<security>** element and set the `mode` attribute to `Message`.</span></span>

1. <span data-ttu-id="d959a-127">**\<security >** 요소 내에서 **\<메시지 >** 요소를 추가 하 고 `clientCredentialType` 특성을 `Certificate`로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d959a-127">Within the **\<security>** element, add a **\<message>** element and set the `clientCredentialType` attribute to `Certificate`.</span></span>

```xml
<wsHttpBinding>
  <binding name="MessageSecurity">
    <security mode="Message">
      <message clientCredentialType="Certificate" />
    </security>
  </binding>
</wsHttpBinding>
```
