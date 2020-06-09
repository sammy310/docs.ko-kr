---
title: '방법: 이중 페더레이션 바인딩 만들기'
ms.date: 03/30/2017
ms.assetid: 4331d2bc-5455-492a-9189-634a82597726
ms.openlocfilehash: e93651ce9fe9dae55c299fcb061da6bdc4b6bc5e
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598972"
---
# <a name="how-to-create-a-duplex-federated-binding"></a><span data-ttu-id="590fa-102">방법: 이중 페더레이션 바인딩 만들기</span><span class="sxs-lookup"><span data-stu-id="590fa-102">How to: Create a Duplex Federated Binding</span></span>

<span data-ttu-id="590fa-103"><xref:System.ServiceModel.WSFederationHttpBinding>은 데이터그램 및 요청/응답 메시지 교환 계약만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="590fa-103"><xref:System.ServiceModel.WSFederationHttpBinding> only supports the datagram and request/reply message exchange contracts.</span></span> <span data-ttu-id="590fa-104">이중 메시지 교환 계약을 사용하려면 사용자 지정 바인딩을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="590fa-104">To use the duplex message exchange contract, you must create a custom binding.</span></span> <span data-ttu-id="590fa-105">다음 절차에서는 HTTP 및 TCP 전송에 대해서는 메시지 모드 보안을 사용하고 TCP 전송에 대해서는 혼합 모드 보안을 사용하여 구성에서 이 작업을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="590fa-105">The following procedures show how to do this in configuration, using Message mode security for the HTTP and TCP transports, and using mixed mode security for the TCP transport.</span></span> <span data-ttu-id="590fa-106">3개의 바인딩을 모두 보여 주는 샘플 코드는 이 항목의 끝에 나옵니다.</span><span class="sxs-lookup"><span data-stu-id="590fa-106">Sample code showing all 3 bindings is at the end of this topic.</span></span>

