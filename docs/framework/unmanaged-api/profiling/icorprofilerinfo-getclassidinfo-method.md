---
title: ICorProfilerInfo::GetClassIDInfo 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetClassIDInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetClassIDInfo
helpviewer_keywords:
- GetClassIDInfo method [.NET Framework profiling]
- ICorProfilerInfo::GetClassIDInfo method [.NET Framework profiling]
ms.assetid: 9e93b99e-5aca-415c-8e37-7f33753b612d
topic_type:
- apiref
ms.openlocfilehash: 4b9c577fab91e9527a1edc6c93e0618c8fe4e662
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76864076"
---
# <a name="icorprofilerinfogetclassidinfo-method"></a><span data-ttu-id="7e3e8-102">ICorProfilerInfo::GetClassIDInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="7e3e8-102">ICorProfilerInfo::GetClassIDInfo Method</span></span>
<span data-ttu-id="7e3e8-103">지정 된 클래스에 대 한 부모 모듈과 메타 데이터 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7e3e8-103">Gets the parent module and the metadata token for the specified class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e3e8-104">구문</span><span class="sxs-lookup"><span data-stu-id="7e3e8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClassIDInfo(  
    [in]  ClassID   classId,  
    [out] ModuleID  *pModuleId,  
    [out] mdTypeDef *pTypeDefToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7e3e8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7e3e8-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="7e3e8-106">진행 정보를 가져올 클래스의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="7e3e8-106">[in] The ID of the class for which to get the information.</span></span>  
  
 `pModuleId`  
 <span data-ttu-id="7e3e8-107">제한이 클래스의 부모 모듈 ID에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7e3e8-107">[out] A pointer to the ID of the parent module of the class.</span></span>  
  
 `pTypeDefToken`  
 <span data-ttu-id="7e3e8-108">제한이 클래스의 메타 데이터 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7e3e8-108">[out] A pointer to the metadata token for the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7e3e8-109">주의</span><span class="sxs-lookup"><span data-stu-id="7e3e8-109">Remarks</span></span>  
 <span data-ttu-id="7e3e8-110">프로파일러 코드는 [ICorProfilerInfo:: GetModuleMetaData](icorprofilerinfo-getmodulemetadata-method.md) 를 호출 하 여 지정 된 모듈에 대 한 메타 데이터 인터페이스를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e3e8-110">The profiler code can call [ICorProfilerInfo::GetModuleMetaData](icorprofilerinfo-getmodulemetadata-method.md) to obtain a metadata interface for a given module.</span></span> <span data-ttu-id="7e3e8-111">그런 다음 `pTypeDefToken`에서 참조된 위치로 반환되는 메타데이터 토큰을 사용하여 클래스에 대한 메타데이터에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e3e8-111">The metadata token that is returned to the location referenced by `pTypeDefToken` can then be used to access the metadata for the class.</span></span>  
  
 <span data-ttu-id="7e3e8-112">제네릭 형식에 대 한 자세한 정보를 보려면 [ICorProfilerInfo2:: GetClassIDInfo2](icorprofilerinfo2-getclassidinfo2-method.md)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e3e8-112">To get more information for generic types, use [ICorProfilerInfo2::GetClassIDInfo2](icorprofilerinfo2-getclassidinfo2-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e3e8-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7e3e8-113">Requirements</span></span>  
 <span data-ttu-id="7e3e8-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7e3e8-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e3e8-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7e3e8-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7e3e8-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7e3e8-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7e3e8-117">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e3e8-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e3e8-118">참조</span><span class="sxs-lookup"><span data-stu-id="7e3e8-118">See also</span></span>

- [<span data-ttu-id="7e3e8-119">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7e3e8-119">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
