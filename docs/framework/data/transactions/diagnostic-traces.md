---
title: 진단 추적
description: .NET의 진단 추적에 대해 알아봅니다. 추적은 애플리케이션 실행 중에 생성된 특정 메시지의 게시입니다.
ms.date: 03/30/2017
ms.assetid: 28e77a63-d20d-4b6a-9caf-ddad86550427
ms.openlocfilehash: 1999cd922b9e7299cbf3c10a702eb4d2dc6c3fbb
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177243"
---
# <a name="diagnostic-traces"></a><span data-ttu-id="b6964-104">진단 추적</span><span class="sxs-lookup"><span data-stu-id="b6964-104">Diagnostic Traces</span></span>

<span data-ttu-id="b6964-105">추적은 애플리케이션 실행 중에 생성된 특정 메시지의 게시입니다.</span><span class="sxs-lookup"><span data-stu-id="b6964-105">Traces are the publishing of specific messages that are generated during application execution.</span></span> <span data-ttu-id="b6964-106">추적을 사용하는 경우 전송된 메시지를 수집 및 기록하는 메커니즘이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6964-106">When using tracing, you must have a mechanism for collecting and recording the messages that are sent.</span></span> <span data-ttu-id="b6964-107">수신기가 추적 메시지를 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="b6964-107">Trace messages are received by listeners.</span></span> <span data-ttu-id="b6964-108">수신기의 목적은 추적 메시지를 수집, 저장 및 라우팅하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b6964-108">The purpose of a listener is to collect, store, and route tracing messages.</span></span> <span data-ttu-id="b6964-109">수신기는 추적 출력을 로그, 창 또는 텍스트 파일과 같은 적절한 대상에 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="b6964-109">Listeners direct the tracing output to an appropriate target, such as a log, window, or text file.</span></span>  
  
 <span data-ttu-id="b6964-110">추적을 사용하면 이러한 수신기 중 하나인 <xref:System.Diagnostics.DefaultTraceListener>가 자동으로 만들어지고 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6964-110">One such listener, the <xref:System.Diagnostics.DefaultTraceListener>, is automatically created and initialized when tracing is enabled.</span></span> <span data-ttu-id="b6964-111">추적 출력을 추가 소스에 보내려면 추가 추적 수신기를 만들고 초기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6964-111">If you want trace output to be directed to any additional sources, you must create and initialize additional trace listeners.</span></span> <span data-ttu-id="b6964-112">수신기를 만들 때는 개인이 필요로 하는 내용을 반영해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6964-112">The listeners you create should reflect your individual needs.</span></span> <span data-ttu-id="b6964-113">예를 들어, 모든 추적 출력의 텍스트 레코드를 필요로 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6964-113">For example, you might want a text record of all trace output.</span></span> <span data-ttu-id="b6964-114">이 경우에는 활성화되면 모든 출력을 새 텍스트 파일에 쓰는 수신기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b6964-114">In this case, you would create a listener that wrote all output to a new text file when enabled.</span></span> <span data-ttu-id="b6964-115">반면에 애플리케이션이 실행되는 동안 출력을 보기만 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6964-115">On the other hand, you might only want to view output during application execution.</span></span> <span data-ttu-id="b6964-116">이 경우에는 모든 출력을 콘솔 창으로 보내는 수신기를 만들면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6964-116">In that case, you might create a listener that directed all output to a console window.</span></span> <span data-ttu-id="b6964-117"><xref:System.Diagnostics.EventLogTraceListener>는 추적 출력을 이벤트 로그로 보낼 수 있고 <xref:System.Diagnostics.TextWriterTraceListener>는 추적 출력을 스트림에 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6964-117">The <xref:System.Diagnostics.EventLogTraceListener> can direct trace output to an event log, and the <xref:System.Diagnostics.TextWriterTraceListener> can write trace output to a stream.</span></span>  
  
## <a name="enabling-tracing"></a><span data-ttu-id="b6964-118">추적 사용</span><span class="sxs-lookup"><span data-stu-id="b6964-118">Enabling Tracing</span></span>  

 <span data-ttu-id="b6964-119">트랜잭션 처리 중에 추적을 사용하려면 애플리케이션의 구성 파일을 편집해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6964-119">To enable traces during transaction processing, you should edit your application’s configuration file.</span></span> <span data-ttu-id="b6964-120">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="b6964-120">The following is an example.</span></span>  
  
