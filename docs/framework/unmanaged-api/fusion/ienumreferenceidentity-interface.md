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
ms.openlocfilehash: 4c5d4bc1fa82f7623168050f4ee36f0ea3cd171e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796435"
---
# <a name="ienumreferenceidentity-interface"></a><span data-ttu-id="dfbd8-102">IEnumReferenceIdentity 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dfbd8-102">IEnumReferenceIdentity Interface</span></span>
<span data-ttu-id="dfbd8-103">개체의 `IReferenceIdentity` 컬렉션에 대 한 열거자 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfbd8-103">Serves as an enumerator for a collection of `IReferenceIdentity` objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dfbd8-104">메서드</span><span class="sxs-lookup"><span data-stu-id="dfbd8-104">Methods</span></span>  
  
|<span data-ttu-id="dfbd8-105">메서드</span><span class="sxs-lookup"><span data-stu-id="dfbd8-105">Method</span></span>|<span data-ttu-id="dfbd8-106">설명</span><span class="sxs-lookup"><span data-stu-id="dfbd8-106">Description</span></span>|  
|------------|-----------------|  
|`IEnumReferenceIdentity::Clone`|<span data-ttu-id="dfbd8-107">`IEnumReferenceIdentity` 이`IEnumReferenceIdentity`와 동일한 멤버를 포함 하는 새에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="dfbd8-107">Gets an interface pointer to a new `IEnumReferenceIdentity` that contains the same members as this `IEnumReferenceIdentity`.</span></span>|  
|`IEnumReferenceIdentity::Next`|<span data-ttu-id="dfbd8-108">현재 위치에서 시작 하 `IReferenceIdentity` 여 지정 된 수의 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="dfbd8-108">Gets the specified number of `IReferenceIdentity` objects, starting at the current position.</span></span>|  
|`IEnumReferenceIdentity::Reset`|<span data-ttu-id="dfbd8-109">명령 포인터를이 `IEnumReferenceIdentity`의 시작 부분으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfbd8-109">Moves the instruction pointer to the beginning of this `IEnumReferenceIdentity`.</span></span>|  
|`IEnumReferenceIdentity::Skip`|<span data-ttu-id="dfbd8-110">명령 포인터를 현재 위치에서 시작 하 여 지정 된 요소 수 만큼 앞으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfbd8-110">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="dfbd8-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dfbd8-111">Requirements</span></span>  
 <span data-ttu-id="dfbd8-112">**플랫폼** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="dfbd8-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dfbd8-113">**헤더:** 격리. h</span><span class="sxs-lookup"><span data-stu-id="dfbd8-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="dfbd8-114">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dfbd8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfbd8-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="dfbd8-115">See also</span></span>

- [<span data-ttu-id="dfbd8-116">Fusion 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dfbd8-116">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="dfbd8-117">IReferenceIdentity 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dfbd8-117">IReferenceIdentity Interface</span></span>](ireferenceidentity-interface.md)
