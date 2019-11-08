---
title: <netNamedPipeBinding>의 <transport>
ms.date: 03/30/2017
ms.assetid: d9eff52d-4bde-4586-b56a-b0ec24611f8d
ms.openlocfilehash: d40178e59b89c2912123e1927e9e960f6d880871
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73735966"
---
# <a name="transport-of-netnamedpipebinding"></a><span data-ttu-id="8a0d9-102">\<전송 > \<netNamedPipeBinding ></span><span class="sxs-lookup"><span data-stu-id="8a0d9-102">\<transport> of \<netNamedPipeBinding></span></span>
<span data-ttu-id="8a0d9-103">명명된 파이프에 대한 전송 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="8a0d9-103">Defines the transport security settings for a named pipe.</span></span>  
  
<span data-ttu-id="8a0d9-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8a0d9-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8a0d9-105">[ **\<system serviceModel >** ](system-servicemodel.md) &nbsp; &nbsp; </span><span class="sxs-lookup"><span data-stu-id="8a0d9-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="8a0d9-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**바인딩**](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="8a0d9-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="8a0d9-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netNamedPipeBinding >** ](netnamedpipebinding.md)</span><span class="sxs-lookup"><span data-stu-id="8a0d9-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netNamedPipeBinding>**](netnamedpipebinding.md)</span></span>\
<span data-ttu-id="8a0d9-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<바인딩 >** </span><span class="sxs-lookup"><span data-stu-id="8a0d9-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="8a0d9-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**security >** ](security-of-netnamedpipebinding.md)</span><span class="sxs-lookup"><span data-stu-id="8a0d9-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netnamedpipebinding.md)</span></span>\
<span data-ttu-id="8a0d9-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**전송 >**</span><span class="sxs-lookup"><span data-stu-id="8a0d9-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a0d9-111">구문</span><span class="sxs-lookup"><span data-stu-id="8a0d9-111">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding>
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8a0d9-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8a0d9-112">Attributes and Elements</span></span>  
 <span data-ttu-id="8a0d9-113">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8a0d9-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8a0d9-114">특성</span><span class="sxs-lookup"><span data-stu-id="8a0d9-114">Attributes</span></span>  
  
|<span data-ttu-id="8a0d9-115">특성</span><span class="sxs-lookup"><span data-stu-id="8a0d9-115">Attribute</span></span>|<span data-ttu-id="8a0d9-116">설명</span><span class="sxs-lookup"><span data-stu-id="8a0d9-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8a0d9-117">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="8a0d9-117">protectionLevel</span></span>|<span data-ttu-id="8a0d9-118">명명된 파이프의 보호 수준을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="8a0d9-118">Defines protection level of the named pipe.</span></span> <span data-ttu-id="8a0d9-119">메시지에 서명 하면 전송 중인 메시지를 제 3 자가 변조 하는 위험을 완화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a0d9-119">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="8a0d9-120">암호화는 전송 중에 데이터 수준의 개인 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a0d9-120">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="8a0d9-121">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8a0d9-121">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="8a0d9-122">-없음: 보호 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8a0d9-122">-   None: No protection.</span></span><br /><span data-ttu-id="8a0d9-123">-서명: 메시지가 서명 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a0d9-123">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="8a0d9-124">-EncryptAndSign: 메시지가 암호화 되 고 서명 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a0d9-124">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="8a0d9-125">기본값은 EncryptAndSign입니다.</span><span class="sxs-lookup"><span data-stu-id="8a0d9-125">The default value is EncryptAndSign.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8a0d9-126">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8a0d9-126">Child Elements</span></span>  
 <span data-ttu-id="8a0d9-127">없음</span><span class="sxs-lookup"><span data-stu-id="8a0d9-127">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8a0d9-128">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8a0d9-128">Parent Elements</span></span>  
  
|<span data-ttu-id="8a0d9-129">요소</span><span class="sxs-lookup"><span data-stu-id="8a0d9-129">Element</span></span>|<span data-ttu-id="8a0d9-130">설명</span><span class="sxs-lookup"><span data-stu-id="8a0d9-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8a0d9-131">\<security ></span><span class="sxs-lookup"><span data-stu-id="8a0d9-131">\<security></span></span>](security-of-netnamedpipebinding.md)|<span data-ttu-id="8a0d9-132">바인딩에 대한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="8a0d9-132">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8a0d9-133">참조</span><span class="sxs-lookup"><span data-stu-id="8a0d9-133">See also</span></span>

- <xref:System.ServiceModel.NamedPipeTransportSecurity>
- <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetNamedPipeSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>
- [<span data-ttu-id="8a0d9-134">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="8a0d9-134">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="8a0d9-135">바인딩</span><span class="sxs-lookup"><span data-stu-id="8a0d9-135">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="8a0d9-136">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="8a0d9-136">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="8a0d9-137">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="8a0d9-137">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="8a0d9-138">\<binding ></span><span class="sxs-lookup"><span data-stu-id="8a0d9-138">\<binding></span></span>](bindings.md)
