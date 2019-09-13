---
title: ICorProfilerInfo8 인터페이스
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 2baa33a7a3527392d8095b5d0ec7ad6af8a71a8e
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928932"
---
# <a name="icorprofilerinfo8-interface"></a><span data-ttu-id="21427-102">ICorProfilerInfo8 인터페이스</span><span class="sxs-lookup"><span data-stu-id="21427-102">ICorProfilerInfo8 Interface</span></span>

<span data-ttu-id="21427-103">동적 메서드에 대 한 정보를 쿼리 하는 메서드를 제공 하는 [ICorProfilerInfo7](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md) 의 서브 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="21427-103">A subclass of [ICorProfilerInfo7](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md) that provides methods to query information about dynamic methods.</span></span>

## <a name="methods"></a><span data-ttu-id="21427-104">메서드</span><span class="sxs-lookup"><span data-stu-id="21427-104">Methods</span></span>  

| <span data-ttu-id="21427-105">메서드</span><span class="sxs-lookup"><span data-stu-id="21427-105">Method</span></span>|<span data-ttu-id="21427-106">Description</span><span class="sxs-lookup"><span data-stu-id="21427-106">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="21427-107">IsFunctionDynamic 메서드</span><span class="sxs-lookup"><span data-stu-id="21427-107">IsFunctionDynamic Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-isfunctiondynamic-method.md)| <span data-ttu-id="21427-108">함수에 연결 된 메타 데이터가 있는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="21427-108">Determines if a function does not have associated metadata.</span></span>|
|[<span data-ttu-id="21427-109">GetFunctionFromIP3 메서드</span><span class="sxs-lookup"><span data-stu-id="21427-109">GetFunctionFromIP3 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-getfunctionfromip3-method.md)| <span data-ttu-id="21427-110">관리 코드 명령 포인터를 FunctionID에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="21427-110">Maps a managed code instruction pointer to a FunctionID.</span></span> <span data-ttu-id="21427-111">이 메서드는 동적 메서드와 비동적 메서드 모두에 대해 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="21427-111">This method works for both dynamic and non-dynamic methods.</span></span> |
|[<span data-ttu-id="21427-112">GetDynamicFunctionInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="21427-112">GetDynamicFunctionInfo Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-getdynamicfunctioninfo-method.md)| <span data-ttu-id="21427-113">동적 메서드에 대 한 정보를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="21427-113">Retrieves information about dynamic methods.</span></span> |

## <a name="requirements"></a><span data-ttu-id="21427-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="21427-114">Requirements</span></span>  
<span data-ttu-id="21427-115">**플랫폼** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="21427-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="21427-116">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="21427-116">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="21427-117">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="21427-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="21427-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="21427-118">See also</span></span>

- [<span data-ttu-id="21427-119">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="21427-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
