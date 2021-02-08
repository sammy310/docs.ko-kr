---
description: '자세히 알아보기: ICorDebugVariableHomeEnum 인터페이스'
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
ms.openlocfilehash: c56c68a6b5f9d329fe8af23f47b40fa629bfe3ba
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790622"
---
# <a name="icordebugvariablehomeenum-interface"></a><span data-ttu-id="88aef-103">ICorDebugVariableHomeEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="88aef-103">ICorDebugVariableHomeEnum Interface</span></span>

<span data-ttu-id="88aef-104">함수의 지역 변수 및 인수에 대 한 열거자를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="88aef-104">Provides an enumerator to the local variables and arguments in a function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="88aef-105">메서드</span><span class="sxs-lookup"><span data-stu-id="88aef-105">Methods</span></span>  
  
|<span data-ttu-id="88aef-106">메서드</span><span class="sxs-lookup"><span data-stu-id="88aef-106">Method</span></span>|<span data-ttu-id="88aef-107">설명</span><span class="sxs-lookup"><span data-stu-id="88aef-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="88aef-108">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="88aef-108">Next Method</span></span>](icordebugvariablehomeenum-next-method.md)|<span data-ttu-id="88aef-109">함수의 지역 변수 및 인수에 대 한 정보를 포함 하는 지정 된 수의 [ICorDebugVariableHome](icordebugvariablehome-interface.md) 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="88aef-109">Gets the specified number of [ICorDebugVariableHome](icordebugvariablehome-interface.md) instances that contain information about the local variables and arguments in a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="88aef-110">설명</span><span class="sxs-lookup"><span data-stu-id="88aef-110">Remarks</span></span>  

 <span data-ttu-id="88aef-111">`ICorDebugVariableHomeEnum`인터페이스는 ICorDebugEnum 인터페이스를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="88aef-111">The `ICorDebugVariableHomeEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="88aef-112">`ICorDebugVariableHomeEnum`인스턴스는 [ICorDebugCode4:: EnumerateVariableHomes](icordebugcode4-enumeratevariablehomes-method.md) 메서드를 호출 하 여 [ICorDebugVariableHome](icordebugvariablehome-interface.md) 인스턴스로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="88aef-112">An `ICorDebugVariableHomeEnum` instance is populated with [ICorDebugVariableHome](icordebugvariablehome-interface.md) instances by calling the [ICorDebugCode4::EnumerateVariableHomes](icordebugcode4-enumeratevariablehomes-method.md) method.</span></span> <span data-ttu-id="88aef-113">컬렉션의 각 [ICorDebugVariableHome](icordebugvariablehome-interface.md) 인스턴스는 함수의 지역 변수 또는 인수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="88aef-113">Each [ICorDebugVariableHome](icordebugvariablehome-interface.md) instance in the collection represents a local variable or argument in a function.</span></span> <span data-ttu-id="88aef-114">컬렉션의  [ICorDebugVariableHome](icordebugvariablehome-interface.md) 개체는 [ICorDebugVariableHomeEnum:: Next](icordebugvariablehomeenum-next-method.md) 메서드를 호출 하 여 열거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88aef-114">The  [ICorDebugVariableHome](icordebugvariablehome-interface.md) objects in the collection can be enumerated by calling the [ICorDebugVariableHomeEnum::Next](icordebugvariablehomeenum-next-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88aef-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="88aef-115">Requirements</span></span>  

 <span data-ttu-id="88aef-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="88aef-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88aef-117">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="88aef-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="88aef-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="88aef-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="88aef-119">**.NET Framework 버전:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88aef-119">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88aef-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="88aef-120">See also</span></span>

- [<span data-ttu-id="88aef-121">ICorDebugVariableHome 인터페이스</span><span class="sxs-lookup"><span data-stu-id="88aef-121">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
- [<span data-ttu-id="88aef-122">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="88aef-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