```xml  
<configuration>  
<system.diagnostics>  
     <sources>  
          <source name="System.Transactions" switchValue="Warning">  
               <listeners>  
                    <add name="tx"
                     type="System.Diagnostics.XmlWriterTraceListener"
                     initializeData= "tx.log" />  
               </listeners>  
          </source>  
     </sources>  
</system.diagnostics>  
</configuration>  
```  
  
 <span data-ttu-id="b6964-121"><xref:System.Transactions> 추적은 "System.Transactions"라는 소스에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6964-121"><xref:System.Transactions> traces are written to the source named "System.Transactions".</span></span> <span data-ttu-id="b6964-122">`add`를 사용하여 사용할 추적 수신기의 이름과 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6964-122">You can use `add` to specify the name and type of the trace listener you want to use.</span></span> <span data-ttu-id="b6964-123">예제 구성에서는 수신기 이름을 "tx"로 지정하고 표준 .NET Framework 추적 수신기(<xref:System.Diagnostics.XmlWriterTraceListener>)를 사용할 형식으로 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="b6964-123">In our example configuration, we named the Listener "tx" and added the standard .NET Framework trace listener (<xref:System.Diagnostics.XmlWriterTraceListener>) as the type we want to use.</span></span> <span data-ttu-id="b6964-124">`initializeData`를 사용하여 해당 수신기의 로그 파일 이름을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b6964-124">Use `initializeData` to set the name of the log file for that listener.</span></span> <span data-ttu-id="b6964-125">또한 단순한 파일 이름 대신 정규화된 경로를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6964-125">In addition, you can substitute a fully qualified path for a simple file name.</span></span>  
  
 <span data-ttu-id="b6964-126">각 추적 메시지 형식에 수준이 할당되어 중요도를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b6964-126">Each trace message type is assigned a level to indicate its degree of importance.</span></span> <span data-ttu-id="b6964-127">app-domain의 추적 수준이 이벤트 형식의 수준보다 낮거나 같으면 해당 메시지가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6964-127">If the app-domain’s trace level is equal or lower than the level of an event type, then that message is generated.</span></span> <span data-ttu-id="b6964-128">추적 수준은 구성 파일의 `switchValue` 설정에 의해 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6964-128">The tracing level is controlled by the `switchValue` setting in the configuration file.</span></span> <span data-ttu-id="b6964-129">진단 추적 메시지와 연결된 수준은 다음 표에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6964-129">The levels that are associated with diagnostic trace messages are defined in the following table.</span></span>  
  
