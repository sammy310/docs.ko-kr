---
title: '방법: 이중 페더레이션 바인딩 만들기'
ms.date: 03/30/2017
ms.assetid: 4331d2bc-5455-492a-9189-634a82597726
ms.openlocfilehash: 510faa0b1d791b1d164c55e9fa32daafa559d56c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59346238"
---
# <a name="how-to-create-a-duplex-federated-binding"></a><span data-ttu-id="b90e2-102">방법: 이중 페더레이션 바인딩 만들기</span><span class="sxs-lookup"><span data-stu-id="b90e2-102">How to: Create a Duplex Federated Binding</span></span>
<span data-ttu-id="b90e2-103"><xref:System.ServiceModel.WSFederationHttpBinding>은 데이터그램 및 요청/응답 메시지 교환 계약만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="b90e2-103"><xref:System.ServiceModel.WSFederationHttpBinding> only supports the datagram and request/reply message exchange contracts.</span></span> <span data-ttu-id="b90e2-104">이중 메시지 교환 계약을 사용하려면 사용자 지정 바인딩을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b90e2-104">To use the duplex message exchange contract, you must create a custom binding.</span></span> <span data-ttu-id="b90e2-105">다음 절차에서는 HTTP 및 TCP 전송에 대해서는 메시지 모드 보안을 사용하고 TCP 전송에 대해서는 혼합 모드 보안을 사용하여 구성에서 이 작업을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b90e2-105">The following procedures show how to do this in configuration, using Message mode security for the HTTP and TCP transports, and using mixed mode security for the TCP transport.</span></span> <span data-ttu-id="b90e2-106">3개의 바인딩을 모두 보여 주는 샘플 코드는 이 항목의 끝에 나옵니다.</span><span class="sxs-lookup"><span data-stu-id="b90e2-106">Sample code showing all 3 bindings is at the end of this topic.</span></span>  
  
 <span data-ttu-id="b90e2-107">코드에서 바인딩을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b90e2-107">You can also create the binding in code.</span></span> <span data-ttu-id="b90e2-108">만들려는 바인딩 요소 스택에의 설명을 참조 하세요. [방법: SecurityBindingElement를 사용 하 여 사용자 지정 바인딩을 만들려면](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b90e2-108">For a description of the binding elements stack to create, see [How to: Create a Custom Binding Using the SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span></span>  
  
### <a name="to-create-a-duplex-federated-custom-binding-with-http"></a><span data-ttu-id="b90e2-109">HTTP를 사용하여 이중 페더레이션 사용자 지정 바인딩을 만들려면</span><span class="sxs-lookup"><span data-stu-id="b90e2-109">To create a duplex federated custom binding with HTTP</span></span>  
  
1. <span data-ttu-id="b90e2-110">에 [ \<바인딩 >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) 노드의 구성 파일 만들기를 [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="b90e2-110">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>  
  
2. <span data-ttu-id="b90e2-111">내부를 [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) 요소를 만들기는 [ \<바인딩 >](../../../../docs/framework/misc/binding.md) 요소를 `name` 특성이로 설정 `FederationDuplexHttpMessageSecurityBinding`합니다.</span><span class="sxs-lookup"><span data-stu-id="b90e2-111">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../../../docs/framework/misc/binding.md) element with the `name` attribute set to `FederationDuplexHttpMessageSecurityBinding`.</span></span>  
  
3. <span data-ttu-id="b90e2-112">내부를 [ \<바인딩 >](../../../../docs/framework/misc/binding.md) 요소를 만들기는 [ \<보안 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) 요소를 `authenticationMode` 특성이로 설정 `SecureConversation`합니다.</span><span class="sxs-lookup"><span data-stu-id="b90e2-112">Inside the [\<binding>](../../../../docs/framework/misc/binding.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>  
  
4. <span data-ttu-id="b90e2-113">내 합니다 [ \<보안 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) 요소를 만들기는 [ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) 요소를 `authenticationMode` 특성이로 설정 `IssuedTokenForCertificate` 또는 `IssuedTokenForSslNegotiated`.</span><span class="sxs-lookup"><span data-stu-id="b90e2-113">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>  
  
5. <span data-ttu-id="b90e2-114">다음은 [ \<보안 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) 요소는 빈 항목 만들기 [ \<compositeDuplex >](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="b90e2-114">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<compositeDuplex>](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) element.</span></span>  
  
6. <span data-ttu-id="b90e2-115">다음은 [ \<compositeDuplex >](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) 요소는 빈 항목 만들기 [ \<oneWay >](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="b90e2-115">Following the [\<compositeDuplex>](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) element, create an empty [\<oneWay>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) element.</span></span>  
  
7. <span data-ttu-id="b90e2-116">다음은 [ \<oneWay >](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) 요소는 빈 항목 만들기 [ \<httpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="b90e2-116">Following the [\<oneWay>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) element, create an empty [\<httpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md) element.</span></span>  
  
### <a name="to-create-a-duplex-federated-custom-binding-with-tcp-message-security-mode"></a><span data-ttu-id="b90e2-117">TCP 메시지 보안 모드를 사용하여 이중 페더레이션 사용자 지정 바인딩을 만들려면</span><span class="sxs-lookup"><span data-stu-id="b90e2-117">To create a duplex federated custom binding with TCP message security mode</span></span>  
  
1. <span data-ttu-id="b90e2-118">에 [ \<바인딩 >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) 노드의 구성 파일 만들기를 [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="b90e2-118">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>   
  
2. <span data-ttu-id="b90e2-119">내부를 [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) 요소를 만들기는 [ \<바인딩 >](../../../../docs/framework/misc/binding.md) 요소를 `name` 특성이로 설정 `FederationDuplexTcpMessageSecurityBinding`합니다.</span><span class="sxs-lookup"><span data-stu-id="b90e2-119">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../../../docs/framework/misc/binding.md) element with the `name` attribute set to `FederationDuplexTcpMessageSecurityBinding`.</span></span>  
  
3. <span data-ttu-id="b90e2-120">내부를 [ \<바인딩 >](../../../../docs/framework/misc/binding.md) 요소를 만들기는 [ \<보안 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) 요소를 `authenticationMode` 특성이로 설정 `SecureConversation`합니다.</span><span class="sxs-lookup"><span data-stu-id="b90e2-120">Inside the [\<binding>](../../../../docs/framework/misc/binding.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>  
  
4. <span data-ttu-id="b90e2-121">내 합니다 [ \<보안 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) 요소를 만들기는 [ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) 요소를 `authenticationMode` 특성이로 설정 `IssuedTokenForCertificate` 또는 `IssuedTokenForSslNegotiated`.</span><span class="sxs-lookup"><span data-stu-id="b90e2-121">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>  
  
5. <span data-ttu-id="b90e2-122">다음은 [ \<보안 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) 요소는 빈 항목 만들기 [ \<tcpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="b90e2-122">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<tcpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) element.</span></span>  
  
### <a name="to-create-a-duplex-federated-custom-binding-with-tcp-mixed-security-mode"></a><span data-ttu-id="b90e2-123">TCP 혼합 보안 모드를 사용하여 이중 페더레이션 사용자 지정 바인딩을 만들려면</span><span class="sxs-lookup"><span data-stu-id="b90e2-123">To create a duplex federated custom binding with TCP mixed security mode</span></span>  
  
1. <span data-ttu-id="b90e2-124">에 [ \<바인딩 >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) 노드의 구성 파일 만들기를 [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="b90e2-124">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>   
  
2. <span data-ttu-id="b90e2-125">내부를 [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) 요소를 만들기는 [ \<바인딩 >](../../../../docs/framework/misc/binding.md) 요소를 `name` 특성이로 설정 `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding`합니다.</span><span class="sxs-lookup"><span data-stu-id="b90e2-125">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../../../docs/framework/misc/binding.md) element with the `name` attribute set to `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding`.</span></span>  
  
3. <span data-ttu-id="b90e2-126">내부를 [ \<바인딩 >](../../../../docs/framework/misc/binding.md) 요소를 만들기는 [ \<보안 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) 요소를 `authenticationMode` 특성이로 설정 `SecureConversation`합니다.</span><span class="sxs-lookup"><span data-stu-id="b90e2-126">Inside the [\<binding>](../../../../docs/framework/misc/binding.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>  
  
4. <span data-ttu-id="b90e2-127">내 합니다 [ \<보안 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) 요소를 만들기는 [ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) 요소를 `authenticationMode` 특성이로 설정 `IssuedTokenForCertificate` 또는 `IssuedTokenForSslNegotiated`.</span><span class="sxs-lookup"><span data-stu-id="b90e2-127">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>  
  
5. <span data-ttu-id="b90e2-128">다음은 [ \<보안 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) 요소는 빈 항목 만들기 [ \<sslStreamSecurity >](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="b90e2-128">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<sslStreamSecurity>](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) element.</span></span>  
  
6. <span data-ttu-id="b90e2-129">다음은 [ \<sslStreamSecurity >](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) 요소는 빈 항목 만들기 [ \<tcpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="b90e2-129">Following the [\<sslStreamSecurity>](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) element, create an empty [\<tcpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) element.</span></span>  
  
## <a name="code-sample"></a><span data-ttu-id="b90e2-130">코드 샘플</span><span class="sxs-lookup"><span data-stu-id="b90e2-130">Code Sample</span></span>  
  
#### <a name="sample-with-3-bindings"></a><span data-ttu-id="b90e2-131">3개의 바인딩에 대한 샘플</span><span class="sxs-lookup"><span data-stu-id="b90e2-131">Sample with 3 Bindings</span></span>  
  
1. <span data-ttu-id="b90e2-132">구성 파일에 다음 코드를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="b90e2-132">Insert the following code into your configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b90e2-133">예제</span><span class="sxs-lookup"><span data-stu-id="b90e2-133">Example</span></span>  
  
```xml  
<bindings>  
   <customBinding>  
      <binding name="FederationDuplexHttpMessageSecurityBinding">  
<!-- duplex contract requires secure conversation with require cancellation = true -->  
          <security authenticationMode="SecureConversation">  
              <secureConversationBootstrap authenticationMode="IssuedTokenForSslNegotiated" />  
          </security>  
          <compositeDuplex />  
          <oneWay />  
          <httpTransport />  
       </binding>  
<!-- duplex over https is not supported -->  
       <binding name="FederationDuplexTcpMessageSecurityBinding">  
<!-- duplex contract requires secure conversation with require cancellation = true -->  
          <security authenticationMode="SecureConversation">  
              <secureConversationBootstrap authenticationMode="IssuedTokenForSslNegotiated" />  
          </security>  
          <tcpTransport />  
       </binding>              
       <binding name="FederationDuplexTcpTransportSecurityWithMessageCredentialsBinding">  
<!-- duplex contract requires secure conversation with require cancellation = true -->  
          <security authenticationMode="SecureConversation">  
              <secureConversationBootstrap authenticationMode="IssuedTokenOverTransport" />  
          </security>  
<!-- requireClientCertificate = true or <windowsStreamSecurity /> can be used, but does not make sense for most scenarios -->  
          <sslStreamSecurity />  
          <tcpTransport />  
       </binding>              
    </customBinding>  
</bindings>  
```
