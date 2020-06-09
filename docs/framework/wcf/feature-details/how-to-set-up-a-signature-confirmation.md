---
title: '방법: 서명 확인 설정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- signature confirmation
- WCF, security
ms.assetid: 2424c137-c7c2-4aa9-8d5d-a066e12fefda
ms.openlocfilehash: 9423922753efee7aac32e430f97307c715e43464
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84586925"
---
# <a name="how-to-set-up-a-signature-confirmation"></a><span data-ttu-id="4f57d-102">방법: 서명 확인 설정</span><span class="sxs-lookup"><span data-stu-id="4f57d-102">How to: Set Up a Signature Confirmation</span></span>

<span data-ttu-id="4f57d-103">*서명 확인* 은 보낸 사람의 원본 메시지에 대 한 응답으로 수신 된 회신이 생성 되었는지 확인 하기 위해 메시지 개시자를 위한 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="4f57d-103">*Signature confirmation* is a mechanism for a message initiator to ensure that a received reply was generated in response to the sender's original message.</span></span> <span data-ttu-id="4f57d-104">서명 확인은 WS-Security 1.1 사양에서 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f57d-104">Signature confirmation is defined in the WS-Security 1.1 specification.</span></span> <span data-ttu-id="4f57d-105">엔드포인트가 WS-Security 1.0을 지원할 경우, 서명 확인을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4f57d-105">If an endpoint supports WS-Security 1.0, you cannot use signature confirmation.</span></span>

<span data-ttu-id="4f57d-106">다음 절차에서는 <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>를 사용하여 서명 확인을 사용하도록 설정하는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4f57d-106">The following procedures specify how to enable signature confirmation using an <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>.</span></span> <span data-ttu-id="4f57d-107"><xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>를 사용하는 경우에도 동일한 절차를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f57d-107">You can use the same procedure with a <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.</span></span> <span data-ttu-id="4f57d-108">이 절차는 [방법: SecurityBindingElement를 사용 하 여 사용자 지정 바인딩 만들기](how-to-create-a-custom-binding-using-the-securitybindingelement.md)에서 찾은 기본 단계를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f57d-108">The procedure builds upon the basic steps found in [How to: Create a Custom Binding Using the SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span></span>

### <a name="to-enable-signature-confirmation-in-code"></a><span data-ttu-id="4f57d-109">코드에서 서명 확인을 사용하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="4f57d-109">To enable signature confirmation in code</span></span>

1. <span data-ttu-id="4f57d-110"><xref:System.ServiceModel.Channels.BindingElementCollection> 클래스의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4f57d-110">Create an instance of the <xref:System.ServiceModel.Channels.BindingElementCollection> class.</span></span>

2. <span data-ttu-id="4f57d-111">클래스의 인스턴스를 만듭니다 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> .</span><span class="sxs-lookup"><span data-stu-id="4f57d-111">Create an instance of the  <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> class.</span></span>

3. <span data-ttu-id="4f57d-112"><xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.RequireSignatureConfirmation%2A>을 `true`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="4f57d-112">Set the <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.RequireSignatureConfirmation%2A> to `true`.</span></span>

4. <span data-ttu-id="4f57d-113">보안 요소를 바인딩 컬렉션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4f57d-113">Add the security element to the binding collection.</span></span>

5. <span data-ttu-id="4f57d-114">[방법: SecurityBindingElement를 사용 하 여 사용자 지정 바인딩 만들기](how-to-create-a-custom-binding-using-the-securitybindingelement.md)에 지정 된 대로 사용자 지정 바인딩을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4f57d-114">Create a custom binding, as specified in [How to: Create a Custom Binding Using the SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span></span>

### <a name="to-enable-signature-confirmation-in-configuration"></a><span data-ttu-id="4f57d-115">구성에서 서명 확인을 사용하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="4f57d-115">To enable signature confirmation in configuration</span></span>

1. <span data-ttu-id="4f57d-116">`<customBinding>` 요소를 구성 파일의 `<bindings>` 섹션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4f57d-116">Add a `<customBinding>` element to the `<bindings>` section of the configuration file.</span></span>

