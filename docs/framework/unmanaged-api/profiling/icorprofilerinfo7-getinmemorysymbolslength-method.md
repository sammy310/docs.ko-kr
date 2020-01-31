---
title: ICorProfilerInfo7::GetInMemorySymbolsLength Method
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo7.GetInMemorySymbolsLength
api_location:
- mscorwks.dll
- icorprof.idl
api_type:
- COM
ms.assetid: d62c4a4c-8a62-45aa-8f01-a8387cf36159
ms.openlocfilehash: a675cc301d2dd32f87e3864a3123e2044761ef91
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868358"
---
# <a name="icorprofilerinfo7getinmemorysymbolslength-method"></a><span data-ttu-id="caec1-102">ICorProfilerInfo7::GetInMemorySymbolsLength Method</span><span class="sxs-lookup"><span data-stu-id="caec1-102">ICorProfilerInfo7::GetInMemorySymbolsLength Method</span></span>
<span data-ttu-id="caec1-103">[.NET Framework 4.6.1 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="caec1-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="caec1-104">메모리 내 기호 스트림의 길이를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="caec1-104">Returns the length of an in-memory symbol stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="caec1-105">구문</span><span class="sxs-lookup"><span data-stu-id="caec1-105">Syntax</span></span>  
  
```cpp  
HRESULT GetInMemorySymbolsLength(  
        [in] ModuleID moduleId,  
        [out] DWORD* pCountSymbolBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="caec1-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="caec1-106">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="caec1-107">진행 메모리 내 스트림을 포함 하는 모듈의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="caec1-107">[in] The identifier of the module containing the in-memory stream.</span></span>  
  
 <span data-ttu-id="caec1-108">pCountSymbolBytes</span><span class="sxs-lookup"><span data-stu-id="caec1-108">pCountSymbolBytes</span></span>  
 <span data-ttu-id="caec1-109">제한이 메서드가 반환 될 때 스트림의 길이 (바이트)를 포함 하는 `DWORD` 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="caec1-109">[out] A pointer to a `DWORD` value that, when the method returns, contains the length of the stream in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="caec1-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="caec1-110">Return Value</span></span>  
 <span data-ttu-id="caec1-111">이 메서드는 메모리 스트림의 길이가 0 인 경우에도이를 확인할 수 있는 경우 `S_OK`을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="caec1-111">The method returns `S_OK` if the length of the memory stream can be determined, even if it is zero (0).</span></span>  
  
 <span data-ttu-id="caec1-112">메서드는 <xref:System.Reflection.Emit?displayProperty=nameWithType>를 사용 하 여 메서드를 만든 경우 `CORPROF_E_MODULE_IS_DYNAMIC`를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="caec1-112">The method returns `CORPROF_E_MODULE_IS_DYNAMIC` if the method was created using <xref:System.Reflection.Emit?displayProperty=nameWithType>.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="caec1-113">주의</span><span class="sxs-lookup"><span data-stu-id="caec1-113">Remarks</span></span>  
 <span data-ttu-id="caec1-114">모듈에 메모리 내 기호가 있으면 스트림의 길이가 `pCountSymbolBytes`에 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="caec1-114">If the module has in-memory symbols, the length of the stream is placed in `pCountSymbolBytes`.</span></span> <span data-ttu-id="caec1-115">모듈에 메모리 내 기호가 없으면를 `*pCountSymbolBytes = 0`합니다.</span><span class="sxs-lookup"><span data-stu-id="caec1-115">If the module doesn't have in-memory     symbols, `*pCountSymbolBytes = 0`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="caec1-116">현재 구현에서는 리플렉션 내보내기를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="caec1-116">The current implementation does not support Reflection.Emit.</span></span> <span data-ttu-id="caec1-117">리플렉션을 사용 하 여 모듈을 만든 경우이 메서드는 `CORPROF_E_MODULE_IS_DYNAMIC`를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="caec1-117">If the module was created by using Reflection.Emit, the method returns `CORPROF_E_MODULE_IS_DYNAMIC`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="caec1-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="caec1-118">Requirements</span></span>  
 <span data-ttu-id="caec1-119">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="caec1-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="caec1-120">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="caec1-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="caec1-121">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="caec1-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="caec1-122">**.NET Framework 버전:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="caec1-122">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="caec1-123">참조</span><span class="sxs-lookup"><span data-stu-id="caec1-123">See also</span></span>

- [<span data-ttu-id="caec1-124">ICorProfilerInfo7 인터페이스</span><span class="sxs-lookup"><span data-stu-id="caec1-124">ICorProfilerInfo7 Interface</span></span>](icorprofilerinfo7-interface.md)
