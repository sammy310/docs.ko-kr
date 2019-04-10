---
title: IReferenceIdentity 인터페이스
ms.date: 03/30/2017
api_name:
- IReferenceIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IReferenceIdentity
helpviewer_keywords:
- IReferenceIdentity interface [.NET Framework fusion]
ms.assetid: 9180ac5a-7019-4716-9f83-8a91d157239a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dd46ea26532074c9ea42da4d07a38ed583aad076
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59220164"
---
# <a name="ireferenceidentity-interface"></a><span data-ttu-id="54144-102">IReferenceIdentity 인터페이스</span><span class="sxs-lookup"><span data-stu-id="54144-102">IReferenceIdentity Interface</span></span>
<span data-ttu-id="54144-103">코드 개체의 고유 서명에 대 한 참조를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="54144-103">Represents a reference to the unique signature of a code object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="54144-104">메서드</span><span class="sxs-lookup"><span data-stu-id="54144-104">Methods</span></span>  
  
|<span data-ttu-id="54144-105">메서드</span><span class="sxs-lookup"><span data-stu-id="54144-105">Method</span></span>|<span data-ttu-id="54144-106">설명</span><span class="sxs-lookup"><span data-stu-id="54144-106">Description</span></span>|  
|------------|-----------------|  
|`IReferenceIdentity::Clone`|<span data-ttu-id="54144-107">새 인터페이스 포인터를 가져옵니다 `IReferenceIdentity` 인스턴스는 동일한이 `IReferenceIdentity`, 지정 된 특성 변경을 제외 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54144-107">Gets an interface pointer to a new `IReferenceIdentity` instance that is identical to this `IReferenceIdentity`, except for the specified attribute changes.</span></span>|  
|`IReferenceIdentity::EnumAttributes`|<span data-ttu-id="54144-108">한 인터페이스 포인터를 가져옵니다는 `IEnumIDENTITY_ATTRIBUTE` 이 연관 된 특성을 포함 하는 인스턴스 `IReferenceIdentity`합니다.</span><span class="sxs-lookup"><span data-stu-id="54144-108">Gets an interface pointer to an `IEnumIDENTITY_ATTRIBUTE` instance that contains the attributes associated with this `IReferenceIdentity`.</span></span>|  
|`IReferenceIdentity::GetAttribute`|<span data-ttu-id="54144-109">지정한 이름 가진 지정 된 네임 스페이스에 특성의 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="54144-109">Gets the value of the attribute in the specified namespace, with the specified name.</span></span>|  
|`IReferenceIdentity::SetAttribute`|<span data-ttu-id="54144-110">지정된 된 네임 스페이스와 지정된 된 값으로 지정 된 이름을 가진 특성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="54144-110">Sets the attribute that has the specified namespace and the specified name to the specified value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="54144-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="54144-111">Requirements</span></span>  
 <span data-ttu-id="54144-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="54144-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54144-113">**헤더:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="54144-113">**Header:** Isolation.h</span></span>  
  
 **<span data-ttu-id="54144-114">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="54144-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="54144-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="54144-115">See also</span></span>

- [<span data-ttu-id="54144-116">Fusion 인터페이스</span><span class="sxs-lookup"><span data-stu-id="54144-116">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [<span data-ttu-id="54144-117">IEnumIDENTITY_ATTRIBUTE 인터페이스</span><span class="sxs-lookup"><span data-stu-id="54144-117">IEnumIDENTITY_ATTRIBUTE Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md)
