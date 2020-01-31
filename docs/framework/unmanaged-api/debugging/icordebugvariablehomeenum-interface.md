---
title: ICorDebugVariableHomeEnum 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHomeEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHomeEnum
helpviewer_keywords:
- ICorDebugVariableHomeEnum interface [.NET Framework debugging]
ms.assetid: c312ae6d-c8dc-48d6-9f1e-ead515c88fdf
topic_type:
- apiref
ms.openlocfilehash: 74b3c7bed54f3735efbd5d2c56962d427518f71a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790941"
---
# <a name="icordebugvariablehomeenum-interface"></a><span data-ttu-id="3dfed-102">ICorDebugVariableHomeEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3dfed-102">ICorDebugVariableHomeEnum Interface</span></span>
<span data-ttu-id="3dfed-103">함수의 지역 변수 및 인수에 대 한 열거자를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3dfed-103">Provides an enumerator to the local variables and arguments in a function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3dfed-104">메서드</span><span class="sxs-lookup"><span data-stu-id="3dfed-104">Methods</span></span>  
  
|<span data-ttu-id="3dfed-105">메서드</span><span class="sxs-lookup"><span data-stu-id="3dfed-105">Method</span></span>|<span data-ttu-id="3dfed-106">설명</span><span class="sxs-lookup"><span data-stu-id="3dfed-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3dfed-107">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="3dfed-107">Next Method</span></span>](icordebugvariablehomeenum-next-method.md)|<span data-ttu-id="3dfed-108">함수의 지역 변수 및 인수에 대 한 정보를 포함 하는 지정 된 수의 [ICorDebugVariableHome](icordebugvariablehome-interface.md) 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3dfed-108">Gets the specified number of [ICorDebugVariableHome](icordebugvariablehome-interface.md) instances that contain information about the local variables and arguments in a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3dfed-109">주의</span><span class="sxs-lookup"><span data-stu-id="3dfed-109">Remarks</span></span>  
 <span data-ttu-id="3dfed-110">`ICorDebugVariableHomeEnum` 인터페이스는 ICorDebugEnum 인터페이스를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="3dfed-110">The `ICorDebugVariableHomeEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="3dfed-111">`ICorDebugVariableHomeEnum` 인스턴스는 [ICorDebugCode4:: EnumerateVariableHomes](icordebugcode4-enumeratevariablehomes-method.md) 메서드를 호출 하 여 [ICorDebugVariableHome](icordebugvariablehome-interface.md) 인스턴스로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="3dfed-111">An `ICorDebugVariableHomeEnum` instance is populated with [ICorDebugVariableHome](icordebugvariablehome-interface.md) instances by calling the [ICorDebugCode4::EnumerateVariableHomes](icordebugcode4-enumeratevariablehomes-method.md) method.</span></span> <span data-ttu-id="3dfed-112">컬렉션의 각 [ICorDebugVariableHome](icordebugvariablehome-interface.md) 인스턴스는 함수의 지역 변수 또는 인수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3dfed-112">Each [ICorDebugVariableHome](icordebugvariablehome-interface.md) instance in the collection represents a local variable or argument in a function.</span></span> <span data-ttu-id="3dfed-113">컬렉션의 [ICorDebugVariableHome](icordebugvariablehome-interface.md) 개체는 [ICorDebugVariableHomeEnum:: Next](icordebugvariablehomeenum-next-method.md) 메서드를 호출 하 여 열거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3dfed-113">The  [ICorDebugVariableHome](icordebugvariablehome-interface.md) objects in the collection can be enumerated by calling the [ICorDebugVariableHomeEnum::Next](icordebugvariablehomeenum-next-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3dfed-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3dfed-114">Requirements</span></span>  
 <span data-ttu-id="3dfed-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3dfed-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3dfed-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3dfed-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3dfed-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3dfed-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3dfed-118">**.NET Framework 버전:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3dfed-118">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3dfed-119">참조</span><span class="sxs-lookup"><span data-stu-id="3dfed-119">See also</span></span>

- [<span data-ttu-id="3dfed-120">ICorDebugVariableHome 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3dfed-120">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
- [<span data-ttu-id="3dfed-121">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3dfed-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
