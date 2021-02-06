---
description: '자세히 알아보기: ICorProfilerInfo8 인터페이스'
title: ICorProfilerInfo8 인터페이스
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 4538c9d314283c67ab0bfe6af3f3768062cffda4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99646545"
---
# <a name="icorprofilerinfo8-interface"></a><span data-ttu-id="9d43c-103">ICorProfilerInfo8 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9d43c-103">ICorProfilerInfo8 Interface</span></span>

<span data-ttu-id="9d43c-104">동적 메서드에 대 한 정보를 쿼리 하는 메서드를 제공 하는 [ICorProfilerInfo7](icorprofilerinfo7-interface.md) 의 서브 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="9d43c-104">A subclass of [ICorProfilerInfo7](icorprofilerinfo7-interface.md) that provides methods to query information about dynamic methods.</span></span>

## <a name="methods"></a><span data-ttu-id="9d43c-105">메서드</span><span class="sxs-lookup"><span data-stu-id="9d43c-105">Methods</span></span>  

| <span data-ttu-id="9d43c-106">메서드</span><span class="sxs-lookup"><span data-stu-id="9d43c-106">Method</span></span>|<span data-ttu-id="9d43c-107">설명</span><span class="sxs-lookup"><span data-stu-id="9d43c-107">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="9d43c-108">IsFunctionDynamic 메서드</span><span class="sxs-lookup"><span data-stu-id="9d43c-108">IsFunctionDynamic Method</span></span>](icorprofilerinfo8-isfunctiondynamic-method.md)| <span data-ttu-id="9d43c-109">함수에 연결 된 메타 데이터가 있는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d43c-109">Determines if a function does not have associated metadata.</span></span>|
|[<span data-ttu-id="9d43c-110">GetFunctionFromIP3 메서드</span><span class="sxs-lookup"><span data-stu-id="9d43c-110">GetFunctionFromIP3 Method</span></span>](icorprofilerinfo8-getfunctionfromip3-method.md)| <span data-ttu-id="9d43c-111">관리 코드 명령 포인터를 FunctionID에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="9d43c-111">Maps a managed code instruction pointer to a FunctionID.</span></span> <span data-ttu-id="9d43c-112">이 메서드는 동적 메서드와 비동적 메서드 모두에 대해 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d43c-112">This method works for both dynamic and non-dynamic methods.</span></span> |
|[<span data-ttu-id="9d43c-113">GetDynamicFunctionInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="9d43c-113">GetDynamicFunctionInfo Method</span></span>](icorprofilerinfo8-getdynamicfunctioninfo-method.md)| <span data-ttu-id="9d43c-114">동적 메서드에 대 한 정보를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d43c-114">Retrieves information about dynamic methods.</span></span> |

## <a name="requirements"></a><span data-ttu-id="9d43c-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9d43c-115">Requirements</span></span>  

<span data-ttu-id="9d43c-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9d43c-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="9d43c-117">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9d43c-117">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="9d43c-118">**.NET Framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="9d43c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="9d43c-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9d43c-119">See also</span></span>

- [<span data-ttu-id="9d43c-120">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9d43c-120">Profiling Interfaces</span></span>](profiling-interfaces.md)
