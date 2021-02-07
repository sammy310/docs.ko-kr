---
description: '자세한 정보: WMI 클래스 참조'
title: WMI 클래스 참조
ms.date: 03/30/2017
ms.assetid: b95a51f5-8251-4619-ae05-7de88cb90f9a
ms.openlocfilehash: 6413065b5740b190aee122ef34727da120737afa
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99757023"
---
# <a name="wmi-class-reference"></a><span data-ttu-id="cbf5d-103">WMI 클래스 참조</span><span class="sxs-lookup"><span data-stu-id="cbf5d-103">WMI Class Reference</span></span>

<span data-ttu-id="cbf5d-104">이 섹션에는 WCF (Windows Communication Foundation) WMI 공급자에 의해 노출 되는 모든 WMI 클래스가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbf5d-104">This section lists all the WMI classes exposed by the Windows Communication Foundation (WCF) WMI provider.</span></span>  
  
## <a name="accessing-wmi-instances"></a><span data-ttu-id="cbf5d-105">WMI 인스턴스에 액세스</span><span class="sxs-lookup"><span data-stu-id="cbf5d-105">Accessing WMI Instances</span></span>  

 <span data-ttu-id="cbf5d-106">WMI 개체 참조에 나열된 모든 클래스는 Service, AppDomain, Contract, ServiceAppDomain, ServiceToEndpointAssociation 및 Endpoint를 제외하고 직접 인스턴스화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cbf5d-106">All the classes listed in the WMI Object Reference cannot be directly instantiated, except for Service, AppDomain, Contract, ServiceAppDomain, ServiceToEndpointAssociation and Endpoint.</span></span> <span data-ttu-id="cbf5d-107">다른 인스턴스에 액세스하려면 앞에서 설명한 최상위 클래스의 속성에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="cbf5d-107">To access other instances, you can access the properties of the previously mentioned top level classes.</span></span> <span data-ttu-id="cbf5d-108">예를 들어 > 바인딩-> BindingElements 끝점 인스턴스에서 TransportBindingElement 인스턴스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbf5d-108">For example, you can access the TransportBindingElement instance from the Endpoint instance -> Binding -> BindingElements.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cbf5d-109">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="cbf5d-109">In This Section</span></span>  

 [<span data-ttu-id="cbf5d-110">ActivityTransfer</span><span class="sxs-lookup"><span data-stu-id="cbf5d-110">ActivityTransfer</span></span>](activitytransfer.md)  
  
 [<span data-ttu-id="cbf5d-111">AppDomainInfo</span><span class="sxs-lookup"><span data-stu-id="cbf5d-111">AppDomainInfo</span></span>](appdomaininfo.md)  
  
 [<span data-ttu-id="cbf5d-112">AspNetCompatibilityRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="cbf5d-112">AspNetCompatibilityRequirementsAttribute</span></span>](aspnetcompatibilityrequirementsattribute.md)  
  
 [<span data-ttu-id="cbf5d-113">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="cbf5d-113">AsymmetricSecurityBindingElement</span></span>](asymmetricsecuritybindingelement.md)  
  
 <span data-ttu-id="cbf5d-114">"Behavior 클래스"</span><span class="sxs-lookup"><span data-stu-id="cbf5d-114">"Behavior class"</span></span>  
  
 [<span data-ttu-id="cbf5d-115">BinaryMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="cbf5d-115">BinaryMessageEncodingBindingElement</span></span>](binarymessageencodingbindingelement.md)  
  
 [<span data-ttu-id="cbf5d-116">바인딩되</span><span class="sxs-lookup"><span data-stu-id="cbf5d-116">Binding</span></span>](binding.md)  
  
 [<span data-ttu-id="cbf5d-117">BindingElement</span><span class="sxs-lookup"><span data-stu-id="cbf5d-117">BindingElement</span></span>](bindingelement.md)  
  
 [<span data-ttu-id="cbf5d-118">CallbackBehavior</span><span class="sxs-lookup"><span data-stu-id="cbf5d-118">CallbackBehavior</span></span>](callbackbehavior.md)  
  
 [<span data-ttu-id="cbf5d-119">Channel 클래스</span><span class="sxs-lookup"><span data-stu-id="cbf5d-119">Channel class</span></span>](channel-class.md)  
  
 [<span data-ttu-id="cbf5d-120">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="cbf5d-120">ChannelPoolSettings</span></span>](channelpoolsettings.md)  
  
 [<span data-ttu-id="cbf5d-121">ClientCredentials</span><span class="sxs-lookup"><span data-stu-id="cbf5d-121">ClientCredentials</span></span>](clientcredentials.md)  
  
 [<span data-ttu-id="cbf5d-122">ClientViaBehavior</span><span class="sxs-lookup"><span data-stu-id="cbf5d-122">ClientViaBehavior</span></span>](clientviabehavior.md)  
  
 [<span data-ttu-id="cbf5d-123">CompositeDuplexBindingElement</span><span class="sxs-lookup"><span data-stu-id="cbf5d-123">CompositeDuplexBindingElement</span></span>](compositeduplexbindingelement.md)  
  
 [<span data-ttu-id="cbf5d-124">ConnectionOrientedTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="cbf5d-124">ConnectionOrientedTransportBindingElement</span></span>](connectionorientedtransportbindingelement.md)  
  
 [<span data-ttu-id="cbf5d-125">내용의</span><span class="sxs-lookup"><span data-stu-id="cbf5d-125">Contract</span></span>](contract.md)  
  
 [<span data-ttu-id="cbf5d-126">CustomBindingElement</span><span class="sxs-lookup"><span data-stu-id="cbf5d-126">CustomBindingElement</span></span>](custombindingelement.md)  
  
 [<span data-ttu-id="cbf5d-127">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="cbf5d-127">DeliveryRequirementsAttribute</span></span>](deliveryrequirementsattribute.md)  
  
 [<span data-ttu-id="cbf5d-128">엔드포인트</span><span class="sxs-lookup"><span data-stu-id="cbf5d-128">Endpoint</span></span>](endpoint.md)  
  
 [<span data-ttu-id="cbf5d-129">HttpsTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="cbf5d-129">HttpsTransportBindingElement</span></span>](httpstransportbindingelement.md)  
  
 [<span data-ttu-id="cbf5d-130">HttpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="cbf5d-130">HttpTransportBindingElement</span></span>](httptransportbindingelement.md)  
  
 [<span data-ttu-id="cbf5d-131">LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="cbf5d-131">LocalServiceSecuritySettings</span></span>](localservicesecuritysettings.md)  
  
 [<span data-ttu-id="cbf5d-132">MatchAllEndpointBehavior</span><span class="sxs-lookup"><span data-stu-id="cbf5d-132">MatchAllEndpointBehavior</span></span>](matchallendpointbehavior.md)  
  
 [<span data-ttu-id="cbf5d-133">MessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="cbf5d-133">MessageEncodingBindingElement</span></span>](messageencodingbindingelement.md)  
  
 [<span data-ttu-id="cbf5d-134">MsmqBindingElementBase</span><span class="sxs-lookup"><span data-stu-id="cbf5d-134">MsmqBindingElementBase</span></span>](msmqbindingelementbase.md)  
  
 [<span data-ttu-id="cbf5d-135">MsmqIntegrationBindingElement</span><span class="sxs-lookup"><span data-stu-id="cbf5d-135">MsmqIntegrationBindingElement</span></span>](msmqintegrationbindingelement.md)  
  
 [<span data-ttu-id="cbf5d-136">MsmqTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="cbf5d-136">MsmqTransportBindingElement</span></span>](msmqtransportbindingelement.md)  
  
 [<span data-ttu-id="cbf5d-137">MtomMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="cbf5d-137">MtomMessageEncodingBindingElement</span></span>](mtommessageencodingbindingelement.md)  
  
 [<span data-ttu-id="cbf5d-138">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="cbf5d-138">MustUnderstandBehavior</span></span>](mustunderstandbehavior.md)  
  
 [<span data-ttu-id="cbf5d-139">NamedPipeConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="cbf5d-139">NamedPipeConnectionPoolSettings</span></span>](namedpipeconnectionpoolsettings.md)  
  
 [<span data-ttu-id="cbf5d-140">NamedPipeTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="cbf5d-140">NamedPipeTransportBindingElement</span></span>](namedpipetransportbindingelement.md)  
  
 [<span data-ttu-id="cbf5d-141">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="cbf5d-141">OneWayBindingElement</span></span>](onewaybindingelement.md)  
  
 <span data-ttu-id="cbf5d-142">"Operation 클래스"</span><span class="sxs-lookup"><span data-stu-id="cbf5d-142">"Operation class"</span></span>  
  
 [<span data-ttu-id="cbf5d-143">OperationBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="cbf5d-143">OperationBehaviorAttribute</span></span>](operationbehaviorattribute.md)  
  
 [<span data-ttu-id="cbf5d-144">PeerCustomResolverBindingElement</span><span class="sxs-lookup"><span data-stu-id="cbf5d-144">PeerCustomResolverBindingElement</span></span>](peercustomresolverbindingelement.md)  
  
 [<span data-ttu-id="cbf5d-145">PeerResolverBindingElement</span><span class="sxs-lookup"><span data-stu-id="cbf5d-145">PeerResolverBindingElement</span></span>](peerresolverbindingelement.md)  
  
 [<span data-ttu-id="cbf5d-146">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="cbf5d-146">PeerSecuritySettings</span></span>](peersecuritysettings.md)  
  
 [<span data-ttu-id="cbf5d-147">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="cbf5d-147">PeerTransportBindingElement</span></span>](peertransportbindingelement.md)  
  
 [<span data-ttu-id="cbf5d-148">PeerTransportSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="cbf5d-148">PeerTransportSecuritySettings</span></span>](peertransportsecuritysettings.md)  
  
 [<span data-ttu-id="cbf5d-149">PnrpPeerResolverBindingElement</span><span class="sxs-lookup"><span data-stu-id="cbf5d-149">PnrpPeerResolverBindingElement</span></span>](pnrppeerresolverbindingelement.md)  
  
 [<span data-ttu-id="cbf5d-150">PrivacyNoticeBindingElement</span><span class="sxs-lookup"><span data-stu-id="cbf5d-150">PrivacyNoticeBindingElement</span></span>](privacynoticebindingelement.md)  
  
 [<span data-ttu-id="cbf5d-151">ReliableSessionBindingElement</span><span class="sxs-lookup"><span data-stu-id="cbf5d-151">ReliableSessionBindingElement</span></span>](reliablesessionbindingelement.md)  
  
 [<span data-ttu-id="cbf5d-152">SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="cbf5d-152">SecurityBindingElement</span></span>](securitybindingelement.md)  
  
 [<span data-ttu-id="cbf5d-153">서비스</span><span class="sxs-lookup"><span data-stu-id="cbf5d-153">Service</span></span>](service.md)  
  
 [<span data-ttu-id="cbf5d-154">ServiceAppDomain</span><span class="sxs-lookup"><span data-stu-id="cbf5d-154">ServiceAppDomain</span></span>](serviceappdomain.md)  
  
 [<span data-ttu-id="cbf5d-155">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="cbf5d-155">ServiceAuthorizationBehavior</span></span>](serviceauthorizationbehavior.md)  
  
 [<span data-ttu-id="cbf5d-156">ServiceBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="cbf5d-156">ServiceBehaviorAttribute</span></span>](servicebehaviorattribute.md)  
  
 [<span data-ttu-id="cbf5d-157">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="cbf5d-157">ServiceCredentials</span></span>](servicecredentials.md)  
  
 [<span data-ttu-id="cbf5d-158">ServiceDebugBehavior</span><span class="sxs-lookup"><span data-stu-id="cbf5d-158">ServiceDebugBehavior</span></span>](servicedebugbehavior.md)  
  
 [<span data-ttu-id="cbf5d-159">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="cbf5d-159">ServiceMetadataBehavior</span></span>](servicemetadatabehavior.md)  
  
 [<span data-ttu-id="cbf5d-160">ServiceSecurityAuditBehavior</span><span class="sxs-lookup"><span data-stu-id="cbf5d-160">ServiceSecurityAuditBehavior</span></span>](servicesecurityauditbehavior.md)  
  
 [<span data-ttu-id="cbf5d-161">ServiceThrottlingBehavior</span><span class="sxs-lookup"><span data-stu-id="cbf5d-161">ServiceThrottlingBehavior</span></span>](servicethrottlingbehavior.md)  
  
 [<span data-ttu-id="cbf5d-162">ServiceTimeoutsBehavior</span><span class="sxs-lookup"><span data-stu-id="cbf5d-162">ServiceTimeoutsBehavior</span></span>](servicetimeoutsbehavior.md)  
  
 [<span data-ttu-id="cbf5d-163">ServiceToEndpointAssociation</span><span class="sxs-lookup"><span data-stu-id="cbf5d-163">ServiceToEndpointAssociation</span></span>](servicetoendpointassociation.md)  
  
 [<span data-ttu-id="cbf5d-164">SslStreamSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="cbf5d-164">SslStreamSecurityBindingElement</span></span>](sslstreamsecuritybindingelement.md)  
  
 [<span data-ttu-id="cbf5d-165">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="cbf5d-165">SymmetricSecurityBindingElement</span></span>](symmetricsecuritybindingelement.md)  
  
 [<span data-ttu-id="cbf5d-166">SynchronousReceiveBehavior</span><span class="sxs-lookup"><span data-stu-id="cbf5d-166">SynchronousReceiveBehavior</span></span>](synchronousreceivebehavior.md)  
  
 [<span data-ttu-id="cbf5d-167">TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="cbf5d-167">TcpConnectionPoolSettings</span></span>](tcpconnectionpoolsettings.md)  
  
 [<span data-ttu-id="cbf5d-168">TcpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="cbf5d-168">TcpTransportBindingElement</span></span>](tcptransportbindingelement.md)  
  
 [<span data-ttu-id="cbf5d-169">TextMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="cbf5d-169">TextMessageEncodingBindingElement</span></span>](textmessageencodingbindingelement.md)  
  
 [<span data-ttu-id="cbf5d-170">TraceListener</span><span class="sxs-lookup"><span data-stu-id="cbf5d-170">TraceListener</span></span>](tracelistener.md)  
  
 [<span data-ttu-id="cbf5d-171">TraceListenerArgument</span><span class="sxs-lookup"><span data-stu-id="cbf5d-171">TraceListenerArgument</span></span>](tracelistenerargument.md)  
  
 [<span data-ttu-id="cbf5d-172">TransactedBatchingBehavior</span><span class="sxs-lookup"><span data-stu-id="cbf5d-172">TransactedBatchingBehavior</span></span>](transactedbatchingbehavior.md)  
  
 [<span data-ttu-id="cbf5d-173">TransactionFlowAttribute</span><span class="sxs-lookup"><span data-stu-id="cbf5d-173">TransactionFlowAttribute</span></span>](transactionflowattribute.md)  
  
 [<span data-ttu-id="cbf5d-174">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="cbf5d-174">TransactionFlowBindingElement</span></span>](transactionflowbindingelement.md)  
  
 [<span data-ttu-id="cbf5d-175">TransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="cbf5d-175">TransportBindingElement</span></span>](transportbindingelement.md)  
  
 [<span data-ttu-id="cbf5d-176">TransportSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="cbf5d-176">TransportSecurityBindingElement</span></span>](transportsecuritybindingelement.md)  
  
 [<span data-ttu-id="cbf5d-177">UseManagedPresentationBindingElement</span><span class="sxs-lookup"><span data-stu-id="cbf5d-177">UseManagedPresentationBindingElement</span></span>](usemanagedpresentationbindingelement.md)  
  
 [<span data-ttu-id="cbf5d-178">WindowsStreamSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="cbf5d-178">WindowsStreamSecurityBindingElement</span></span>](windowsstreamsecuritybindingelement.md)  
  
 [<span data-ttu-id="cbf5d-179">WSAT_TraceEvent</span><span class="sxs-lookup"><span data-stu-id="cbf5d-179">WSAT_TraceEvent</span></span>](wsat-traceevent.md)  
  
 [<span data-ttu-id="cbf5d-180">WSAT_TraceProvider</span><span class="sxs-lookup"><span data-stu-id="cbf5d-180">WSAT_TraceProvider</span></span>](wsat-traceprovider.md)  
  
 [<span data-ttu-id="cbf5d-181">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="cbf5d-181">WSAT_TraceRecord</span></span>](wsat-tracerecord.md)  
  
 [<span data-ttu-id="cbf5d-182">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="cbf5d-182">XmlDictionaryReaderQuotas</span></span>](xmldictionaryreaderquotas.md)  
  
 [<span data-ttu-id="cbf5d-183">XmlSerializerOperationBehavior</span><span class="sxs-lookup"><span data-stu-id="cbf5d-183">XmlSerializerOperationBehavior</span></span>](xmlserializeroperationbehavior.md)
