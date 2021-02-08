---
description: '자세히 알아보기: ICorProfilerInfo:: GetObjectSize 메서드'
title: ICorProfilerInfo::GetObjectSize 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetObjectSize
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetObjectSize
helpviewer_keywords:
- GetObjectSize method [.NET Framework profiling]
- ICorProfilerInfo::GetObjectSize method [.NET Framework profiling]
ms.assetid: 9f02e763-73f7-42cb-a41c-f78499d9482c
topic_type:
- apiref
ms.openlocfilehash: c762b43e87c6f25b301f3f677728ca8cbe19b138
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99788633"
---
# <a name="icorprofilerinfogetobjectsize-method"></a><span data-ttu-id="a4804-103">ICorProfilerInfo::GetObjectSize 메서드</span><span class="sxs-lookup"><span data-stu-id="a4804-103">ICorProfilerInfo::GetObjectSize Method</span></span>

<span data-ttu-id="a4804-104">지정 된 개체의 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a4804-104">Gets the size of a specified object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4804-105">구문</span><span class="sxs-lookup"><span data-stu-id="a4804-105">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectSize(  
    [in]  ObjectID objectId,  
    [out] ULONG  *pcSize);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a4804-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a4804-106">Parameters</span></span>  

 `objectId`  
 <span data-ttu-id="a4804-107">진행 개체의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="a4804-107">[in] The ID of the object.</span></span>  
  
 `pcSize`  
 <span data-ttu-id="a4804-108">제한이 개체의 크기 (바이트)에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a4804-108">[out] A pointer to the object's size, in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a4804-109">설명</span><span class="sxs-lookup"><span data-stu-id="a4804-109">Remarks</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="a4804-110">이 메서드는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4804-110">This method is obsolete.</span></span> <span data-ttu-id="a4804-111">64 비트 플랫폼에서 4GB 보다 큰 개체에 대 한 COR_E_OVERFLOW를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4804-111">It returns COR_E_OVERFLOW for objects greater than 4GB on 64-bit platforms.</span></span> <span data-ttu-id="a4804-112">대신  [ICorProfilerInfo4:: GetObjectSize2](icorprofilerinfo4-getobjectsize2-method.md) 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4804-112">Use the  [ICorProfilerInfo4::GetObjectSize2](icorprofilerinfo4-getobjectsize2-method.md) method instead.</span></span>  
  
 <span data-ttu-id="a4804-113">동일한 유형의 개체 마다 크기가 같은 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="a4804-113">Different objects of the same types often have the same size.</span></span> <span data-ttu-id="a4804-114">그러나 배열 또는 문자열과 같은 일부 형식에는 각 개체에 대해 다른 크기를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4804-114">However, some types, such as arrays or strings, may have a different size for each object.</span></span>  
  
 <span data-ttu-id="a4804-115">메서드에서 반환 되는 크기에는 `GetObjectSize` 개체가 가비지 컬렉션 힙에 있는 후에 나타날 수 있는 맞춤 패딩이 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4804-115">The size returned by the `GetObjectSize` method does not include any alignment padding that may appear after the object is on the garbage collection heap.</span></span> <span data-ttu-id="a4804-116">메서드를 사용 하 여 `GetObjectSize` 가비지 수집 힙의 개체에서 개체로 이동 하는 경우 필요에 따라 맞춤 안쪽 여백을 수동으로 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4804-116">If you use the `GetObjectSize` method to advance from object to object on the garbage collection heap, add alignment padding manually, as necessary.</span></span>  
  
- <span data-ttu-id="a4804-117">32 비트 Windows, COR_PRF_GC_GEN_0, COR_PRF_GC_GEN_1 및 COR_PRF_GC_GEN_2 4 바이트 맞춤을 사용 하 고 COR_PRF_GC_LARGE_OBJECT_HEAP에서는 8 바이트 맞춤을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4804-117">On 32-bit Windows, COR_PRF_GC_GEN_0, COR_PRF_GC_GEN_1, and COR_PRF_GC_GEN_2 use 4-byte alignment, and COR_PRF_GC_LARGE_OBJECT_HEAP uses 8-byte alignment.</span></span>  
  
- <span data-ttu-id="a4804-118">64 비트 Windows에서는 맞춤이 항상 8 바이트입니다.</span><span class="sxs-lookup"><span data-stu-id="a4804-118">On 64-bit Windows, the alignment is always 8 bytes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4804-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a4804-119">Requirements</span></span>  

 <span data-ttu-id="a4804-120">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a4804-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4804-121">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a4804-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a4804-122">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a4804-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a4804-123">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4804-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4804-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a4804-124">See also</span></span>

- [<span data-ttu-id="a4804-125">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a4804-125">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
