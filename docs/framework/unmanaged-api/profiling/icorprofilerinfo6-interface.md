---
title: ICorProfilerInfo6 인터페이스
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo6
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 6f2bb148-1e2b-4e45-a5a5-0ceddc40064b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: febe130b4d61b6179aeab3bfcd63891c38b13fbe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62041121"
---
# <a name="icorprofilerinfo6-interface"></a><span data-ttu-id="0826f-102">ICorProfilerInfo6 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0826f-102">ICorProfilerInfo6 Interface</span></span>
<span data-ttu-id="0826f-103">[.NET Framework 4.6 및 이상 버전에서 지원 됨]</span><span class="sxs-lookup"><span data-stu-id="0826f-103">[Supported in the .NET Framework 4.6 and later versions]</span></span>  
  
 <span data-ttu-id="0826f-104">서브 클래스 [ICorProfilerInfo5](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md) 인라인 지정된 메서드를 지정 된 NGen 모듈에 정의 된 모든 메서드에 대 한 열거자를 제공 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="0826f-104">A subclass of [ICorProfilerInfo5](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md) that provides an enumerator for all methods that are defined in a given NGen module and inline a given method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0826f-105">메서드</span><span class="sxs-lookup"><span data-stu-id="0826f-105">Methods</span></span>  
  
|<span data-ttu-id="0826f-106">메서드</span><span class="sxs-lookup"><span data-stu-id="0826f-106">Method</span></span>|<span data-ttu-id="0826f-107">설명</span><span class="sxs-lookup"><span data-stu-id="0826f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0826f-108">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="0826f-108">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-enumngenmodulemethodsinliningthismethod-method.md)|<span data-ttu-id="0826f-109">지정 된 NGen 모듈에 속하고 지정 된 메서드의 본문에 인라인 처리 되지 않은 모든 메서드에 대 한 열거자를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0826f-109">Returns an enumerator for all methods that belong to a given NGen module and that are inlined in the body of a given method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0826f-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0826f-110">Requirements</span></span>  
 <span data-ttu-id="0826f-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0826f-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0826f-112">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0826f-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0826f-113">**.NET Framework 버전:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0826f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0826f-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="0826f-114">See also</span></span>

- [<span data-ttu-id="0826f-115">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0826f-115">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
