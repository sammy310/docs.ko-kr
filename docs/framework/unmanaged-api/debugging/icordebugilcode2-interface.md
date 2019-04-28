---
title: ICorDebugILCode2 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugILCode2
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: f9dc2afd-df8a-464d-bdbf-5af0a1d4bf85
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3a27dbd8b5013937bb97f37113687405c988c1fe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645220"
---
# <a name="icordebugilcode2-interface"></a><span data-ttu-id="67aac-102">ICorDebugILCode2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="67aac-102">ICorDebugILCode2 Interface</span></span>
<span data-ttu-id="67aac-103">[.NET Framework 4.5.2 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="67aac-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="67aac-104">논리적으로 확장 합니다 [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) 인터페이스 함수의 로컬 변수 서명에 대 한 토큰을 반환 하 고 프로파일러의 계측 된 IL (중간 언어)을 매핑하는 방법을 제공 하기 위해 원래 메서드 IL 오프셋 오프셋 합니다.</span><span class="sxs-lookup"><span data-stu-id="67aac-104">Logically extends the [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) interface to provide methods that return the token for a function's local variable signature, and that map a profiler's instrumented intermediate language (IL) offsets to original method IL offsets.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="67aac-105">메서드</span><span class="sxs-lookup"><span data-stu-id="67aac-105">Methods</span></span>  
  
|<span data-ttu-id="67aac-106">메서드</span><span class="sxs-lookup"><span data-stu-id="67aac-106">Method</span></span>|<span data-ttu-id="67aac-107">설명</span><span class="sxs-lookup"><span data-stu-id="67aac-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="67aac-108">GetInstrumentedILMap 메서드</span><span class="sxs-lookup"><span data-stu-id="67aac-108">GetInstrumentedILMap Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-getinstrumentedilmap-method.md)|<span data-ttu-id="67aac-109">이 인스턴스에 대해 프로파일러가 계측한 IL 오프셋에서 원래 메서드 IL 오프셋으로의 맵을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="67aac-109">Returns a map from profiler instrumented IL offsets to original method IL offsets for this instance.</span></span>|  
|[<span data-ttu-id="67aac-110">GetLocalVarSigToken 메서드</span><span class="sxs-lookup"><span data-stu-id="67aac-110">GetLocalVarSigToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-getlocalvarsigtoken-method.md)|<span data-ttu-id="67aac-111">이 인스턴스로 표시되는 함수의 로컬 변수 서명에 대한 메타데이터 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="67aac-111">Gets the metadata token for the local variable signature for the function that is represented by this instance.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="67aac-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="67aac-112">Requirements</span></span>  
 <span data-ttu-id="67aac-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="67aac-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67aac-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="67aac-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="67aac-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="67aac-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="67aac-116">**.NET Framework 버전:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67aac-116">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67aac-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="67aac-117">See also</span></span>

- [<span data-ttu-id="67aac-118">ICorDebugILCode 인터페이스</span><span class="sxs-lookup"><span data-stu-id="67aac-118">ICorDebugILCode Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md)
- [<span data-ttu-id="67aac-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="67aac-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="67aac-120">디버깅</span><span class="sxs-lookup"><span data-stu-id="67aac-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
