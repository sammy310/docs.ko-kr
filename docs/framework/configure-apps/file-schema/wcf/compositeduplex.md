---
title: <compositeDuplex>
ms.date: 03/30/2017
ms.assetid: 725004d1-ce88-4405-a220-78e89844f81f
ms.openlocfilehash: a73085320eaf248887422316e1b7787b8654d71d
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400484"
---
# <a name="compositeduplex"></a><span data-ttu-id="55689-101">\<compositeDuplex></span><span class="sxs-lookup"><span data-stu-id="55689-101">\<compositeDuplex></span></span>
<span data-ttu-id="55689-102">서비스에서 클라이언트에 메시지를 돌려 보낼 수 있도록 클라이언트가 서비스에 대한 엔드포인트를 공개해야 할 때 사용되는 바인딩 요소를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="55689-102">Defines the binding element that is used when the client must expose an endpoint for the service to send messages back to the client.</span></span>  
  
<span data-ttu-id="55689-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="55689-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="55689-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="55689-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="55689-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<바인딩 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="55689-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="55689-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="55689-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="55689-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<바인딩 >** </span><span class="sxs-lookup"><span data-stu-id="55689-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="55689-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<compositeDuplex >**</span><span class="sxs-lookup"><span data-stu-id="55689-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<compositeDuplex>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55689-109">구문</span><span class="sxs-lookup"><span data-stu-id="55689-109">Syntax</span></span>  
  
```xml  
<compositeDuplex clientBaseAddress="URI" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="55689-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="55689-110">Attributes and Elements</span></span>  
 <span data-ttu-id="55689-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="55689-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="55689-112">특성</span><span class="sxs-lookup"><span data-stu-id="55689-112">Attributes</span></span>  
  
|<span data-ttu-id="55689-113">특성</span><span class="sxs-lookup"><span data-stu-id="55689-113">Attribute</span></span>|<span data-ttu-id="55689-114">Description</span><span class="sxs-lookup"><span data-stu-id="55689-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="55689-115">clientBaseAddress</span><span class="sxs-lookup"><span data-stu-id="55689-115">clientBaseAddress</span></span>|<span data-ttu-id="55689-116">이중 모드에서 백 채널의 주소를 설정하는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="55689-116">A URI that sets the address of the back channel in duplex mode.</span></span> <span data-ttu-id="55689-117">서비스에서는 이 주소를 사용하여 접속한 후 클라이언트와의 연결을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="55689-117">The service uses this address to make contact and establish a connection with the client.</span></span><br /><br /> <span data-ttu-id="55689-118">이 특성이 설정 되지 않으면 기본 주소 "`full qualified name+default port\TemporaryIndigoAddress\guid`"가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55689-118">If this attribute is not set, a default address "`full qualified name+default port\TemporaryIndigoAddress\guid`" is generated.</span></span> <span data-ttu-id="55689-119">기본값은 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="55689-119">The default is `null`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="55689-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="55689-120">Child Elements</span></span>  
 <span data-ttu-id="55689-121">없음</span><span class="sxs-lookup"><span data-stu-id="55689-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="55689-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="55689-122">Parent Elements</span></span>  
  
|<span data-ttu-id="55689-123">요소</span><span class="sxs-lookup"><span data-stu-id="55689-123">Element</span></span>|<span data-ttu-id="55689-124">설명</span><span class="sxs-lookup"><span data-stu-id="55689-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="55689-125">\<binding></span><span class="sxs-lookup"><span data-stu-id="55689-125">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="55689-126">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="55689-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="55689-127">설명</span><span class="sxs-lookup"><span data-stu-id="55689-127">Remarks</span></span>  
 <span data-ttu-id="55689-128">이 구성 요소는 HTTP와 같이 원래는 이중 통신을 허용하지 않는 전송에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="55689-128">This configuration element is used with transports that do not allow duplex communications natively, for example, HTTP.</span></span> <span data-ttu-id="55689-129">그에 반해 TCP는 기본적으로 이중 통신을 허용하므로, 이 바인딩 요소를 사용하지 않더라도 서비스에서 클라이언트로 회신 메시지를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55689-129">TCP, by contrast, allows duplex communications natively, and does not require the use of this binding element for the service to send messages back to a client.</span></span>  
  
 <span data-ttu-id="55689-130">서비스에서 접속하여 연결을 설정하려면 클라이언트가 주소를 공개해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55689-130">The client must expose an address for the service to make contact and establish a connection.</span></span> <span data-ttu-id="55689-131">이 클라이언트 주소는 `clientBaseAddress` 특성을 사용하여 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="55689-131">This client address is provided by the `clientBaseAddress` attribute.</span></span> <span data-ttu-id="55689-132">WCF(Windows Communication Foundation)에서는 ClientBaseAddress를 사용자가 명시적으로 설정하지 않은 경우 자동으로 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="55689-132">Note that Windows Communication Foundation (WCF) auto-generates a ClientBaseAddress if one is not explicitly set by the user.</span></span>  
  
## <a name="example"></a><span data-ttu-id="55689-133">예제</span><span class="sxs-lookup"><span data-stu-id="55689-133">Example</span></span>  
  
```xml  
<compositeDuplex clientBaseAddress="http://www.contoso.com" />
```  
  
## <a name="see-also"></a><span data-ttu-id="55689-134">참고자료</span><span class="sxs-lookup"><span data-stu-id="55689-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.CompositeDuplexElement>
- <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="55689-135">바인딩</span><span class="sxs-lookup"><span data-stu-id="55689-135">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="55689-136">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="55689-136">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="55689-137">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="55689-137">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="55689-138">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="55689-138">\<customBinding></span></span>](custombinding.md)
