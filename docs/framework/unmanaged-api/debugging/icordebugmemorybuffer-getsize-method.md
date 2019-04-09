---
title: ICorDebugMemoryBuffer::GetSize 메서드
ms.date: 03/30/2017
ms.assetid: 9ffd5482-268e-4680-9fd1-bfb0b7d66450
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d687f2bbd3c20564368d4246961b56382ea14cf5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59099679"
---
# <a name="icordebugmemorybuffergetsize-method"></a><span data-ttu-id="2bef7-102">ICorDebugMemoryBuffer::GetSize 메서드</span><span class="sxs-lookup"><span data-stu-id="2bef7-102">ICorDebugMemoryBuffer::GetSize Method</span></span>
<span data-ttu-id="2bef7-103">메모리 버퍼의 크기(바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2bef7-103">Gets the size of the memory buffer in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bef7-104">구문</span><span class="sxs-lookup"><span data-stu-id="2bef7-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbBufferLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2bef7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2bef7-105">Parameters</span></span>  
 `pcbBufferLength`  
 <span data-ttu-id="2bef7-106">[out] 메모리 버퍼 크기에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2bef7-106">[out] A pointer to the size of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2bef7-107">설명</span><span class="sxs-lookup"><span data-stu-id="2bef7-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2bef7-108">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2bef7-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2bef7-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2bef7-109">Requirements</span></span>  
 <span data-ttu-id="2bef7-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2bef7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2bef7-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2bef7-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2bef7-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2bef7-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="2bef7-113">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="2bef7-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2bef7-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="2bef7-114">See also</span></span>

- [<span data-ttu-id="2bef7-115">ICorDebugMemoryBuffer 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2bef7-115">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="2bef7-116">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2bef7-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