|<span data-ttu-id="b6964-130">추적 수준</span><span class="sxs-lookup"><span data-stu-id="b6964-130">Trace Level</span></span>|<span data-ttu-id="b6964-131">설명</span><span class="sxs-lookup"><span data-stu-id="b6964-131">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="b6964-132">위험</span><span class="sxs-lookup"><span data-stu-id="b6964-132">Critical</span></span>|<span data-ttu-id="b6964-133">다음과 같은 심각한 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="b6964-133">Serious failures, such as the following, have occurred:</span></span><br /><br /> <span data-ttu-id="b6964-134">-사용자 기능이 즉시 손실 될 수 있는 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="b6964-134">-   An error that can cause an immediate loss in user functionality.</span></span><br /><span data-ttu-id="b6964-135">-기능 손실을 방지 하기 위해 관리자가 작업을 수행 해야 하는 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="b6964-135">-   An event that requires an administrator to take action to avoid loss of functionality.</span></span><br /><span data-ttu-id="b6964-136">-코드가 중단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6964-136">-   Code hangs.</span></span><br /><span data-ttu-id="b6964-137">-이 추적 수준은 다른 중요 한 추적을 해석 하는 데 충분 한 컨텍스트를 제공할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6964-137">-   This tracing level can also provide sufficient context for interpreting other critical traces.</span></span> <span data-ttu-id="b6964-138">이를 통해 심각한 오류를 발생시키는 작업 시퀀스를 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6964-138">This can help to identify the sequence of operations leading to a serious failure.</span></span>|  
|<span data-ttu-id="b6964-139">오류</span><span class="sxs-lookup"><span data-stu-id="b6964-139">Error</span></span>|<span data-ttu-id="b6964-140">사용자 기능이 손실될 수 있는 오류(예: 잘못된 구성 또는 네트워크 동작)가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="b6964-140">An error (for example, invalid configuration or network behavior) has occurred that can result in a loss of user functionality.</span></span>|  
|<span data-ttu-id="b6964-141">경고</span><span class="sxs-lookup"><span data-stu-id="b6964-141">Warning</span></span>|<span data-ttu-id="b6964-142">이후에 오류 또는 치명적인 오류를 발생시킬 수 있는 조건이 있습니다(예: 할당 실패 또는 한도 접근).</span><span class="sxs-lookup"><span data-stu-id="b6964-142">A condition exists that can subsequently result in an error or critical failure (for example, allocation failing or approaching a limit).</span></span> <span data-ttu-id="b6964-143">사용자 코드 오류(예: 트랜잭션 중단, 시간 초과, 인증 실패)의 정상적인 처리 중에 경고가 생성될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6964-143">Normal processing of errors from user code (for example, transaction aborted, timeouts, authentication failed) can also generate a warning.</span></span>|  
|<span data-ttu-id="b6964-144">정보</span><span class="sxs-lookup"><span data-stu-id="b6964-144">Information</span></span>|<span data-ttu-id="b6964-145">시스템 상태 모니터링 및 진단, 성능 측정 또는 프로파일링에 유용한 메시지가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6964-145">Messages helpful for monitoring and diagnosing system status, measuring performance, or profiling are generated.</span></span> <span data-ttu-id="b6964-146">여기에는 만들어지거나 커밋되는 트랜잭션, 중요한 경계 초과 또는 중요한 리소스 할당 같은 트랜잭션 및 인리스트먼트 수명 이벤트가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6964-146">These can include transaction and enlistment lifetime events, such as a transaction being created or committed, the crossing of a significant boundary, or the allocation of significant resources.</span></span> <span data-ttu-id="b6964-147">개발자는 용량 계획 및 성능 관리에 이러한 정보를 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6964-147">A developer can then utilize such information for capacity planning and performance management.</span></span>|  
  
## <a name="trace-codes"></a><span data-ttu-id="b6964-148">추적 코드</span><span class="sxs-lookup"><span data-stu-id="b6964-148">Trace Codes</span></span>  

 <span data-ttu-id="b6964-149">다음 표에서는 <xref:System.Transactions> 인프라에서 생성되는 추적 코드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b6964-149">The following table lists the trace codes that are generated by the <xref:System.Transactions> infrastructure.</span></span> <span data-ttu-id="b6964-150">이 표에는 추적 코드 식별자, 추적 <xref:System.Diagnostics.EventTypeFilter.EventType%2A> 의 열거 수준 및 추적에 대 한 **TraceRecord** 에 포함 된 추가 데이터가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6964-150">Included in the table are the trace code identifier, the <xref:System.Diagnostics.EventTypeFilter.EventType%2A> enumeration level for the trace, and the extra data contained in the **TraceRecord** for the trace.</span></span> <span data-ttu-id="b6964-151">또한 추적의 해당 추적 수준도 **TraceRecord**에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6964-151">In addition, the corresponding trace level of the trace is also stored in the **TraceRecord**.</span></span>  
  
