---
title: 'ICorDebugMemoryBuffer:: GetStartAddress 메서드'
ms.date: 03/30/2017
ms.assetid: f804d9ab-8c88-44f0-b278-5fcca7f87726
ms.openlocfilehash: e2876398ceaf863bbb3c7e576d59b89c52f1bdaf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127983"
---
# <a name="icordebugmemorybuffergetstartaddress-method"></a><span data-ttu-id="785ef-102">ICorDebugMemoryBuffer:: GetStartAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="785ef-102">ICorDebugMemoryBuffer::GetStartAddress Method</span></span>
<span data-ttu-id="785ef-103">메모리 버퍼의 시작 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="785ef-103">Gets the starting address of the memory buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="785ef-104">구문</span><span class="sxs-lookup"><span data-stu-id="785ef-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStartAddress(  
   [out] LPCVOID *address  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="785ef-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="785ef-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="785ef-106">[out] 메모리 버퍼의 시작 주소에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="785ef-106">[out] A pointer to the starting address of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="785ef-107">주의</span><span class="sxs-lookup"><span data-stu-id="785ef-107">Remarks</span></span>  
  
> [!WARNING]
> <span data-ttu-id="785ef-108">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="785ef-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="785ef-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="785ef-109">Requirements</span></span>  
 <span data-ttu-id="785ef-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="785ef-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="785ef-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="785ef-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="785ef-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="785ef-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="785ef-113">**.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="785ef-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="785ef-114">참조</span><span class="sxs-lookup"><span data-stu-id="785ef-114">See also</span></span>

- [<span data-ttu-id="785ef-115">ICorDebugMemoryBuffer 인터페이스</span><span class="sxs-lookup"><span data-stu-id="785ef-115">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="785ef-116">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="785ef-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
