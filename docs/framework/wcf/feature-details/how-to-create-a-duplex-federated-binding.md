---
description: '자세히 알아보기: 방법: 이중 페더레이션 바인딩 만들기'
title: '방법: 이중 페더레이션 바인딩 만들기'
ms.date: 03/30/2017
ms.assetid: 4331d2bc-5455-492a-9189-634a82597726
ms.openlocfilehash: 92d5eeeffab88d88aa245b51738048dced2d5d2d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99779909"
---
# <a name="how-to-create-a-duplex-federated-binding"></a><span data-ttu-id="ff536-103">방법: 이중 페더레이션 바인딩 만들기</span><span class="sxs-lookup"><span data-stu-id="ff536-103">How to: Create a Duplex Federated Binding</span></span>

<span data-ttu-id="ff536-104"><xref:System.ServiceModel.WSFederationHttpBinding>은 데이터그램 및 요청/응답 메시지 교환 계약만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ff536-104"><xref:System.ServiceModel.WSFederationHttpBinding> only supports the datagram and request/reply message exchange contracts.</span></span> <span data-ttu-id="ff536-105">이중 메시지 교환 계약을 사용하려면 사용자 지정 바인딩을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff536-105">To use the duplex message exchange contract, you must create a custom binding.</span></span> <span data-ttu-id="ff536-106">다음 절차에서는 HTTP 및 TCP 전송에 대해서는 메시지 모드 보안을 사용하고 TCP 전송에 대해서는 혼합 모드 보안을 사용하여 구성에서 이 작업을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ff536-106">The following procedures show how to do this in configuration, using Message mode security for the HTTP and TCP transports, and using mixed mode security for the TCP transport.</span></span> <span data-ttu-id="ff536-107">3개의 바인딩을 모두 보여 주는 샘플 코드는 이 항목의 끝에 나옵니다.</span><span class="sxs-lookup"><span data-stu-id="ff536-107">Sample code showing all 3 bindings is at the end of this topic.</span></span>

