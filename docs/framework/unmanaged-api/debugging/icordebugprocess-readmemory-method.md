---
description: '자세히 알아보기: ICorDebugProcess:: ReadMemory 메서드'
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
ms.openlocfilehash: bdf1bda9df416b6d3142e3ae09955e706f260802
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746804"
---
# <a name="icordebugprocessreadmemory-method"></a><span data-ttu-id="461fd-103">ICorDebugProcess::ReadMemory 메서드</span><span class="sxs-lookup"><span data-stu-id="461fd-103">ICorDebugProcess::ReadMemory Method</span></span>

<span data-ttu-id="461fd-104">이 프로세스에 대해 지정 된 메모리 영역을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="461fd-104">Reads a specified area of memory for this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="461fd-105">구문</span><span class="sxs-lookup"><span data-stu-id="461fd-105">Syntax</span></span>  
  
```cpp  
HRESULT ReadMemory(  
    [in]  CORDB_ADDRESS address,
    [in]  DWORD size,  
    [out, size_is(size), length_is(size)] BYTE buffer[],  
    [out] SIZE_T *read);  
```  
  
## <a name="parameters"></a><span data-ttu-id="461fd-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="461fd-106">Parameters</span></span>  

 `address`  
 <span data-ttu-id="461fd-107">진행 `CORDB_ADDRESS` 읽을 메모리의 기준 주소를 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="461fd-107">[in] A `CORDB_ADDRESS` value that specifies the base address of the memory to be read.</span></span>  
  
 `size`  
 <span data-ttu-id="461fd-108">진행 메모리에서 읽을 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="461fd-108">[in] The number of bytes to be read from memory.</span></span>  
  
 `buffer`  
 <span data-ttu-id="461fd-109">제한이 메모리의 콘텐츠를 받는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="461fd-109">[out] A buffer that receives the contents of the memory.</span></span>  
  
 `read`  
 <span data-ttu-id="461fd-110">제한이 지정 된 버퍼로 전송 된 바이트 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="461fd-110">[out] A pointer to the number of bytes transferred into the specified buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="461fd-111">설명</span><span class="sxs-lookup"><span data-stu-id="461fd-111">Remarks</span></span>  

 <span data-ttu-id="461fd-112">`ReadMemory`메서드는 주로 interop 디버깅에서 디버기의 관리 되지 않는 부분에 사용 되는 메모리 영역을 검사 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="461fd-112">The `ReadMemory` method is primarily intended to be used by interop debugging to inspect memory regions that are being used by the unmanaged portion of the debuggee.</span></span> <span data-ttu-id="461fd-113">이 메서드를 사용 하 여 MSIL (Microsoft 중간 언어) 코드 및 네이티브 JIT 컴파일된 코드를 읽을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="461fd-113">This method can also be used to read Microsoft intermediate language (MSIL) code and native JIT-compiled code.</span></span>  
  
 <span data-ttu-id="461fd-114">관리 되는 모든 중단점은 매개 변수에서 반환 되는 데이터에서 제거 됩니다 `buffer` .</span><span class="sxs-lookup"><span data-stu-id="461fd-114">Any managed breakpoints will be removed from the data that is returned in the `buffer` parameter.</span></span> <span data-ttu-id="461fd-115">[ICorDebugProcess2:: SetUnmanagedBreakpoint](icordebugprocess2-setunmanagedbreakpoint-method.md)에 의해 설정 된 네이티브 중단점에 대해서는 조정이 수행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="461fd-115">No adjustments will be made for native breakpoints set by [ICorDebugProcess2::SetUnmanagedBreakpoint](icordebugprocess2-setunmanagedbreakpoint-method.md).</span></span>  
  
 <span data-ttu-id="461fd-116">프로세스 메모리의 캐싱이 수행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="461fd-116">No caching of process memory is performed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="461fd-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="461fd-117">Requirements</span></span>  

 <span data-ttu-id="461fd-118">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="461fd-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="461fd-119">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="461fd-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="461fd-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="461fd-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="461fd-121">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="461fd-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
