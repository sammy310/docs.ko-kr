---
title: <compositeDuplex>
ms.date: 03/30/2017
ms.assetid: 725004d1-ce88-4405-a220-78e89844f81f
ms.openlocfilehash: a5209efddd489f8cb04b3266e6ba0bb033eeae6c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176021"
---
# \<compositeDuplex>

<span data-ttu-id="b8fcf-101">서비스에서 클라이언트에 메시지를 돌려 보낼 수 있도록 클라이언트가 서비스에 대한 엔드포인트를 공개해야 할 때 사용되는 바인딩 요소를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b8fcf-101">Defines the binding element that is used when the client must expose an endpoint for the service to send messages back to the client.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<compositeDuplex>**  
  
## <a name="syntax"></a><span data-ttu-id="b8fcf-102">구문</span><span class="sxs-lookup"><span data-stu-id="b8fcf-102">Syntax</span></span>  
  
```xml  
<compositeDuplex clientBaseAddress="URI" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b8fcf-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b8fcf-103">Attributes and Elements</span></span>  

 <span data-ttu-id="b8fcf-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b8fcf-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b8fcf-105">특성</span><span class="sxs-lookup"><span data-stu-id="b8fcf-105">Attributes</span></span>  
  
|<span data-ttu-id="b8fcf-106">attribute</span><span class="sxs-lookup"><span data-stu-id="b8fcf-106">Attribute</span></span>|<span data-ttu-id="b8fcf-107">설명</span><span class="sxs-lookup"><span data-stu-id="b8fcf-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b8fcf-108">clientBaseAddress</span><span class="sxs-lookup"><span data-stu-id="b8fcf-108">clientBaseAddress</span></span>|<span data-ttu-id="b8fcf-109">이중 모드에서 백 채널의 주소를 설정하는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="b8fcf-109">A URI that sets the address of the back channel in duplex mode.</span></span> <span data-ttu-id="b8fcf-110">서비스에서는 이 주소를 사용하여 접속한 후 클라이언트와의 연결을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b8fcf-110">The service uses this address to make contact and establish a connection with the client.</span></span><br /><br /> <span data-ttu-id="b8fcf-111">이 특성이 설정 되지 않으면 기본 주소 " `full qualified name+default port\TemporaryIndigoAddress\guid` "가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8fcf-111">If this attribute is not set, a default address "`full qualified name+default port\TemporaryIndigoAddress\guid`" is generated.</span></span> <span data-ttu-id="b8fcf-112">기본값은 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="b8fcf-112">The default is `null`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b8fcf-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b8fcf-113">Child Elements</span></span>  

 <span data-ttu-id="b8fcf-114">없음</span><span class="sxs-lookup"><span data-stu-id="b8fcf-114">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b8fcf-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b8fcf-115">Parent Elements</span></span>  
  
|<span data-ttu-id="b8fcf-116">요소</span><span class="sxs-lookup"><span data-stu-id="b8fcf-116">Element</span></span>|<span data-ttu-id="b8fcf-117">설명</span><span class="sxs-lookup"><span data-stu-id="b8fcf-117">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="b8fcf-118">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b8fcf-118">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b8fcf-119">설명</span><span class="sxs-lookup"><span data-stu-id="b8fcf-119">Remarks</span></span>  

 <span data-ttu-id="b8fcf-120">이 구성 요소는 HTTP와 같이 원래는 이중 통신을 허용하지 않는 전송에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8fcf-120">This configuration element is used with transports that do not allow duplex communications natively, for example, HTTP.</span></span> <span data-ttu-id="b8fcf-121">그에 반해 TCP는 기본적으로 이중 통신을 허용하므로, 이 바인딩 요소를 사용하지 않더라도 서비스에서 클라이언트로 회신 메시지를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8fcf-121">TCP, by contrast, allows duplex communications natively, and does not require the use of this binding element for the service to send messages back to a client.</span></span>  
  
 <span data-ttu-id="b8fcf-122">서비스에서 접속하여 연결을 설정하려면 클라이언트가 주소를 공개해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8fcf-122">The client must expose an address for the service to make contact and establish a connection.</span></span> <span data-ttu-id="b8fcf-123">이 클라이언트 주소는 `clientBaseAddress` 특성을 사용하여 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b8fcf-123">This client address is provided by the `clientBaseAddress` attribute.</span></span> <span data-ttu-id="b8fcf-124">WCF(Windows Communication Foundation)에서는 ClientBaseAddress를 사용자가 명시적으로 설정하지 않은 경우 자동으로 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8fcf-124">Note that Windows Communication Foundation (WCF) auto-generates a ClientBaseAddress if one is not explicitly set by the user.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8fcf-125">예제</span><span class="sxs-lookup"><span data-stu-id="b8fcf-125">Example</span></span>  
  
```xml  
<compositeDuplex clientBaseAddress="http://www.contoso.com" />
```  
  
## <a name="see-also"></a><span data-ttu-id="b8fcf-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b8fcf-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.CompositeDuplexElement>
- <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="b8fcf-127">바인딩하</span><span class="sxs-lookup"><span data-stu-id="b8fcf-127">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="b8fcf-128">바인딩 확장명</span><span class="sxs-lookup"><span data-stu-id="b8fcf-128">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="b8fcf-129">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="b8fcf-129">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
