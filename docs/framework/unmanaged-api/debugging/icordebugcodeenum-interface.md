---
title: ICorDebugCodeEnum 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugCodeEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCodeEnum
helpviewer_keywords:
- ICorDebugCodeEnum interface [.NET Framework debugging]
ms.assetid: b5589171-a4a0-4c00-bbdc-6e0a42233b75
topic_type:
- apiref
ms.openlocfilehash: cce0efa925683b5361a5422112db3f8231e2dfb4
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82893272"
---
# <a name="icordebugcodeenum-interface"></a><span data-ttu-id="0201a-102">ICorDebugCodeEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0201a-102">ICorDebugCodeEnum Interface</span></span>

<span data-ttu-id="0201a-103">"ICorDebugEnum" 메서드를 구현 하 고 "ICorDebugCode" 배열을 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="0201a-103">Implements "ICorDebugEnum" methods, and enumerates "ICorDebugCode" arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0201a-104">메서드</span><span class="sxs-lookup"><span data-stu-id="0201a-104">Methods</span></span>  
  
|<span data-ttu-id="0201a-105">메서드</span><span class="sxs-lookup"><span data-stu-id="0201a-105">Method</span></span>|<span data-ttu-id="0201a-106">설명</span><span class="sxs-lookup"><span data-stu-id="0201a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0201a-107">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="0201a-107">Next Method</span></span>](icordebugcodeenum-next-method.md)|<span data-ttu-id="0201a-108">현재 위치에서 시작 하 `ICorDebugCode` 여 열거형에서 지정 된 수의 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0201a-108">Gets the specified number of `ICorDebugCode` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0201a-109">설명</span><span class="sxs-lookup"><span data-stu-id="0201a-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0201a-110">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0201a-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0201a-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0201a-111">Requirements</span></span>  
 <span data-ttu-id="0201a-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0201a-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0201a-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0201a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0201a-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0201a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0201a-115">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0201a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0201a-116">참조</span><span class="sxs-lookup"><span data-stu-id="0201a-116">See also</span></span>

- [<span data-ttu-id="0201a-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0201a-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
