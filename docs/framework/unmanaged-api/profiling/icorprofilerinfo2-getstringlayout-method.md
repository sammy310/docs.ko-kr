---
description: '자세히 알아보기: ICorProfilerInfo2:: GetStringLayout 메서드'
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
ms.openlocfilehash: 145d748d756fd30ef0522d1c516f8f63ca604545
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99716369"
---
# <a name="icorprofilerinfo2getstringlayout-method"></a><span data-ttu-id="079b0-103">ICorProfilerInfo2::GetStringLayout 메서드</span><span class="sxs-lookup"><span data-stu-id="079b0-103">ICorProfilerInfo2::GetStringLayout Method</span></span>

<span data-ttu-id="079b0-104">문자열 개체의 레이아웃 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="079b0-104">Gets information about the layout of a string object.</span></span> <span data-ttu-id="079b0-105">이 메서드는 .NET Framework 4에서 더 이상 사용 되지 않으며 [ICorProfilerInfo3:: GetStringLayout2](icorprofilerinfo3-getstringlayout2-method.md) 메서드로 대체 됩니다.</span><span class="sxs-lookup"><span data-stu-id="079b0-105">This method is deprecated in the .NET Framework 4, and is superseded by the [ICorProfilerInfo3::GetStringLayout2](icorprofilerinfo3-getstringlayout2-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="079b0-106">구문</span><span class="sxs-lookup"><span data-stu-id="079b0-106">Syntax</span></span>  
  
```cpp  
HRESULT GetStringLayout(  
    [out] ULONG *pBufferLengthOffset,  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="079b0-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="079b0-107">Parameters</span></span>  

 `pBufferLengthOffset`  
 <span data-ttu-id="079b0-108">제한이 `ObjectID` 문자열의 길이를 저장 하는 포인터를 기준으로 하는 위치의 오프셋에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="079b0-108">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string.</span></span> <span data-ttu-id="079b0-109">길이는로 저장 됩니다 `DWORD` .</span><span class="sxs-lookup"><span data-stu-id="079b0-109">The length is stored as a `DWORD`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="079b0-110">이 매개 변수는 버퍼의 길이가 아니라 문자열 자체의 길이를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="079b0-110">This parameter returns the length of the string itself, not the length of the buffer.</span></span> <span data-ttu-id="079b0-111">버퍼의 길이는 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="079b0-111">The length of the buffer is no longer available.</span></span>  
  
 `PStringLengthOffset`  
 <span data-ttu-id="079b0-112">제한이 `ObjectID` 문자열 자체의 길이를 저장 하는 포인터를 기준으로 하는 위치의 오프셋에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="079b0-112">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string itself.</span></span> <span data-ttu-id="079b0-113">길이는로 저장 됩니다 `DWORD` .</span><span class="sxs-lookup"><span data-stu-id="079b0-113">The length is stored as a `DWORD`.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="079b0-114">제한이 `ObjectID` 와이드 문자 문자열을 저장 하는 포인터를 기준으로 하는 버퍼의 오프셋에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="079b0-114">[out] A pointer to the offset of the buffer, relative to the `ObjectID` pointer, that stores the string of wide characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="079b0-115">설명</span><span class="sxs-lookup"><span data-stu-id="079b0-115">Remarks</span></span>  

 <span data-ttu-id="079b0-116">`GetStringLayout`메서드는 다음이 저장 된 위치에 대 한 포인터에 상대적인 오프셋을 가져옵니다 `ObjectID` .</span><span class="sxs-lookup"><span data-stu-id="079b0-116">The `GetStringLayout` method gets the offsets, relative to the `ObjectID` pointer, of the locations in which the following are stored:</span></span>  
  
- <span data-ttu-id="079b0-117">문자열 버퍼의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="079b0-117">The length of the string's buffer.</span></span>  
  
- <span data-ttu-id="079b0-118">문자열 자체의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="079b0-118">The length of the string itself.</span></span>  
  
- <span data-ttu-id="079b0-119">와이드 문자의 실제 문자열을 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="079b0-119">The buffer that contains the actual string of wide characters.</span></span>  
  
 <span data-ttu-id="079b0-120">문자열이 null로 종료 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="079b0-120">Strings may be null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="079b0-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="079b0-121">Requirements</span></span>  

 <span data-ttu-id="079b0-122">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="079b0-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="079b0-123">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="079b0-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="079b0-124">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="079b0-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="079b0-125">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="079b0-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="079b0-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="079b0-126">See also</span></span>

- [<span data-ttu-id="079b0-127">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="079b0-127">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="079b0-128">ICorProfilerInfo2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="079b0-128">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
