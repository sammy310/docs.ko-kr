---
title: ICorProfilerInfo2::GetStaticFieldInfo 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetStaticFieldInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetStaticFieldInfo
helpviewer_keywords:
- ICorProfilerInfo2::GetStaticFieldInfo method [.NET Framework profiling]
- GetStaticFieldInfo method [.NET Framework profiling]
ms.assetid: fc663e76-e23f-49a8-bdd5-52cdf1a3b2b3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c0106b2dd1151e302c0082b306d999ab5a1c4322
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59177751"
---
# <a name="icorprofilerinfo2getstaticfieldinfo-method"></a><span data-ttu-id="3f208-102">ICorProfilerInfo2::GetStaticFieldInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="3f208-102">ICorProfilerInfo2::GetStaticFieldInfo Method</span></span>
<span data-ttu-id="3f208-103">지정된 된 필드에 적용 되는 정적의 종류를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3f208-103">Gets a value that indicates the kind of static that applies to the specified field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f208-104">구문</span><span class="sxs-lookup"><span data-stu-id="3f208-104">Syntax</span></span>  
  
```  
HRESULT GetStaticFieldInfo (  
    [in] ClassID               classId,  
    [in] mdFieldDef            fieldToken,  
    [out] COR_PRF_STATIC_TYPE  *pFieldInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f208-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3f208-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="3f208-106">[in] 정적 필드 정의 되어 있는 클래스의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3f208-106">[in] The ID of the class in which the static field is defined.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="3f208-107">[in] 정적 필드에 대 한 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="3f208-107">[in] The metadata token for the static field.</span></span>  
  
 `pFieldInfo`  
 <span data-ttu-id="3f208-108">[out] 값에 대 한 포인터를 [COR_PRF_STATIC_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-static-type-enumeration.md) 열거형 나타내는 지정된 된 필드가 정적 인지 한 경우, 정적의 종류에 적용 되는 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="3f208-108">[out] A pointer to a value of the [COR_PRF_STATIC_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-static-type-enumeration.md) enumeration that indicates whether the specified field is static, and if so, the kind of static that applies to the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3f208-109">설명</span><span class="sxs-lookup"><span data-stu-id="3f208-109">Remarks</span></span>  
 <span data-ttu-id="3f208-110">정적 필드의 주소를 가져오려면 호출할 함수를 확인 하려면이 정보를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f208-110">This information can be used to determine which function to call to get the address of the static field.</span></span>  
  
 <span data-ttu-id="3f208-111">프로파일러 코드의 메타 데이터 주소를 실제로 있는지 확인 하려면 정적 필드를 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f208-111">The profiler code should still check the metadata for a static field to ensure that it actually has an address.</span></span> <span data-ttu-id="3f208-112">정적 리터럴 (즉, 상수) 메타 데이터에만 존재 하 고 주소를가지고 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3f208-112">Static literals (that is, constants) exist only in the metadata and do not have an address.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f208-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3f208-113">Requirements</span></span>  
 <span data-ttu-id="3f208-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="3f208-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f208-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3f208-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3f208-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f208-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="3f208-117">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="3f208-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3f208-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="3f208-118">See also</span></span>

- [<span data-ttu-id="3f208-119">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3f208-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="3f208-120">ICorProfilerInfo2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3f208-120">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
