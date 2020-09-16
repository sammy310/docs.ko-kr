---
title: ICorDebugFunction3 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugFunction3
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: b22717b9-ead5-4eea-887e-789b52d613dc
topic_type:
- apiref
ms.openlocfilehash: 8c9c507f00780d5ef5c5aeb28a1b10493351f37e
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90546974"
---
# <a name="icordebugfunction3-interface"></a><span data-ttu-id="7b5df-102">ICorDebugFunction3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7b5df-102">ICorDebugFunction3 Interface</span></span>
<span data-ttu-id="7b5df-103">[.NET Framework 4.5.2 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="7b5df-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="7b5df-104">ReJIT 요청의 코드에 액세스할 수 있도록 ICorDebugFunction 인터페이스를 논리적으로 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="7b5df-104">Logically extends the ICorDebugFunction interface to provide access to code from a ReJIT request.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7b5df-105">메서드</span><span class="sxs-lookup"><span data-stu-id="7b5df-105">Methods</span></span>  
  
|<span data-ttu-id="7b5df-106">메서드</span><span class="sxs-lookup"><span data-stu-id="7b5df-106">Method</span></span>|<span data-ttu-id="7b5df-107">Description</span><span class="sxs-lookup"><span data-stu-id="7b5df-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7b5df-108">GetActiveReJitRequestILCode 메서드</span><span class="sxs-lookup"><span data-stu-id="7b5df-108">GetActiveReJitRequestILCode Method</span></span>](icordebugfunction3-getactiverejitrequestilcode-method.md)|<span data-ttu-id="7b5df-109">활성 ReJIT 요청에서 IL을 포함 하는 [ICorDebugILCode](icordebugilcode-interface.md) 에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7b5df-109">Gets an interface pointer to an [ICorDebugILCode](icordebugilcode-interface.md) that contains the IL from an active ReJIT request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7b5df-110">설명</span><span class="sxs-lookup"><span data-stu-id="7b5df-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b5df-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7b5df-111">Requirements</span></span>  
 <span data-ttu-id="7b5df-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7b5df-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b5df-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7b5df-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7b5df-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7b5df-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7b5df-115">**.NET Framework 버전:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b5df-115">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b5df-116">참조</span><span class="sxs-lookup"><span data-stu-id="7b5df-116">See also</span></span>

- [<span data-ttu-id="7b5df-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7b5df-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="7b5df-118">디버깅</span><span class="sxs-lookup"><span data-stu-id="7b5df-118">Debugging</span></span>](index.md)
- [<span data-ttu-id="7b5df-119">ReJIT: 방법 가이드</span><span class="sxs-lookup"><span data-stu-id="7b5df-119">ReJIT: A How-To Guide</span></span>](/archive/blogs/davbr/rejit-a-how-to-guide)
