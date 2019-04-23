---
title: IEnumReferenceIdentity 인터페이스
ms.date: 03/30/2017
api_name:
- IEnumReferenceIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IEnumReferenceIdentity
helpviewer_keywords:
- IEnumReferenceIdentity interface [.NET Framework fusion]
ms.assetid: a17b3155-7216-4e16-8c9f-abce21f549e7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 766b17bae0c58d9872ff9c118f330ebc3220257e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59123489"
---
# <a name="ienumreferenceidentity-interface"></a><span data-ttu-id="bfaf3-102">IEnumReferenceIdentity 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bfaf3-102">IEnumReferenceIdentity Interface</span></span>
<span data-ttu-id="bfaf3-103">컬렉션의 열거자 역할을 `IReferenceIdentity` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="bfaf3-103">Serves as an enumerator for a collection of `IReferenceIdentity` objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bfaf3-104">메서드</span><span class="sxs-lookup"><span data-stu-id="bfaf3-104">Methods</span></span>  
  
|<span data-ttu-id="bfaf3-105">메서드</span><span class="sxs-lookup"><span data-stu-id="bfaf3-105">Method</span></span>|<span data-ttu-id="bfaf3-106">설명</span><span class="sxs-lookup"><span data-stu-id="bfaf3-106">Description</span></span>|  
|------------|-----------------|  
|`IEnumReferenceIdentity::Clone`|<span data-ttu-id="bfaf3-107">새 인터페이스 포인터를 가져옵니다 `IEnumReferenceIdentity` 이 동일한 멤버를 포함 하는 `IEnumReferenceIdentity`합니다.</span><span class="sxs-lookup"><span data-stu-id="bfaf3-107">Gets an interface pointer to a new `IEnumReferenceIdentity` that contains the same members as this `IEnumReferenceIdentity`.</span></span>|  
|`IEnumReferenceIdentity::Next`|<span data-ttu-id="bfaf3-108">지정 된 수를 가져옵니다 `IReferenceIdentity` 개체를 현재 위치에서 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfaf3-108">Gets the specified number of `IReferenceIdentity` objects, starting at the current position.</span></span>|  
|`IEnumReferenceIdentity::Reset`|<span data-ttu-id="bfaf3-109">이 부분에 명령 포인터를 이동 `IEnumReferenceIdentity`합니다.</span><span class="sxs-lookup"><span data-stu-id="bfaf3-109">Moves the instruction pointer to the beginning of this `IEnumReferenceIdentity`.</span></span>|  
|`IEnumReferenceIdentity::Skip`|<span data-ttu-id="bfaf3-110">요소를 현재 위치부터 지정한 수 만큼 앞으로 명령 포인터를 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfaf3-110">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bfaf3-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bfaf3-111">Requirements</span></span>  
 <span data-ttu-id="bfaf3-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="bfaf3-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bfaf3-113">**헤더:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="bfaf3-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="bfaf3-114">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bfaf3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfaf3-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="bfaf3-115">See also</span></span>

- [<span data-ttu-id="bfaf3-116">Fusion 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bfaf3-116">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [<span data-ttu-id="bfaf3-117">IReferenceIdentity 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bfaf3-117">IReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)
