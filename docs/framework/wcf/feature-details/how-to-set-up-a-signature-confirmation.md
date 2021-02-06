---
description: '자세히 알아보기: 방법: 서명 확인 설정'
title: '방법: 서명 확인 설정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- signature confirmation
- WCF, security
ms.assetid: 2424c137-c7c2-4aa9-8d5d-a066e12fefda
ms.openlocfilehash: 158ec2a5f74038f5c1ca1af847f57457a8881974
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99643191"
---
# <a name="how-to-set-up-a-signature-confirmation"></a><span data-ttu-id="39bf4-103">방법: 서명 확인 설정</span><span class="sxs-lookup"><span data-stu-id="39bf4-103">How to: Set Up a Signature Confirmation</span></span>

<span data-ttu-id="39bf4-104">*서명 확인* 은 보낸 사람의 원본 메시지에 대 한 응답으로 수신 된 회신이 생성 되었는지 확인 하기 위해 메시지 개시자를 위한 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="39bf4-104">*Signature confirmation* is a mechanism for a message initiator to ensure that a received reply was generated in response to the sender's original message.</span></span> <span data-ttu-id="39bf4-105">서명 확인은 WS-Security 1.1 사양에서 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="39bf4-105">Signature confirmation is defined in the WS-Security 1.1 specification.</span></span> <span data-ttu-id="39bf4-106">엔드포인트가 WS-Security 1.0을 지원할 경우, 서명 확인을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="39bf4-106">If an endpoint supports WS-Security 1.0, you cannot use signature confirmation.</span></span>

<span data-ttu-id="39bf4-107">다음 절차에서는 <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>를 사용하여 서명 확인을 사용하도록 설정하는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="39bf4-107">The following procedures specify how to enable signature confirmation using an <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>.</span></span> <span data-ttu-id="39bf4-108"><xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>를 사용하는 경우에도 동일한 절차를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39bf4-108">You can use the same procedure with a <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.</span></span> <span data-ttu-id="39bf4-109">이 절차는 [방법: SecurityBindingElement를 사용 하 여 사용자 지정 바인딩 만들기](how-to-create-a-custom-binding-using-the-securitybindingelement.md)에서 찾은 기본 단계를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="39bf4-109">The procedure builds upon the basic steps found in [How to: Create a Custom Binding Using the SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span></span>

### <a name="to-enable-signature-confirmation-in-code"></a><span data-ttu-id="39bf4-110">코드에서 서명 확인을 사용하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="39bf4-110">To enable signature confirmation in code</span></span>

1. <span data-ttu-id="39bf4-111"><xref:System.ServiceModel.Channels.BindingElementCollection> 클래스의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="39bf4-111">Create an instance of the <xref:System.ServiceModel.Channels.BindingElementCollection> class.</span></span>

2. <span data-ttu-id="39bf4-112">클래스의 인스턴스를 만듭니다  <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> .</span><span class="sxs-lookup"><span data-stu-id="39bf4-112">Create an instance of the  <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> class.</span></span>

3. <span data-ttu-id="39bf4-113"><xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.RequireSignatureConfirmation%2A>을 `true`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="39bf4-113">Set the <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.RequireSignatureConfirmation%2A> to `true`.</span></span>

4. <span data-ttu-id="39bf4-114">보안 요소를 바인딩 컬렉션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="39bf4-114">Add the security element to the binding collection.</span></span>

