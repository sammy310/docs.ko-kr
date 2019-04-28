---
title: <compositeDuplex>
ms.date: 03/30/2017
ms.assetid: 725004d1-ce88-4405-a220-78e89844f81f
ms.openlocfilehash: 1e5ecc2b937aa0cdb159a6cbd1222fe6d4af79fb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704182"
---
# <a name="compositeduplex"></a><span data-ttu-id="b0e80-101">\<compositeDuplex></span><span class="sxs-lookup"><span data-stu-id="b0e80-101">\<compositeDuplex></span></span>
<span data-ttu-id="b0e80-102">서비스에서 클라이언트에 메시지를 돌려 보낼 수 있도록 클라이언트가 서비스에 대한 엔드포인트를 공개해야 할 때 사용되는 바인딩 요소를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b0e80-102">Defines the binding element that is used when the client must expose an endpoint for the service to send messages back to the client.</span></span>  
  
 <span data-ttu-id="b0e80-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="b0e80-103">\<system.serviceModel></span></span>  
<span data-ttu-id="b0e80-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="b0e80-104">\<bindings></span></span>  
<span data-ttu-id="b0e80-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="b0e80-105">\<customBinding></span></span>  
<span data-ttu-id="b0e80-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="b0e80-106">\<binding></span></span>  
<span data-ttu-id="b0e80-107">\<compositeDuplex></span><span class="sxs-lookup"><span data-stu-id="b0e80-107">\<compositeDuplex></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0e80-108">구문</span><span class="sxs-lookup"><span data-stu-id="b0e80-108">Syntax</span></span>  
  
```xml  
<compositeDuplex clientBaseAddress="URI" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b0e80-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b0e80-109">Attributes and Elements</span></span>  
 <span data-ttu-id="b0e80-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b0e80-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b0e80-111">특성</span><span class="sxs-lookup"><span data-stu-id="b0e80-111">Attributes</span></span>  
  
|<span data-ttu-id="b0e80-112">특성</span><span class="sxs-lookup"><span data-stu-id="b0e80-112">Attribute</span></span>|<span data-ttu-id="b0e80-113">설명</span><span class="sxs-lookup"><span data-stu-id="b0e80-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b0e80-114">clientBaseAddress</span><span class="sxs-lookup"><span data-stu-id="b0e80-114">clientBaseAddress</span></span>|<span data-ttu-id="b0e80-115">이중 모드에서 백 채널의 주소를 설정하는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="b0e80-115">A URI that sets the address of the back channel in duplex mode.</span></span> <span data-ttu-id="b0e80-116">서비스에서는 이 주소를 사용하여 접속한 후 클라이언트와의 연결을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b0e80-116">The service uses this address to make contact and establish a connection with the client.</span></span><br /><br /> <span data-ttu-id="b0e80-117">하는 경우이 특성은 설정 되지 않으면는 기본 주소 "`full qualified name+default port\TemporaryIndigoAddress\guid`" 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0e80-117">If this attribute is not set, a default address "`full qualified name+default port\TemporaryIndigoAddress\guid`" is generated.</span></span> <span data-ttu-id="b0e80-118">기본값은 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="b0e80-118">The default is `null`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b0e80-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b0e80-119">Child Elements</span></span>  
 <span data-ttu-id="b0e80-120">없음</span><span class="sxs-lookup"><span data-stu-id="b0e80-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b0e80-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b0e80-121">Parent Elements</span></span>  
  
|<span data-ttu-id="b0e80-122">요소</span><span class="sxs-lookup"><span data-stu-id="b0e80-122">Element</span></span>|<span data-ttu-id="b0e80-123">설명</span><span class="sxs-lookup"><span data-stu-id="b0e80-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b0e80-124">\<binding></span><span class="sxs-lookup"><span data-stu-id="b0e80-124">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="b0e80-125">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b0e80-125">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b0e80-126">설명</span><span class="sxs-lookup"><span data-stu-id="b0e80-126">Remarks</span></span>  
 <span data-ttu-id="b0e80-127">이 구성 요소는 HTTP와 같이 원래는 이중 통신을 허용하지 않는 전송에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0e80-127">This configuration element is used with transports that do not allow duplex communications natively, for example, HTTP.</span></span> <span data-ttu-id="b0e80-128">그에 반해 TCP는 기본적으로 이중 통신을 허용하므로, 이 바인딩 요소를 사용하지 않더라도 서비스에서 클라이언트로 회신 메시지를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0e80-128">TCP, by contrast, allows duplex communications natively, and does not require the use of this binding element for the service to send messages back to a client.</span></span>  
  
 <span data-ttu-id="b0e80-129">서비스에서 접속하여 연결을 설정하려면 클라이언트가 주소를 공개해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0e80-129">The client must expose an address for the service to make contact and establish a connection.</span></span> <span data-ttu-id="b0e80-130">이 클라이언트 주소는 `clientBaseAddress` 특성을 사용하여 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b0e80-130">This client address is provided by the `clientBaseAddress` attribute.</span></span> <span data-ttu-id="b0e80-131">WCF(Windows Communication Foundation)에서는 ClientBaseAddress를 사용자가 명시적으로 설정하지 않은 경우 자동으로 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0e80-131">Note that Windows Communication Foundation (WCF) auto-generates a ClientBaseAddress if one is not explicitly set by the user.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b0e80-132">예제</span><span class="sxs-lookup"><span data-stu-id="b0e80-132">Example</span></span>  
  
```xml  
<compositeDuplex clientBaseAddress="http://www.contoso.com" />
```  
  
## <a name="see-also"></a><span data-ttu-id="b0e80-133">참고자료</span><span class="sxs-lookup"><span data-stu-id="b0e80-133">See also</span></span>

- <xref:System.ServiceModel.Configuration.CompositeDuplexElement>
- <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="b0e80-134">바인딩</span><span class="sxs-lookup"><span data-stu-id="b0e80-134">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="b0e80-135">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="b0e80-135">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="b0e80-136">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="b0e80-136">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="b0e80-137">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="b0e80-137">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
