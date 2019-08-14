---
title: '방법: 이중 페더레이션 바인딩 만들기'
ms.date: 03/30/2017
ms.assetid: 4331d2bc-5455-492a-9189-634a82597726
ms.openlocfilehash: 71c970fa45d7d4ccd55fceddb2360d0aa0a768f8
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/13/2019
ms.locfileid: "68972054"
---
# <a name="how-to-create-a-duplex-federated-binding"></a><span data-ttu-id="1bafe-102">방법: 이중 페더레이션 바인딩 만들기</span><span class="sxs-lookup"><span data-stu-id="1bafe-102">How to: Create a Duplex Federated Binding</span></span>

<span data-ttu-id="1bafe-103"><xref:System.ServiceModel.WSFederationHttpBinding>은 데이터그램 및 요청/응답 메시지 교환 계약만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="1bafe-103"><xref:System.ServiceModel.WSFederationHttpBinding> only supports the datagram and request/reply message exchange contracts.</span></span> <span data-ttu-id="1bafe-104">이중 메시지 교환 계약을 사용하려면 사용자 지정 바인딩을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1bafe-104">To use the duplex message exchange contract, you must create a custom binding.</span></span> <span data-ttu-id="1bafe-105">다음 절차에서는 HTTP 및 TCP 전송에 대해서는 메시지 모드 보안을 사용하고 TCP 전송에 대해서는 혼합 모드 보안을 사용하여 구성에서 이 작업을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1bafe-105">The following procedures show how to do this in configuration, using Message mode security for the HTTP and TCP transports, and using mixed mode security for the TCP transport.</span></span> <span data-ttu-id="1bafe-106">3개의 바인딩을 모두 보여 주는 샘플 코드는 이 항목의 끝에 나옵니다.</span><span class="sxs-lookup"><span data-stu-id="1bafe-106">Sample code showing all 3 bindings is at the end of this topic.</span></span>

