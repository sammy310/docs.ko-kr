---
title: 'ICorDebugMutableDataTarget:: WriteVirtual 메서드'
ms.date: 03/30/2017
ms.assetid: 80833648-58a7-491a-8dc8-9a48e9bb3adc
ms.openlocfilehash: 5947caa8dfb97574bb4b3c5634d962df153211c7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132687"
---
# <a name="icordebugmutabledatatargetwritevirtual-method"></a><span data-ttu-id="509cd-102">ICorDebugMutableDataTarget:: WriteVirtual 메서드</span><span class="sxs-lookup"><span data-stu-id="509cd-102">ICorDebugMutableDataTarget::WriteVirtual Method</span></span>
<span data-ttu-id="509cd-103">대상 프로세스 주소 공간에 메모리를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="509cd-103">Writes memory into the target process address space.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="509cd-104">구문</span><span class="sxs-lookup"><span data-stu-id="509cd-104">Syntax</span></span>  
  
```cpp  
HRESULT WriteVirtual(  
   [in] CORDB_ADDRESS address,  
   [in, size_is(bytesRequested)] const BYTE * pBuffer,  
   [in] ULONG32 bytesRequested);  
```  
  
## <a name="parameters"></a><span data-ttu-id="509cd-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="509cd-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="509cd-106">[in] `pBuffer`의 콘텐츠를 쓸 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="509cd-106">[in] The address at which to write the contents of `pBuffer`.</span></span>  
  
 `pBuffer`  
 <span data-ttu-id="509cd-107">[in] 쓸 바이트를 포함하는 바이트 배열에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="509cd-107">[in] A pointer to a byte array that contains the bytes to be written.</span></span>  
  
 `address`  
 <span data-ttu-id="509cd-108">[in] `pBuffer`의 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="509cd-108">[in] The number of bytes in `pBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="509cd-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="509cd-109">Return Value</span></span>  
 <span data-ttu-id="509cd-110">성공하면 `S_OK`이고 실패하면 다른 `HRESULT`입니다.</span><span class="sxs-lookup"><span data-stu-id="509cd-110">`S_OK` on success, or any other `HRESULT` on failure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="509cd-111">주의</span><span class="sxs-lookup"><span data-stu-id="509cd-111">Remarks</span></span>  
 <span data-ttu-id="509cd-112">바이트를 쓸 수 없는 경우 대상 주소 공간의 바이트를 변경하지 않고 메서드 호출이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="509cd-112">If any bytes cannot be written, the method call fails without changing any bytes in the target address space.</span></span> <span data-ttu-id="509cd-113">그러지 않으면 대상이 일관성 없는 상태가 되어 이후 디버깅을 신뢰할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="509cd-113">(Otherwise, the target would be in an inconsistent state that makes further debugging unreliable.)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="509cd-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="509cd-114">Requirements</span></span>  
 <span data-ttu-id="509cd-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="509cd-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="509cd-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="509cd-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="509cd-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="509cd-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="509cd-118">**.NET Framework 버전:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="509cd-118">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="509cd-119">참조</span><span class="sxs-lookup"><span data-stu-id="509cd-119">See also</span></span>

- [<span data-ttu-id="509cd-120">ICorDebugMutableDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="509cd-120">ICorDebugMutableDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)
- [<span data-ttu-id="509cd-121">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="509cd-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
