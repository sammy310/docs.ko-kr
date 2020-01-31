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
ms.openlocfilehash: 537840ac03b4136682b78cb964950ab5670a7d7e
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868618"
---
# <a name="icorprofilerinfo2getstringlayout-method"></a><span data-ttu-id="11aa6-102">ICorProfilerInfo2::GetStringLayout 메서드</span><span class="sxs-lookup"><span data-stu-id="11aa6-102">ICorProfilerInfo2::GetStringLayout Method</span></span>
<span data-ttu-id="11aa6-103">문자열 개체의 레이아웃 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="11aa6-103">Gets information about the layout of a string object.</span></span> <span data-ttu-id="11aa6-104">이 메서드는 .NET Framework 4에서 더 이상 사용 되지 않으며 [ICorProfilerInfo3:: GetStringLayout2](icorprofilerinfo3-getstringlayout2-method.md) 메서드로 대체 됩니다.</span><span class="sxs-lookup"><span data-stu-id="11aa6-104">This method is deprecated in the .NET Framework 4, and is superseded by the [ICorProfilerInfo3::GetStringLayout2](icorprofilerinfo3-getstringlayout2-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11aa6-105">구문</span><span class="sxs-lookup"><span data-stu-id="11aa6-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStringLayout(  
    [out] ULONG *pBufferLengthOffset,  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="11aa6-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="11aa6-106">Parameters</span></span>  
 `pBufferLengthOffset`  
 <span data-ttu-id="11aa6-107">제한이 문자열의 길이를 저장 하는 `ObjectID` 포인터를 기준으로 하는 위치의 오프셋에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="11aa6-107">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string.</span></span> <span data-ttu-id="11aa6-108">길이는 `DWORD`로 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="11aa6-108">The length is stored as a `DWORD`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="11aa6-109">이 매개 변수는 버퍼의 길이가 아니라 문자열 자체의 길이를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="11aa6-109">This parameter returns the length of the string itself, not the length of the buffer.</span></span> <span data-ttu-id="11aa6-110">버퍼의 길이는 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="11aa6-110">The length of the buffer is no longer available.</span></span>  
  
 `PStringLengthOffset`  
 <span data-ttu-id="11aa6-111">제한이 문자열 자체의 길이를 저장 하는 `ObjectID` 포인터를 기준으로 하는 위치의 오프셋에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="11aa6-111">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string itself.</span></span> <span data-ttu-id="11aa6-112">길이는 `DWORD`로 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="11aa6-112">The length is stored as a `DWORD`.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="11aa6-113">제한이 와이드 문자 문자열을 저장 하는 `ObjectID` 포인터를 기준으로 하는 버퍼의 오프셋에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="11aa6-113">[out] A pointer to the offset of the buffer, relative to the `ObjectID` pointer, that stores the string of wide characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="11aa6-114">주의</span><span class="sxs-lookup"><span data-stu-id="11aa6-114">Remarks</span></span>  
 <span data-ttu-id="11aa6-115">`GetStringLayout` 메서드는 `ObjectID` 포인터를 기준으로 다음이 저장 된 위치의 오프셋을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="11aa6-115">The `GetStringLayout` method gets the offsets, relative to the `ObjectID` pointer, of the locations in which the following are stored:</span></span>  
  
- <span data-ttu-id="11aa6-116">문자열 버퍼의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="11aa6-116">The length of the string's buffer.</span></span>  
  
- <span data-ttu-id="11aa6-117">문자열 자체의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="11aa6-117">The length of the string itself.</span></span>  
  
- <span data-ttu-id="11aa6-118">와이드 문자의 실제 문자열을 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="11aa6-118">The buffer that contains the actual string of wide characters.</span></span>  
  
 <span data-ttu-id="11aa6-119">문자열이 null로 종료 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11aa6-119">Strings may be null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11aa6-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="11aa6-120">Requirements</span></span>  
 <span data-ttu-id="11aa6-121">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="11aa6-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11aa6-122">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="11aa6-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="11aa6-123">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="11aa6-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="11aa6-124">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11aa6-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11aa6-125">참조</span><span class="sxs-lookup"><span data-stu-id="11aa6-125">See also</span></span>

- [<span data-ttu-id="11aa6-126">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="11aa6-126">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="11aa6-127">ICorProfilerInfo2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="11aa6-127">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
