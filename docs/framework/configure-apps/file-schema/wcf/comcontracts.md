---
description: 다음에 대해 자세히 알아보세요. <comContracts>
title: <comContracts>
ms.date: 03/30/2017
ms.assetid: 42e74148-223d-4888-a8ed-1d928527eb09
ms.openlocfilehash: 263210b4499274fe009a6b1b1e46c1f09dd007ab
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638654"
---
# \<comContracts>

<span data-ttu-id="52b2c-102">`comContracts` 구성 섹션에는 COM+ 통합 서비스 계약의 다양한 속성을 지정할 수 있게 해 주는 요소가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52b2c-102">The `comContracts` configuration section contains elements that allow you to specify various properties of a COM+ integration service contract.</span></span>  
  
## <a name="specifying-namespace-and-contract"></a><span data-ttu-id="52b2c-103">네임스페이스 및 계약 지정</span><span class="sxs-lookup"><span data-stu-id="52b2c-103">Specifying Namespace and Contract</span></span>  

 <span data-ttu-id="52b2c-104">COM + 통합 서비스 계약은 현재 `http://tempuri.org` 네임 스페이스로 제한 되며, 계약 이름은 지원 COM 인터페이스에서 파생 됩니다.</span><span class="sxs-lookup"><span data-stu-id="52b2c-104">COM+ integration service contracts are currently restricted to the `http://tempuri.org` namespace, and contract name is derived from the supporting COM interface.</span></span> <span data-ttu-id="52b2c-105">그러나 구성 파일에서 `comContracts` 섹션을 사용하여 대안을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52b2c-105">You can, however, specify alternatives by using the `comContracts` section in the configuration file.</span></span>  
  
 <span data-ttu-id="52b2c-106">예를 들어 다음 구성을 사용하여 서비스 계약의 네임스페이스 및 계약 이름과 세션 바인딩에 사용법을 적용할 옵션을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52b2c-106">For example, you can use the following configuration to specify the namespace and contract name of the service contract, as well as an option to enforce usage on sessionful bindings.</span></span>  
  
```xml  
<comContracts>
  <comContract contract="{5163B1E7-F0CF-4B6A-9A02-4AB654F34284}"
               namespace="http://tempuri.org/5163B1E7-F0CF-4B6A-9A02-4AB654F34284"
               name="_Broker"
               requireSession="true">
  </comContract>
</comContracts>
```  
  
 <span data-ttu-id="52b2c-107">지정된 네임스페이스와 계약 이름은 서비스가 초기화될 때 생성된 서비스 설명에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="52b2c-107">When the service is initialized, the specified namespaces and contract names are applied to the generated service descriptions.</span></span>  
  
 <span data-ttu-id="52b2c-108">이 섹션이 비어 있으면 서비스 초기화에서는 지원 COM 인터페이스 ID에서 가져온 기본 네임스페이스 및 계약 이름을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="52b2c-108">When this section is empty, the service initialization applies a default namespace and contract name taken from the supporting COM interface ID.</span></span>  
  
 <span data-ttu-id="52b2c-109">또한 요소를 사용 하 여 [\<exposedMethod>](exposedmethod.md) COM + 구성 요소의 인터페이스가 웹 서비스로 노출 될 때 노출 되는 COM + 메서드를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52b2c-109">In addition, you can use the [\<exposedMethod>](exposedmethod.md) element to specify COM+ methods that are exposed when the interface on a COM+ component is exposed as a Web service.</span></span> <span data-ttu-id="52b2c-110">또한를 사용 하 여 [\<persistableTypes>](persistabletypes.md) 통합에 사용 되는 지속 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52b2c-110">You can also use the [\<persistableTypes>](persistabletypes.md) to specify persistable types used in integration.</span></span> <span data-ttu-id="52b2c-111">마지막으로 요소를 사용 하 여 [\<userDefinedType>](userdefinedtype.md) 서비스 계약에 포함 될 UDT (사용자 정의 형식)를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52b2c-111">Finally, you can use the [\<userDefinedType>](userdefinedtype.md) element to include User Defined Types (UDT) that are to be included in the service contract.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52b2c-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="52b2c-112">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComContractElementCollection>
- <xref:System.ServiceModel.Configuration.ComContractElement>
- [\<exposedMethod>](exposedmethod.md)
- [\<persistableTypes>](persistabletypes.md)
- [\<userDefinedType>](userdefinedtype.md)
- [\<comContract>](comcontract.md)
- [<span data-ttu-id="52b2c-113">COM + 응용 프로그램과 통합</span><span class="sxs-lookup"><span data-stu-id="52b2c-113">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="52b2c-114">방법: COM+ 서비스 설정 구성</span><span class="sxs-lookup"><span data-stu-id="52b2c-114">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
