---
title: HTTP, TCP 또는 명명된 파이프를 사용하는 비동기 시나리오
ms.date: 03/30/2017
ms.assetid: a4d62402-43a4-48a4-9ced-220633ebc4ce
ms.openlocfilehash: 00213c8d117f4319d7e29312dd0b9805d916231a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96244147"
---
# <a name="asynchronous-scenarios-using-http-tcp-or-named-pipe"></a><span data-ttu-id="35c14-102">HTTP, TCP 또는 명명된 파이프를 사용하는 비동기 시나리오</span><span class="sxs-lookup"><span data-stu-id="35c14-102">Asynchronous Scenarios using HTTP, TCP, or Named-Pipe</span></span>

<span data-ttu-id="35c14-103">이 항목에서는 HTTP, TCP 또는 명명된 파이프를 사용하는 다중 스레드 요청이 포함된 다양한 비동기 request/reply 시나리오의 작업 및 전송에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="35c14-103">This topic describes the activities and transfers for different asynchronous request/reply scenarios, with multithreaded requests using HTTP, TCP, or named pipe.</span></span>  
  
## <a name="asynchronous-requestreply-without-errors"></a><span data-ttu-id="35c14-104">오류가 없는 비동기 Request/Reply</span><span class="sxs-lookup"><span data-stu-id="35c14-104">Asynchronous Request/Reply without Errors</span></span>  

 <span data-ttu-id="35c14-105">이 단원에서는 다중 스레드 클라이언트에서의 비동기 request/reply 시나리오 작업 및 전송에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="35c14-105">This section describes the activities and transfers for an asynchronous request/reply scenario, with multithreaded clients.</span></span>  
  
 <span data-ttu-id="35c14-106">`beginCall`이 반환되고 `endCall`이 반환되면 호출자 작업이 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="35c14-106">The caller activity terminates when `beginCall` returns, and `endCall` returns.</span></span> <span data-ttu-id="35c14-107">콜백을 호출하면 콜백이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="35c14-107">If a callback is called, the callback returns.</span></span>  
  
 <span data-ttu-id="35c14-108">`beginCall`이 반환되거나, `endCall`이 반환되거나, 작업에서 호출한 경우 콜백이 반환되면 호출된 작업이 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="35c14-108">The called activity terminates when `beginCall` returns, `endCall` returns, or when the callback returns if it was called from that activity.</span></span>  
  
### <a name="asynchronous-client-without-callback"></a><span data-ttu-id="35c14-109">콜백이 없는 비동기 클라이언트</span><span class="sxs-lookup"><span data-stu-id="35c14-109">Asynchronous Client without Callback</span></span>  
  
#### <a name="propagation-is-enabled-on-both-sides-using-http"></a><span data-ttu-id="35c14-110">전파는 양쪽 모두에서 HTTP를 사용하여 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="35c14-110">Propagation is Enabled on Both Sides, using HTTP</span></span>  

 ![PropagateActivity가 true로 설정 된 경우 콜백이 없는 비동기 클라이언트입니다.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-client-no-callback.gif)
  
 <span data-ttu-id="35c14-112">인 경우 `propagateActivity=true` processmessage는 전송할 Processmessage 동작을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="35c14-112">If `propagateActivity=true`, ProcessMessage indicates which ProcessAction activity to transfer to.</span></span>  
  
 <span data-ttu-id="35c14-113">HTTP기반 시나리오의 경우 ReceiveBytes는 처음 보내는 메시지에서 호출되어 요청 수명이 끝날 때까지 존재합니다.</span><span class="sxs-lookup"><span data-stu-id="35c14-113">For HTTP-based scenarios, ReceiveBytes is invoked on the first message to send, and exists for the lifetime of the request.</span></span>  
  
