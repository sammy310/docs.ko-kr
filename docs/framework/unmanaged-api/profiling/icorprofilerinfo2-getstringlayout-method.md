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
ms.openlocfilehash: 71e2bc1d60e050d817429db5bc6926b3b16c637c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431412"
---
# <a name="icorprofilerinfo2getstringlayout-method"></a><span data-ttu-id="e490c-102">ICorProfilerInfo2::GetStringLayout 메서드</span><span class="sxs-lookup"><span data-stu-id="e490c-102">ICorProfilerInfo2::GetStringLayout Method</span></span>
<span data-ttu-id="e490c-103">문자열 개체의 레이아웃 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e490c-103">Gets information about the layout of a string object.</span></span> <span data-ttu-id="e490c-104">이 메서드는 .NET Framework 4에서 더 이상 사용 되지 않으며 [ICorProfilerInfo3:: GetStringLayout2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getstringlayout2-method.md) 메서드로 대체 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e490c-104">This method is deprecated in the .NET Framework 4, and is superseded by the [ICorProfilerInfo3::GetStringLayout2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getstringlayout2-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e490c-105">구문</span><span class="sxs-lookup"><span data-stu-id="e490c-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStringLayout(  
    [out] ULONG *pBufferLengthOffset,  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e490c-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e490c-106">Parameters</span></span>  
 `pBufferLengthOffset`  
 <span data-ttu-id="e490c-107">제한이 문자열의 길이를 저장 하는 `ObjectID` 포인터를 기준으로 하는 위치의 오프셋에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e490c-107">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string.</span></span> <span data-ttu-id="e490c-108">길이는 `DWORD`로 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e490c-108">The length is stored as a `DWORD`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e490c-109">이 매개 변수는 버퍼의 길이가 아니라 문자열 자체의 길이를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e490c-109">This parameter returns the length of the string itself, not the length of the buffer.</span></span> <span data-ttu-id="e490c-110">버퍼의 길이는 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e490c-110">The length of the buffer is no longer available.</span></span>  
  
 `PStringLengthOffset`  
 <span data-ttu-id="e490c-111">제한이 문자열 자체의 길이를 저장 하는 `ObjectID` 포인터를 기준으로 하는 위치의 오프셋에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e490c-111">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string itself.</span></span> <span data-ttu-id="e490c-112">길이는 `DWORD`로 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e490c-112">The length is stored as a `DWORD`.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="e490c-113">제한이 와이드 문자 문자열을 저장 하는 `ObjectID` 포인터를 기준으로 하는 버퍼의 오프셋에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e490c-113">[out] A pointer to the offset of the buffer, relative to the `ObjectID` pointer, that stores the string of wide characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e490c-114">설명</span><span class="sxs-lookup"><span data-stu-id="e490c-114">Remarks</span></span>  
 <span data-ttu-id="e490c-115">`GetStringLayout` 메서드는 `ObjectID` 포인터를 기준으로 다음이 저장 된 위치의 오프셋을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e490c-115">The `GetStringLayout` method gets the offsets, relative to the `ObjectID` pointer, of the locations in which the following are stored:</span></span>  
  
- <span data-ttu-id="e490c-116">문자열 버퍼의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="e490c-116">The length of the string's buffer.</span></span>  
  
- <span data-ttu-id="e490c-117">문자열 자체의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="e490c-117">The length of the string itself.</span></span>  
  
- <span data-ttu-id="e490c-118">와이드 문자의 실제 문자열을 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="e490c-118">The buffer that contains the actual string of wide characters.</span></span>  
  
 <span data-ttu-id="e490c-119">문자열이 null로 종료 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e490c-119">Strings may be null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e490c-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e490c-120">Requirements</span></span>  
 <span data-ttu-id="e490c-121">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e490c-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e490c-122">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e490c-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e490c-123">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e490c-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e490c-124">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e490c-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e490c-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="e490c-125">See also</span></span>

- [<span data-ttu-id="e490c-126">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e490c-126">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="e490c-127">ICorProfilerInfo2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e490c-127">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