<span data-ttu-id="ff536-108">코드에서 바인딩을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff536-108">You can also create the binding in code.</span></span> <span data-ttu-id="ff536-109">만들 바인딩 요소 스택에 대 한 설명은 [방법: SecurityBindingElement를 사용 하 여 사용자 지정 바인딩 만들기](how-to-create-a-custom-binding-using-the-securitybindingelement.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ff536-109">For a description of the binding elements stack to create, see [How to: Create a Custom Binding Using the SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span></span>

## <a name="to-create-a-duplex-federated-custom-binding-with-http"></a><span data-ttu-id="ff536-110">HTTP를 사용하여 이중 페더레이션 사용자 지정 바인딩을 만들려면</span><span class="sxs-lookup"><span data-stu-id="ff536-110">To create a duplex federated custom binding with HTTP</span></span>

1. <span data-ttu-id="ff536-111">[\<bindings>](../../configure-apps/file-schema/wcf/bindings.md)구성 파일의 노드에서 요소를 만듭니다 [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) .</span><span class="sxs-lookup"><span data-stu-id="ff536-111">In the [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) element.</span></span>

2. <span data-ttu-id="ff536-112">요소 내 [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) 에서 [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) 특성이로 설정 된 요소를 만듭니다 `name` `FederationDuplexHttpMessageSecurityBinding` .</span><span class="sxs-lookup"><span data-stu-id="ff536-112">Inside the [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element with the `name` attribute set to `FederationDuplexHttpMessageSecurityBinding`.</span></span>

3. <span data-ttu-id="ff536-113">요소 내 [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) 에서 [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) 특성이로 설정 된 요소를 만듭니다 `authenticationMode` `SecureConversation` .</span><span class="sxs-lookup"><span data-stu-id="ff536-113">Inside the [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element, create a [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>

4. <span data-ttu-id="ff536-114">요소 내 [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) 에서 [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) `authenticationMode` 특성이 또는로 설정 된 요소를 만듭니다 `IssuedTokenForCertificate` `IssuedTokenForSslNegotiated` .</span><span class="sxs-lookup"><span data-stu-id="ff536-114">Inside the [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>

5. <span data-ttu-id="ff536-115">요소 뒤 [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) 에 빈 요소를 만듭니다 [\<compositeDuplex>](../../configure-apps/file-schema/wcf/compositeduplex.md) .</span><span class="sxs-lookup"><span data-stu-id="ff536-115">Following the [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<compositeDuplex>](../../configure-apps/file-schema/wcf/compositeduplex.md) element.</span></span>

6. <span data-ttu-id="ff536-116">요소 뒤 [\<compositeDuplex>](../../configure-apps/file-schema/wcf/compositeduplex.md) 에 빈 요소를 만듭니다 [\<oneWay>](../../configure-apps/file-schema/wcf/oneway.md) .</span><span class="sxs-lookup"><span data-stu-id="ff536-116">Following the [\<compositeDuplex>](../../configure-apps/file-schema/wcf/compositeduplex.md) element, create an empty [\<oneWay>](../../configure-apps/file-schema/wcf/oneway.md) element.</span></span>

7. <span data-ttu-id="ff536-117">요소 뒤 [\<oneWay>](../../configure-apps/file-schema/wcf/oneway.md) 에 빈 요소를 만듭니다 [\<httpTransport>](../../configure-apps/file-schema/wcf/httptransport.md) .</span><span class="sxs-lookup"><span data-stu-id="ff536-117">Following the [\<oneWay>](../../configure-apps/file-schema/wcf/oneway.md) element, create an empty [\<httpTransport>](../../configure-apps/file-schema/wcf/httptransport.md) element.</span></span>

## <a name="to-create-a-duplex-federated-custom-binding-with-tcp-message-security-mode"></a><span data-ttu-id="ff536-118">TCP 메시지 보안 모드를 사용하여 이중 페더레이션 사용자 지정 바인딩을 만들려면</span><span class="sxs-lookup"><span data-stu-id="ff536-118">To create a duplex federated custom binding with TCP message security mode</span></span>

1. <span data-ttu-id="ff536-119">[\<bindings>](../../configure-apps/file-schema/wcf/bindings.md)구성 파일의 노드에서 요소를 만듭니다 [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) .</span><span class="sxs-lookup"><span data-stu-id="ff536-119">In the [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) element.</span></span>

2. <span data-ttu-id="ff536-120">요소 내 [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) 에서 [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) 특성이로 설정 된 요소를 만듭니다 `name` `FederationDuplexTcpMessageSecurityBinding` .</span><span class="sxs-lookup"><span data-stu-id="ff536-120">Inside the [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element with the `name` attribute set to `FederationDuplexTcpMessageSecurityBinding`.</span></span>

3. <span data-ttu-id="ff536-121">요소 내 [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) 에서 [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) 특성이로 설정 된 요소를 만듭니다 `authenticationMode` `SecureConversation` .</span><span class="sxs-lookup"><span data-stu-id="ff536-121">Inside the [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element, create a [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>

4. <span data-ttu-id="ff536-122">요소 내 [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) 에서 [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) `authenticationMode` 특성이 또는로 설정 된 요소를 만듭니다 `IssuedTokenForCertificate` `IssuedTokenForSslNegotiated` .</span><span class="sxs-lookup"><span data-stu-id="ff536-122">Inside the [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>

5. <span data-ttu-id="ff536-123">요소 뒤 [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) 에 빈 요소를 만듭니다 [\<tcpTransport>](../../configure-apps/file-schema/wcf/tcptransport.md) .</span><span class="sxs-lookup"><span data-stu-id="ff536-123">Following the [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<tcpTransport>](../../configure-apps/file-schema/wcf/tcptransport.md) element.</span></span>

## <a name="to-create-a-duplex-federated-custom-binding-with-tcp-mixed-security-mode"></a><span data-ttu-id="ff536-124">TCP 혼합 보안 모드를 사용하여 이중 페더레이션 사용자 지정 바인딩을 만들려면</span><span class="sxs-lookup"><span data-stu-id="ff536-124">To create a duplex federated custom binding with TCP mixed security mode</span></span>

1. <span data-ttu-id="ff536-125">[\<bindings>](../../configure-apps/file-schema/wcf/bindings.md)구성 파일의 노드에서 요소를 만듭니다 [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) .</span><span class="sxs-lookup"><span data-stu-id="ff536-125">In the [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) element.</span></span>

2. <span data-ttu-id="ff536-126">요소 내 [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) 에서 [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) 특성이로 설정 된 요소를 만듭니다 `name` `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding` .</span><span class="sxs-lookup"><span data-stu-id="ff536-126">Inside the [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element with the `name` attribute set to `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding`.</span></span>

3. <span data-ttu-id="ff536-127">요소 내 [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) 에서 [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) 특성이로 설정 된 요소를 만듭니다 `authenticationMode` `SecureConversation` .</span><span class="sxs-lookup"><span data-stu-id="ff536-127">Inside the [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element, create a [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>

4. <span data-ttu-id="ff536-128">요소 내 [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) 에서 [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) `authenticationMode` 특성이 또는로 설정 된 요소를 만듭니다 `IssuedTokenForCertificate` `IssuedTokenForSslNegotiated` .</span><span class="sxs-lookup"><span data-stu-id="ff536-128">Inside the [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>

5. <span data-ttu-id="ff536-129">요소 뒤 [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) 에 빈 요소를 만듭니다 [\<sslStreamSecurity>](../../configure-apps/file-schema/wcf/sslstreamsecurity.md) .</span><span class="sxs-lookup"><span data-stu-id="ff536-129">Following the [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<sslStreamSecurity>](../../configure-apps/file-schema/wcf/sslstreamsecurity.md) element.</span></span>

6. <span data-ttu-id="ff536-130">요소 뒤 [\<sslStreamSecurity>](../../configure-apps/file-schema/wcf/sslstreamsecurity.md) 에 빈 요소를 만듭니다 [\<tcpTransport>](../../configure-apps/file-schema/wcf/tcptransport.md) .</span><span class="sxs-lookup"><span data-stu-id="ff536-130">Following the [\<sslStreamSecurity>](../../configure-apps/file-schema/wcf/sslstreamsecurity.md) element, create an empty [\<tcpTransport>](../../configure-apps/file-schema/wcf/tcptransport.md) element.</span></span>

## <a name="code-sample"></a><span data-ttu-id="ff536-131">코드 예제</span><span class="sxs-lookup"><span data-stu-id="ff536-131">Code Sample</span></span>

### <a name="sample-with-3-bindings"></a><span data-ttu-id="ff536-132">3개의 바인딩에 대한 샘플</span><span class="sxs-lookup"><span data-stu-id="ff536-132">Sample with 3 Bindings</span></span>

1. <span data-ttu-id="ff536-133">구성 파일에 다음 코드를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="ff536-133">Insert the following code into your configuration file.</span></span>

## <a name="example"></a><span data-ttu-id="ff536-134">예제</span><span class="sxs-lookup"><span data-stu-id="ff536-134">Example</span></span>

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