2. <span data-ttu-id="4f57d-117">`<binding>` 요소를 추가하고 이름 특성을 적절한 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="4f57d-117">Add a `<binding>` element and set the name attribute to an appropriate value.</span></span>

3. <span data-ttu-id="4f57d-118">적절한 인코딩 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4f57d-118">Add an appropriate encoding element.</span></span> <span data-ttu-id="4f57d-119">다음 예제에서는 `<TextMessageEncoding>` 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4f57d-119">The following example adds a `<TextMessageEncoding>` element.</span></span>

4. <span data-ttu-id="4f57d-120">`<security>` 자식 요소를 추가하고 `requireSignatureConfirmation` 특성을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="4f57d-120">Add a `<security>` child element and set the `requireSignatureConfirmation` attribute to `true`.</span></span>

5. <span data-ttu-id="4f57d-121">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="4f57d-121">Optional.</span></span> <span data-ttu-id="4f57d-122">부트스트랩 하는 동안 서명 확인을 사용 하도록 설정 하려면 자식 요소를 추가 하 [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) 고 `requireSignatureConfirmation` 특성을로 설정 `true` 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f57d-122">To enable signature confirmation during the bootstrap, add a [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) child element and set the `requireSignatureConfirmation` attribute to `true`.</span></span>

6. <span data-ttu-id="4f57d-123">적절한 전송 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4f57d-123">Add an appropriate transport element.</span></span> <span data-ttu-id="4f57d-124">다음 예제에서는를 추가 합니다 [\<httpTransport>](../../configure-apps/file-schema/wcf/httptransport.md) .</span><span class="sxs-lookup"><span data-stu-id="4f57d-124">The following example adds an [\<httpTransport>](../../configure-apps/file-schema/wcf/httptransport.md):</span></span>

    ```xml
    <bindings>
      <customBinding>
        <binding name="SignatureConfirmationBinding">
          <security requireSignatureConfirmation="true">
            <secureConversationBootstrap requireSignatureConfirmation="true" />
              </security>
           <textMessageEncoding />
             <httpTransport />
        </binding>
      </customBinding>
    </bindings>
    ```

## <a name="example"></a><span data-ttu-id="4f57d-125">예제</span><span class="sxs-lookup"><span data-stu-id="4f57d-125">Example</span></span>

<span data-ttu-id="4f57d-126">다음 코드는 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>의 인스턴스를 만들고 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.RequireSignatureConfirmation%2A> 속성을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="4f57d-126">The following code creates an instance of the <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> and sets the <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.RequireSignatureConfirmation%2A> property to `true`.</span></span> <span data-ttu-id="4f57d-127">이 예제에서는 앞의 예제에서 살펴본 `<secureConversationBootstrap>` 요소를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4f57d-127">Note that this example does not use the `<secureConversationBootstrap>` element shown in the preceding example.</span></span> <span data-ttu-id="4f57d-128">이 예제에서는 Windows(Kerberos 프로토콜) 토큰을 사용할 경우의 서명 확인을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4f57d-128">This example demonstrates signature confirmation when using a Windows (Kerberos protocol) token.</span></span> <span data-ttu-id="4f57d-129">이 경우에는 클라이언트의 서명이 서비스로부터의 모든 응답에서 반환되며 클라이언트에 의해 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f57d-129">In this case, the signature of the client is returned in all responses from the service and is confirmed by the client.</span></span>

[!code-csharp[c_SignatureConfirmation#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_signatureconfirmation/cs/source.cs#1)]
[!code-vb[c_SignatureConfirmation#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_signatureconfirmation/vb/source.vb#1)]

## <a name="see-also"></a><span data-ttu-id="4f57d-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4f57d-130">See also</span></span>

- <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>
- <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>
- <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateMutualCertificateBindingElement%2A>
- [<span data-ttu-id="4f57d-131">방법: SecurityBindingElement를 사용하여 사용자 지정 바인딩 만들기</span><span class="sxs-lookup"><span data-stu-id="4f57d-131">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="4f57d-132">방법: 지정된 인증 모드에 대한 SecurityBindingElement 만들기</span><span class="sxs-lookup"><span data-stu-id="4f57d-132">How to: Create a SecurityBindingElement for a Specified Authentication Mode</span></span>](how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)
