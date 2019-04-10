---
title: <transport> / <netNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: d9eff52d-4bde-4586-b56a-b0ec24611f8d
ms.openlocfilehash: a6d3dd2c24e90bdcdc6520e62dcc1dbe7ce797f9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59199832"
---
# <a name="transport-of-netnamedpipebinding"></a><span data-ttu-id="6a676-102">\<전송 >의 \<netNamedPipeBinding ></span><span class="sxs-lookup"><span data-stu-id="6a676-102">\<transport> of \<netNamedPipeBinding></span></span>
<span data-ttu-id="6a676-103">명명된 파이프에 대한 전송 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6a676-103">Defines the transport security settings for a named pipe.</span></span>  
  
 <span data-ttu-id="6a676-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="6a676-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="6a676-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="6a676-105">\<bindings></span></span>  
<span data-ttu-id="6a676-106">\<netNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="6a676-106">\<netNamedPipeBinding></span></span>  
<span data-ttu-id="6a676-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="6a676-107">\<binding></span></span>  
<span data-ttu-id="6a676-108">\<security></span><span class="sxs-lookup"><span data-stu-id="6a676-108">\<security></span></span>  
<span data-ttu-id="6a676-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="6a676-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a676-110">구문</span><span class="sxs-lookup"><span data-stu-id="6a676-110">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding>
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6a676-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="6a676-111">Attributes and Elements</span></span>  
 <span data-ttu-id="6a676-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6a676-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6a676-113">특성</span><span class="sxs-lookup"><span data-stu-id="6a676-113">Attributes</span></span>  
  
|<span data-ttu-id="6a676-114">특성</span><span class="sxs-lookup"><span data-stu-id="6a676-114">Attribute</span></span>|<span data-ttu-id="6a676-115">설명</span><span class="sxs-lookup"><span data-stu-id="6a676-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6a676-116">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="6a676-116">protectionLevel</span></span>|<span data-ttu-id="6a676-117">명명된 파이프의 보호 수준을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6a676-117">Defines protection level of the named pipe.</span></span> <span data-ttu-id="6a676-118">메시지에 서명하면 전송 중인 메시지를 제3자가 손상할 위험을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a676-118">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="6a676-119">암호화는 전송 중에 데이터 수준에서 개인 정보를 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="6a676-119">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="6a676-120">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6a676-120">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="6a676-121">-None. 보호되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6a676-121">-   None: No protection.</span></span><br /><span data-ttu-id="6a676-122">기호: 메시지가 서명됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a676-122">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="6a676-123">-   EncryptAndSign: 메시지가 암호화되고 서명됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a676-123">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="6a676-124">기본값은 EncryptAndSign입니다.</span><span class="sxs-lookup"><span data-stu-id="6a676-124">The default value is EncryptAndSign.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6a676-125">자식 요소</span><span class="sxs-lookup"><span data-stu-id="6a676-125">Child Elements</span></span>  
 <span data-ttu-id="6a676-126">없음</span><span class="sxs-lookup"><span data-stu-id="6a676-126">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6a676-127">부모 요소</span><span class="sxs-lookup"><span data-stu-id="6a676-127">Parent Elements</span></span>  
  
|<span data-ttu-id="6a676-128">요소</span><span class="sxs-lookup"><span data-stu-id="6a676-128">Element</span></span>|<span data-ttu-id="6a676-129">설명</span><span class="sxs-lookup"><span data-stu-id="6a676-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6a676-130">\<security></span><span class="sxs-lookup"><span data-stu-id="6a676-130">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netnamedpipebinding.md)|<span data-ttu-id="6a676-131">바인딩에 대한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6a676-131">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6a676-132">참고자료</span><span class="sxs-lookup"><span data-stu-id="6a676-132">See also</span></span>

- <xref:System.ServiceModel.NamedPipeTransportSecurity>
- <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetNamedPipeSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>
- [<span data-ttu-id="6a676-133">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="6a676-133">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="6a676-134">바인딩</span><span class="sxs-lookup"><span data-stu-id="6a676-134">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="6a676-135">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="6a676-135">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="6a676-136">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="6a676-136">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="6a676-137">\<binding></span><span class="sxs-lookup"><span data-stu-id="6a676-137">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