<span data-ttu-id="1bafe-107">코드에서 바인딩을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bafe-107">You can also create the binding in code.</span></span> <span data-ttu-id="1bafe-108">만들 바인딩 요소 스택에 대 한 자세한 내용은 [방법: SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)를 사용 하 여 사용자 지정 바인딩을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1bafe-108">For a description of the binding elements stack to create, see [How to: Create a Custom Binding Using the SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span></span>

## <a name="to-create-a-duplex-federated-custom-binding-with-http"></a><span data-ttu-id="1bafe-109">HTTP를 사용하여 이중 페더레이션 사용자 지정 바인딩을 만들려면</span><span class="sxs-lookup"><span data-stu-id="1bafe-109">To create a duplex federated custom binding with HTTP</span></span>

1. <span data-ttu-id="1bafe-110">구성 파일의 [ 바인딩>노드에서customBinding>요소를만듭니다.\<](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)</span><span class="sxs-lookup"><span data-stu-id="1bafe-110">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>

2. <span data-ttu-id="1bafe-111">CustomBinding > `name` 요소 내에서 특성을 로`FederationDuplexHttpMessageSecurityBinding`설정 하 여 [바인딩 > 요소를 만듭니다. \<](../../../../docs/framework/misc/binding.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="1bafe-111">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../../../docs/framework/misc/binding.md) element with the `name` attribute set to `FederationDuplexHttpMessageSecurityBinding`.</span></span>

3. <span data-ttu-id="1bafe-112">바인딩 > `authenticationMode` 요소 내에서 특성을 로`SecureConversation`설정 하 여 [보안 > 요소를 만듭니다. \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) [ \<](../../../../docs/framework/misc/binding.md)</span><span class="sxs-lookup"><span data-stu-id="1bafe-112">Inside the [\<binding>](../../../../docs/framework/misc/binding.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>

4. <span data-ttu-id="1bafe-113">`authenticationMode` `IssuedTokenForCertificate` [Security > 요소 내에서 특성을 또는로 설정 하 여 secureConversationBootstrap > 요소를 만듭니다. \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) `IssuedTokenForSslNegotiated`</span><span class="sxs-lookup"><span data-stu-id="1bafe-113">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>

5. <span data-ttu-id="1bafe-114">Security > 요소 다음에 빈 [ \<compositeDuplex >](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) 요소를 만듭니다. [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="1bafe-114">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<compositeDuplex>](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) element.</span></span>

6. <span data-ttu-id="1bafe-115">CompositeDuplex > 요소 다음에 빈 [ \<oneWay >](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) 요소를 만듭니다. [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md)</span><span class="sxs-lookup"><span data-stu-id="1bafe-115">Following the [\<compositeDuplex>](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) element, create an empty [\<oneWay>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) element.</span></span>

7. <span data-ttu-id="1bafe-116">OneWay > 요소 다음에 빈 [ \<httptransport >](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md) 요소를 만듭니다. [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)</span><span class="sxs-lookup"><span data-stu-id="1bafe-116">Following the [\<oneWay>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) element, create an empty [\<httpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md) element.</span></span>

## <a name="to-create-a-duplex-federated-custom-binding-with-tcp-message-security-mode"></a><span data-ttu-id="1bafe-117">TCP 메시지 보안 모드를 사용하여 이중 페더레이션 사용자 지정 바인딩을 만들려면</span><span class="sxs-lookup"><span data-stu-id="1bafe-117">To create a duplex federated custom binding with TCP message security mode</span></span>

1. <span data-ttu-id="1bafe-118">구성 파일의 [ 바인딩>노드에서customBinding>요소를만듭니다.\<](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)</span><span class="sxs-lookup"><span data-stu-id="1bafe-118">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>

2. <span data-ttu-id="1bafe-119">CustomBinding > `name` 요소 내에서 특성을 로`FederationDuplexTcpMessageSecurityBinding`설정 하 여 [바인딩 > 요소를 만듭니다. \<](../../../../docs/framework/misc/binding.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="1bafe-119">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../../../docs/framework/misc/binding.md) element with the `name` attribute set to `FederationDuplexTcpMessageSecurityBinding`.</span></span>

3. <span data-ttu-id="1bafe-120">바인딩 > `authenticationMode` 요소 내에서 특성을 로`SecureConversation`설정 하 여 [보안 > 요소를 만듭니다. \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) [ \<](../../../../docs/framework/misc/binding.md)</span><span class="sxs-lookup"><span data-stu-id="1bafe-120">Inside the [\<binding>](../../../../docs/framework/misc/binding.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>

4. <span data-ttu-id="1bafe-121">`authenticationMode` `IssuedTokenForCertificate` [Security > 요소 내에서 특성을 또는로 설정 하 여 secureConversationBootstrap > 요소를 만듭니다. \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) `IssuedTokenForSslNegotiated`</span><span class="sxs-lookup"><span data-stu-id="1bafe-121">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>

5. <span data-ttu-id="1bafe-122">Security > 요소 다음에 빈 [ \<tcptransport >](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) 요소를 만듭니다. [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="1bafe-122">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<tcpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) element.</span></span>

## <a name="to-create-a-duplex-federated-custom-binding-with-tcp-mixed-security-mode"></a><span data-ttu-id="1bafe-123">TCP 혼합 보안 모드를 사용하여 이중 페더레이션 사용자 지정 바인딩을 만들려면</span><span class="sxs-lookup"><span data-stu-id="1bafe-123">To create a duplex federated custom binding with TCP mixed security mode</span></span>

1. <span data-ttu-id="1bafe-124">구성 파일의 [ 바인딩>노드에서customBinding>요소를만듭니다.\<](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)</span><span class="sxs-lookup"><span data-stu-id="1bafe-124">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>

2. <span data-ttu-id="1bafe-125">CustomBinding > `name` 요소 내에서 특성을 로`FederationDuplexTcpTransportSecurityWithMessageCredentialBinding`설정 하 여 [바인딩 > 요소를 만듭니다. \<](../../../../docs/framework/misc/binding.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="1bafe-125">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../../../docs/framework/misc/binding.md) element with the `name` attribute set to `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding`.</span></span>

3. <span data-ttu-id="1bafe-126">바인딩 > `authenticationMode` 요소 내에서 특성을 로`SecureConversation`설정 하 여 [보안 > 요소를 만듭니다. \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) [ \<](../../../../docs/framework/misc/binding.md)</span><span class="sxs-lookup"><span data-stu-id="1bafe-126">Inside the [\<binding>](../../../../docs/framework/misc/binding.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>

4. <span data-ttu-id="1bafe-127">`authenticationMode` `IssuedTokenForCertificate` [Security > 요소 내에서 특성을 또는로 설정 하 여 secureConversationBootstrap > 요소를 만듭니다. \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) `IssuedTokenForSslNegotiated`</span><span class="sxs-lookup"><span data-stu-id="1bafe-127">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>

5. <span data-ttu-id="1bafe-128">Security > 요소 다음에 빈 [ \<sslstreamsecurity >](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) 요소를 만듭니다. [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="1bafe-128">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<sslStreamSecurity>](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) element.</span></span>

6. <span data-ttu-id="1bafe-129">Sslstreamsecurity > 요소 다음에 빈 [ \<tcptransport >](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) 요소를 만듭니다. [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md)</span><span class="sxs-lookup"><span data-stu-id="1bafe-129">Following the [\<sslStreamSecurity>](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) element, create an empty [\<tcpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) element.</span></span>

## <a name="code-sample"></a><span data-ttu-id="1bafe-130">코드 예제</span><span class="sxs-lookup"><span data-stu-id="1bafe-130">Code Sample</span></span>

### <a name="sample-with-3-bindings"></a><span data-ttu-id="1bafe-131">3개의 바인딩에 대한 샘플</span><span class="sxs-lookup"><span data-stu-id="1bafe-131">Sample with 3 Bindings</span></span>

1. <span data-ttu-id="1bafe-132">구성 파일에 다음 코드를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="1bafe-132">Insert the following code into your configuration file.</span></span>

## <a name="example"></a><span data-ttu-id="1bafe-133">예제</span><span class="sxs-lookup"><span data-stu-id="1bafe-133">Example</span></span>

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
