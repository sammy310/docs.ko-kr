---
title: <userDefinedType>
ms.date: 03/30/2017
ms.assetid: 0f70ec06-8249-4f0c-9f49-b4df59985fb8
ms.openlocfilehash: 46beb88cedf051ed1683161b6ed9b37273ed01f1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59182141"
---
# <a name="userdefinedtype"></a><span data-ttu-id="10a30-101">\<userDefinedType></span><span class="sxs-lookup"><span data-stu-id="10a30-101">\<userDefinedType></span></span>
<span data-ttu-id="10a30-102">서비스 계약에 포함될 UDT(사용자 정의 형식)를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="10a30-102">Represents a User Defined Type (UDT) that is to be included in the service contract.</span></span>  
  
 <span data-ttu-id="10a30-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="10a30-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="10a30-104">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="10a30-104">\<comContracts></span></span>  
<span data-ttu-id="10a30-105">\<comContract></span><span class="sxs-lookup"><span data-stu-id="10a30-105">\<comContract></span></span>  
<span data-ttu-id="10a30-106">\<userDefinedTypes></span><span class="sxs-lookup"><span data-stu-id="10a30-106">\<userDefinedTypes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10a30-107">구문</span><span class="sxs-lookup"><span data-stu-id="10a30-107">Syntax</span></span>  
  
