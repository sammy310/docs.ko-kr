---
description: '자세히 알아보기: ICorDebugValue3 인터페이스'
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
ms.openlocfilehash: e5868b91d23426a2d8dd8fed87b13ec61fef95ef
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794652"
---
# <a name="icordebugvalue3-interface"></a><span data-ttu-id="08e50-103">ICorDebugValue3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="08e50-103">ICorDebugValue3 Interface</span></span>

<span data-ttu-id="08e50-104">"ICorDebugValue" 및 "ICorDebugValue2" 인터페이스를 확장 하 여 2gb 보다 큰 배열에 대 한 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="08e50-104">Extends the "ICorDebugValue" and "ICorDebugValue2" interfaces to provide support for arrays that are larger than 2 GB.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="08e50-105">메서드</span><span class="sxs-lookup"><span data-stu-id="08e50-105">Methods</span></span>  
  
|<span data-ttu-id="08e50-106">메서드</span><span class="sxs-lookup"><span data-stu-id="08e50-106">Method</span></span>|<span data-ttu-id="08e50-107">설명</span><span class="sxs-lookup"><span data-stu-id="08e50-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="08e50-108">GetSize64 메서드</span><span class="sxs-lookup"><span data-stu-id="08e50-108">GetSize64 Method</span></span>](icordebugvalue3-getsize64-method.md)|<span data-ttu-id="08e50-109">이 개체의 크기 (바이트)를 가져옵니다 `ICorDebugValue3` .</span><span class="sxs-lookup"><span data-stu-id="08e50-109">Gets the size, in bytes, of this `ICorDebugValue3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="08e50-110">설명</span><span class="sxs-lookup"><span data-stu-id="08e50-110">Remarks</span></span>  

 <span data-ttu-id="08e50-111">[ICorDebugValue:: GetSize](icordebugvalue3-getsize64-method.md) 메서드는 0 바이트에서 2147483647 바이트 범위의 개체 크기를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="08e50-111">The [ICorDebugValue::GetSize](icordebugvalue3-getsize64-method.md) method returns an object size that ranges from 0 to 2,147,483,647 bytes.</span></span> <span data-ttu-id="08e50-112">.NET Framework 4.5에서 배열의 크기는 2gb를 초과할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08e50-112">In the .NET Framework 4.5, the size of arrays can exceed 2 GB.</span></span> <span data-ttu-id="08e50-113">`ICorDebugValue3`인터페이스를 사용 하면 이러한 배열의 크기를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08e50-113">The `ICorDebugValue3` interface enables you to determine the size of these arrays.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08e50-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="08e50-114">Requirements</span></span>  

 <span data-ttu-id="08e50-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="08e50-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08e50-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="08e50-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="08e50-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="08e50-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="08e50-118">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08e50-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08e50-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="08e50-119">See also</span></span>

- [<span data-ttu-id="08e50-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="08e50-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="08e50-121">디버깅</span><span class="sxs-lookup"><span data-stu-id="08e50-121">Debugging</span></span>](index.md)