|<span data-ttu-id="b6964-152">TraceCode</span><span class="sxs-lookup"><span data-stu-id="b6964-152">TraceCode</span></span>|<span data-ttu-id="b6964-153">EventType</span><span class="sxs-lookup"><span data-stu-id="b6964-153">EventType</span></span>|<span data-ttu-id="b6964-154">TraceRecord의 추가 데이터</span><span class="sxs-lookup"><span data-stu-id="b6964-154">Extra data in TraceRecord</span></span>|  
|---------------|---------------|-------------------------------|  
|<span data-ttu-id="b6964-155">TransactionCreated</span><span class="sxs-lookup"><span data-stu-id="b6964-155">TransactionCreated</span></span>|<span data-ttu-id="b6964-156">정보</span><span class="sxs-lookup"><span data-stu-id="b6964-156">Info</span></span>|<span data-ttu-id="b6964-157">TransactionTraceId</span><span class="sxs-lookup"><span data-stu-id="b6964-157">TransactionTraceId</span></span>|  
|<span data-ttu-id="b6964-158">TransactionPromoted</span><span class="sxs-lookup"><span data-stu-id="b6964-158">TransactionPromoted</span></span>|<span data-ttu-id="b6964-159">정보</span><span class="sxs-lookup"><span data-stu-id="b6964-159">Info</span></span>|<span data-ttu-id="b6964-160">로컬 TransactionTraceId, 분산 TransactionTraceId</span><span class="sxs-lookup"><span data-stu-id="b6964-160">Local TransactionTraceId, Distributed TransactionTraceId</span></span>|  
|<span data-ttu-id="b6964-161">EnlistmentCreated</span><span class="sxs-lookup"><span data-stu-id="b6964-161">EnlistmentCreated</span></span>|<span data-ttu-id="b6964-162">정보</span><span class="sxs-lookup"><span data-stu-id="b6964-162">Info</span></span>|<span data-ttu-id="b6964-163">TransactionTraceId, EnlistmentTraceId, EnlistmentType(durable/volatile), EnlistmentOptions</span><span class="sxs-lookup"><span data-stu-id="b6964-163">TransactionTraceId, EnlistmentTraceId, EnlistmentType (durable/volatile), EnlistmentOptions</span></span>|  
|<span data-ttu-id="b6964-164">EnlistmentCallbackNegative</span><span class="sxs-lookup"><span data-stu-id="b6964-164">EnlistmentCallbackNegative</span></span>|<span data-ttu-id="b6964-165">경고</span><span class="sxs-lookup"><span data-stu-id="b6964-165">Warning</span></span>|<span data-ttu-id="b6964-166">TransactionTraceId, EnlistmentTraceId,</span><span class="sxs-lookup"><span data-stu-id="b6964-166">TransactionTraceId, EnlistmentTraceId,</span></span><br /><br /> <span data-ttu-id="b6964-167">Callback(forcerollback/aborted/indoubt)</span><span class="sxs-lookup"><span data-stu-id="b6964-167">Callback (forcerollback/aborted/indoubt)</span></span>|  
|<span data-ttu-id="b6964-168">TransactionRollbackCalled</span><span class="sxs-lookup"><span data-stu-id="b6964-168">TransactionRollbackCalled</span></span>|<span data-ttu-id="b6964-169">경고</span><span class="sxs-lookup"><span data-stu-id="b6964-169">Warning</span></span>|<span data-ttu-id="b6964-170">TransactionTraceId</span><span class="sxs-lookup"><span data-stu-id="b6964-170">TransactionTraceId</span></span>|  
|<span data-ttu-id="b6964-171">TransactionAborted</span><span class="sxs-lookup"><span data-stu-id="b6964-171">TransactionAborted</span></span>|<span data-ttu-id="b6964-172">경고</span><span class="sxs-lookup"><span data-stu-id="b6964-172">Warning</span></span>|<span data-ttu-id="b6964-173">TransactionTraceId</span><span class="sxs-lookup"><span data-stu-id="b6964-173">TransactionTraceId</span></span>|  
|<span data-ttu-id="b6964-174">TransactionInDoubt</span><span class="sxs-lookup"><span data-stu-id="b6964-174">TransactionInDoubt</span></span>|<span data-ttu-id="b6964-175">경고</span><span class="sxs-lookup"><span data-stu-id="b6964-175">Warning</span></span>|<span data-ttu-id="b6964-176">TransactionTraceId</span><span class="sxs-lookup"><span data-stu-id="b6964-176">TransactionTraceId</span></span>|  
|<span data-ttu-id="b6964-177">TransactionScopeCreated</span><span class="sxs-lookup"><span data-stu-id="b6964-177">TransactionScopeCreated</span></span>|<span data-ttu-id="b6964-178">정보</span><span class="sxs-lookup"><span data-stu-id="b6964-178">Info</span></span>|<span data-ttu-id="b6964-179">TransactionScopeResult. 다음 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6964-179">TransactionScopeResult, which can be the following:</span></span><br /><br /> <span data-ttu-id="b6964-180">-새 트랜잭션.</span><span class="sxs-lookup"><span data-stu-id="b6964-180">-   New transaction.</span></span><br /><span data-ttu-id="b6964-181">-트랜잭션이 전달 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b6964-181">-   Transaction passed.</span></span><br /><span data-ttu-id="b6964-182">-종속 트랜잭션이 전달 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b6964-182">-   Dependent transaction passed.</span></span><br /><span data-ttu-id="b6964-183">-현재 트랜잭션을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6964-183">-   Using current transaction.</span></span><br /><span data-ttu-id="b6964-184">-트랜잭션이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b6964-184">-   No transaction.</span></span><br /><br /> <span data-ttu-id="b6964-185">새 현재 TransactionTraceId</span><span class="sxs-lookup"><span data-stu-id="b6964-185">new current TransactionTraceId</span></span>|  
|<span data-ttu-id="b6964-186">TransactionScopeDisposed</span><span class="sxs-lookup"><span data-stu-id="b6964-186">TransactionScopeDisposed</span></span>|<span data-ttu-id="b6964-187">정보</span><span class="sxs-lookup"><span data-stu-id="b6964-187">Info</span></span>|<span data-ttu-id="b6964-188">범위 "예상" 현재 트랜잭션의 TransactionTraceId입니다.</span><span class="sxs-lookup"><span data-stu-id="b6964-188">TransactionTraceId of the scope’s "expected" current transaction.</span></span>|  
|<span data-ttu-id="b6964-189">TransactionScopeIncomplete</span><span class="sxs-lookup"><span data-stu-id="b6964-189">TransactionScopeIncomplete</span></span>|<span data-ttu-id="b6964-190">경고</span><span class="sxs-lookup"><span data-stu-id="b6964-190">Warning</span></span>|<span data-ttu-id="b6964-191">범위 "예상" 현재 트랜잭션의 TransactionTraceId입니다.</span><span class="sxs-lookup"><span data-stu-id="b6964-191">TransactionTraceId of the scope’s "expected" current transaction.</span></span>|  
|<span data-ttu-id="b6964-192">TransactionScopeNestedIncorrectly</span><span class="sxs-lookup"><span data-stu-id="b6964-192">TransactionScopeNestedIncorrectly</span></span>|<span data-ttu-id="b6964-193">경고</span><span class="sxs-lookup"><span data-stu-id="b6964-193">Warning</span></span>|<span data-ttu-id="b6964-194">범위 "예상" 현재 트랜잭션의 TransactionTraceId입니다.</span><span class="sxs-lookup"><span data-stu-id="b6964-194">TransactionTraceId of the scope’s "expected" current transaction.</span></span>|  
|<span data-ttu-id="b6964-195">TransactionScopeCurrentTransactionChanged</span><span class="sxs-lookup"><span data-stu-id="b6964-195">TransactionScopeCurrentTransactionChanged</span></span>|<span data-ttu-id="b6964-196">경고</span><span class="sxs-lookup"><span data-stu-id="b6964-196">Warning</span></span>|<span data-ttu-id="b6964-197">이전의 현재 TransactionTraceId, 기타 TransactionTraceId</span><span class="sxs-lookup"><span data-stu-id="b6964-197">Old current TransactionTraceId, other TransactionTraceId</span></span>|  
|<span data-ttu-id="b6964-198">TransactionScopeTimeout</span><span class="sxs-lookup"><span data-stu-id="b6964-198">TransactionScopeTimeout</span></span>|<span data-ttu-id="b6964-199">경고</span><span class="sxs-lookup"><span data-stu-id="b6964-199">Warning</span></span>|<span data-ttu-id="b6964-200">범위 "예상" 현재 트랜잭션의 TransactionTraceId입니다.</span><span class="sxs-lookup"><span data-stu-id="b6964-200">TransactionTraceId of the scope’s "expected" current transaction.</span></span>|  
|<span data-ttu-id="b6964-201">DependentCloneCreated</span><span class="sxs-lookup"><span data-stu-id="b6964-201">DependentCloneCreated</span></span>|<span data-ttu-id="b6964-202">정보</span><span class="sxs-lookup"><span data-stu-id="b6964-202">Info</span></span>|<span data-ttu-id="b6964-203">TransactionTraceId, 만들어지는 종속 트랜잭션의 형식(RollbackIfNotComplete/BlockCommitUntilComplete)</span><span class="sxs-lookup"><span data-stu-id="b6964-203">TransactionTraceId, type of dependent transaction created (RollbackIfNotComplete/BlockCommitUntilComplete)</span></span>|  
|<span data-ttu-id="b6964-204">DependentCloneComplete</span><span class="sxs-lookup"><span data-stu-id="b6964-204">DependentCloneComplete</span></span>|<span data-ttu-id="b6964-205">정보</span><span class="sxs-lookup"><span data-stu-id="b6964-205">Info</span></span>|<span data-ttu-id="b6964-206">TransactionTraceId</span><span class="sxs-lookup"><span data-stu-id="b6964-206">TransactionTraceId</span></span>|  
|<span data-ttu-id="b6964-207">RecoveryComplete</span><span class="sxs-lookup"><span data-stu-id="b6964-207">RecoveryComplete</span></span>|<span data-ttu-id="b6964-208">정보</span><span class="sxs-lookup"><span data-stu-id="b6964-208">Info</span></span>|<span data-ttu-id="b6964-209">리소스 관리자 GUID(기본 클래스로부터)</span><span class="sxs-lookup"><span data-stu-id="b6964-209">Resource Manager GUID (from base)</span></span>|  
|<span data-ttu-id="b6964-210">Reenlist</span><span class="sxs-lookup"><span data-stu-id="b6964-210">Reenlist</span></span>|<span data-ttu-id="b6964-211">정보</span><span class="sxs-lookup"><span data-stu-id="b6964-211">Info</span></span>|<span data-ttu-id="b6964-212">리소스 관리자 GUID(기본 클래스로부터)</span><span class="sxs-lookup"><span data-stu-id="b6964-212">Resource Manager GUID (from base)</span></span>|  
|<span data-ttu-id="b6964-213">TransactionSerialized</span><span class="sxs-lookup"><span data-stu-id="b6964-213">TransactionSerialized</span></span>|<span data-ttu-id="b6964-214">정보</span><span class="sxs-lookup"><span data-stu-id="b6964-214">Info</span></span>|<span data-ttu-id="b6964-215">TransactionTraceId</span><span class="sxs-lookup"><span data-stu-id="b6964-215">TransactionTraceId.</span></span>|  
|<span data-ttu-id="b6964-216">TransactionException</span><span class="sxs-lookup"><span data-stu-id="b6964-216">TransactionException</span></span>|<span data-ttu-id="b6964-217">오류</span><span class="sxs-lookup"><span data-stu-id="b6964-217">Error</span></span>|<span data-ttu-id="b6964-218">예외 메시지</span><span class="sxs-lookup"><span data-stu-id="b6964-218">Exception message</span></span>|  
|<span data-ttu-id="b6964-219">InvalidOperationException</span><span class="sxs-lookup"><span data-stu-id="b6964-219">InvalidOperationException</span></span>|<span data-ttu-id="b6964-220">오류</span><span class="sxs-lookup"><span data-stu-id="b6964-220">Error</span></span>|<span data-ttu-id="b6964-221">예외 메시지</span><span class="sxs-lookup"><span data-stu-id="b6964-221">Exception message</span></span>|  
|<span data-ttu-id="b6964-222">InternalError</span><span class="sxs-lookup"><span data-stu-id="b6964-222">InternalError</span></span>|<span data-ttu-id="b6964-223">위험</span><span class="sxs-lookup"><span data-stu-id="b6964-223">Critical</span></span>|<span data-ttu-id="b6964-224">예외 메시지</span><span class="sxs-lookup"><span data-stu-id="b6964-224">Exception message</span></span>|  
|<span data-ttu-id="b6964-225">TransferEvent</span><span class="sxs-lookup"><span data-stu-id="b6964-225">TransferEvent</span></span>||<span data-ttu-id="b6964-226">트랜잭션을 역직렬화하거나 <xref:System.Transactions> 트랜잭션에서 분산 트랜잭션으로 승격하는 경우 ExecutionContext의 현재 ActivityID 및 분산 트랜잭션 ID가 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6964-226">When a transaction is deserialized, or promoted from a <xref:System.Transactions> transaction to a distributed one, the current ActivityID from the ExecutionContext and the distributed transaction ID are written.</span></span><br /><br /> <span data-ttu-id="b6964-227">DTC가 관리되는 코드로 콜백되는 경우 분산 트랜잭션 ID는 콜백 기간 동안 ExecutionContext에 ActivityID로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6964-227">When the DTC calls back into managed code, the distributed transaction ID is set as the ActivityID in the ExecutionContext for the duration of the callback.</span></span>|  
|<span data-ttu-id="b6964-228">ConfiguredDefaultTimeoutAdjusted</span><span class="sxs-lookup"><span data-stu-id="b6964-228">ConfiguredDefaultTimeoutAdjusted</span></span>|<span data-ttu-id="b6964-229">경고</span><span class="sxs-lookup"><span data-stu-id="b6964-229">Warning</span></span>|<span data-ttu-id="b6964-230">추가 데이터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b6964-230">No extra data</span></span>|  
|<span data-ttu-id="b6964-231">TransactionTimeout</span><span class="sxs-lookup"><span data-stu-id="b6964-231">TransactionTimeout</span></span>|<span data-ttu-id="b6964-232">경고</span><span class="sxs-lookup"><span data-stu-id="b6964-232">Warning</span></span>|<span data-ttu-id="b6964-233">시간 초과되는 트랜잭션의 TransactionTraceId입니다.</span><span class="sxs-lookup"><span data-stu-id="b6964-233">The TransactionTraceId of the transaction being timed out.</span></span>|  
  
 <span data-ttu-id="b6964-234">앞의 각 추가 데이터 항목에 대한 XML 스키마에는 다음 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6964-234">The XML schema for each of the preceding extra data items has the following format.</span></span>  
  