```xml  
<comContracts>
  <comContract>
    <userDefinedTypes>
      <userDefinedType name="String"
                       typeLibID="String"
                       typeLibVersion="String"
                       typeDefID="String">
      </userDefinedType>
    </userDefinedTypes>
  </comContract>
</comContracts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="10a30-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="10a30-108">Attributes and Elements</span></span>  
 <span data-ttu-id="10a30-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="10a30-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="10a30-110">특성</span><span class="sxs-lookup"><span data-stu-id="10a30-110">Attributes</span></span>  
  
|<span data-ttu-id="10a30-111">특성</span><span class="sxs-lookup"><span data-stu-id="10a30-111">Attribute</span></span>|<span data-ttu-id="10a30-112">설명</span><span class="sxs-lookup"><span data-stu-id="10a30-112">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="10a30-113">읽기 가능한 형식의 이름을 제공하는 문자열이 포함된 선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="10a30-113">An optional attribute that contains a string that provides the readable type name.</span></span> <span data-ttu-id="10a30-114">이 특성은 런타임에서 사용되지 않지만, 판독기에서 형식을 구별할 때 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="10a30-114">This is not used by the runtime but helps a reader to distinguish the types.</span></span>|  
|`TypeDefID`|<span data-ttu-id="10a30-115">등록된 형식 라이브러리에 있는 특정 UDT 형식을 식별하는 GUID 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="10a30-115">A GUID string that identifies the specific UDT type within the registered type library.</span></span>|  
|`TypeLibID`|<span data-ttu-id="10a30-116">형식을 정의하는 등록된 형식 라이브러리를 식별하는 GUID 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="10a30-116">A GUID string that identifies the registered type library that defines the type.</span></span>|  
|`TypeLibVersion`|<span data-ttu-id="10a30-117">: 형식을 정의하는 형식 라이브러리 버전을 식별하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="10a30-117">A string that identifies the type library version that defines the type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="10a30-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="10a30-118">Child Elements</span></span>  
 <span data-ttu-id="10a30-119">없음</span><span class="sxs-lookup"><span data-stu-id="10a30-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="10a30-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="10a30-120">Parent Elements</span></span>  
  
|<span data-ttu-id="10a30-121">요소</span><span class="sxs-lookup"><span data-stu-id="10a30-121">Element</span></span>|<span data-ttu-id="10a30-122">설명</span><span class="sxs-lookup"><span data-stu-id="10a30-122">Description</span></span>|  
|-------------|-----------------|  
|`userDefinedTypes`|<span data-ttu-id="10a30-123">`userDefinedType` 요소의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="10a30-123">A collection of `userDefinedType` elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="10a30-124">설명</span><span class="sxs-lookup"><span data-stu-id="10a30-124">Remarks</span></span>  
 <span data-ttu-id="10a30-125">COM+ 통합 런타임에서는 형식 라이브러리를 검사하여 서비스를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="10a30-125">The COM+ integration runtime creates services by inspecting the type library.</span></span> <span data-ttu-id="10a30-126">COM+ 구성 요소에 VARIANT를 전달하는 메서드가 포함될 경우 시스템에서 런타임 전에 전달될 실제 형식을 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="10a30-126">When a COM+ component contains methods that pass a VARIANT, the system cannot determine the actual types to be passed prior to runtime.</span></span> <span data-ttu-id="10a30-127">따라서 VARIANT 내에서 UDT(사용자 정의 형식)를 전달하려고 시도하면 알려진 serialization 형식이 아니므로 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="10a30-127">Therefore, when you attempt to pass a User Defined Type (UDT) within a VARIANT, it fails because it is not a known type for serialization.</span></span>  
  
 <span data-ttu-id="10a30-128">이 문제를 방지하기 위해 UDT를 구성 파일에 추가함으로써 적절한 서비스 계약에 알려진 형식으로 포함되게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10a30-128">To circumvent this problem, you can add the UDTs to the configuration file so that they can be included as known types on the appropriate service contract.</span></span> <span data-ttu-id="10a30-129">그러기 위해서는 UDT와 계약, 즉 이를 사용하는 원래 COM 인터페이스를 고유하게 식별해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10a30-129">In order to do so, you have to uniquely identify the UDT and the contract(s), that is, the original COM interface(s) that uses it.</span></span>  
  
 <span data-ttu-id="10a30-130">다음 예제에서는 이러한 목적으로 구성 파일의 <`userDefinedTypes`> 섹션에 특정 UDT 두 개를 추가하는 것을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="10a30-130">The following example demonstrates adding two specific UDTs to the <`userDefinedTypes`> section of the configuration file for this purpose.</span></span>  
  
```xml  
<comContracts>
  <comContract contract="{5163B1E7-F0CF-4B6A-9A02-4AB654F34284}"
               namespace="http://tempuri.org/5163B1E7-F0CF-4B6A-9A02-4AB654F34284"
               name="_Broker"
               requireSession="true">
    <userDefinedTypes>
      <userDefinedType name="CustomerType"
                       typeLibID="{91DC728C-4F1A-45de-A9B6-B538E209CEA6}"
                       typeLibVersion="1.0"
                       typeDefID="{D129765C-F211-434e-825A-9A63198C41F2}">
      </userDefinedType>
      <userDefinedType name="AddressType"
                       typeLibID="{91DC728C-4F1A-45de-A9B6-B538E209CEA6}"
                       typeLibVersion="1.0"
                       typeDefID="{4616AE0D-687A-43B7-BC63-141AE3DFD099}">
      </userDefinedType>
    </userDefinedTypes>
    <exposedMethods>
      <exposedMethod name="BuyStock" />
      <exposedMethod name="SellStock" />
      <exposedMethod name="ExecuteTransaction" />
    </exposedMethods>
  </comContract>
</comContracts>
```  
  
 <span data-ttu-id="10a30-131">서비스가 초기화될 때 통합 런타임에서는 지정된 형식을 찾아 지정된 계약의 알려진 형식 컬렉션에 이를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="10a30-131">When the service is initialized, the integration runtime looks up the specified types and adds them to the known types collection for the specified contracts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10a30-132">참고자료</span><span class="sxs-lookup"><span data-stu-id="10a30-132">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComContractElement.UserDefinedTypes%2A>
- <xref:System.ServiceModel.Configuration.ComUdtElementCollection>
- <xref:System.ServiceModel.Configuration.ComUdtElement>
- [<span data-ttu-id="10a30-133">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="10a30-133">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)
- [<span data-ttu-id="10a30-134">COM+ 애플리케이션과 통합</span><span class="sxs-lookup"><span data-stu-id="10a30-134">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="10a30-135">방법: COM + 서비스 설정 구성</span><span class="sxs-lookup"><span data-stu-id="10a30-135">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
