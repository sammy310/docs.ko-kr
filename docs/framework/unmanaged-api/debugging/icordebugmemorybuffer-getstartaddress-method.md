---
title: ICorDebugMemoryBuffer::GetStartAddress 메서드
ms.date: 03/30/2017
ms.assetid: f804d9ab-8c88-44f0-b278-5fcca7f87726
ms.openlocfilehash: f76bf1479db987e4956d8b876f67d629d927f956
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710764"
---
# <a name="icordebugmemorybuffergetstartaddress-method"></a><span data-ttu-id="fa539-102">ICorDebugMemoryBuffer::GetStartAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="fa539-102">ICorDebugMemoryBuffer::GetStartAddress Method</span></span>

<span data-ttu-id="fa539-103">메모리 버퍼의 시작 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fa539-103">Gets the starting address of the memory buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa539-104">구문</span><span class="sxs-lookup"><span data-stu-id="fa539-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStartAddress(  
   [out] LPCVOID *address  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa539-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fa539-105">Parameters</span></span>  

 `address`  
 <span data-ttu-id="fa539-106">[out] 메모리 버퍼의 시작 주소에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="fa539-106">[out] A pointer to the starting address of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa539-107">설명</span><span class="sxs-lookup"><span data-stu-id="fa539-107">Remarks</span></span>  
  
> [!WARNING]
> <span data-ttu-id="fa539-108">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa539-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa539-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fa539-109">Requirements</span></span>  

 <span data-ttu-id="fa539-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fa539-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa539-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fa539-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fa539-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fa539-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fa539-113">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa539-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa539-114">참조</span><span class="sxs-lookup"><span data-stu-id="fa539-114">See also</span></span>

- [<span data-ttu-id="fa539-115">ICorDebugMemoryBuffer 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fa539-115">ICorDebugMemoryBuffer Interface</span></span>](icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="fa539-116">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fa539-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