5. <span data-ttu-id="39bf4-115">[방법: SecurityBindingElement를 사용 하 여 사용자 지정 바인딩 만들기](how-to-create-a-custom-binding-using-the-securitybindingelement.md)에 지정 된 대로 사용자 지정 바인딩을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="39bf4-115">Create a custom binding, as specified in [How to: Create a Custom Binding Using the SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span></span>

### <a name="to-enable-signature-confirmation-in-configuration"></a><span data-ttu-id="39bf4-116">구성에서 서명 확인을 사용하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="39bf4-116">To enable signature confirmation in configuration</span></span>

1. <span data-ttu-id="39bf4-117">`<customBinding>` 요소를 구성 파일의 `<bindings>` 섹션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="39bf4-117">Add a `<customBinding>` element to the `<bindings>` section of the configuration file.</span></span>

2. <span data-ttu-id="39bf4-118">`<binding>` 요소를 추가하고 이름 특성을 적절한 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="39bf4-118">Add a `<binding>` element and set the name attribute to an appropriate value.</span></span>

3. <span data-ttu-id="39bf4-119">적절한 인코딩 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="39bf4-119">Add an appropriate encoding element.</span></span> <span data-ttu-id="39bf4-120">다음 예제에서는 `<TextMessageEncoding>` 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="39bf4-120">The following example adds a `<TextMessageEncoding>` element.</span></span>

4. <span data-ttu-id="39bf4-121">`<security>` 자식 요소를 추가하고 `requireSignatureConfirmation` 특성을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="39bf4-121">Add a `<security>` child element and set the `requireSignatureConfirmation` attribute to `true`.</span></span>

5. <span data-ttu-id="39bf4-122">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="39bf4-122">Optional.</span></span> <span data-ttu-id="39bf4-123">부트스트랩 하는 동안 서명 확인을 사용 하도록 설정 하려면 자식 요소를 추가 하 [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) 고 `requireSignatureConfirmation` 특성을로 설정 `true` 합니다.</span><span class="sxs-lookup"><span data-stu-id="39bf4-123">To enable signature confirmation during the bootstrap, add a [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) child element and set the `requireSignatureConfirmation` attribute to `true`.</span></span>

6. <span data-ttu-id="39bf4-124">적절한 전송 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="39bf4-124">Add an appropriate transport element.</span></span> <span data-ttu-id="39bf4-125">다음 예제에서는를 추가 합니다 [\<httpTransport>](../../configure-apps/file-schema/wcf/httptransport.md) .</span><span class="sxs-lookup"><span data-stu-id="39bf4-125">The following example adds an [\<httpTransport>](../../configure-apps/file-schema/wcf/httptransport.md):</span></span>

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

## <a name="example"></a><span data-ttu-id="39bf4-126">예제</span><span class="sxs-lookup"><span data-stu-id="39bf4-126">Example</span></span>

<span data-ttu-id="39bf4-127">다음 코드는 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>의 인스턴스를 만들고 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.RequireSignatureConfirmation%2A> 속성을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="39bf4-127">The following code creates an instance of the <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> and sets the <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.RequireSignatureConfirmation%2A> property to `true`.</span></span> <span data-ttu-id="39bf4-128">이 예제에서는 앞의 예제에서 살펴본 `<secureConversationBootstrap>` 요소를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="39bf4-128">Note that this example does not use the `<secureConversationBootstrap>` element shown in the preceding example.</span></span> <span data-ttu-id="39bf4-129">이 예제에서는 Windows(Kerberos 프로토콜) 토큰을 사용할 경우의 서명 확인을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="39bf4-129">This example demonstrates signature confirmation when using a Windows (Kerberos protocol) token.</span></span> <span data-ttu-id="39bf4-130">이 경우에는 클라이언트의 서명이 서비스로부터의 모든 응답에서 반환되며 클라이언트에 의해 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="39bf4-130">In this case, the signature of the client is returned in all responses from the service and is confirmed by the client.</span></span>

[!code-csharp[c_SignatureConfirmation#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_signatureconfirmation/cs/source.cs#1)]
[!code-vb[c_SignatureConfirmation#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_signatureconfirmation/vb/source.vb#1)]

## <a name="see-also"></a><span data-ttu-id="39bf4-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="39bf4-131">See also</span></span>

- <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>
- <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>
- <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateMutualCertificateBindingElement%2A>
- [<span data-ttu-id="39bf4-132">방법: SecurityBindingElement를 사용하여 사용자 지정 바인딩 만들기</span><span class="sxs-lookup"><span data-stu-id="39bf4-132">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="39bf4-133">방법: 지정된 인증 모드에 대한 SecurityBindingElement 만들기</span><span class="sxs-lookup"><span data-stu-id="39bf4-133">How to: Create a SecurityBindingElement for a Specified Authentication Mode</span></span>](how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)