#### <a name="propagation-is-disabled-on-either-sides-using-http"></a><span data-ttu-id="35c14-114">HTTP를 사용하며 한쪽에서 전파가 비활성화</span><span class="sxs-lookup"><span data-stu-id="35c14-114">Propagation is Disabled on Either Sides, using HTTP</span></span>  

 <span data-ttu-id="35c14-115">한쪽 `propagateActivity=false` 에 있는 경우 ProcessMessage는 전송할 Processmessage 동작을 나타내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="35c14-115">If `propagateActivity=false` on either side, ProcessMessage does not indicate which ProcessAction activity to transfer to.</span></span> <span data-ttu-id="35c14-116">따라서 새 임시 ProcessAction 동작이 새 ID로 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="35c14-116">Therefore, a new temporary ProcessAction activity with a new ID is invoked.</span></span> <span data-ttu-id="35c14-117">비동기 응답이 ServiceModel 모드에 있는 요청과 일치하는 경우 로컬 컨텍스트에서 작업 ID를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35c14-117">When the asynchronous response is matched to the request in ServiceModel code, the Activity ID can be retrieved from the local context.</span></span> <span data-ttu-id="35c14-118">실제 ProcessAction 동작을 해당 ID와 함께 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35c14-118">The actual ProcessAction activity can be transferred to with that ID.</span></span>  
  
 ![양쪽에서 propagateActivity가 false로 설정 된 콜백이 없는 비동기 클라이언트입니다.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-scenario-propagation-disabled-either-side.gif)  

 <span data-ttu-id="35c14-120">HTTP기반 시나리오의 경우 ReceiveBytes는 처음 보내는 메시지에서 호출되어 요청 수명이 끝날 때까지 존재합니다.</span><span class="sxs-lookup"><span data-stu-id="35c14-120">For HTTP-based scenarios, ReceiveBytes is invoked on the first message to send, and exists for the lifetime of the request.</span></span>  
  
 <span data-ttu-id="35c14-121">프로세스 동작 작업은 호출자 또는 호출 수신자에서 비동기 클라이언트에 생성 되 `propagateActivity=false` 고 응답 메시지에 작업 헤더가 포함 되지 않은 경우에 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="35c14-121">A Process Action activity is created on an asynchronous client when `propagateActivity=false` at the caller or callee, and when the response message does not include an Action header.</span></span>  
  
#### <a name="propagation-is-enabled-on-both-sides-using-tcp-or-named-pipe"></a><span data-ttu-id="35c14-122">전파는 양쪽 모두에서 TCP 또는 명명된 파이프를 사용하여 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="35c14-122">Propagation is Enabled on Both Sides, using TCP or Named Pipe</span></span>  

 ![양쪽에서 propagateActivity가 true로 설정 되 고, 명명 된 파이프/TCP에서 콜백이 없는 비동기 클라이언트입니다.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-scenario-propagation-enabled-using-tcp.gif)  
  
 <span data-ttu-id="35c14-124">명명된 파이프 또는 TCP 기반 시나리오에서 ReceiveBytes는 클라이언트가 열리면 호출되어 연결이 지속되는 동안 존재합니다.</span><span class="sxs-lookup"><span data-stu-id="35c14-124">For a Named-Pipe or TCP-based scenario, ReceiveBytes is invoked when the client is opened, and exists for the lifetime of the connection.</span></span>  
  
 <span data-ttu-id="35c14-125">첫 번째 이미지와 마찬가지로 `propagateActivity=true` processmessage는 전송할 Processmessage 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="35c14-125">Similar to the first image, if `propagateActivity=true`, ProcessMessage indicates which ProcessAction activity to transfer to.</span></span>  
  
#### <a name="propagation-is-disabled-on-either-sides-using-tcp-or-named-pipe"></a><span data-ttu-id="35c14-126">전파는 한쪽에서 TCP 또는 명명된 파이프를 사용하여 비활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="35c14-126">Propagation is Disabled on Either Sides, using TCP or Named Pipe</span></span>  

 <span data-ttu-id="35c14-127">명명된 파이프 또는 TCP 기반 시나리오에서 ReceiveBytes는 클라이언트가 열리면 호출되어 연결이 지속되는 동안 존재합니다.</span><span class="sxs-lookup"><span data-stu-id="35c14-127">For a Named-Pipe or TCP-based scenario, ReceiveBytes is invoked when the client is opened, and exists for the lifetime of the connection.</span></span>  
  
 <span data-ttu-id="35c14-128">두 번째 이미지와 마찬가지로 두 `propagateActivity=false` 쪽 모두에서 ProcessMessage는 전송할 Processmessage 작업을 나타내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="35c14-128">Similar to the second image, if `propagateActivity=false` on either side, ProcessMessage does not indicate which ProcessAction activity to transfer to.</span></span> <span data-ttu-id="35c14-129">따라서 새 임시 ProcessAction 동작이 새 ID로 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="35c14-129">Therefore, a new temporary ProcessAction activity with a new ID is invoked.</span></span> <span data-ttu-id="35c14-130">비동기 응답이 ServiceModel 모드에 있는 요청과 일치하는 경우 로컬 컨텍스트에서 작업 ID를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35c14-130">When the asynchronous response is matched to the request in ServiceModel code, the Activity ID can be retrieved from the local context.</span></span> <span data-ttu-id="35c14-131">실제 ProcessAction 동작을 해당 ID와 함께 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35c14-131">The actual ProcessAction activity can be transferred to with that ID.</span></span>  
  
 ![콜백이 없는 비동기 클라이언트는 양쪽 및 명명 된 파이프/TCP에서 propagateActivity가 false로 설정 됩니다.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-scenario-propagation-disabled-using-tcp.gif)  