### <a name="transactiontraceidentifier"></a><span data-ttu-id="b6964-235">TransactionTraceIdentifier</span><span class="sxs-lookup"><span data-stu-id="b6964-235">TransactionTraceIdentifier</span></span>  

 `<TransactionTraceIdentifier>`  
  
 `<TransactionIdentifier >`  
  
 `string representation of transaction id`  
  
 `</TransactionIdentifier>`  
  
 `< CloneIdentifier >`  
  
 `the clone id number`  
  
 `</CloneIdentifier>`  
  
 `</TransactionTraceIdentifier>`  
  
### <a name="enlistmenttraceidentifier"></a><span data-ttu-id="b6964-236">EnlistmentTraceIdentifier</span><span class="sxs-lookup"><span data-stu-id="b6964-236">EnlistmentTraceIdentifier</span></span>  

 `<EnlistmentTraceIdentifier>`  
  
 `<ResourceManagerId>`  
  
 `string form of guid`  
  
 `</ResourceManagerId>`  
  
 `<TransactionTraceIdentifier>`  
  
 `<TransactionIdentifier >`  
  
 `string representation of transaction id`  
  
 `</TransactionIdentifier>`  
  
 `<CloneIdentifier >`  
  
 `the clone id number`  
  
 `</CloneIdentifier>`  
  
 `<TransactionTraceIdentifier>`  
  
 `<EnlistmentIdentifier>`  
  
 `the enlistment id number`  
  
 `</EnlistmentIdentifier>`  
  
 `</EnlistmentTraceIdentifier>`  
  
### <a name="resource-manager-identifier"></a><span data-ttu-id="b6964-237">리소스 관리자 식별자</span><span class="sxs-lookup"><span data-stu-id="b6964-237">Resource Manager Identifier</span></span>  

 `<ResourceManagerId>`  
  
 `string form of guid`  
  
 `</ResourceManagerId>`  
  
## <a name="security-issues-for-tracing"></a><span data-ttu-id="b6964-238">추적과 관련된 보안 문제</span><span class="sxs-lookup"><span data-stu-id="b6964-238">Security Issues For Tracing</span></span>  

 <span data-ttu-id="b6964-239">관리자가 추적을 설정하면 기본적으로 공개적으로 볼 수 있는 추적 로그에 중요한 정보가 기록될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6964-239">When you as an administrator turn on tracing, sensitive information might be written to a trace log that is publicly viewable by default.</span></span> <span data-ttu-id="b6964-240">가능한 보안 위협을 줄이려면 공유 및 파일 시스템 액세스 권한에 의해 제어되는 안전한 위치에 추적 로그를 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6964-240">To mitigate any possible security threat, you should consider storing the trace log in a secure location controlled by share and file system access permissions.</span></span>
