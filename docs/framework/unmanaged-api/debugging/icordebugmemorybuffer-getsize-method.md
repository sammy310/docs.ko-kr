---
description: '자세히 알아보기: ICorDebugMemoryBuffer:: GetSize 메서드'
title: ICorDebugMemoryBuffer::GetSize 메서드
ms.date: 03/30/2017
ms.assetid: 9ffd5482-268e-4680-9fd1-bfb0b7d66450
ms.openlocfilehash: 7de23dd13a1e0ef841145e3845d7d0052ce3ef9a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754042"
---
# <a name="icordebugmemorybuffergetsize-method"></a><span data-ttu-id="2b2bb-103">ICorDebugMemoryBuffer::GetSize 메서드</span><span class="sxs-lookup"><span data-stu-id="2b2bb-103">ICorDebugMemoryBuffer::GetSize Method</span></span>

<span data-ttu-id="2b2bb-104">메모리 버퍼의 크기(바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2b2bb-104">Gets the size of the memory buffer in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b2bb-105">구문</span><span class="sxs-lookup"><span data-stu-id="2b2bb-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbBufferLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2b2bb-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2b2bb-106">Parameters</span></span>  

 `pcbBufferLength`  
 <span data-ttu-id="2b2bb-107">[out] 메모리 버퍼 크기에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2b2bb-107">[out] A pointer to the size of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2b2bb-108">설명</span><span class="sxs-lookup"><span data-stu-id="2b2bb-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2b2bb-109">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b2bb-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b2bb-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2b2bb-110">Requirements</span></span>  

 <span data-ttu-id="2b2bb-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2b2bb-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b2bb-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2b2bb-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2b2bb-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2b2bb-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2b2bb-114">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b2bb-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b2bb-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2b2bb-115">See also</span></span>

- [<span data-ttu-id="2b2bb-116">ICorDebugMemoryBuffer 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2b2bb-116">ICorDebugMemoryBuffer Interface</span></span>](icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="2b2bb-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2b2bb-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
