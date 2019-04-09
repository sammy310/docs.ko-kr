---
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d366a0093ca82d2e5b3c40729777a1b6c0766bda
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59092203"
---
# <a name="icorprofilerinfogetobjectsize-method"></a><span data-ttu-id="cf896-102">ICorProfilerInfo::GetObjectSize 메서드</span><span class="sxs-lookup"><span data-stu-id="cf896-102">ICorProfilerInfo::GetObjectSize Method</span></span>
<span data-ttu-id="cf896-103">지정된 된 개체의 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cf896-103">Gets the size of a specified object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf896-104">구문</span><span class="sxs-lookup"><span data-stu-id="cf896-104">Syntax</span></span>  
  
```  
HRESULT GetObjectSize(  
    [in]  ObjectID objectId,  
    [out] ULONG  *pcSize);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf896-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cf896-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="cf896-106">[in] 개체의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="cf896-106">[in] The ID of the object.</span></span>  
  
 `pcSize`  
 <span data-ttu-id="cf896-107">[out] 개체의 크기 (바이트)에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="cf896-107">[out] A pointer to the object's size, in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cf896-108">설명</span><span class="sxs-lookup"><span data-stu-id="cf896-108">Remarks</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="cf896-109">이 메서드는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cf896-109">This method is obsolete.</span></span> <span data-ttu-id="cf896-110">반환 COR_E_OVERFLOW 개체에 대 한 4GB 보다 큰 64 비트 플랫폼에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf896-110">It returns COR_E_OVERFLOW for objects greater than 4GB on 64-bit platforms.</span></span> <span data-ttu-id="cf896-111">사용 된 [ICorProfilerInfo4::GetObjectSize2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getobjectsize2-method.md) 메서드 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf896-111">Use the  [ICorProfilerInfo4::GetObjectSize2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getobjectsize2-method.md) method instead.</span></span>  
  
 <span data-ttu-id="cf896-112">동일한 유형의 다른 개체에는 동일한 크기가 있는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="cf896-112">Different objects of the same types often have the same size.</span></span> <span data-ttu-id="cf896-113">그러나 배열 또는 문자열 같은 일부 유형의 경우에 각 개체에 대해 다른 크기가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf896-113">However, some types, such as arrays or strings, may have a different size for each object.</span></span>  
  
 <span data-ttu-id="cf896-114">반환 되는 크기는 `GetObjectSize` 메서드는 개체가 가비지 컬렉션 힙에 후 나타날 수 있는 맞춤 안쪽 여백을 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cf896-114">The size returned by the `GetObjectSize` method does not include any alignment padding that may appear after the object is on the garbage collection heap.</span></span> <span data-ttu-id="cf896-115">사용 하는 경우는 `GetObjectSize` 메서드 가비지 컬렉션 힙에 개체에서 개체를 수동으로 필요에 따라 패딩 맞춤을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf896-115">If you use the `GetObjectSize` method to advance from object to object on the garbage collection heap, add alignment padding manually, as necessary.</span></span>  
  
-   <span data-ttu-id="cf896-116">32 비트 Windows에서 COR_PRF_GC_GEN_0, COR_PRF_GC_GEN_1, 및 COR_PRF_GC_GEN_2 4 바이트 맞춤을 사용 하 고 COR_PRF_GC_LARGE_OBJECT_HEAP 8 바이트 정렬을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf896-116">On 32-bit Windows, COR_PRF_GC_GEN_0, COR_PRF_GC_GEN_1, and COR_PRF_GC_GEN_2 use 4-byte alignment, and COR_PRF_GC_LARGE_OBJECT_HEAP uses 8-byte alignment.</span></span>  
  
-   <span data-ttu-id="cf896-117">64 비트 Windows에 맞춤은 항상 8 바이트입니다.</span><span class="sxs-lookup"><span data-stu-id="cf896-117">On 64-bit Windows, the alignment is always 8 bytes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf896-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cf896-118">Requirements</span></span>  
 <span data-ttu-id="cf896-119">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="cf896-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf896-120">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cf896-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cf896-121">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cf896-121">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="cf896-122">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="cf896-122">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="cf896-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="cf896-123">See also</span></span>

- [<span data-ttu-id="cf896-124">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cf896-124">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
