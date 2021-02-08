---
description: '다음에 대 한 자세한 정보:: <transport><netNamedPipeBinding>'
title: <netNamedPipeBinding>의 <transport>
ms.date: 03/30/2017
ms.assetid: d9eff52d-4bde-4586-b56a-b0ec24611f8d
ms.openlocfilehash: a54c429bcac192ddc46df7232c33ab98bd1a4c58
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99773487"
---
# <a name="transport-of-netnamedpipebinding"></a><span data-ttu-id="41cbb-103">\<netNamedPipeBinding>의 \<transport></span><span class="sxs-lookup"><span data-stu-id="41cbb-103">\<transport> of \<netNamedPipeBinding></span></span>

<span data-ttu-id="41cbb-104">명명된 파이프에 대한 전송 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="41cbb-104">Defines the transport security settings for a named pipe.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netNamedPipeBinding>**](netnamedpipebinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netnamedpipebinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="41cbb-105">구문</span><span class="sxs-lookup"><span data-stu-id="41cbb-105">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding>
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="41cbb-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="41cbb-106">Attributes and Elements</span></span>  

 <span data-ttu-id="41cbb-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="41cbb-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="41cbb-108">특성</span><span class="sxs-lookup"><span data-stu-id="41cbb-108">Attributes</span></span>  
  
|<span data-ttu-id="41cbb-109">attribute</span><span class="sxs-lookup"><span data-stu-id="41cbb-109">Attribute</span></span>|<span data-ttu-id="41cbb-110">설명</span><span class="sxs-lookup"><span data-stu-id="41cbb-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="41cbb-111">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="41cbb-111">protectionLevel</span></span>|<span data-ttu-id="41cbb-112">명명된 파이프의 보호 수준을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="41cbb-112">Defines protection level of the named pipe.</span></span> <span data-ttu-id="41cbb-113">메시지에 서명하면 전송 중인 메시지를 제3자가 손상할 위험을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41cbb-113">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="41cbb-114">암호화는 전송 중에 데이터 수준에서 개인 정보를 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="41cbb-114">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="41cbb-115">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="41cbb-115">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="41cbb-116">-없음: 보호 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="41cbb-116">-   None: No protection.</span></span><br /><span data-ttu-id="41cbb-117">-서명: 메시지가 서명 됩니다.</span><span class="sxs-lookup"><span data-stu-id="41cbb-117">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="41cbb-118">-EncryptAndSign: 메시지가 암호화 되 고 서명 됩니다.</span><span class="sxs-lookup"><span data-stu-id="41cbb-118">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="41cbb-119">기본값은 EncryptAndSign입니다.</span><span class="sxs-lookup"><span data-stu-id="41cbb-119">The default value is EncryptAndSign.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="41cbb-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="41cbb-120">Child Elements</span></span>  

 <span data-ttu-id="41cbb-121">없음</span><span class="sxs-lookup"><span data-stu-id="41cbb-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="41cbb-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="41cbb-122">Parent Elements</span></span>  
  
|<span data-ttu-id="41cbb-123">요소</span><span class="sxs-lookup"><span data-stu-id="41cbb-123">Element</span></span>|<span data-ttu-id="41cbb-124">설명</span><span class="sxs-lookup"><span data-stu-id="41cbb-124">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-netnamedpipebinding.md)|<span data-ttu-id="41cbb-125">바인딩에 대한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="41cbb-125">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="41cbb-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="41cbb-126">See also</span></span>

- <xref:System.ServiceModel.NamedPipeTransportSecurity>
- <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetNamedPipeSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>
- [<span data-ttu-id="41cbb-127">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="41cbb-127">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="41cbb-128">바인딩</span><span class="sxs-lookup"><span data-stu-id="41cbb-128">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="41cbb-129">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="41cbb-129">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="41cbb-130">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="41cbb-130">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
