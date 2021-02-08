---
description: IEnumIDENTITY_ATTRIBUTE 인터페이스에 대해 자세히 알아보세요.
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
ms.openlocfilehash: b621a722e35d5b31f487e8823b1627fdfe1e7888
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800151"
---
# <a name="ienumidentity_attribute-interface"></a><span data-ttu-id="d3670-103">IEnumIDENTITY_ATTRIBUTE 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d3670-103">IEnumIDENTITY_ATTRIBUTE Interface</span></span>

<span data-ttu-id="d3670-104">현재 범위에 있는 코드 개체의 특성에 대 한 열거자 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3670-104">Serves as an enumerator for the attributes of the code object in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d3670-105">메서드</span><span class="sxs-lookup"><span data-stu-id="d3670-105">Methods</span></span>  
  
|<span data-ttu-id="d3670-106">메서드</span><span class="sxs-lookup"><span data-stu-id="d3670-106">Method</span></span>|<span data-ttu-id="d3670-107">설명</span><span class="sxs-lookup"><span data-stu-id="d3670-107">Description</span></span>|  
|------------|-----------------|  
|`IEnumIDENTITY_ATTRIBUTE::Clone`|<span data-ttu-id="d3670-108">`IEnumIDENTITY_ATTRIBUTE`이와 동일한 멤버를 포함 하는 새에 대 한 인터페이스 포인터를 가져옵니다 `IEnumIDENTITY_ATTRIBUTE` .</span><span class="sxs-lookup"><span data-stu-id="d3670-108">Gets an interface pointer to a new `IEnumIDENTITY_ATTRIBUTE` that contains the same members as this `IEnumIDENTITY_ATTRIBUTE`.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::CurrentIntoBuffer`|<span data-ttu-id="d3670-109">이의 요소에 포함 된 데이터를 `IEnumIDENTITY_ATTRIBUTE` 지정 된 데이터 버퍼에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="d3670-109">Writes the data contained in the elements of this `IEnumIDENTITY_ATTRIBUTE` to the specified data buffer.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Next`|<span data-ttu-id="d3670-110">현재 위치에서 시작 하 여 지정 된 수의 특성을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d3670-110">Gets the specified number of attributes, starting at the current position.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Reset`|<span data-ttu-id="d3670-111">명령 포인터를이의 시작 부분으로 이동 합니다 `IEnumIDENTITY_ATTRIBUTE` .</span><span class="sxs-lookup"><span data-stu-id="d3670-111">Moves the instruction pointer to the beginning of this `IEnumIDENTITY_ATTRIBUTE`.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Skip`|<span data-ttu-id="d3670-112">명령 포인터를 현재 위치에서 시작 하 여 지정 된 요소 수 만큼 앞으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3670-112">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d3670-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d3670-113">Requirements</span></span>  

 <span data-ttu-id="d3670-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d3670-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3670-115">**헤더:** 격리. h</span><span class="sxs-lookup"><span data-stu-id="d3670-115">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="d3670-116">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3670-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3670-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d3670-117">See also</span></span>

- [<span data-ttu-id="d3670-118">Fusion 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d3670-118">Fusion Interfaces</span></span>](fusion-interfaces.md)
