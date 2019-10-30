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
ms.openlocfilehash: 7e6bc57fb470a5c12549bb5f9445ecf1551425a4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73107837"
---
# <a name="ienumidentity_attribute-interface"></a><span data-ttu-id="7a018-102">IEnumIDENTITY_ATTRIBUTE 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7a018-102">IEnumIDENTITY_ATTRIBUTE Interface</span></span>
<span data-ttu-id="7a018-103">현재 범위에 있는 코드 개체의 특성에 대 한 열거자 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a018-103">Serves as an enumerator for the attributes of the code object in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7a018-104">메서드</span><span class="sxs-lookup"><span data-stu-id="7a018-104">Methods</span></span>  
  
|<span data-ttu-id="7a018-105">메서드</span><span class="sxs-lookup"><span data-stu-id="7a018-105">Method</span></span>|<span data-ttu-id="7a018-106">설명</span><span class="sxs-lookup"><span data-stu-id="7a018-106">Description</span></span>|  
|------------|-----------------|  
|`IEnumIDENTITY_ATTRIBUTE::Clone`|<span data-ttu-id="7a018-107">이 `IEnumIDENTITY_ATTRIBUTE`와 동일한 멤버를 포함 하는 새 `IEnumIDENTITY_ATTRIBUTE`에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7a018-107">Gets an interface pointer to a new `IEnumIDENTITY_ATTRIBUTE` that contains the same members as this `IEnumIDENTITY_ATTRIBUTE`.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::CurrentIntoBuffer`|<span data-ttu-id="7a018-108">이 `IEnumIDENTITY_ATTRIBUTE`의 요소에 포함 된 데이터를 지정 된 데이터 버퍼에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="7a018-108">Writes the data contained in the elements of this `IEnumIDENTITY_ATTRIBUTE` to the specified data buffer.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Next`|<span data-ttu-id="7a018-109">현재 위치에서 시작 하 여 지정 된 수의 특성을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7a018-109">Gets the specified number of attributes, starting at the current position.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Reset`|<span data-ttu-id="7a018-110">명령 포인터를이 `IEnumIDENTITY_ATTRIBUTE`의 시작 부분으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a018-110">Moves the instruction pointer to the beginning of this `IEnumIDENTITY_ATTRIBUTE`.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Skip`|<span data-ttu-id="7a018-111">명령 포인터를 현재 위치에서 시작 하 여 지정 된 요소 수 만큼 앞으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a018-111">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7a018-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7a018-112">Requirements</span></span>  
 <span data-ttu-id="7a018-113">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7a018-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a018-114">**헤더:** 격리. h</span><span class="sxs-lookup"><span data-stu-id="7a018-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="7a018-115">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a018-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a018-116">참조</span><span class="sxs-lookup"><span data-stu-id="7a018-116">See also</span></span>

- [<span data-ttu-id="7a018-117">Fusion 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7a018-117">Fusion Interfaces</span></span>](fusion-interfaces.md)
