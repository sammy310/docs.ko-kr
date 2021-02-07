---
description: '자세히 알아보기: 방법: 클라이언트 자격 증명 형식 지정'
title: '방법: 클라이언트 자격 증명 형식 지정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security credentials, adding to SOAP messages
- WCF, security
ms.assetid: 10f51bee-5f92-4c1a-9126-fa5418535d8f
ms.openlocfilehash: f6536778e8814a1b5a4c03e22c0fe4108f89b6eb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99752537"
---
# <a name="how-to-specify-the-client-credential-type"></a><span data-ttu-id="6b2f0-103">방법: 클라이언트 자격 증명 형식 지정</span><span class="sxs-lookup"><span data-stu-id="6b2f0-103">How to: Specify the Client Credential Type</span></span>

<span data-ttu-id="6b2f0-104">전송 또는 메시지 보안 모드를 설정한 후에는 클라이언트 자격 증명 형식을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b2f0-104">After setting a security mode (either transport or message), you have the option of setting the client credential type.</span></span> <span data-ttu-id="6b2f0-105">이 속성은 인증을 위한 서비스에 제공해야 할 자격 증명 유형을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6b2f0-105">This property specifies what type of credential the client must provide to the service for authentication.</span></span> <span data-ttu-id="6b2f0-106">보안 모드를 설정 하는 방법에 대 한 자세한 내용은 (클라이언트 자격 증명 형식을 설정 하는 데 필요한 단계) [방법: 보안 모드 설정](how-to-set-the-security-mode.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6b2f0-106">For more information about setting the security mode (a necessary step before setting the client credential type), see [How to: Set the Security Mode](how-to-set-the-security-mode.md).</span></span>  
  
### <a name="to-set-the-client-credential-type-in-code"></a><span data-ttu-id="6b2f0-107">클라이언트 자격 증명 형식을 코드로 설정하려면</span><span class="sxs-lookup"><span data-stu-id="6b2f0-107">To set the client credential type in code</span></span>  
  
1. <span data-ttu-id="6b2f0-108">서비스에서 사용할 바인딩의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6b2f0-108">Create an instance of the binding that the service will use.</span></span> <span data-ttu-id="6b2f0-109">이 예제에서는 <xref:System.ServiceModel.WSHttpBinding> 바인딩을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6b2f0-109">This example uses the <xref:System.ServiceModel.WSHttpBinding> binding.</span></span>  
  
2. <span data-ttu-id="6b2f0-110"><xref:System.ServiceModel.WSHttpSecurity.Mode%2A> 속성을 적절한 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6b2f0-110">Set the <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> property to an appropriate value.</span></span> <span data-ttu-id="6b2f0-111">이 예제에서는 메시지 모드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6b2f0-111">This example uses the Message mode.</span></span>  
  
3. <span data-ttu-id="6b2f0-112"><xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> 속성을 적절한 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6b2f0-112">Set the <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> property to an appropriate value.</span></span> <span data-ttu-id="6b2f0-113">이 예제에서는 Windows 인증(<xref:System.ServiceModel.MessageCredentialType.Windows>)을 사용하도록 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6b2f0-113">This example sets it to use Windows authentication (<xref:System.ServiceModel.MessageCredentialType.Windows>).</span></span>  
  
     [!code-csharp[c_ProgrammingSecurity#14](../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#14)]
     [!code-vb[c_ProgrammingSecurity#14](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#14)]  
  
### <a name="to-set-the-client-credential-type-in-configuration"></a><span data-ttu-id="6b2f0-114">클라이언트 자격 증명 형식을 구성에 설정하려면</span><span class="sxs-lookup"><span data-stu-id="6b2f0-114">To set the client credential type in configuration</span></span>  
  
1. <span data-ttu-id="6b2f0-115">[\<system.serviceModel>](../configure-apps/file-schema/wcf/system-servicemodel.md)구성 파일에 요소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b2f0-115">Add a [\<system.serviceModel>](../configure-apps/file-schema/wcf/system-servicemodel.md) element to the configuration file.</span></span>  
  
2. <span data-ttu-id="6b2f0-116">요소를 자식 요소로 추가 [\<bindings>](../configure-apps/file-schema/wcf/bindings.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b2f0-116">As a child element, add a [\<bindings>](../configure-apps/file-schema/wcf/bindings.md) element.</span></span>  
  
3. <span data-ttu-id="6b2f0-117">적절한 바인딩을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6b2f0-117">Add an appropriate binding.</span></span> <span data-ttu-id="6b2f0-118">이 예제에서는 요소를 사용 [\<wsHttpBinding>](../configure-apps/file-schema/wcf/wshttpbinding.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b2f0-118">This example uses the [\<wsHttpBinding>](../configure-apps/file-schema/wcf/wshttpbinding.md) element.</span></span>  
  
4. <span data-ttu-id="6b2f0-119">요소를 추가 [\<binding>](../configure-apps/file-schema/wcf/bindings.md) 하 고 `name` 특성을 적절 한 값으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b2f0-119">Add a [\<binding>](../configure-apps/file-schema/wcf/bindings.md) element and set the `name` attribute to an appropriate value.</span></span> <span data-ttu-id="6b2f0-120">이 예제에서는 "SecureBinding"을 이름으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6b2f0-120">This example uses the name "SecureBinding".</span></span>  
  
5. <span data-ttu-id="6b2f0-121">`<security>` 바인딩을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6b2f0-121">Add a `<security>` binding.</span></span> <span data-ttu-id="6b2f0-122">`mode` 특성을 적절한 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6b2f0-122">Set the `mode` attribute to an appropriate value.</span></span> <span data-ttu-id="6b2f0-123">이 예제에서는 `"Message"`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6b2f0-123">This example sets it to `"Message"`.</span></span>  
  
6. <span data-ttu-id="6b2f0-124">보안 모드의 결정에 따라 `<message>` 또는 `<transport>` 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6b2f0-124">Add either a `<message>` or `<transport>` element, as determined by the security mode.</span></span> <span data-ttu-id="6b2f0-125">`clientCredentialType` 특성을 적절한 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6b2f0-125">Set the `clientCredentialType` attribute to an appropriate value.</span></span> <span data-ttu-id="6b2f0-126">이 예에서는 `"Windows"`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6b2f0-126">This example uses `"Windows"`.</span></span>  
  
    ```xml  
    <system.serviceModel>  
      <bindings>  
        <wsHttpBinding>  
          <binding name="SecureBinding">  
            <security mode="Message">  
                 <message clientCredentialType="Windows" />  
             </security>  
          </binding>  
        </wsHttpBinding>  
      </bindings>  
    </system.serviceModel>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="6b2f0-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6b2f0-127">See also</span></span>

- [<span data-ttu-id="6b2f0-128">서비스에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="6b2f0-128">Securing Services</span></span>](securing-services.md)
- [<span data-ttu-id="6b2f0-129">방법: 보안 모드 설정</span><span class="sxs-lookup"><span data-stu-id="6b2f0-129">How to: Set the Security Mode</span></span>](how-to-set-the-security-mode.md)
