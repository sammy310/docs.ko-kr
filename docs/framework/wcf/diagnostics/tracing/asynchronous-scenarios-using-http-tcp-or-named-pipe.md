---
title: HTTP, TCP 또는 명명된 파이프를 사용하는 비동기 시나리오
ms.date: 03/30/2017
ms.assetid: a4d62402-43a4-48a4-9ced-220633ebc4ce
ms.openlocfilehash: d08f70186a59b8717c4441167ee720ba1c20b9dc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61998292"
---
# <a name="asynchronous-scenarios-using-http-tcp-or-named-pipe"></a><span data-ttu-id="c6e81-102">HTTP, TCP 또는 명명된 파이프를 사용하는 비동기 시나리오</span><span class="sxs-lookup"><span data-stu-id="c6e81-102">Asynchronous Scenarios using HTTP, TCP, or Named-Pipe</span></span>
<span data-ttu-id="c6e81-103">이 항목에서는 HTTP, TCP 또는 명명된 파이프를 사용하는 다중 스레드 요청이 포함된 다양한 비동기 request/reply 시나리오의 작업 및 전송에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e81-103">This topic describes the activities and transfers for different asynchronous request/reply scenarios, with multithreaded requests using HTTP, TCP, or named pipe.</span></span>  
  
## <a name="asynchronous-requestreply-without-errors"></a><span data-ttu-id="c6e81-104">오류가 없는 비동기 Request/Reply</span><span class="sxs-lookup"><span data-stu-id="c6e81-104">Asynchronous Request/Reply without Errors</span></span>  
 <span data-ttu-id="c6e81-105">이 단원에서는 다중 스레드 클라이언트에서의 비동기 request/reply 시나리오 작업 및 전송에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e81-105">This section describes the activities and transfers for an asynchronous request/reply scenario, with multithreaded clients.</span></span>  
  
 <span data-ttu-id="c6e81-106">`beginCall`이 반환되고 `endCall`이 반환되면 호출자 작업이 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6e81-106">The caller activity terminates when `beginCall` returns, and `endCall` returns.</span></span> <span data-ttu-id="c6e81-107">콜백을 호출하면 콜백이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6e81-107">If a callback is called, the callback returns.</span></span>  
  
 <span data-ttu-id="c6e81-108">`beginCall`이 반환되거나, `endCall`이 반환되거나, 작업에서 호출한 경우 콜백이 반환되면 호출된 작업이 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6e81-108">The called activity terminates when `beginCall` returns, `endCall` returns, or when the callback returns if it was called from that activity.</span></span>  
  
### <a name="asynchronous-client-without-callback"></a><span data-ttu-id="c6e81-109">콜백이 없는 비동기 클라이언트</span><span class="sxs-lookup"><span data-stu-id="c6e81-109">Asynchronous Client without Callback</span></span>  
  
#### <a name="propagation-is-enabled-on-both-sides-using-http"></a><span data-ttu-id="c6e81-110">전파는 양쪽 모두에서 HTTP를 사용하여 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6e81-110">Propagation is Enabled on Both Sides, using HTTP</span></span>  
 <span data-ttu-id="c6e81-111">![비동기 시나리오](../../../../../docs/framework/wcf/diagnostics/tracing/media/asyn1.gif "Asyn1")</span><span class="sxs-lookup"><span data-stu-id="c6e81-111">![Asynchronous scenarios](../../../../../docs/framework/wcf/diagnostics/tracing/media/asyn1.gif "Asyn1")</span></span>  
  
 <span data-ttu-id="c6e81-112">그림 1입니다.</span><span class="sxs-lookup"><span data-stu-id="c6e81-112">Figure 1.</span></span> <span data-ttu-id="c6e81-113">콜백이 없는 비동기 클라이언트, `propagateActivity` = `true` 양쪽, HTTP</span><span class="sxs-lookup"><span data-stu-id="c6e81-113">Asynchronous client, no callback, `propagateActivity`=`true` on both sides, HTTP</span></span>  
  
 <span data-ttu-id="c6e81-114">하는 경우 `propagateActivity` = `true`를 ProcessMessage는 전송 목표 ProcessAction 동작을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c6e81-114">If `propagateActivity`=`true`, ProcessMessage indicates which ProcessAction activity to transfer to.</span></span>  
  
 <span data-ttu-id="c6e81-115">HTTP기반 시나리오의 경우 ReceiveBytes는 처음 보내는 메시지에서 호출되어 요청 수명이 끝날 때까지 존재합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e81-115">For HTTP-based scenarios, ReceiveBytes is invoked on the first message to send, and exists for the lifetime of the request.</span></span>  
  
