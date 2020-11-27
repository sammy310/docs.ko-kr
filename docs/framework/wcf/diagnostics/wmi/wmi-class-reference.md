---
title: WMI 클래스 참조
ms.date: 03/30/2017
ms.assetid: b95a51f5-8251-4619-ae05-7de88cb90f9a
ms.openlocfilehash: 9830fbf50e8df625e3d3077a66c66e0370204acb
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262257"
---
# <a name="wmi-class-reference"></a><span data-ttu-id="7c833-102">WMI 클래스 참조</span><span class="sxs-lookup"><span data-stu-id="7c833-102">WMI Class Reference</span></span>

<span data-ttu-id="7c833-103">이 섹션에는 WCF (Windows Communication Foundation) WMI 공급자에 의해 노출 되는 모든 WMI 클래스가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c833-103">This section lists all the WMI classes exposed by the Windows Communication Foundation (WCF) WMI provider.</span></span>  
  
## <a name="accessing-wmi-instances"></a><span data-ttu-id="7c833-104">WMI 인스턴스에 액세스</span><span class="sxs-lookup"><span data-stu-id="7c833-104">Accessing WMI Instances</span></span>  

 <span data-ttu-id="7c833-105">WMI 개체 참조에 나열된 모든 클래스는 Service, AppDomain, Contract, ServiceAppDomain, ServiceToEndpointAssociation 및 Endpoint를 제외하고 직접 인스턴스화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c833-105">All the classes listed in the WMI Object Reference cannot be directly instantiated, except for Service, AppDomain, Contract, ServiceAppDomain, ServiceToEndpointAssociation and Endpoint.</span></span> <span data-ttu-id="7c833-106">다른 인스턴스에 액세스하려면 앞에서 설명한 최상위 클래스의 속성에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="7c833-106">To access other instances, you can access the properties of the previously mentioned top level classes.</span></span> <span data-ttu-id="7c833-107">예를 들어 > 바인딩-> BindingElements 끝점 인스턴스에서 TransportBindingElement 인스턴스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c833-107">For example, you can access the TransportBindingElement instance from the Endpoint instance -> Binding -> BindingElements.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7c833-108">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="7c833-108">In This Section</span></span>  

 [<span data-ttu-id="7c833-109">ActivityTransfer</span><span class="sxs-lookup"><span data-stu-id="7c833-109">ActivityTransfer</span></span>](activitytransfer.md)  
  
 [<span data-ttu-id="7c833-110">AppDomainInfo</span><span class="sxs-lookup"><span data-stu-id="7c833-110">AppDomainInfo</span></span>](appdomaininfo.md)  
  
 [<span data-ttu-id="7c833-111">AspNetCompatibilityRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="7c833-111">AspNetCompatibilityRequirementsAttribute</span></span>](aspnetcompatibilityrequirementsattribute.md)  
  
 [<span data-ttu-id="7c833-112">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="7c833-112">AsymmetricSecurityBindingElement</span></span>](asymmetricsecuritybindingelement.md)  
  
 <span data-ttu-id="7c833-113">"Behavior 클래스"</span><span class="sxs-lookup"><span data-stu-id="7c833-113">"Behavior class"</span></span>  
  
 [<span data-ttu-id="7c833-114">BinaryMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="7c833-114">BinaryMessageEncodingBindingElement</span></span>](binarymessageencodingbindingelement.md)  
  
 [<span data-ttu-id="7c833-115">바인딩</span><span class="sxs-lookup"><span data-stu-id="7c833-115">Binding</span></span>](binding.md)  
  
 [<span data-ttu-id="7c833-116">BindingElement</span><span class="sxs-lookup"><span data-stu-id="7c833-116">BindingElement</span></span>](bindingelement.md)  
  
 [<span data-ttu-id="7c833-117">CallbackBehavior</span><span class="sxs-lookup"><span data-stu-id="7c833-117">CallbackBehavior</span></span>](callbackbehavior.md)  
  
 [<span data-ttu-id="7c833-118">Channel 클래스</span><span class="sxs-lookup"><span data-stu-id="7c833-118">Channel class</span></span>](channel-class.md)  
  
 [<span data-ttu-id="7c833-119">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="7c833-119">ChannelPoolSettings</span></span>](channelpoolsettings.md)  
  
 [<span data-ttu-id="7c833-120">ClientCredentials</span><span class="sxs-lookup"><span data-stu-id="7c833-120">ClientCredentials</span></span>](clientcredentials.md)  
  
 [<span data-ttu-id="7c833-121">ClientViaBehavior</span><span class="sxs-lookup"><span data-stu-id="7c833-121">ClientViaBehavior</span></span>](clientviabehavior.md)  
  
 [<span data-ttu-id="7c833-122">CompositeDuplexBindingElement</span><span class="sxs-lookup"><span data-stu-id="7c833-122">CompositeDuplexBindingElement</span></span>](compositeduplexbindingelement.md)  
  
 [<span data-ttu-id="7c833-123">ConnectionOrientedTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="7c833-123">ConnectionOrientedTransportBindingElement</span></span>](connectionorientedtransportbindingelement.md)  
  
 [<span data-ttu-id="7c833-124">내용의</span><span class="sxs-lookup"><span data-stu-id="7c833-124">Contract</span></span>](contract.md)  
  
 [<span data-ttu-id="7c833-125">CustomBindingElement</span><span class="sxs-lookup"><span data-stu-id="7c833-125">CustomBindingElement</span></span>](custombindingelement.md)  
  
 [<span data-ttu-id="7c833-126">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="7c833-126">DeliveryRequirementsAttribute</span></span>](deliveryrequirementsattribute.md)  
  
 [<span data-ttu-id="7c833-127">엔드포인트</span><span class="sxs-lookup"><span data-stu-id="7c833-127">Endpoint</span></span>](endpoint.md)  
  
 [<span data-ttu-id="7c833-128">HttpsTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="7c833-128">HttpsTransportBindingElement</span></span>](httpstransportbindingelement.md)  
  
 [<span data-ttu-id="7c833-129">HttpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="7c833-129">HttpTransportBindingElement</span></span>](httptransportbindingelement.md)  
  
 [<span data-ttu-id="7c833-130">LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="7c833-130">LocalServiceSecuritySettings</span></span>](localservicesecuritysettings.md)  
  
 [<span data-ttu-id="7c833-131">MatchAllEndpointBehavior</span><span class="sxs-lookup"><span data-stu-id="7c833-131">MatchAllEndpointBehavior</span></span>](matchallendpointbehavior.md)  
  
 [<span data-ttu-id="7c833-132">MessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="7c833-132">MessageEncodingBindingElement</span></span>](messageencodingbindingelement.md)  
  
 [<span data-ttu-id="7c833-133">MsmqBindingElementBase</span><span class="sxs-lookup"><span data-stu-id="7c833-133">MsmqBindingElementBase</span></span>](msmqbindingelementbase.md)  
  
 [<span data-ttu-id="7c833-134">MsmqIntegrationBindingElement</span><span class="sxs-lookup"><span data-stu-id="7c833-134">MsmqIntegrationBindingElement</span></span>](msmqintegrationbindingelement.md)  
  
 [<span data-ttu-id="7c833-135">MsmqTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="7c833-135">MsmqTransportBindingElement</span></span>](msmqtransportbindingelement.md)  
  
 [<span data-ttu-id="7c833-136">MtomMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="7c833-136">MtomMessageEncodingBindingElement</span></span>](mtommessageencodingbindingelement.md)  
  
 [<span data-ttu-id="7c833-137">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="7c833-137">MustUnderstandBehavior</span></span>](mustunderstandbehavior.md)  
  
 [<span data-ttu-id="7c833-138">NamedPipeConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="7c833-138">NamedPipeConnectionPoolSettings</span></span>](namedpipeconnectionpoolsettings.md)  
  
 [<span data-ttu-id="7c833-139">NamedPipeTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="7c833-139">NamedPipeTransportBindingElement</span></span>](namedpipetransportbindingelement.md)  
  
 [<span data-ttu-id="7c833-140">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="7c833-140">OneWayBindingElement</span></span>](onewaybindingelement.md)  
  
 <span data-ttu-id="7c833-141">"Operation 클래스"</span><span class="sxs-lookup"><span data-stu-id="7c833-141">"Operation class"</span></span>  
  
 [<span data-ttu-id="7c833-142">OperationBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="7c833-142">OperationBehaviorAttribute</span></span>](operationbehaviorattribute.md)  
  
 [<span data-ttu-id="7c833-143">PeerCustomResolverBindingElement</span><span class="sxs-lookup"><span data-stu-id="7c833-143">PeerCustomResolverBindingElement</span></span>](peercustomresolverbindingelement.md)  
  
 [<span data-ttu-id="7c833-144">PeerResolverBindingElement</span><span class="sxs-lookup"><span data-stu-id="7c833-144">PeerResolverBindingElement</span></span>](peerresolverbindingelement.md)  
  
 [<span data-ttu-id="7c833-145">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="7c833-145">PeerSecuritySettings</span></span>](peersecuritysettings.md)  
  
 [<span data-ttu-id="7c833-146">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="7c833-146">PeerTransportBindingElement</span></span>](peertransportbindingelement.md)  
  
 [<span data-ttu-id="7c833-147">PeerTransportSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="7c833-147">PeerTransportSecuritySettings</span></span>](peertransportsecuritysettings.md)  
  
 [<span data-ttu-id="7c833-148">PnrpPeerResolverBindingElement</span><span class="sxs-lookup"><span data-stu-id="7c833-148">PnrpPeerResolverBindingElement</span></span>](pnrppeerresolverbindingelement.md)  
  
 [<span data-ttu-id="7c833-149">PrivacyNoticeBindingElement</span><span class="sxs-lookup"><span data-stu-id="7c833-149">PrivacyNoticeBindingElement</span></span>](privacynoticebindingelement.md)  
  
 [<span data-ttu-id="7c833-150">ReliableSessionBindingElement</span><span class="sxs-lookup"><span data-stu-id="7c833-150">ReliableSessionBindingElement</span></span>](reliablesessionbindingelement.md)  
  
 [<span data-ttu-id="7c833-151">SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="7c833-151">SecurityBindingElement</span></span>](securitybindingelement.md)  
  
 [<span data-ttu-id="7c833-152">서비스</span><span class="sxs-lookup"><span data-stu-id="7c833-152">Service</span></span>](service.md)  
  
 [<span data-ttu-id="7c833-153">ServiceAppDomain</span><span class="sxs-lookup"><span data-stu-id="7c833-153">ServiceAppDomain</span></span>](serviceappdomain.md)  
  
 [<span data-ttu-id="7c833-154">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="7c833-154">ServiceAuthorizationBehavior</span></span>](serviceauthorizationbehavior.md)  
  
 [<span data-ttu-id="7c833-155">ServiceBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="7c833-155">ServiceBehaviorAttribute</span></span>](servicebehaviorattribute.md)  
  
 [<span data-ttu-id="7c833-156">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="7c833-156">ServiceCredentials</span></span>](servicecredentials.md)  
  
 [<span data-ttu-id="7c833-157">ServiceDebugBehavior</span><span class="sxs-lookup"><span data-stu-id="7c833-157">ServiceDebugBehavior</span></span>](servicedebugbehavior.md)  
  
 [<span data-ttu-id="7c833-158">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="7c833-158">ServiceMetadataBehavior</span></span>](servicemetadatabehavior.md)  
  
 [<span data-ttu-id="7c833-159">ServiceSecurityAuditBehavior</span><span class="sxs-lookup"><span data-stu-id="7c833-159">ServiceSecurityAuditBehavior</span></span>](servicesecurityauditbehavior.md)  
  
 [<span data-ttu-id="7c833-160">ServiceThrottlingBehavior</span><span class="sxs-lookup"><span data-stu-id="7c833-160">ServiceThrottlingBehavior</span></span>](servicethrottlingbehavior.md)  
  
 [<span data-ttu-id="7c833-161">ServiceTimeoutsBehavior</span><span class="sxs-lookup"><span data-stu-id="7c833-161">ServiceTimeoutsBehavior</span></span>](servicetimeoutsbehavior.md)  
  
 [<span data-ttu-id="7c833-162">ServiceToEndpointAssociation</span><span class="sxs-lookup"><span data-stu-id="7c833-162">ServiceToEndpointAssociation</span></span>](servicetoendpointassociation.md)  
  
 [<span data-ttu-id="7c833-163">SslStreamSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="7c833-163">SslStreamSecurityBindingElement</span></span>](sslstreamsecuritybindingelement.md)  
  
 [<span data-ttu-id="7c833-164">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="7c833-164">SymmetricSecurityBindingElement</span></span>](symmetricsecuritybindingelement.md)  
  
 [<span data-ttu-id="7c833-165">SynchronousReceiveBehavior</span><span class="sxs-lookup"><span data-stu-id="7c833-165">SynchronousReceiveBehavior</span></span>](synchronousreceivebehavior.md)  
  
 [<span data-ttu-id="7c833-166">TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="7c833-166">TcpConnectionPoolSettings</span></span>](tcpconnectionpoolsettings.md)  
  
 [<span data-ttu-id="7c833-167">TcpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="7c833-167">TcpTransportBindingElement</span></span>](tcptransportbindingelement.md)  
  
 [<span data-ttu-id="7c833-168">TextMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="7c833-168">TextMessageEncodingBindingElement</span></span>](textmessageencodingbindingelement.md)  
  
 [<span data-ttu-id="7c833-169">TraceListener</span><span class="sxs-lookup"><span data-stu-id="7c833-169">TraceListener</span></span>](tracelistener.md)  
  
 [<span data-ttu-id="7c833-170">TraceListenerArgument</span><span class="sxs-lookup"><span data-stu-id="7c833-170">TraceListenerArgument</span></span>](tracelistenerargument.md)  
  
 [<span data-ttu-id="7c833-171">TransactedBatchingBehavior</span><span class="sxs-lookup"><span data-stu-id="7c833-171">TransactedBatchingBehavior</span></span>](transactedbatchingbehavior.md)  
  
 [<span data-ttu-id="7c833-172">TransactionFlowAttribute</span><span class="sxs-lookup"><span data-stu-id="7c833-172">TransactionFlowAttribute</span></span>](transactionflowattribute.md)  
  
 [<span data-ttu-id="7c833-173">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="7c833-173">TransactionFlowBindingElement</span></span>](transactionflowbindingelement.md)  
  
 [<span data-ttu-id="7c833-174">TransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="7c833-174">TransportBindingElement</span></span>](transportbindingelement.md)  
  
 [<span data-ttu-id="7c833-175">TransportSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="7c833-175">TransportSecurityBindingElement</span></span>](transportsecuritybindingelement.md)  
  
 [<span data-ttu-id="7c833-176">UseManagedPresentationBindingElement</span><span class="sxs-lookup"><span data-stu-id="7c833-176">UseManagedPresentationBindingElement</span></span>](usemanagedpresentationbindingelement.md)  
  
 [<span data-ttu-id="7c833-177">WindowsStreamSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="7c833-177">WindowsStreamSecurityBindingElement</span></span>](windowsstreamsecuritybindingelement.md)  
  
 [<span data-ttu-id="7c833-178">WSAT_TraceEvent</span><span class="sxs-lookup"><span data-stu-id="7c833-178">WSAT_TraceEvent</span></span>](wsat-traceevent.md)  
  
 [<span data-ttu-id="7c833-179">WSAT_TraceProvider</span><span class="sxs-lookup"><span data-stu-id="7c833-179">WSAT_TraceProvider</span></span>](wsat-traceprovider.md)  
  
 [<span data-ttu-id="7c833-180">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="7c833-180">WSAT_TraceRecord</span></span>](wsat-tracerecord.md)  
  
 [<span data-ttu-id="7c833-181">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="7c833-181">XmlDictionaryReaderQuotas</span></span>](xmldictionaryreaderquotas.md)  
  
 [<span data-ttu-id="7c833-182">XmlSerializerOperationBehavior</span><span class="sxs-lookup"><span data-stu-id="7c833-182">XmlSerializerOperationBehavior</span></span>](xmlserializeroperationbehavior.md)
