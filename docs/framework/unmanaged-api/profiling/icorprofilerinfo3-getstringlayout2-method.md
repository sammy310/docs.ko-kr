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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e0957228489df30833790e59da1ca597fc1f92f5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62041186"
---
# <a name="icorprofilerinfo3getstringlayout2-method"></a><span data-ttu-id="1da29-102">ICorProfilerInfo3::GetStringLayout2 메서드</span><span class="sxs-lookup"><span data-stu-id="1da29-102">ICorProfilerInfo3::GetStringLayout2 Method</span></span>
<span data-ttu-id="1da29-103">문자열 개체의 레이아웃 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1da29-103">Gets information about the layout of a string object.</span></span> <span data-ttu-id="1da29-104">이 메서드를 대체 합니다 [ICorProfilerInfo2::GetStringLayout](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstringlayout-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="1da29-104">This method supersedes the [ICorProfilerInfo2::GetStringLayout](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstringlayout-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1da29-105">구문</span><span class="sxs-lookup"><span data-stu-id="1da29-105">Syntax</span></span>  
  
```  
HRESULT GetStringLayout2(  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1da29-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1da29-106">Parameters</span></span>  
 `pStringLengthOffset`  
 <span data-ttu-id="1da29-107">[out] 에 상대적인 위치 오프셋에 대 한 포인터를 `ObjectID` 자체 문자열의 길이 저장 하는 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1da29-107">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string itself.</span></span> <span data-ttu-id="1da29-108">로 저장 되는 `DWORD`합니다.</span><span class="sxs-lookup"><span data-stu-id="1da29-108">The length is stored as a `DWORD`.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="1da29-109">[out] 기준으로 버퍼의 오프셋에 대 한 포인터를 `ObjectID` 와이드 문자 문자열을 저장 하는 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1da29-109">[out] A pointer to the offset of the buffer, relative to the `ObjectID` pointer, which stores the string of wide characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1da29-110">설명</span><span class="sxs-lookup"><span data-stu-id="1da29-110">Remarks</span></span>  
 <span data-ttu-id="1da29-111">문자열 수 또는 null로 종료 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1da29-111">Strings may or may not be null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1da29-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1da29-112">Requirements</span></span>  
 <span data-ttu-id="1da29-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1da29-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1da29-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1da29-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1da29-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1da29-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1da29-116">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1da29-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1da29-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="1da29-117">See also</span></span>

- [<span data-ttu-id="1da29-118">ICorProfilerInfo3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1da29-118">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="1da29-119">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1da29-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
