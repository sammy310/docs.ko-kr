---
description: '자세히 알아보기: ICorDebugMemoryBuffer:: GetStartAddress 메서드'
title: ICorDebugMemoryBuffer::GetStartAddress 메서드
ms.date: 03/30/2017
ms.assetid: f804d9ab-8c88-44f0-b278-5fcca7f87726
ms.openlocfilehash: 46720d70b8a1019e712b577b24dec5d4c3d5a31d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99722713"
---
# <a name="icordebugmemorybuffergetstartaddress-method"></a><span data-ttu-id="979c5-103">ICorDebugMemoryBuffer::GetStartAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="979c5-103">ICorDebugMemoryBuffer::GetStartAddress Method</span></span>

<span data-ttu-id="979c5-104">메모리 버퍼의 시작 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="979c5-104">Gets the starting address of the memory buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="979c5-105">구문</span><span class="sxs-lookup"><span data-stu-id="979c5-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStartAddress(  
   [out] LPCVOID *address  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="979c5-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="979c5-106">Parameters</span></span>  

 `address`  
 <span data-ttu-id="979c5-107">[out] 메모리 버퍼의 시작 주소에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="979c5-107">[out] A pointer to the starting address of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="979c5-108">설명</span><span class="sxs-lookup"><span data-stu-id="979c5-108">Remarks</span></span>  
  
> [!WARNING]
> <span data-ttu-id="979c5-109">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="979c5-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="979c5-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="979c5-110">Requirements</span></span>  

 <span data-ttu-id="979c5-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="979c5-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="979c5-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="979c5-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="979c5-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="979c5-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="979c5-114">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="979c5-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="979c5-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="979c5-115">See also</span></span>

- [<span data-ttu-id="979c5-116">ICorDebugMemoryBuffer 인터페이스</span><span class="sxs-lookup"><span data-stu-id="979c5-116">ICorDebugMemoryBuffer Interface</span></span>](icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="979c5-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="979c5-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