#### <a name="propagation-is-disabled-on-either-sides-using-http"></a><span data-ttu-id="c6e81-116">HTTP를 사용하며 한쪽에서 전파가 비활성화</span><span class="sxs-lookup"><span data-stu-id="c6e81-116">Propagation is Disabled on Either Sides, using HTTP</span></span>  
 <span data-ttu-id="c6e81-117">하는 경우 `propagateActivity` = `false` 한쪽에서 ProcessMessage 전송 목표 ProcessAction 동작 나타내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c6e81-117">If `propagateActivity`=`false` on either side, ProcessMessage does not indicate which ProcessAction activity to transfer to.</span></span> <span data-ttu-id="c6e81-118">따라서 새 임시 ProcessAction 동작이 새 ID로 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6e81-118">Therefore, a new temporary ProcessAction activity with a new ID is invoked.</span></span> <span data-ttu-id="c6e81-119">비동기 응답이 ServiceModel 모드에 있는 요청과 일치하는 경우 로컬 컨텍스트에서 작업 ID를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6e81-119">When the asynchronous response is matched to the request in ServiceModel code, the Activity ID can be retrieved from the local context.</span></span> <span data-ttu-id="c6e81-120">실제 ProcessAction 동작을 해당 ID와 함께 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6e81-120">The actual ProcessAction activity can be transferred to with that ID.</span></span>  
  
 <span data-ttu-id="c6e81-121">![HTTP를 사용 하 여 비동기 시나리오&#47;TCP&#47;명명 된 파이프](../../../../../docs/framework/wcf/diagnostics/tracing/media/async2.gif "Async2")</span><span class="sxs-lookup"><span data-stu-id="c6e81-121">![Asynchronous scenarios using HTTP&#47;TCP&#47;Named Pipe](../../../../../docs/framework/wcf/diagnostics/tracing/media/async2.gif "Async2")</span></span>  
  
 <span data-ttu-id="c6e81-122">그림 2.</span><span class="sxs-lookup"><span data-stu-id="c6e81-122">Figure 2.</span></span> <span data-ttu-id="c6e81-123">콜백이 없는 비동기 클라이언트, `propagateActivity` = `false` 한쪽에서 HTTP</span><span class="sxs-lookup"><span data-stu-id="c6e81-123">Asynchronous client, no callback, `propagateActivity`=`false` on either side, HTTP</span></span>  
  
 <span data-ttu-id="c6e81-124">HTTP기반 시나리오의 경우 ReceiveBytes는 처음 보내는 메시지에서 호출되어 요청 수명이 끝날 때까지 존재합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e81-124">For HTTP-based scenarios, ReceiveBytes is invoked on the first message to send, and exists for the lifetime of the request.</span></span>  
  
 <span data-ttu-id="c6e81-125">비동기 클라이언트에 Process Action 동작이 만들어집니다 때 `propagateActivity` = `false` 호출자 나 호출 수신자에서 응답 메시지는 Action 헤더가 포함 되지 않은 경우.</span><span class="sxs-lookup"><span data-stu-id="c6e81-125">A Process Action activity is created on an asynchronous client when `propagateActivity`=`false` at the caller or callee, and when the response message does not include an Action header.</span></span>  
  
#### <a name="propagation-is-enabled-on-both-sides-using-tcp-or-named-pipe"></a><span data-ttu-id="c6e81-126">전파는 양쪽 모두에서 TCP 또는 명명된 파이프를 사용하여 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6e81-126">Propagation is Enabled on Both Sides, using TCP or Named Pipe</span></span>  
 <span data-ttu-id="c6e81-127">![HTTP를 사용 하 여 비동기 시나리오&#47;TCP&#47;명명 된 파이프](../../../../../docs/framework/wcf/diagnostics/tracing/media/async3.gif "Async3")</span><span class="sxs-lookup"><span data-stu-id="c6e81-127">![Asynchronous scenarios using HTTP&#47;TCP&#47;Named Pipe](../../../../../docs/framework/wcf/diagnostics/tracing/media/async3.gif "Async3")</span></span>  
  
 <span data-ttu-id="c6e81-128">그림 3.</span><span class="sxs-lookup"><span data-stu-id="c6e81-128">Figure 3.</span></span> <span data-ttu-id="c6e81-129">콜백이 없는 비동기 클라이언트, `propagateActivity` = `true` 양쪽 모두 명명 된 파이프/t c P</span><span class="sxs-lookup"><span data-stu-id="c6e81-129">Asynchronous client, no callback, `propagateActivity`=`true` on both sides, Named-Pipe/TCP</span></span>  
  
 <span data-ttu-id="c6e81-130">명명된 파이프 또는 TCP 기반 시나리오에서 ReceiveBytes는 클라이언트가 열리면 호출되어 연결이 지속되는 동안 존재합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e81-130">For a Named-Pipe or TCP-based scenario, ReceiveBytes is invoked when the client is opened, and exists for the lifetime of the connection.</span></span>  
  
 <span data-ttu-id="c6e81-131">그림 1 비슷합니다 `propagateActivity` = `true`를 ProcessMessage는 전송 목표 ProcessAction 동작을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c6e81-131">Similar to Figure 1, if `propagateActivity`=`true`, ProcessMessage indicates which ProcessAction activity to transfer to.</span></span>  
  
#### <a name="propagation-is-disabled-on-either-sides-using-tcp-or-named-pipe"></a><span data-ttu-id="c6e81-132">전파는 한쪽에서 TCP 또는 명명된 파이프를 사용하여 비활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6e81-132">Propagation is Disabled on Either Sides, using TCP or Named Pipe</span></span>  
 <span data-ttu-id="c6e81-133">명명된 파이프 또는 TCP 기반 시나리오에서 ReceiveBytes는 클라이언트가 열리면 호출되어 연결이 지속되는 동안 존재합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e81-133">For a Named-Pipe or TCP-based scenario, ReceiveBytes is invoked when the client is opened, and exists for the lifetime of the connection.</span></span>  
  
 <span data-ttu-id="c6e81-134">Fig.2, 유사한 경우 `propagateActivity` = `false` 한쪽에서 ProcessMessage 전송 목표 ProcessAction 동작 나타내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c6e81-134">Similar to Fig.2, If `propagateActivity`=`false` on either side, ProcessMessage does not indicate which ProcessAction activity to transfer to.</span></span> <span data-ttu-id="c6e81-135">따라서 새 임시 ProcessAction 동작이 새 ID로 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6e81-135">Therefore, a new temporary ProcessAction activity with a new ID is invoked.</span></span> <span data-ttu-id="c6e81-136">비동기 응답이 ServiceModel 모드에 있는 요청과 일치하는 경우 로컬 컨텍스트에서 작업 ID를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6e81-136">When the asynchronous response is matched to the request in ServiceModel code, the Activity ID can be retrieved from the local context.</span></span> <span data-ttu-id="c6e81-137">실제 ProcessAction 동작을 해당 ID와 함께 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6e81-137">The actual ProcessAction activity can be transferred to with that ID.</span></span>  
  
 <span data-ttu-id="c6e81-138">![HTTP를 사용 하 여 비동기 시나리오&#47;TCP&#47; 명명 된 파이프](../../../../../docs/framework/wcf/diagnostics/tracing/media/async4.gif "Async4")</span><span class="sxs-lookup"><span data-stu-id="c6e81-138">![Asynchronous scenarios using HTTP&#47;TCP&#47; Named Pipes](../../../../../docs/framework/wcf/diagnostics/tracing/media/async4.gif "Async4")</span></span>  
  
 <span data-ttu-id="c6e81-139">그림 4와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c6e81-139">Figure 4.</span></span> <span data-ttu-id="c6e81-140">콜백이 없는 비동기 클라이언트, `propagateActivity` = `false` 한쪽에서 명명 된 파이프/t c P</span><span class="sxs-lookup"><span data-stu-id="c6e81-140">Asynchronous client, no callback, `propagateActivity`=`false` on either side, Named-Pipe/TCP</span></span>  
  
### <a name="asynchronous-client-with-callback"></a><span data-ttu-id="c6e81-141">콜백이 있는 비동기 클라이언트</span><span class="sxs-lookup"><span data-stu-id="c6e81-141">Asynchronous client with Callback</span></span>  
 <span data-ttu-id="c6e81-142">이 시나리오에서는 콜백과 `endCall`에 G 및 A’ 작업과 출력/입력되는 전송을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e81-142">This scenario adds activities G and A’, for the callback and `endCall`, and their transfers in/out.</span></span>  
  
 <span data-ttu-id="c6e81-143">이 섹션에서는 사용 하 여 HTTP를 사용 하 여 보여 줍니다 `propragateActivity` = `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e81-143">This section only demonstrates using HTTP with `propragateActivity`=`true`.</span></span> <span data-ttu-id="c6e81-144">그러나 추가 작업 및 전송에도 적용 다른 경우 (즉, `propagateActivity` = `false`, TCP 또는 명명 된 파이프를 사용 하 여).</span><span class="sxs-lookup"><span data-stu-id="c6e81-144">However, the additional activities and transfers also apply to the other cases (that is, `propagateActivity`=`false`, using TCP or Named-Pipe).</span></span>  
  
 <span data-ttu-id="c6e81-145">클라이언트에서 사용자 코드를 호출하여 결과가 준비된 것을 알리면 콜백에서 새 작업(G)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c6e81-145">The callback creates a new activity (G) when the client calls user code to notify that results are ready.</span></span> <span data-ttu-id="c6e81-146">그러면 사용자 코드에서 콜백 내부(그림 5) 또는 콜백 외부(그림 6)로부터 `endCall`을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e81-146">User code then calls `endCall` within the callback (as shown in Figure 5) or outside the callback (Figure 6).</span></span> <span data-ttu-id="c6e81-147">사용자 작업 알지 못하기 때문 `endCall` 호출 되 고,이 작업은 레이블이 지정 된 `A’`합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e81-147">Because it is not known which user activity `endCall` is being called from, this activity is labeled `A’`.</span></span> <span data-ttu-id="c6e81-148">A’는 A와 같을 수도 있고 다를 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6e81-148">It is possible that A’ can be identical to or different from A.</span></span>  
  
 <span data-ttu-id="c6e81-149">![비동기 시나리오](../../../../../docs/framework/wcf/diagnostics/tracing/media/asynccallback1.gif "AsyncCallback1")</span><span class="sxs-lookup"><span data-stu-id="c6e81-149">![Asynchronous scenarios](../../../../../docs/framework/wcf/diagnostics/tracing/media/asynccallback1.gif "AsyncCallback1")</span></span>  
  
 <span data-ttu-id="c6e81-150">그림 5입니다.</span><span class="sxs-lookup"><span data-stu-id="c6e81-150">Figure 5.</span></span> <span data-ttu-id="c6e81-151">콜백이 있는 비동기 클라이언트, 콜백 내부의 `endCall`</span><span class="sxs-lookup"><span data-stu-id="c6e81-151">Asynchronous client with callback, `endCall` in Callback</span></span>  
  
 <span data-ttu-id="c6e81-152">![비동기 시나리오](../../../../../docs/framework/wcf/diagnostics/tracing/media/asynccallback2.gif "AsyncCallback2")</span><span class="sxs-lookup"><span data-stu-id="c6e81-152">![Asynchronous Scenarios](../../../../../docs/framework/wcf/diagnostics/tracing/media/asynccallback2.gif "AsyncCallback2")</span></span>  
  
 <span data-ttu-id="c6e81-153">그림 6입니다.</span><span class="sxs-lookup"><span data-stu-id="c6e81-153">Figure 6.</span></span> <span data-ttu-id="c6e81-154">콜백이 있는 비동기 클라이언트, 콜백 외부의 `endCall`</span><span class="sxs-lookup"><span data-stu-id="c6e81-154">Asynchronous client with callback, `endCall` outside of Callback</span></span>  
  
### <a name="asynchronous-server-with-callback"></a><span data-ttu-id="c6e81-155">콜백이 있는 비동기 서버</span><span class="sxs-lookup"><span data-stu-id="c6e81-155">Asynchronous Server with Callback</span></span>  
 <span data-ttu-id="c6e81-156">![HTTP를 사용 하 여 비동기 시나리오&#47;TCP&#47; 명명 된&#45;파이프](../../../../../docs/framework/wcf/diagnostics/tracing/media/aynchserver.gif "AynchServer")</span><span class="sxs-lookup"><span data-stu-id="c6e81-156">![Asynchronous scenarios using HTTP&#47;TCP&#47; Named&#45;Pipe](../../../../../docs/framework/wcf/diagnostics/tracing/media/aynchserver.gif "AynchServer")</span></span>  
  
 <span data-ttu-id="c6e81-157">그림 7입니다.</span><span class="sxs-lookup"><span data-stu-id="c6e81-157">Figure 7.</span></span> <span data-ttu-id="c6e81-158">콜백이 있는 비동기 서버</span><span class="sxs-lookup"><span data-stu-id="c6e81-158">Asynchronous server, with callback</span></span>  
  
 <span data-ttu-id="c6e81-159">채널 스택에서는 메시지를 받으면 클라이언트를 콜백합니다. 이 처리의 추적은 ProcessRequest 작업 자체에서 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="c6e81-159">The channel stack calls back the client on Message Receive: traces for this processing are emitted in the ProcessRequest activity itself.</span></span>  
  
## <a name="asynchronous-requestreply-with-errors"></a><span data-ttu-id="c6e81-160">오류가 있는 Request/Reply</span><span class="sxs-lookup"><span data-stu-id="c6e81-160">Asynchronous Request/Reply with Errors</span></span>  
 <span data-ttu-id="c6e81-161">`endCall`을 수행하는 동안 오류 메시지 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="c6e81-161">Fault message errors are received during `endCall`.</span></span> <span data-ttu-id="c6e81-162">그 점을 제외한 작업과 전송은 이전 시나리오와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e81-162">Otherwise, activities and transfers are similar to previous scenarios.</span></span>  
  
## <a name="asynchronous-one-way-with-or-without-errors"></a><span data-ttu-id="c6e81-163">오류가 있거나 없는 비동기 단방향</span><span class="sxs-lookup"><span data-stu-id="c6e81-163">Asynchronous One-Way with or without Errors</span></span>  
 <span data-ttu-id="c6e81-164">클라이언트에 응답이나 오류가 반환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c6e81-164">No response or fault is returned to the client.</span></span>