<span data-ttu-id="590fa-107">코드에서 바인딩을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="590fa-107">You can also create the binding in code.</span></span> <span data-ttu-id="590fa-108">만들 바인딩 요소 스택에 대 한 설명은 [방법: SecurityBindingElement를 사용 하 여 사용자 지정 바인딩 만들기](how-to-create-a-custom-binding-using-the-securitybindingelement.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="590fa-108">For a description of the binding elements stack to create, see [How to: Create a Custom Binding Using the SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span></span>

## <a name="to-create-a-duplex-federated-custom-binding-with-http"></a><span data-ttu-id="590fa-109">HTTP를 사용하여 이중 페더레이션 사용자 지정 바인딩을 만들려면</span><span class="sxs-lookup"><span data-stu-id="590fa-109">To create a duplex federated custom binding with HTTP</span></span>

1. <span data-ttu-id="590fa-110">[\<bindings>](../../configure-apps/file-schema/wcf/bindings.md)구성 파일의 노드에서 요소를 만듭니다 [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) .</span><span class="sxs-lookup"><span data-stu-id="590fa-110">In the [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) element.</span></span>

2. <span data-ttu-id="590fa-111">요소 내 [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) 에서 [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) 특성이로 설정 된 요소를 만듭니다 `name` `FederationDuplexHttpMessageSecurityBinding` .</span><span class="sxs-lookup"><span data-stu-id="590fa-111">Inside the [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element with the `name` attribute set to `FederationDuplexHttpMessageSecurityBinding`.</span></span>

3. <span data-ttu-id="590fa-112">요소 내 [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) 에서 [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) 특성이로 설정 된 요소를 만듭니다 `authenticationMode` `SecureConversation` .</span><span class="sxs-lookup"><span data-stu-id="590fa-112">Inside the [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element, create a [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>

4. <span data-ttu-id="590fa-113">요소 내 [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) 에서 [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) `authenticationMode` 특성이 또는로 설정 된 요소를 만듭니다 `IssuedTokenForCertificate` `IssuedTokenForSslNegotiated` .</span><span class="sxs-lookup"><span data-stu-id="590fa-113">Inside the [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>

5. <span data-ttu-id="590fa-114">요소 뒤 [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) 에 빈 요소를 만듭니다 [\<compositeDuplex>](../../configure-apps/file-schema/wcf/compositeduplex.md) .</span><span class="sxs-lookup"><span data-stu-id="590fa-114">Following the [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<compositeDuplex>](../../configure-apps/file-schema/wcf/compositeduplex.md) element.</span></span>

6. <span data-ttu-id="590fa-115">요소 뒤 [\<compositeDuplex>](../../configure-apps/file-schema/wcf/compositeduplex.md) 에 빈 요소를 만듭니다 [\<oneWay>](../../configure-apps/file-schema/wcf/oneway.md) .</span><span class="sxs-lookup"><span data-stu-id="590fa-115">Following the [\<compositeDuplex>](../../configure-apps/file-schema/wcf/compositeduplex.md) element, create an empty [\<oneWay>](../../configure-apps/file-schema/wcf/oneway.md) element.</span></span>

7. <span data-ttu-id="590fa-116">요소 뒤 [\<oneWay>](../../configure-apps/file-schema/wcf/oneway.md) 에 빈 요소를 만듭니다 [\<httpTransport>](../../configure-apps/file-schema/wcf/httptransport.md) .</span><span class="sxs-lookup"><span data-stu-id="590fa-116">Following the [\<oneWay>](../../configure-apps/file-schema/wcf/oneway.md) element, create an empty [\<httpTransport>](../../configure-apps/file-schema/wcf/httptransport.md) element.</span></span>

## <a name="to-create-a-duplex-federated-custom-binding-with-tcp-message-security-mode"></a><span data-ttu-id="590fa-117">TCP 메시지 보안 모드를 사용하여 이중 페더레이션 사용자 지정 바인딩을 만들려면</span><span class="sxs-lookup"><span data-stu-id="590fa-117">To create a duplex federated custom binding with TCP message security mode</span></span>

1. <span data-ttu-id="590fa-118">[\<bindings>](../../configure-apps/file-schema/wcf/bindings.md)구성 파일의 노드에서 요소를 만듭니다 [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) .</span><span class="sxs-lookup"><span data-stu-id="590fa-118">In the [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) element.</span></span>

2. <span data-ttu-id="590fa-119">요소 내 [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) 에서 [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) 특성이로 설정 된 요소를 만듭니다 `name` `FederationDuplexTcpMessageSecurityBinding` .</span><span class="sxs-lookup"><span data-stu-id="590fa-119">Inside the [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element with the `name` attribute set to `FederationDuplexTcpMessageSecurityBinding`.</span></span>

3. <span data-ttu-id="590fa-120">요소 내 [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) 에서 [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) 특성이로 설정 된 요소를 만듭니다 `authenticationMode` `SecureConversation` .</span><span class="sxs-lookup"><span data-stu-id="590fa-120">Inside the [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element, create a [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>

4. <span data-ttu-id="590fa-121">요소 내 [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) 에서 [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) `authenticationMode` 특성이 또는로 설정 된 요소를 만듭니다 `IssuedTokenForCertificate` `IssuedTokenForSslNegotiated` .</span><span class="sxs-lookup"><span data-stu-id="590fa-121">Inside the [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>

5. <span data-ttu-id="590fa-122">요소 뒤 [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) 에 빈 요소를 만듭니다 [\<tcpTransport>](../../configure-apps/file-schema/wcf/tcptransport.md) .</span><span class="sxs-lookup"><span data-stu-id="590fa-122">Following the [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<tcpTransport>](../../configure-apps/file-schema/wcf/tcptransport.md) element.</span></span>

## <a name="to-create-a-duplex-federated-custom-binding-with-tcp-mixed-security-mode"></a><span data-ttu-id="590fa-123">TCP 혼합 보안 모드를 사용하여 이중 페더레이션 사용자 지정 바인딩을 만들려면</span><span class="sxs-lookup"><span data-stu-id="590fa-123">To create a duplex federated custom binding with TCP mixed security mode</span></span>

1. <span data-ttu-id="590fa-124">[\<bindings>](../../configure-apps/file-schema/wcf/bindings.md)구성 파일의 노드에서 요소를 만듭니다 [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) .</span><span class="sxs-lookup"><span data-stu-id="590fa-124">In the [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) element.</span></span>

2. <span data-ttu-id="590fa-125">요소 내 [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) 에서 [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) 특성이로 설정 된 요소를 만듭니다 `name` `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding` .</span><span class="sxs-lookup"><span data-stu-id="590fa-125">Inside the [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element with the `name` attribute set to `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding`.</span></span>

3. <span data-ttu-id="590fa-126">요소 내 [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) 에서 [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) 특성이로 설정 된 요소를 만듭니다 `authenticationMode` `SecureConversation` .</span><span class="sxs-lookup"><span data-stu-id="590fa-126">Inside the [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element, create a [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>

4. <span data-ttu-id="590fa-127">요소 내 [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) 에서 [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) `authenticationMode` 특성이 또는로 설정 된 요소를 만듭니다 `IssuedTokenForCertificate` `IssuedTokenForSslNegotiated` .</span><span class="sxs-lookup"><span data-stu-id="590fa-127">Inside the [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>

5. <span data-ttu-id="590fa-128">요소 뒤 [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) 에 빈 요소를 만듭니다 [\<sslStreamSecurity>](../../configure-apps/file-schema/wcf/sslstreamsecurity.md) .</span><span class="sxs-lookup"><span data-stu-id="590fa-128">Following the [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<sslStreamSecurity>](../../configure-apps/file-schema/wcf/sslstreamsecurity.md) element.</span></span>

6. <span data-ttu-id="590fa-129">요소 뒤 [\<sslStreamSecurity>](../../configure-apps/file-schema/wcf/sslstreamsecurity.md) 에 빈 요소를 만듭니다 [\<tcpTransport>](../../configure-apps/file-schema/wcf/tcptransport.md) .</span><span class="sxs-lookup"><span data-stu-id="590fa-129">Following the [\<sslStreamSecurity>](../../configure-apps/file-schema/wcf/sslstreamsecurity.md) element, create an empty [\<tcpTransport>](../../configure-apps/file-schema/wcf/tcptransport.md) element.</span></span>

## <a name="code-sample"></a><span data-ttu-id="590fa-130">코드 예제</span><span class="sxs-lookup"><span data-stu-id="590fa-130">Code Sample</span></span>

### <a name="sample-with-3-bindings"></a><span data-ttu-id="590fa-131">3개의 바인딩에 대한 샘플</span><span class="sxs-lookup"><span data-stu-id="590fa-131">Sample with 3 Bindings</span></span>

1. <span data-ttu-id="590fa-132">구성 파일에 다음 코드를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="590fa-132">Insert the following code into your configuration file.</span></span>

## <a name="example"></a><span data-ttu-id="590fa-133">예제</span><span class="sxs-lookup"><span data-stu-id="590fa-133">Example</span></span>

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
