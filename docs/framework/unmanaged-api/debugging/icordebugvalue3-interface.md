---
title: ICorDebugValue3 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugValue3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue3
helpviewer_keywords:
- ICorDebugValue3 interface [.NET Framework debugging]
ms.assetid: 7d5385d3-f4a5-47c4-8478-a3513b5e9406
topic_type:
- apiref
ms.openlocfilehash: 5fa042223e47961dad0a6799ab8ca999ef76e285
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791086"
---
# <a name="icordebugvalue3-interface"></a><span data-ttu-id="084b6-102">ICorDebugValue3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="084b6-102">ICorDebugValue3 Interface</span></span>
<span data-ttu-id="084b6-103">"ICorDebugValue" 및 "ICorDebugValue2" 인터페이스를 확장 하 여 2gb 보다 큰 배열에 대 한 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="084b6-103">Extends the "ICorDebugValue" and "ICorDebugValue2" interfaces to provide support for arrays that are larger than 2 GB.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="084b6-104">메서드</span><span class="sxs-lookup"><span data-stu-id="084b6-104">Methods</span></span>  
  
|<span data-ttu-id="084b6-105">메서드</span><span class="sxs-lookup"><span data-stu-id="084b6-105">Method</span></span>|<span data-ttu-id="084b6-106">설명</span><span class="sxs-lookup"><span data-stu-id="084b6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="084b6-107">GetSize64 메서드</span><span class="sxs-lookup"><span data-stu-id="084b6-107">GetSize64 Method</span></span>](icordebugvalue3-getsize64-method.md)|<span data-ttu-id="084b6-108">이 `ICorDebugValue3` 개체의 크기 (바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="084b6-108">Gets the size, in bytes, of this `ICorDebugValue3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="084b6-109">주의</span><span class="sxs-lookup"><span data-stu-id="084b6-109">Remarks</span></span>  
 <span data-ttu-id="084b6-110">[ICorDebugValue:: GetSize](icordebugvalue3-getsize64-method.md) 메서드는 0 바이트에서 2147483647 바이트 범위의 개체 크기를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="084b6-110">The [ICorDebugValue::GetSize](icordebugvalue3-getsize64-method.md) method returns an object size that ranges from 0 to 2,147,483,647 bytes.</span></span> <span data-ttu-id="084b6-111">.NET Framework 4.5에서 배열의 크기는 2gb를 초과할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="084b6-111">In the .NET Framework 4.5, the size of arrays can exceed 2 GB.</span></span> <span data-ttu-id="084b6-112">`ICorDebugValue3` 인터페이스를 사용 하면 이러한 배열의 크기를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="084b6-112">The `ICorDebugValue3` interface enables you to determine the size of these arrays.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="084b6-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="084b6-113">Requirements</span></span>  
 <span data-ttu-id="084b6-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="084b6-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="084b6-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="084b6-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="084b6-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="084b6-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="084b6-117">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="084b6-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="084b6-118">참조</span><span class="sxs-lookup"><span data-stu-id="084b6-118">See also</span></span>

- [<span data-ttu-id="084b6-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="084b6-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="084b6-120">디버깅</span><span class="sxs-lookup"><span data-stu-id="084b6-120">Debugging</span></span>](index.md)
