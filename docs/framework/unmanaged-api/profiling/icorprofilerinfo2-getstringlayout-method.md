---
title: ICorProfilerInfo2::GetStringLayout 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetStringLayout
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetStringLayout
helpviewer_keywords:
- GetStringLayout method [.NET Framework profiling]
- ICorProfilerInfo2::GetStringLayout method [.NET Framework profiling]
ms.assetid: 43189651-a535-4803-a1d1-f1c427ace2ca
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4d4efa7cb3bc98c54be2889855c3b756fdbf2847
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782239"
---
# <a name="icorprofilerinfo2getstringlayout-method"></a><span data-ttu-id="f0ece-102">ICorProfilerInfo2::GetStringLayout 메서드</span><span class="sxs-lookup"><span data-stu-id="f0ece-102">ICorProfilerInfo2::GetStringLayout Method</span></span>
<span data-ttu-id="f0ece-103">문자열 개체의 레이아웃 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f0ece-103">Gets information about the layout of a string object.</span></span> <span data-ttu-id="f0ece-104">이 메서드는.NET Framework 4에서는 사용 되지 않습니다 및으로 인해 교체 되는 [ICorProfilerInfo3::GetStringLayout2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getstringlayout2-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="f0ece-104">This method is deprecated in the .NET Framework 4, and is superseded by the [ICorProfilerInfo3::GetStringLayout2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getstringlayout2-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0ece-105">구문</span><span class="sxs-lookup"><span data-stu-id="f0ece-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStringLayout(  
    [out] ULONG *pBufferLengthOffset,  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0ece-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f0ece-106">Parameters</span></span>  
 `pBufferLengthOffset`  
 <span data-ttu-id="f0ece-107">[out] 에 상대적인 위치 오프셋에 대 한 포인터를 `ObjectID` 문자열의 길이 저장 하는 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f0ece-107">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string.</span></span> <span data-ttu-id="f0ece-108">로 저장 되는 `DWORD`합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ece-108">The length is stored as a `DWORD`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f0ece-109">이 매개 변수 버퍼의 길이가 아닌 문자열 자체의 길이 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ece-109">This parameter returns the length of the string itself, not the length of the buffer.</span></span> <span data-ttu-id="f0ece-110">버퍼의 길이가 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ece-110">The length of the buffer is no longer available.</span></span>  
  
 `PStringLengthOffset`  
 <span data-ttu-id="f0ece-111">[out] 에 상대적인 위치 오프셋에 대 한 포인터를 `ObjectID` 자체 문자열의 길이 저장 하는 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f0ece-111">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string itself.</span></span> <span data-ttu-id="f0ece-112">로 저장 되는 `DWORD`합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ece-112">The length is stored as a `DWORD`.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="f0ece-113">[out] 기준으로 버퍼의 오프셋에 대 한 포인터를 `ObjectID` 와이드 문자 문자열을 저장 하는 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f0ece-113">[out] A pointer to the offset of the buffer, relative to the `ObjectID` pointer, that stores the string of wide characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0ece-114">설명</span><span class="sxs-lookup"><span data-stu-id="f0ece-114">Remarks</span></span>  
 <span data-ttu-id="f0ece-115">합니다 `GetStringLayout` 메서드는 상대적으로 오프셋을 가져옵니다는 `ObjectID` 다음 저장 되는 위치의 포인터:</span><span class="sxs-lookup"><span data-stu-id="f0ece-115">The `GetStringLayout` method gets the offsets, relative to the `ObjectID` pointer, of the locations in which the following are stored:</span></span>  
  
- <span data-ttu-id="f0ece-116">문자열 버퍼의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="f0ece-116">The length of the string's buffer.</span></span>  
  
- <span data-ttu-id="f0ece-117">자체 문자열의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="f0ece-117">The length of the string itself.</span></span>  
  
- <span data-ttu-id="f0ece-118">와이드 문자의 실제 문자열을 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="f0ece-118">The buffer that contains the actual string of wide characters.</span></span>  
  
 <span data-ttu-id="f0ece-119">문자열은 null로 종료 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ece-119">Strings may be null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0ece-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f0ece-120">Requirements</span></span>  
 <span data-ttu-id="f0ece-121">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f0ece-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0ece-122">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f0ece-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f0ece-123">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f0ece-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f0ece-124">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0ece-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0ece-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="f0ece-125">See also</span></span>

- [<span data-ttu-id="f0ece-126">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f0ece-126">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="f0ece-127">ICorProfilerInfo2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f0ece-127">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
