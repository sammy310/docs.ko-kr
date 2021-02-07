---
description: '자세히 알아보기: ICorDebugProcess8 인터페이스'
title: ICorDebugProcess8 인터페이스
ms.date: 03/30/2017
ms.assetid: 7ab1a70f-ec11-46ff-8869-cd8ca679cc51
ms.openlocfilehash: d858470216cfe64c60902836e552f750f4b2d5ec
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99691291"
---
# <a name="icordebugprocess8-interface"></a><span data-ttu-id="dfdb2-103">ICorDebugProcess8 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dfdb2-103">ICorDebugProcess8 Interface</span></span>

<span data-ttu-id="dfdb2-104">[.NET Framework 4.6 이상 버전에서 지원 됨]</span><span class="sxs-lookup"><span data-stu-id="dfdb2-104">[Supported in the .NET Framework 4.6 and later versions]</span></span>  
  
 <span data-ttu-id="dfdb2-105">ICorDebugProcess 인터페이스를 논리적으로 확장 하 여 특정 형식의 [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) 예외 콜백을 사용 하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfdb2-105">Logically extends the ICorDebugProcess interface to enable or disable certain types of [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) exception callbacks.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dfdb2-106">메서드</span><span class="sxs-lookup"><span data-stu-id="dfdb2-106">Methods</span></span>  
  
|<span data-ttu-id="dfdb2-107">메서드</span><span class="sxs-lookup"><span data-stu-id="dfdb2-107">Method</span></span>|<span data-ttu-id="dfdb2-108">설명</span><span class="sxs-lookup"><span data-stu-id="dfdb2-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dfdb2-109">EnableExceptionCallbacksOutsideOfMyCode 메서드</span><span class="sxs-lookup"><span data-stu-id="dfdb2-109">EnableExceptionCallbacksOutsideOfMyCode Method</span></span>](icordebugprocess8-enableexceptioncallbacksoutsideofmycode-method.md)|<span data-ttu-id="dfdb2-110">특정 형식의 [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) 예외 콜백을 사용 하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfdb2-110">Enables or disables certain types of [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) exception callbacks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dfdb2-111">설명</span><span class="sxs-lookup"><span data-stu-id="dfdb2-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dfdb2-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dfdb2-112">Requirements</span></span>  

 <span data-ttu-id="dfdb2-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dfdb2-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dfdb2-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dfdb2-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dfdb2-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dfdb2-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dfdb2-116">**.NET Framework 버전:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dfdb2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfdb2-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dfdb2-117">See also</span></span>

- [<span data-ttu-id="dfdb2-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dfdb2-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="dfdb2-119">디버깅</span><span class="sxs-lookup"><span data-stu-id="dfdb2-119">Debugging</span></span>](index.md)
