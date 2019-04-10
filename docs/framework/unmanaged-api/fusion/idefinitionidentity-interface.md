---
title: IDefinitionIdentity 인터페이스
ms.date: 03/30/2017
api_name:
- IDefinitionIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDefinitionIdentity
helpviewer_keywords:
- IDefinitionIdentity interface [.NET Framework fusion]
ms.assetid: ce5ba888-5fbe-4efd-91cf-f0ff94d8428b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4ff23330f307c10eac134048de39a6e19a67c75b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59192669"
---
# <a name="idefinitionidentity-interface"></a><span data-ttu-id="55aba-102">IDefinitionIdentity 인터페이스</span><span class="sxs-lookup"><span data-stu-id="55aba-102">IDefinitionIdentity Interface</span></span>
<span data-ttu-id="55aba-103">현재 범위에서 응용 프로그램을 정의 하는 코드의 고유한 시그니처를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="55aba-103">Represents the unique signature of the code that defines the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="55aba-104">메서드</span><span class="sxs-lookup"><span data-stu-id="55aba-104">Methods</span></span>  
  
|<span data-ttu-id="55aba-105">메서드</span><span class="sxs-lookup"><span data-stu-id="55aba-105">Method</span></span>|<span data-ttu-id="55aba-106">설명</span><span class="sxs-lookup"><span data-stu-id="55aba-106">Description</span></span>|  
|------------|-----------------|  
|`IDefinitionIdentity::Clone`|<span data-ttu-id="55aba-107">새 인터페이스 포인터를 가져옵니다 `IDefinitionIdentity` 이 동일한 개체 `IDefinitionIdentity`, 지정 된 특성 변경을 제외 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55aba-107">Gets an interface pointer to a new `IDefinitionIdentity` object that is identical to this `IDefinitionIdentity`, except for the specified attribute changes.</span></span>|  
|`IDefinitionIdentity::EnumAttributes`|<span data-ttu-id="55aba-108">한 인터페이스 포인터를 가져옵니다는 [IEnumIDENTITY_ATTRIBUTE](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md) 개체와 연결 된 특성이 포함 된 `IDefinitionIdentity`합니다.</span><span class="sxs-lookup"><span data-stu-id="55aba-108">Gets an interface pointer to an [IEnumIDENTITY_ATTRIBUTE](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md) object that contains the attributes associated with this `IDefinitionIdentity`.</span></span>|  
|`IDefinitionIdentity::GetAttribute`|<span data-ttu-id="55aba-109">지정된 된 네임 스페이스에서 지정한 이름 가진 특성의 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="55aba-109">Gets the value of the attribute with the specified name in the specified namespace.</span></span>|  
|`IDefinitionIdentity::SetAttribute`|<span data-ttu-id="55aba-110">지정된 된 값으로 지정된 된 네임 스페이스에서 지정 된 이름이 있는 특성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="55aba-110">Sets the attribute that has the specified name in the specified namespace to the specified value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="55aba-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="55aba-111">Requirements</span></span>  
 <span data-ttu-id="55aba-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="55aba-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55aba-113">**헤더:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="55aba-113">**Header:** Isolation.h</span></span>  
  
 **<span data-ttu-id="55aba-114">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="55aba-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="55aba-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="55aba-115">See also</span></span>

- [<span data-ttu-id="55aba-116">Fusion 인터페이스</span><span class="sxs-lookup"><span data-stu-id="55aba-116">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
