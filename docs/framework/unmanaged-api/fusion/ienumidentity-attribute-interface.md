---
title: IEnumIDENTITY_ATTRIBUTE 인터페이스
ms.date: 03/30/2017
api_name:
- IEnumIDENTITY_ATTRIBUTE
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IEnumIDENTITY_ATTRIBUTE
helpviewer_keywords:
- IEnumIDENTITY_ATTRIBUTE interface [.NET Framework fusion]
ms.assetid: c2ec2748-e9ae-4e1b-80db-6fcec5cb81a1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d725228f2a7359d415673fdcb90d0cabae1a40be
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697344"
---
# <a name="ienumidentityattribute-interface"></a><span data-ttu-id="b630c-102">IEnumIDENTITY_ATTRIBUTE 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b630c-102">IEnumIDENTITY_ATTRIBUTE Interface</span></span>
<span data-ttu-id="b630c-103">현재 범위에 있는 코드 개체의 특성에 대 한 열거자를 역할도합니다.</span><span class="sxs-lookup"><span data-stu-id="b630c-103">Serves as an enumerator for the attributes of the code object in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b630c-104">메서드</span><span class="sxs-lookup"><span data-stu-id="b630c-104">Methods</span></span>  
  
|<span data-ttu-id="b630c-105">메서드</span><span class="sxs-lookup"><span data-stu-id="b630c-105">Method</span></span>|<span data-ttu-id="b630c-106">설명</span><span class="sxs-lookup"><span data-stu-id="b630c-106">Description</span></span>|  
|------------|-----------------|  
|`IEnumIDENTITY_ATTRIBUTE::Clone`|<span data-ttu-id="b630c-107">새 인터페이스 포인터를 가져옵니다 `IEnumIDENTITY_ATTRIBUTE` 이 동일한 멤버를 포함 하는 `IEnumIDENTITY_ATTRIBUTE`합니다.</span><span class="sxs-lookup"><span data-stu-id="b630c-107">Gets an interface pointer to a new `IEnumIDENTITY_ATTRIBUTE` that contains the same members as this `IEnumIDENTITY_ATTRIBUTE`.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::CurrentIntoBuffer`|<span data-ttu-id="b630c-108">이 요소에 포함 된 데이터를 쓰는 `IEnumIDENTITY_ATTRIBUTE` 지정된 된 데이터 버퍼를 합니다.</span><span class="sxs-lookup"><span data-stu-id="b630c-108">Writes the data contained in the elements of this `IEnumIDENTITY_ATTRIBUTE` to the specified data buffer.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Next`|<span data-ttu-id="b630c-109">특성을 현재 위치부터 지정한 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b630c-109">Gets the specified number of attributes, starting at the current position.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Reset`|<span data-ttu-id="b630c-110">이 부분에 명령 포인터를 이동 `IEnumIDENTITY_ATTRIBUTE`합니다.</span><span class="sxs-lookup"><span data-stu-id="b630c-110">Moves the instruction pointer to the beginning of this `IEnumIDENTITY_ATTRIBUTE`.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Skip`|<span data-ttu-id="b630c-111">요소를 현재 위치부터 지정한 수 만큼 앞으로 명령 포인터를 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b630c-111">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b630c-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b630c-112">Requirements</span></span>  
 <span data-ttu-id="b630c-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b630c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b630c-114">**헤더:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="b630c-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="b630c-115">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b630c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b630c-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="b630c-116">See also</span></span>

- [<span data-ttu-id="b630c-117">Fusion 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b630c-117">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
