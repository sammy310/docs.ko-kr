---
title: '방법: 보안 세션에 대한 보안 컨텍스트 토큰 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 640676b6-c75a-4ff7-aea4-b1a1524d71b2
ms.openlocfilehash: 36cf5ce1aa6e0eef80123ac7008294062d7faf82
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598907"
---
# <a name="how-to-create-a-security-context-token-for-a-secure-session"></a><span data-ttu-id="31fcc-102">방법: 보안 세션에 대한 보안 컨텍스트 토큰 만들기</span><span class="sxs-lookup"><span data-stu-id="31fcc-102">How to: Create a Security Context Token for a Secure Session</span></span>
<span data-ttu-id="31fcc-103">보안 세션에서 상태 저장 SCT(보안 컨텍스트 토큰)을 사용하면 세션에서 서비스 재활용의 영향을 받지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31fcc-103">By using a stateful security context token (SCT) in a secure session, the session can withstand the service being recycled.</span></span> <span data-ttu-id="31fcc-104">예를 들어, 상태 비저장 SCT를 보안 세션에서 사용할 때 IIS(인터넷 정보 서비스)를 다시 설정하면 서비스와 연결된 세션 데이터가 손실됩니다.</span><span class="sxs-lookup"><span data-stu-id="31fcc-104">For instance, when a stateless SCT is used in a secure session and Internet Information Services (IIS) is reset, then the session data that is associated with the service is lost.</span></span> <span data-ttu-id="31fcc-105">이 세션 데이터에는 SCT 토큰 캐시가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31fcc-105">This session data includes an SCT token cache.</span></span> <span data-ttu-id="31fcc-106">따라서 클라이언트가 서비스에 상태 비저장 SCT를 다음에 보낼 때 SCT와 연결된 키를 검색할 수 없기 때문에 오류가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="31fcc-106">So, the next time a client sends the service a stateless SCT, an error is returned, because the key that is associated with the SCT cannot be retrieved.</span></span> <span data-ttu-id="31fcc-107">그러나 상태 저장 SCT를 사용하는 경우에는 SCT와 연결된 키가 SCT에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="31fcc-107">If, however, a stateful SCT is used, then the key that is associated with the SCT is contained within the SCT.</span></span> <span data-ttu-id="31fcc-108">키가 SCT에 포함되어 메시지에 포함되므로 서비스 재활용이 보안 세션에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31fcc-108">Because the key is contained within the SCT and thus contained within the message, the secure session is not affected by the service being recycled.</span></span> <span data-ttu-id="31fcc-109">기본적으로 WCF (Windows Communication Foundation)에서는 보안 세션에서 상태 비저장 Sct를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="31fcc-109">By default, Windows Communication Foundation (WCF) uses stateless SCTs in a secure session.</span></span> <span data-ttu-id="31fcc-110">이 항목에서는 보안 세션에서 상태 저장 SCT를 사용하는 방법에 대해 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="31fcc-110">This topic details how to use stateful SCTs in a secure session.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="31fcc-111"><xref:System.ServiceModel.Channels.IDuplexChannel>에서 파생되는 계약을 포함하는 보안 세션에서는 상태 저장 SCT를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="31fcc-111">Stateful SCTs cannot be used in a secure session that involves a contract that derives from <xref:System.ServiceModel.Channels.IDuplexChannel>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="31fcc-112">보안 세션에서 상태 저장 SCT를 사용하는 애플리케이션의 경우 서비스의 스레드 ID는 연결된 사용자 프로필이 있는 사용자 계정이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="31fcc-112">For applications that use stateful SCTs in a secure session, the thread identity for the service must be a user account that has an associated user profile.</span></span> <span data-ttu-id="31fcc-113">`Local Service`처럼 사용자 프로필이 없는 계정으로 서비스를 실행하면 예외가 throw될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31fcc-113">When the service is run under an account that does not have a user profile, such as `Local Service`, an exception may be thrown.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="31fcc-114">Windows XP에서 가장이 필요한 경우 상태 저장 SCT 없이 보안 세션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="31fcc-114">When impersonation is required on Windows XP, use a secure session without a stateful SCT.</span></span> <span data-ttu-id="31fcc-115">상태 저장 SCT가 가장과 함께 사용되는 경우 <xref:System.InvalidOperationException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="31fcc-115">When stateful SCTs are used with impersonation, an <xref:System.InvalidOperationException> is thrown.</span></span> <span data-ttu-id="31fcc-116">자세한 내용은 [지원 되지 않는 시나리오](unsupported-scenarios.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="31fcc-116">For more information, see [Unsupported Scenarios](unsupported-scenarios.md).</span></span>  
  
### <a name="to-use-stateful-scts-in-a-secure-session"></a><span data-ttu-id="31fcc-117">보안 세션에서 상태 저장 SCT를 사용하려면</span><span class="sxs-lookup"><span data-stu-id="31fcc-117">To use stateful SCTs in a secure session</span></span>  
  
- <span data-ttu-id="31fcc-118">상태 저장 SCT를 사용하는 보안 세션을 통해 SOAP 메시지를 보호하도록 지정하는 사용자 지정 바인딩을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="31fcc-118">Create a custom binding that specifies that SOAP messages are protected by a secure session that uses a stateful SCT.</span></span>  
  
    1. <span data-ttu-id="31fcc-119">서비스의 구성 파일에를 추가 하 여 사용자 지정 바인딩을 정의 합니다 [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) .</span><span class="sxs-lookup"><span data-stu-id="31fcc-119">Define a custom binding, by adding a [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) to the configuration file for the service.</span></span>  
  
        ```xml  
        <customBinding>  
        </customBinding>
        ```  
  
    2. <span data-ttu-id="31fcc-120">자식 요소를에 추가 [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="31fcc-120">Add a [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) child element to the [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md).</span></span>  
  
         <span data-ttu-id="31fcc-121">구성 파일에서 `name` 특성을 고유한 이름으로 설정하여 바인딩 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="31fcc-121">Specify a binding name by setting the `name` attribute to a unique name within the configuration file.</span></span>  
  
        ```xml  
        <binding name="StatefulSCTSecureSession">  
        </binding>
        ```  
  
    3. <span data-ttu-id="31fcc-122">자식 요소를에 추가 하 여이 서비스에서 보내고 받는 메시지에 대 한 인증 모드를 지정 [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="31fcc-122">Specify the authentication mode for messages sent to and from this service by adding a [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) child element to the [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md).</span></span>  
  
         <span data-ttu-id="31fcc-123">`authenticationMode` 특성을 `SecureConversation`으로 설정하여 보안 세션을 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="31fcc-123">Specify that a secure session is used by setting the `authenticationMode` attribute to `SecureConversation`.</span></span> <span data-ttu-id="31fcc-124">`requireSecurityContextCancellation` 특성을 `false`로 설정하여 상태 저장 SCT를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="31fcc-124">Specify that stateful SCTs are used by setting the `requireSecurityContextCancellation` attribute to `false`.</span></span>  
  
        ```xml  
        <security authenticationMode="SecureConversation"  
                  requireSecurityContextCancellation="false">
        </security>
        ```  
  
    4. <span data-ttu-id="31fcc-125">에 자식 요소를 추가 하 여 보안 세션을 설정 하는 동안 클라이언트를 인증 하는 방법을 지정 [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="31fcc-125">Specify how the client is authenticated while the secure session is established by adding a [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) child element to the [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md).</span></span>  
  
         <span data-ttu-id="31fcc-126">`authenticationMode` 특성을 설정하여 클라이언트를 인증하는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="31fcc-126">Specify how the client is authenticated by setting the `authenticationMode` attribute.</span></span>  
  
        ```xml  
        <secureConversationBootstrap authenticationMode="UserNameForCertificate" />  
        ```  
  
    5. <span data-ttu-id="31fcc-127">와 같은 인코딩 요소를 추가 하 여 메시지 인코딩을 지정 [\<textMessageEncoding>](../../configure-apps/file-schema/wcf/textmessageencoding.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="31fcc-127">Specify the message encoding by adding an encoding element, such as [\<textMessageEncoding>](../../configure-apps/file-schema/wcf/textmessageencoding.md).</span></span>  
  
        ```xml  
        <textMessageEncoding />  
        ```  
  
    6. <span data-ttu-id="31fcc-128">전송 요소 (예:)를 추가 하 여 전송을 지정 합니다 [\<httpTransport>](../../configure-apps/file-schema/wcf/httptransport.md) .</span><span class="sxs-lookup"><span data-stu-id="31fcc-128">Specify the transport by adding a transport element, such as the [\<httpTransport>](../../configure-apps/file-schema/wcf/httptransport.md).</span></span>  
  
        ```xml  
        <httpTransport />  
        ```  
  
     <span data-ttu-id="31fcc-129">다음 코드 예제에서는 구성을 사용하여 메시지가 보안 세션에서 상태 저장 SCT와 함께 사용할 수 있는 사용자 지정 바인딩을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="31fcc-129">The following code example uses configuration to specify a custom binding that messages can use with stateful SCTs in a secure session.</span></span>  
  
    ```xml  
    <customBinding>  
      <binding name="StatefulSCTSecureSession">  
        <security authenticationMode="SecureConversation"  
                  requireSecurityContextCancellation="false">  
          <secureConversationBootstrap authenticationMode="UserNameForCertificate" />  
        </security>  
        <textMessageEncoding />  
        <httpTransport />  
      </binding>  
    </customBinding>  
    ```  
  
## <a name="example"></a><span data-ttu-id="31fcc-130">예제</span><span class="sxs-lookup"><span data-stu-id="31fcc-130">Example</span></span>  
 <span data-ttu-id="31fcc-131">다음 코드 예제에서는 <xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate> 인증 모드를 사용하여 보안 세션을 부트스트랩하는 사용자 지정 바인딩을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="31fcc-131">The following code example creates a custom binding that uses the <xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate> authentication mode to bootstrap a secure session.</span></span>  
  
 [!code-csharp[c_CreateStatefulSCT#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_createstatefulsct/cs/secureservice.cs#2)]
 [!code-vb[c_CreateStatefulSCT#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_createstatefulsct/vb/secureservice.vb#2)]  
  
 <span data-ttu-id="31fcc-132">Windows 인증을 상태 저장 SCT와 함께 사용 하는 경우 WCF는 <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> 속성을 실제 호출자의 id로 채우지 않고 속성을 익명으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="31fcc-132">When Windows authentication is used in combination with a stateful SCT, WCF does not populate the <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> property with the actual caller's identity but instead sets the property to anonymous.</span></span> <span data-ttu-id="31fcc-133">WCF 보안은 들어오는 SCT의 모든 요청에 대해 서비스 보안 컨텍스트 내용을 다시 만들어야 하므로 서버는 메모리에서 보안 세션을 추적 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31fcc-133">Because WCF security must re-create the content of the service security context for every request from the incoming SCT, the server does not keep track of the security session in the memory.</span></span> <span data-ttu-id="31fcc-134"><xref:System.Security.Principal.WindowsIdentity> 인스턴스를 SCT로 serialize할 수 없기 때문에 <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> 속성은 익명 ID를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="31fcc-134">Because it is impossible to serialize the <xref:System.Security.Principal.WindowsIdentity> instance into the SCT, the <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> property returns an anonymous identity.</span></span>  
  
 <span data-ttu-id="31fcc-135">다음 구성은이 동작을 보여 주는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="31fcc-135">The following configuration exhibits this behavior.</span></span>  
  
```xml  
<customBinding>  
  <binding name="Cancellation">  
       <textMessageEncoding />  
        <security
            requireSecurityContextCancellation="false">  
              <secureConversationBootstrap />  
        </security>  
    <httpTransport />  
  </binding>  
</customBinding>  
```  
  
## <a name="see-also"></a><span data-ttu-id="31fcc-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="31fcc-136">See also</span></span>

- [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md)