### <a name="asynchronous-client-with-callback"></a><span data-ttu-id="35c14-133">콜백이 있는 비동기 클라이언트</span><span class="sxs-lookup"><span data-stu-id="35c14-133">Asynchronous client with Callback</span></span>  

 <span data-ttu-id="35c14-134">이 시나리오에서는 콜백과 `endCall`에 G 및 A’ 작업과 출력/입력되는 전송을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="35c14-134">This scenario adds activities G and A’, for the callback and `endCall`, and their transfers in/out.</span></span>  
  
 <span data-ttu-id="35c14-135">이 섹션에서는와 함께 HTTP를 사용 하는 방법을 보여 줍니다 `propagateActivity` = `true` .</span><span class="sxs-lookup"><span data-stu-id="35c14-135">This section only demonstrates using HTTP with `propagateActivity`=`true`.</span></span> <span data-ttu-id="35c14-136">그러나 추가 작업 및 전송은 다른 경우 (즉, `propagateActivity` = `false` TCP 또는 명명 된 파이프 사용)에도 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="35c14-136">However, the additional activities and transfers also apply to the other cases (that is, `propagateActivity`=`false`, using TCP or Named-Pipe).</span></span>  
  
 <span data-ttu-id="35c14-137">클라이언트에서 사용자 코드를 호출하여 결과가 준비된 것을 알리면 콜백에서 새 작업(G)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="35c14-137">The callback creates a new activity (G) when the client calls user code to notify that results are ready.</span></span> <span data-ttu-id="35c14-138">그러면 사용자 코드에서 콜백 내부(그림 5) 또는 콜백 외부(그림 6)로부터 `endCall`을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="35c14-138">User code then calls `endCall` within the callback (as shown in Figure 5) or outside the callback (Figure 6).</span></span> <span data-ttu-id="35c14-139">에서 호출 되는 사용자 작업을 알 수 없기 때문에 `endCall` 이 활동에는 레이블이 지정 됩니다 `A’` .</span><span class="sxs-lookup"><span data-stu-id="35c14-139">Because it is not known which user activity `endCall` is being called from, this activity is labeled `A’`.</span></span> <span data-ttu-id="35c14-140">A’는 A와 같을 수도 있고 다를 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35c14-140">It is possible that A’ can be identical to or different from A.</span></span>  
  
 ![콜백이 콜백 인 비동기 클라이언트를 표시 합니다.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-client-callback-endcall-in-callback.gif)  

 ![콜백이 있는 비동기 클라이언트를 표시 합니다. 콜백이 외부에서 endcall입니다.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-client-callback-endcall-outside-callback.gif)  

### <a name="asynchronous-server-with-callback"></a><span data-ttu-id="35c14-143">콜백이 있는 비동기 서버</span><span class="sxs-lookup"><span data-stu-id="35c14-143">Asynchronous Server with Callback</span></span>  

 ![콜백이 있는 비동기 서버를 표시 합니다.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-server-callback.gif)  

 <span data-ttu-id="35c14-145">채널 스택에서는 메시지를 받으면 클라이언트를 콜백합니다. 이 처리의 추적은 ProcessRequest 작업 자체에서 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="35c14-145">The channel stack calls back the client on Message Receive: traces for this processing are emitted in the ProcessRequest activity itself.</span></span>  
  
## <a name="asynchronous-requestreply-with-errors"></a><span data-ttu-id="35c14-146">오류가 있는 Request/Reply</span><span class="sxs-lookup"><span data-stu-id="35c14-146">Asynchronous Request/Reply with Errors</span></span>  

 <span data-ttu-id="35c14-147">`endCall`을 수행하는 동안 오류 메시지 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="35c14-147">Fault message errors are received during `endCall`.</span></span> <span data-ttu-id="35c14-148">그 점을 제외한 작업과 전송은 이전 시나리오와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="35c14-148">Otherwise, activities and transfers are similar to previous scenarios.</span></span>  
  
## <a name="asynchronous-one-way-with-or-without-errors"></a><span data-ttu-id="35c14-149">오류가 있거나 없는 비동기 단방향</span><span class="sxs-lookup"><span data-stu-id="35c14-149">Asynchronous One-Way with or without Errors</span></span>  

 <span data-ttu-id="35c14-150">클라이언트에 응답이나 오류가 반환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="35c14-150">No response or fault is returned to the client.</span></span>
