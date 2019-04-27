---
title: WMI 클래스 참조
ms.date: 03/30/2017
ms.assetid: b95a51f5-8251-4619-ae05-7de88cb90f9a
ms.openlocfilehash: 73b36bfc3df917982a2cc9071bdb31f42b3b2dff
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61915659"
---
# <a name="wmi-class-reference"></a><span data-ttu-id="ec803-102">WMI 클래스 참조</span><span class="sxs-lookup"><span data-stu-id="ec803-102">WMI Class Reference</span></span>
<span data-ttu-id="ec803-103">이 섹션에서는 Windows Communication Foundation (WCF) WMI 공급자가 노출 하는 모든 WMI 클래스를 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec803-103">This section lists all the WMI classes exposed by the Windows Communication Foundation (WCF) WMI provider.</span></span>  
  
## <a name="accessing-wmi-instances"></a><span data-ttu-id="ec803-104">WMI 인스턴스에 액세스</span><span class="sxs-lookup"><span data-stu-id="ec803-104">Accessing WMI Instances</span></span>  
 <span data-ttu-id="ec803-105">WMI 개체 참조에 나열된 모든 클래스는 Service, AppDomain, Contract, ServiceAppDomain, ServiceToEndpointAssociation 및 Endpoint를 제외하고 직접 인스턴스화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ec803-105">All the classes listed in the WMI Object Reference cannot be directly instantiated, except for Service, AppDomain, Contract, ServiceAppDomain, ServiceToEndpointAssociation and Endpoint.</span></span> <span data-ttu-id="ec803-106">다른 인스턴스에 액세스하려면 앞에서 설명한 최상위 클래스의 속성에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="ec803-106">To access other instances, you can access the properties of the previously mentioned top level classes.</span></span> <span data-ttu-id="ec803-107">TransportBindingElement 인스턴스에 액세스할 수는 예를 들어 Endpoint 인스턴스->에서 Binding-> BindingElements 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec803-107">For example, you can access the TransportBindingElement instance from the Endpoint instance -> Binding -> BindingElements.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ec803-108">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="ec803-108">In This Section</span></span>  
 [<span data-ttu-id="ec803-109">ActivityTransfer</span><span class="sxs-lookup"><span data-stu-id="ec803-109">ActivityTransfer</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/activitytransfer.md)  
  
 [<span data-ttu-id="ec803-110">AppDomainInfo</span><span class="sxs-lookup"><span data-stu-id="ec803-110">AppDomainInfo</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/appdomaininfo.md)  
  
 [<span data-ttu-id="ec803-111">AspNetCompatibilityRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="ec803-111">AspNetCompatibilityRequirementsAttribute</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/aspnetcompatibilityrequirementsattribute.md)  
  
 [<span data-ttu-id="ec803-112">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="ec803-112">AsymmetricSecurityBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/asymmetricsecuritybindingelement.md)  
  
 <span data-ttu-id="ec803-113">"동작 클래스"</span><span class="sxs-lookup"><span data-stu-id="ec803-113">"Behavior class"</span></span>  
  
 [<span data-ttu-id="ec803-114">BinaryMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="ec803-114">BinaryMessageEncodingBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/binarymessageencodingbindingelement.md)  
  
 [<span data-ttu-id="ec803-115">Binding</span><span class="sxs-lookup"><span data-stu-id="ec803-115">Binding</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/binding.md)  
  
 [<span data-ttu-id="ec803-116">BindingElement</span><span class="sxs-lookup"><span data-stu-id="ec803-116">BindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/bindingelement.md)  
  
 [<span data-ttu-id="ec803-117">CallbackBehavior</span><span class="sxs-lookup"><span data-stu-id="ec803-117">CallbackBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/callbackbehavior.md)  
  
 [<span data-ttu-id="ec803-118">Channel 클래스</span><span class="sxs-lookup"><span data-stu-id="ec803-118">Channel class</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/channel-class.md)  
  
 [<span data-ttu-id="ec803-119">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="ec803-119">ChannelPoolSettings</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/channelpoolsettings.md)  
  
 [<span data-ttu-id="ec803-120">ClientCredentials</span><span class="sxs-lookup"><span data-stu-id="ec803-120">ClientCredentials</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/clientcredentials.md)  
  
 [<span data-ttu-id="ec803-121">ClientViaBehavior</span><span class="sxs-lookup"><span data-stu-id="ec803-121">ClientViaBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/clientviabehavior.md)  
  
 [<span data-ttu-id="ec803-122">CompositeDuplexBindingElement</span><span class="sxs-lookup"><span data-stu-id="ec803-122">CompositeDuplexBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/compositeduplexbindingelement.md)  
  
 [<span data-ttu-id="ec803-123">ConnectionOrientedTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="ec803-123">ConnectionOrientedTransportBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/connectionorientedtransportbindingelement.md)  
  
 [<span data-ttu-id="ec803-124">Contract</span><span class="sxs-lookup"><span data-stu-id="ec803-124">Contract</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/contract.md)  
  
 [<span data-ttu-id="ec803-125">CustomBindingElement</span><span class="sxs-lookup"><span data-stu-id="ec803-125">CustomBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/custombindingelement.md)  
  
 [<span data-ttu-id="ec803-126">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="ec803-126">DeliveryRequirementsAttribute</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/deliveryrequirementsattribute.md)  
  
 [<span data-ttu-id="ec803-127">엔드포인트</span><span class="sxs-lookup"><span data-stu-id="ec803-127">Endpoint</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/endpoint.md)  
  
 [<span data-ttu-id="ec803-128">HttpsTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="ec803-128">HttpsTransportBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/httpstransportbindingelement.md)  
  
 [<span data-ttu-id="ec803-129">HttpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="ec803-129">HttpTransportBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/httptransportbindingelement.md)  
  
 [<span data-ttu-id="ec803-130">LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="ec803-130">LocalServiceSecuritySettings</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/localservicesecuritysettings.md)  
  
 [<span data-ttu-id="ec803-131">MatchAllEndpointBehavior</span><span class="sxs-lookup"><span data-stu-id="ec803-131">MatchAllEndpointBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/matchallendpointbehavior.md)  
  
 [<span data-ttu-id="ec803-132">MessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="ec803-132">MessageEncodingBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/messageencodingbindingelement.md)  
  
 [<span data-ttu-id="ec803-133">MsmqBindingElementBase</span><span class="sxs-lookup"><span data-stu-id="ec803-133">MsmqBindingElementBase</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/msmqbindingelementbase.md)  
  
 [<span data-ttu-id="ec803-134">MsmqIntegrationBindingElement</span><span class="sxs-lookup"><span data-stu-id="ec803-134">MsmqIntegrationBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/msmqintegrationbindingelement.md)  
  
 [<span data-ttu-id="ec803-135">MsmqTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="ec803-135">MsmqTransportBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/msmqtransportbindingelement.md)  
  
 [<span data-ttu-id="ec803-136">MtomMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="ec803-136">MtomMessageEncodingBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/mtommessageencodingbindingelement.md)  
  
 [<span data-ttu-id="ec803-137">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="ec803-137">MustUnderstandBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/mustunderstandbehavior.md)  
  
 [<span data-ttu-id="ec803-138">NamedPipeConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="ec803-138">NamedPipeConnectionPoolSettings</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/namedpipeconnectionpoolsettings.md)  
  
 [<span data-ttu-id="ec803-139">NamedPipeTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="ec803-139">NamedPipeTransportBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/namedpipetransportbindingelement.md)  
  
 [<span data-ttu-id="ec803-140">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="ec803-140">OneWayBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/onewaybindingelement.md)  
  
 <span data-ttu-id="ec803-141">"작업 클래스"</span><span class="sxs-lookup"><span data-stu-id="ec803-141">"Operation class"</span></span>  
  
 [<span data-ttu-id="ec803-142">OperationBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="ec803-142">OperationBehaviorAttribute</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/operationbehaviorattribute.md)  
  
 [<span data-ttu-id="ec803-143">PeerCustomResolverBindingElement</span><span class="sxs-lookup"><span data-stu-id="ec803-143">PeerCustomResolverBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/peercustomresolverbindingelement.md)  
  
 [<span data-ttu-id="ec803-144">PeerResolverBindingElement</span><span class="sxs-lookup"><span data-stu-id="ec803-144">PeerResolverBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/peerresolverbindingelement.md)  
  
 [<span data-ttu-id="ec803-145">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="ec803-145">PeerSecuritySettings</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/peersecuritysettings.md)  
  
 [<span data-ttu-id="ec803-146">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="ec803-146">PeerTransportBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/peertransportbindingelement.md)  
  
 [<span data-ttu-id="ec803-147">PeerTransportSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="ec803-147">PeerTransportSecuritySettings</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/peertransportsecuritysettings.md)  
  
 [<span data-ttu-id="ec803-148">PnrpPeerResolverBindingElement</span><span class="sxs-lookup"><span data-stu-id="ec803-148">PnrpPeerResolverBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/pnrppeerresolverbindingelement.md)  
  
 [<span data-ttu-id="ec803-149">PrivacyNoticeBindingElement</span><span class="sxs-lookup"><span data-stu-id="ec803-149">PrivacyNoticeBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/privacynoticebindingelement.md)  
  
 [<span data-ttu-id="ec803-150">ReliableSessionBindingElement</span><span class="sxs-lookup"><span data-stu-id="ec803-150">ReliableSessionBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/reliablesessionbindingelement.md)  
  
 [<span data-ttu-id="ec803-151">SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="ec803-151">SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/securitybindingelement.md)  
  
 [<span data-ttu-id="ec803-152">Service</span><span class="sxs-lookup"><span data-stu-id="ec803-152">Service</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/service.md)  
  
 [<span data-ttu-id="ec803-153">ServiceAppDomain</span><span class="sxs-lookup"><span data-stu-id="ec803-153">ServiceAppDomain</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/serviceappdomain.md)  
  
 [<span data-ttu-id="ec803-154">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="ec803-154">ServiceAuthorizationBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/serviceauthorizationbehavior.md)  
  
 [<span data-ttu-id="ec803-155">ServiceBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="ec803-155">ServiceBehaviorAttribute</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/servicebehaviorattribute.md)  
  
 [<span data-ttu-id="ec803-156">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="ec803-156">ServiceCredentials</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/servicecredentials.md)  
  
 [<span data-ttu-id="ec803-157">ServiceDebugBehavior</span><span class="sxs-lookup"><span data-stu-id="ec803-157">ServiceDebugBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/servicedebugbehavior.md)  
  
 [<span data-ttu-id="ec803-158">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="ec803-158">ServiceMetadataBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/servicemetadatabehavior.md)  
  
 [<span data-ttu-id="ec803-159">ServiceSecurityAuditBehavior</span><span class="sxs-lookup"><span data-stu-id="ec803-159">ServiceSecurityAuditBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/servicesecurityauditbehavior.md)  
  
 [<span data-ttu-id="ec803-160">ServiceThrottlingBehavior</span><span class="sxs-lookup"><span data-stu-id="ec803-160">ServiceThrottlingBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/servicethrottlingbehavior.md)  
  
 [<span data-ttu-id="ec803-161">ServiceTimeoutsBehavior</span><span class="sxs-lookup"><span data-stu-id="ec803-161">ServiceTimeoutsBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/servicetimeoutsbehavior.md)  
  
 [<span data-ttu-id="ec803-162">ServiceToEndpointAssociation</span><span class="sxs-lookup"><span data-stu-id="ec803-162">ServiceToEndpointAssociation</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/servicetoendpointassociation.md)  
  
 [<span data-ttu-id="ec803-163">SslStreamSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="ec803-163">SslStreamSecurityBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/sslstreamsecuritybindingelement.md)  
  
 [<span data-ttu-id="ec803-164">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="ec803-164">SymmetricSecurityBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/symmetricsecuritybindingelement.md)  
  
 [<span data-ttu-id="ec803-165">SynchronousReceiveBehavior</span><span class="sxs-lookup"><span data-stu-id="ec803-165">SynchronousReceiveBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/synchronousreceivebehavior.md)  
  
 [<span data-ttu-id="ec803-166">TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="ec803-166">TcpConnectionPoolSettings</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/tcpconnectionpoolsettings.md)  
  
 [<span data-ttu-id="ec803-167">TcpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="ec803-167">TcpTransportBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/tcptransportbindingelement.md)  
  
 [<span data-ttu-id="ec803-168">TextMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="ec803-168">TextMessageEncodingBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/textmessageencodingbindingelement.md)  
  
 [<span data-ttu-id="ec803-169">TraceListener</span><span class="sxs-lookup"><span data-stu-id="ec803-169">TraceListener</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/tracelistener.md)  
  
 [<span data-ttu-id="ec803-170">TraceListenerArgument</span><span class="sxs-lookup"><span data-stu-id="ec803-170">TraceListenerArgument</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/tracelistenerargument.md)  
  
 [<span data-ttu-id="ec803-171">TransactedBatchingBehavior</span><span class="sxs-lookup"><span data-stu-id="ec803-171">TransactedBatchingBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/transactedbatchingbehavior.md)  
  
 [<span data-ttu-id="ec803-172">TransactionFlowAttribute</span><span class="sxs-lookup"><span data-stu-id="ec803-172">TransactionFlowAttribute</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/transactionflowattribute.md)  
  
 [<span data-ttu-id="ec803-173">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="ec803-173">TransactionFlowBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/transactionflowbindingelement.md)  
  
 [<span data-ttu-id="ec803-174">TransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="ec803-174">TransportBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/transportbindingelement.md)  
  
 [<span data-ttu-id="ec803-175">TransportSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="ec803-175">TransportSecurityBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/transportsecuritybindingelement.md)  
  
 [<span data-ttu-id="ec803-176">UseManagedPresentationBindingElement</span><span class="sxs-lookup"><span data-stu-id="ec803-176">UseManagedPresentationBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/usemanagedpresentationbindingelement.md)  
  
 [<span data-ttu-id="ec803-177">WindowsStreamSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="ec803-177">WindowsStreamSecurityBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/windowsstreamsecuritybindingelement.md)  
  
 [<span data-ttu-id="ec803-178">WSAT_TraceEvent</span><span class="sxs-lookup"><span data-stu-id="ec803-178">WSAT_TraceEvent</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/wsat-traceevent.md)  
  
 [<span data-ttu-id="ec803-179">WSAT_TraceProvider</span><span class="sxs-lookup"><span data-stu-id="ec803-179">WSAT_TraceProvider</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/wsat-traceprovider.md)  
  
 [<span data-ttu-id="ec803-180">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="ec803-180">WSAT_TraceRecord</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/wsat-tracerecord.md)  
  
 [<span data-ttu-id="ec803-181">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="ec803-181">XmlDictionaryReaderQuotas</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/xmldictionaryreaderquotas.md)  
  
 [<span data-ttu-id="ec803-182">XmlSerializerOperationBehavior</span><span class="sxs-lookup"><span data-stu-id="ec803-182">XmlSerializerOperationBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/xmlserializeroperationbehavior.md)
