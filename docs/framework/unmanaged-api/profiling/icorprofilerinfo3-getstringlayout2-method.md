---
title: ICorProfilerInfo3::GetStringLayout2 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetStringLayout2 Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetStringLayout2
helpviewer_keywords:
- ICorProfilerInfo3::GetStringLayout2 method [.NET Framework profiling]
- GetStringLayout2 method [.NET Framework profiling]
ms.assetid: 1a268496-ee51-4d84-8700-ee56fd0c499d
topic_type:
- apiref
ms.openlocfilehash: 1e3dc4735af68da7f76fc6fce84d2dd4ac3f576e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449659"
---
# <a name="icorprofilerinfo3getstringlayout2-method"></a><span data-ttu-id="c3221-102">ICorProfilerInfo3::GetStringLayout2 메서드</span><span class="sxs-lookup"><span data-stu-id="c3221-102">ICorProfilerInfo3::GetStringLayout2 Method</span></span>
<span data-ttu-id="c3221-103">문자열 개체의 레이아웃 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c3221-103">Gets information about the layout of a string object.</span></span> <span data-ttu-id="c3221-104">This method supersedes the [ICorProfilerInfo2::GetStringLayout](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstringlayout-method.md) method.</span><span class="sxs-lookup"><span data-stu-id="c3221-104">This method supersedes the [ICorProfilerInfo2::GetStringLayout](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstringlayout-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3221-105">구문</span><span class="sxs-lookup"><span data-stu-id="c3221-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStringLayout2(  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3221-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c3221-106">Parameters</span></span>  
 `pStringLengthOffset`  
 <span data-ttu-id="c3221-107">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string itself.</span><span class="sxs-lookup"><span data-stu-id="c3221-107">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string itself.</span></span> <span data-ttu-id="c3221-108">The length is stored as a `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="c3221-108">The length is stored as a `DWORD`.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="c3221-109">[out] A pointer to the offset of the buffer, relative to the `ObjectID` pointer, which stores the string of wide characters.</span><span class="sxs-lookup"><span data-stu-id="c3221-109">[out] A pointer to the offset of the buffer, relative to the `ObjectID` pointer, which stores the string of wide characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c3221-110">주의</span><span class="sxs-lookup"><span data-stu-id="c3221-110">Remarks</span></span>  
 <span data-ttu-id="c3221-111">Strings may or may not be null-terminated.</span><span class="sxs-lookup"><span data-stu-id="c3221-111">Strings may or may not be null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3221-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c3221-112">Requirements</span></span>  
 <span data-ttu-id="c3221-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c3221-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3221-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c3221-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c3221-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c3221-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c3221-116">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3221-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3221-117">참조</span><span class="sxs-lookup"><span data-stu-id="c3221-117">See also</span></span>

- [<span data-ttu-id="c3221-118">ICorProfilerInfo3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c3221-118">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="c3221-119">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c3221-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
