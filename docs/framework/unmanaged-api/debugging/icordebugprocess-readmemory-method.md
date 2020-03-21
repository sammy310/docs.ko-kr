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
ms.openlocfilehash: 383e3f8990a1f355c94ff5e9f9daa69bdbdd97bb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178658"
---
# <a name="icordebugprocessreadmemory-method"></a><span data-ttu-id="f9c4e-102">ICorDebugProcess::ReadMemory 메서드</span><span class="sxs-lookup"><span data-stu-id="f9c4e-102">ICorDebugProcess::ReadMemory Method</span></span>
<span data-ttu-id="f9c4e-103">이 프로세스에 대해 지정된 메모리 영역을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="f9c4e-103">Reads a specified area of memory for this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9c4e-104">구문</span><span class="sxs-lookup"><span data-stu-id="f9c4e-104">Syntax</span></span>  
  
```cpp  
HRESULT ReadMemory(  
    [in]  CORDB_ADDRESS address,
    [in]  DWORD size,  
    [out, size_is(size), length_is(size)] BYTE buffer[],  
    [out] SIZE_T *read);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f9c4e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f9c4e-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="f9c4e-106">【인】 읽을 `CORDB_ADDRESS` 메모리의 기본 주소를 지정하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f9c4e-106">[in] A `CORDB_ADDRESS` value that specifies the base address of the memory to be read.</span></span>  
  
 `size`  
 <span data-ttu-id="f9c4e-107">【인】 메모리에서 읽을 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="f9c4e-107">[in] The number of bytes to be read from memory.</span></span>  
  
 `buffer`  
 <span data-ttu-id="f9c4e-108">【아웃】 메모리의 내용을 받는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="f9c4e-108">[out] A buffer that receives the contents of the memory.</span></span>  
  
 `read`  
 <span data-ttu-id="f9c4e-109">【아웃】 지정된 버퍼로 전송된 바이트 수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f9c4e-109">[out] A pointer to the number of bytes transferred into the specified buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f9c4e-110">설명</span><span class="sxs-lookup"><span data-stu-id="f9c4e-110">Remarks</span></span>  
 <span data-ttu-id="f9c4e-111">이 `ReadMemory` 메서드는 주로 디버지의 관리되지 않는 부분에서 사용 중인 메모리 영역을 검사하기 위해 interop 디버깅에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9c4e-111">The `ReadMemory` method is primarily intended to be used by interop debugging to inspect memory regions that are being used by the unmanaged portion of the debuggee.</span></span> <span data-ttu-id="f9c4e-112">이 메서드는 Microsoft 중간 언어(MSIL) 코드와 기본 JIT 컴파일된 코드를 읽는 데 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9c4e-112">This method can also be used to read Microsoft intermediate language (MSIL) code and native JIT-compiled code.</span></span>  
  
 <span data-ttu-id="f9c4e-113">관리되는 모든 중단점은 `buffer` 매개 변수에 반환되는 데이터에서 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9c4e-113">Any managed breakpoints will be removed from the data that is returned in the `buffer` parameter.</span></span> <span data-ttu-id="f9c4e-114">[ICorDebugProcess2:SetUnmanaged 중단점에서](icordebugprocess2-setunmanagedbreakpoint-method.md)설정한 네이티브 중단점에 대해 조정이 수행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f9c4e-114">No adjustments will be made for native breakpoints set by [ICorDebugProcess2::SetUnmanagedBreakpoint](icordebugprocess2-setunmanagedbreakpoint-method.md).</span></span>  
  
 <span data-ttu-id="f9c4e-115">프로세스 메모리의 캐싱이 수행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f9c4e-115">No caching of process memory is performed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9c4e-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f9c4e-116">Requirements</span></span>  
 <span data-ttu-id="f9c4e-117">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f9c4e-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9c4e-118">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f9c4e-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f9c4e-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f9c4e-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f9c4e-120">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9c4e-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
