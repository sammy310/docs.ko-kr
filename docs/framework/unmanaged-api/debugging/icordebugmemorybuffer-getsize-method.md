---
title: ICorDebugMemoryBuffer::GetSize 메서드
ms.date: 03/30/2017
ms.assetid: 9ffd5482-268e-4680-9fd1-bfb0b7d66450
ms.openlocfilehash: 7f5458dd12ca83c1a5190bbf7fab0f8e5d06a0e1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710763"
---
# <a name="icordebugmemorybuffergetsize-method"></a><span data-ttu-id="0d79e-102">ICorDebugMemoryBuffer::GetSize 메서드</span><span class="sxs-lookup"><span data-stu-id="0d79e-102">ICorDebugMemoryBuffer::GetSize Method</span></span>

<span data-ttu-id="0d79e-103">메모리 버퍼의 크기(바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0d79e-103">Gets the size of the memory buffer in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d79e-104">구문</span><span class="sxs-lookup"><span data-stu-id="0d79e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbBufferLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0d79e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0d79e-105">Parameters</span></span>  

 `pcbBufferLength`  
 <span data-ttu-id="0d79e-106">[out] 메모리 버퍼 크기에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0d79e-106">[out] A pointer to the size of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0d79e-107">설명</span><span class="sxs-lookup"><span data-stu-id="0d79e-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0d79e-108">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d79e-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d79e-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0d79e-109">Requirements</span></span>  

 <span data-ttu-id="0d79e-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0d79e-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d79e-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0d79e-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0d79e-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0d79e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0d79e-113">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d79e-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d79e-114">참조</span><span class="sxs-lookup"><span data-stu-id="0d79e-114">See also</span></span>

- [<span data-ttu-id="0d79e-115">ICorDebugMemoryBuffer 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0d79e-115">ICorDebugMemoryBuffer Interface</span></span>](icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="0d79e-116">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0d79e-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
