---
title: <netNamedPipeBinding>의 <transport>
ms.date: 03/30/2017
ms.assetid: d9eff52d-4bde-4586-b56a-b0ec24611f8d
ms.openlocfilehash: 81c52405478d4c1ab5c65aab73f7feff61b879d0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91178023"
---
# <a name="transport-of-netnamedpipebinding"></a><span data-ttu-id="02c92-102">\<netNamedPipeBinding>의 \<transport></span><span class="sxs-lookup"><span data-stu-id="02c92-102">\<transport> of \<netNamedPipeBinding></span></span>

<span data-ttu-id="02c92-103">명명된 파이프에 대한 전송 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="02c92-103">Defines the transport security settings for a named pipe.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netNamedPipeBinding>**](netnamedpipebinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netnamedpipebinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="02c92-104">구문</span><span class="sxs-lookup"><span data-stu-id="02c92-104">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding>
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="02c92-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="02c92-105">Attributes and Elements</span></span>  

 <span data-ttu-id="02c92-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="02c92-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="02c92-107">특성</span><span class="sxs-lookup"><span data-stu-id="02c92-107">Attributes</span></span>  
  
|<span data-ttu-id="02c92-108">attribute</span><span class="sxs-lookup"><span data-stu-id="02c92-108">Attribute</span></span>|<span data-ttu-id="02c92-109">설명</span><span class="sxs-lookup"><span data-stu-id="02c92-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="02c92-110">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="02c92-110">protectionLevel</span></span>|<span data-ttu-id="02c92-111">명명된 파이프의 보호 수준을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="02c92-111">Defines protection level of the named pipe.</span></span> <span data-ttu-id="02c92-112">메시지에 서명하면 전송 중인 메시지를 제3자가 손상할 위험을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02c92-112">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="02c92-113">암호화는 전송 중에 데이터 수준에서 개인 정보를 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="02c92-113">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="02c92-114">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="02c92-114">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="02c92-115">-없음: 보호 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="02c92-115">-   None: No protection.</span></span><br /><span data-ttu-id="02c92-116">-서명: 메시지가 서명 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02c92-116">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="02c92-117">-EncryptAndSign: 메시지가 암호화 되 고 서명 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02c92-117">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="02c92-118">기본값은 EncryptAndSign입니다.</span><span class="sxs-lookup"><span data-stu-id="02c92-118">The default value is EncryptAndSign.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="02c92-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="02c92-119">Child Elements</span></span>  

 <span data-ttu-id="02c92-120">없음</span><span class="sxs-lookup"><span data-stu-id="02c92-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="02c92-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="02c92-121">Parent Elements</span></span>  
  
|<span data-ttu-id="02c92-122">요소</span><span class="sxs-lookup"><span data-stu-id="02c92-122">Element</span></span>|<span data-ttu-id="02c92-123">설명</span><span class="sxs-lookup"><span data-stu-id="02c92-123">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-netnamedpipebinding.md)|<span data-ttu-id="02c92-124">바인딩에 대한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="02c92-124">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="02c92-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="02c92-125">See also</span></span>

- <xref:System.ServiceModel.NamedPipeTransportSecurity>
- <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetNamedPipeSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>
- [<span data-ttu-id="02c92-126">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="02c92-126">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="02c92-127">바인딩하</span><span class="sxs-lookup"><span data-stu-id="02c92-127">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="02c92-128">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="02c92-128">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="02c92-129">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="02c92-129">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
