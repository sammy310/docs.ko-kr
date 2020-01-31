---
title: ICorProfilerCallback::AppDomainCreationStarted 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AppDomainCreationStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AppDomainCreationStarted
helpviewer_keywords:
- AppDomainCreationStarted method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainCreationStarted method [.NET Framework profiling]
ms.assetid: b2a8240b-07fe-4859-bb2b-7d3adbfa0a9f
topic_type:
- apiref
ms.openlocfilehash: 35dbed6a723f5319dc506a44198456e3794464fc
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790228"
---
# <a name="icorprofilercallbackappdomaincreationstarted-method"></a><span data-ttu-id="9e853-102">ICorProfilerCallback::AppDomainCreationStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="9e853-102">ICorProfilerCallback::AppDomainCreationStarted Method</span></span>
<span data-ttu-id="9e853-103">응용 프로그램 도메인이 생성 중임을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="9e853-103">Notifies the profiler that an application domain is being created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e853-104">구문</span><span class="sxs-lookup"><span data-stu-id="9e853-104">Syntax</span></span>  
  
```cpp  
HRESULT AppDomainCreationStarted(  
    [in] AppDomainID appDomainId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e853-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9e853-105">Parameters</span></span>

- `appDomainId`

  <span data-ttu-id="9e853-106">\[]은 만들 도메인을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e853-106">\[in] Identifies the domain which is being created.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="9e853-107">주의</span><span class="sxs-lookup"><span data-stu-id="9e853-107">Remarks</span></span>  
 <span data-ttu-id="9e853-108">[ICorProfilerCallback:: AppDomainCreationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomaincreationfinished-method.md) 메서드가 호출 될 때까지 정보 요청에 대해 ID가 유효 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9e853-108">The ID is not valid for any information request until the [ICorProfilerCallback::AppDomainCreationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomaincreationfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e853-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9e853-109">Requirements</span></span>  
 <span data-ttu-id="9e853-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9e853-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e853-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9e853-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9e853-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9e853-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9e853-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e853-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e853-114">참조</span><span class="sxs-lookup"><span data-stu-id="9e853-114">See also</span></span>

- [<span data-ttu-id="9e853-115">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9e853-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
