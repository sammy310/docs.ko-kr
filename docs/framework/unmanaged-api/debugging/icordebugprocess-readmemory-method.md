---
title: ICorDebugProcess::ReadMemory 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.ReadMemory
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::ReadMemory
helpviewer_keywords:
- ReadMemory method [.NET Framework debugging]
- ICorDebugProcess::ReadMemory method [.NET Framework debugging]
ms.assetid: 28e4b2f6-9589-445c-be24-24a3306795e7
topic_type:
- apiref
ms.openlocfilehash: ccd2350589126109ff11da439a8b83abfc4b91fa
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210477"
---
# <a name="icordebugprocessreadmemory-method"></a><span data-ttu-id="14373-102">ICorDebugProcess::ReadMemory 메서드</span><span class="sxs-lookup"><span data-stu-id="14373-102">ICorDebugProcess::ReadMemory Method</span></span>
<span data-ttu-id="14373-103">이 프로세스에 대해 지정 된 메모리 영역을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="14373-103">Reads a specified area of memory for this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14373-104">구문</span><span class="sxs-lookup"><span data-stu-id="14373-104">Syntax</span></span>  
  
```cpp  
HRESULT ReadMemory(  
    [in]  CORDB_ADDRESS address,
    [in]  DWORD size,  
    [out, size_is(size), length_is(size)] BYTE buffer[],  
    [out] SIZE_T *read);  
```  
  
## <a name="parameters"></a><span data-ttu-id="14373-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="14373-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="14373-106">진행 `CORDB_ADDRESS`읽을 메모리의 기준 주소를 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="14373-106">[in] A `CORDB_ADDRESS` value that specifies the base address of the memory to be read.</span></span>  
  
 `size`  
 <span data-ttu-id="14373-107">진행 메모리에서 읽을 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="14373-107">[in] The number of bytes to be read from memory.</span></span>  
  
 `buffer`  
 <span data-ttu-id="14373-108">제한이 메모리의 콘텐츠를 받는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="14373-108">[out] A buffer that receives the contents of the memory.</span></span>  
  
 `read`  
 <span data-ttu-id="14373-109">제한이 지정 된 버퍼로 전송 된 바이트 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="14373-109">[out] A pointer to the number of bytes transferred into the specified buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="14373-110">설명</span><span class="sxs-lookup"><span data-stu-id="14373-110">Remarks</span></span>  
 <span data-ttu-id="14373-111">`ReadMemory`메서드는 주로 interop 디버깅에서 디버기의 관리 되지 않는 부분에 사용 되는 메모리 영역을 검사 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14373-111">The `ReadMemory` method is primarily intended to be used by interop debugging to inspect memory regions that are being used by the unmanaged portion of the debuggee.</span></span> <span data-ttu-id="14373-112">이 메서드를 사용 하 여 MSIL (Microsoft 중간 언어) 코드 및 네이티브 JIT 컴파일된 코드를 읽을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14373-112">This method can also be used to read Microsoft intermediate language (MSIL) code and native JIT-compiled code.</span></span>  
  
 <span data-ttu-id="14373-113">관리 되는 모든 중단점은 매개 변수에서 반환 되는 데이터에서 제거 됩니다 `buffer` .</span><span class="sxs-lookup"><span data-stu-id="14373-113">Any managed breakpoints will be removed from the data that is returned in the `buffer` parameter.</span></span> <span data-ttu-id="14373-114">[ICorDebugProcess2:: SetUnmanagedBreakpoint](icordebugprocess2-setunmanagedbreakpoint-method.md)에 의해 설정 된 네이티브 중단점에 대해서는 조정이 수행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14373-114">No adjustments will be made for native breakpoints set by [ICorDebugProcess2::SetUnmanagedBreakpoint](icordebugprocess2-setunmanagedbreakpoint-method.md).</span></span>  
  
 <span data-ttu-id="14373-115">프로세스 메모리의 캐싱이 수행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14373-115">No caching of process memory is performed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14373-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="14373-116">Requirements</span></span>  
 <span data-ttu-id="14373-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="14373-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14373-118">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="14373-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="14373-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="14373-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="14373-120">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14373-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
