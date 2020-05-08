---
title: ICorDebugDataTarget::ReadVirtual 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget.ReadVirtual Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget::ReadVirtual
helpviewer_keywords:
- ICorDebugDataTarget::ReadVirtual method [.NET Framework debugging]
- ReadVirtual method, ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: 55e57640-b3d2-413d-b4f4-fbc27fb8e37c
topic_type:
- apiref
ms.openlocfilehash: 36a18d92f05db55957bba55de84490c0da1a1f86
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976514"
---
# <a name="icordebugdatatargetreadvirtual-method"></a><span data-ttu-id="59599-102">ICorDebugDataTarget::ReadVirtual 메서드</span><span class="sxs-lookup"><span data-stu-id="59599-102">ICorDebugDataTarget::ReadVirtual Method</span></span>
<span data-ttu-id="59599-103">지정 된 주소에서 시작 하는 연속 메모리 블록을 가져와 제공 된 버퍼에 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="59599-103">Gets a block of contiguous memory starting at the specified address, and returns it in the supplied buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59599-104">구문</span><span class="sxs-lookup"><span data-stu-id="59599-104">Syntax</span></span>  
  
```cpp  
HRESULT ReadVirtual(  
    [in] CORDB_ADDRESS   address,  
    [out, size_is(bytesRequested), length_is(*pBytesRead)]  
          BYTE *     pBuffer,  
    [in]  ULONG32    bytesRequested,  
    [out] ULONG32 *  pBytesRead);  
```  
  
## <a name="parameters"></a><span data-ttu-id="59599-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="59599-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="59599-106">진행 요청 된 메모리의 시작 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="59599-106">[in] The start address of requested memory.</span></span>  
  
 `pbuffer`  
 <span data-ttu-id="59599-107">제한이 메모리가 저장 될 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="59599-107">[out] The buffer where the memory will be stored.</span></span>  
  
 `bytesRequested`  
 <span data-ttu-id="59599-108">진행 대상 주소에서 가져올 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="59599-108">[in] The number of bytes to get from the target address.</span></span>  
  
 `pBytesRead`  
 <span data-ttu-id="59599-109">제한이 실제로 대상 주소에서 읽은 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="59599-109">[out] The number of bytes actually read from the target address.</span></span> <span data-ttu-id="59599-110">이는 보다 `bytesRequested`적을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59599-110">This can be fewer than `bytesRequested`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="59599-111">설명</span><span class="sxs-lookup"><span data-stu-id="59599-111">Remarks</span></span>  
 <span data-ttu-id="59599-112">지정 된 시작 주소에서 첫 번째 바이트를 읽을 수 있는 경우 호출은 null 종료 문자열과 같이 자체 설명 길이를 사용 하 여 데이터 구조를 효율적으로 읽을 수 있도록 성공을 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="59599-112">If the first byte (at the specified start address) can be read, the call should return success (to support efficient reading of data structures with self-describing length, like null-terminated strings).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59599-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="59599-113">Requirements</span></span>  
 <span data-ttu-id="59599-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="59599-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59599-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="59599-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="59599-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="59599-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="59599-117">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59599-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59599-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="59599-118">See also</span></span>

- [<span data-ttu-id="59599-119">ICorDebugDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="59599-119">ICorDebugDataTarget Interface</span></span>](icordebugdatatarget-interface.md)
- [<span data-ttu-id="59599-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="59599-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="59599-121">디버깅</span><span class="sxs-lookup"><span data-stu-id="59599-121">Debugging</span></span>](index.md)
