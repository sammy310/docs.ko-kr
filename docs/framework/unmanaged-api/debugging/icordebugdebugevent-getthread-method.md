---
description: '자세히 알아보기: ICorDebugDebugEvent:: GetThread 메서드'
title: ICorDebugDebugEvent::GetThread 메서드
ms.date: 03/30/2017
ms.assetid: 4f2e9a2c-8369-4a07-a881-ad5422626353
ms.openlocfilehash: 1d476603572f31882f481d414e483c6712f1b5fc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99710415"
---
# <a name="icordebugdebugeventgetthread-method"></a><span data-ttu-id="a2ed7-103">ICorDebugDebugEvent::GetThread 메서드</span><span class="sxs-lookup"><span data-stu-id="a2ed7-103">ICorDebugDebugEvent::GetThread Method</span></span>

<span data-ttu-id="a2ed7-104">이벤트가 발생한 스레드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a2ed7-104">Gets the thread on which the event occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2ed7-105">구문</span><span class="sxs-lookup"><span data-stu-id="a2ed7-105">Syntax</span></span>  
  
```cpp  
HRESULT GetThread(  
        [out]ICorDebugThread **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a2ed7-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a2ed7-106">Parameters</span></span>  

 <span data-ttu-id="a2ed7-107">ppThread</span><span class="sxs-lookup"><span data-stu-id="a2ed7-107">ppThread</span></span>  
 <span data-ttu-id="a2ed7-108">[out] 이벤트가 발생한 스레드를 나타내는 ICorDebugThread 개체의 주소에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a2ed7-108">[out] A pointer to the address of an ICorDebugThread object that represents the thread on which the event occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a2ed7-109">설명</span><span class="sxs-lookup"><span data-stu-id="a2ed7-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a2ed7-110">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2ed7-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2ed7-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a2ed7-111">Requirements</span></span>  

 <span data-ttu-id="a2ed7-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a2ed7-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2ed7-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a2ed7-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a2ed7-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a2ed7-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a2ed7-115">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2ed7-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2ed7-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a2ed7-116">See also</span></span>

- [<span data-ttu-id="a2ed7-117">ICorDebugDebugEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a2ed7-117">ICorDebugDebugEvent Interface</span></span>](icordebugdebugevent-interface.md)
- [<span data-ttu-id="a2ed7-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a2ed7-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
