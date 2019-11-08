---
title: <compositeDuplex>
ms.date: 03/30/2017
ms.assetid: 725004d1-ce88-4405-a220-78e89844f81f
ms.openlocfilehash: c3bae4dfee36e9de62c27bbccecd9a31a5b7d459
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73736782"
---
# <a name="compositeduplex"></a><span data-ttu-id="c84e5-101">\<compositeDuplex ></span><span class="sxs-lookup"><span data-stu-id="c84e5-101">\<compositeDuplex></span></span>
<span data-ttu-id="c84e5-102">서비스에서 클라이언트에 메시지를 돌려 보낼 수 있도록 클라이언트가 서비스에 대한 엔드포인트를 공개해야 할 때 사용되는 바인딩 요소를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c84e5-102">Defines the binding element that is used when the client must expose an endpoint for the service to send messages back to the client.</span></span>  
  
<span data-ttu-id="c84e5-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c84e5-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c84e5-104">[ **\<system serviceModel >** ](system-servicemodel.md) &nbsp; &nbsp; </span><span class="sxs-lookup"><span data-stu-id="c84e5-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="c84e5-105">&nbsp;&nbsp;&nbsp;&nbsp;\<[**바인딩**](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="c84e5-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="c84e5-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="c84e5-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="c84e5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<바인딩 >** </span><span class="sxs-lookup"><span data-stu-id="c84e5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="c84e5-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**compositeDuplex >**</span><span class="sxs-lookup"><span data-stu-id="c84e5-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<compositeDuplex>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c84e5-109">구문</span><span class="sxs-lookup"><span data-stu-id="c84e5-109">Syntax</span></span>  
  
```xml  
<compositeDuplex clientBaseAddress="URI" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c84e5-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c84e5-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c84e5-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c84e5-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c84e5-112">특성</span><span class="sxs-lookup"><span data-stu-id="c84e5-112">Attributes</span></span>  
  
|<span data-ttu-id="c84e5-113">특성</span><span class="sxs-lookup"><span data-stu-id="c84e5-113">Attribute</span></span>|<span data-ttu-id="c84e5-114">설명</span><span class="sxs-lookup"><span data-stu-id="c84e5-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c84e5-115">clientBaseAddress</span><span class="sxs-lookup"><span data-stu-id="c84e5-115">clientBaseAddress</span></span>|<span data-ttu-id="c84e5-116">이중 모드에서 백 채널의 주소를 설정하는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="c84e5-116">A URI that sets the address of the back channel in duplex mode.</span></span> <span data-ttu-id="c84e5-117">서비스는이 주소를 사용 하 여 연락처를 만들고 클라이언트와의 연결을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c84e5-117">The service uses this address to make contact and establish a connection with the client.</span></span><br /><br /> <span data-ttu-id="c84e5-118">이 특성이 설정 되지 않으면 기본 주소 "`full qualified name+default port\TemporaryIndigoAddress\guid`"이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c84e5-118">If this attribute is not set, a default address "`full qualified name+default port\TemporaryIndigoAddress\guid`" is generated.</span></span> <span data-ttu-id="c84e5-119">기본값은 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="c84e5-119">The default is `null`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c84e5-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c84e5-120">Child Elements</span></span>  
 <span data-ttu-id="c84e5-121">없음</span><span class="sxs-lookup"><span data-stu-id="c84e5-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c84e5-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c84e5-122">Parent Elements</span></span>  
  
|<span data-ttu-id="c84e5-123">요소</span><span class="sxs-lookup"><span data-stu-id="c84e5-123">Element</span></span>|<span data-ttu-id="c84e5-124">설명</span><span class="sxs-lookup"><span data-stu-id="c84e5-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c84e5-125">\<binding ></span><span class="sxs-lookup"><span data-stu-id="c84e5-125">\<binding></span></span>](bindings.md)|<span data-ttu-id="c84e5-126">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c84e5-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c84e5-127">주의</span><span class="sxs-lookup"><span data-stu-id="c84e5-127">Remarks</span></span>  
 <span data-ttu-id="c84e5-128">이 구성 요소는 HTTP와 같이 원래는 이중 통신을 허용하지 않는 전송에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c84e5-128">This configuration element is used with transports that do not allow duplex communications natively, for example, HTTP.</span></span> <span data-ttu-id="c84e5-129">이와 대조적으로 TCP는 기본적으로 이중 통신을 허용 하며, 서비스에 대해이 바인딩 요소를 사용 하 여 메시지를 클라이언트로 다시 보낼 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c84e5-129">TCP, by contrast, allows duplex communications natively, and does not require the use of this binding element for the service to send messages back to a client.</span></span>  
  
 <span data-ttu-id="c84e5-130">클라이언트는 연락처를 만들고 연결을 설정 하기 위해 서비스에 대 한 주소를 노출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c84e5-130">The client must expose an address for the service to make contact and establish a connection.</span></span> <span data-ttu-id="c84e5-131">이 클라이언트 주소는 `clientBaseAddress` 특성을 사용하여 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c84e5-131">This client address is provided by the `clientBaseAddress` attribute.</span></span> <span data-ttu-id="c84e5-132">WCF(Windows Communication Foundation)에서는 ClientBaseAddress를 사용자가 명시적으로 설정하지 않은 경우 자동으로 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c84e5-132">Note that Windows Communication Foundation (WCF) auto-generates a ClientBaseAddress if one is not explicitly set by the user.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c84e5-133">예제</span><span class="sxs-lookup"><span data-stu-id="c84e5-133">Example</span></span>  
  
```xml  
<compositeDuplex clientBaseAddress="http://www.contoso.com" />
```  
  
## <a name="see-also"></a><span data-ttu-id="c84e5-134">참조</span><span class="sxs-lookup"><span data-stu-id="c84e5-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.CompositeDuplexElement>
- <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="c84e5-135">바인딩</span><span class="sxs-lookup"><span data-stu-id="c84e5-135">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="c84e5-136">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="c84e5-136">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="c84e5-137">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="c84e5-137">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="c84e5-138">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="c84e5-138">\<customBinding></span></span>](custombinding.md)
