---
description: ICorDebugProcess6::P rocessStateChanged 메서드에 대해 자세히 알아보세요.
title: ICorDebugProcess6::ProcessStateChanged 메서드
ms.date: 03/30/2017
ms.assetid: fb6d30d9-54f3-462b-8ebf-ce0440791ad5
ms.openlocfilehash: 8060c29598adf5d4bbe7bffb4cd6611ee19a2669
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99691369"
---
# <a name="icordebugprocess6processstatechanged-method"></a><span data-ttu-id="ae405-103">ICorDebugProcess6::ProcessStateChanged 메서드</span><span class="sxs-lookup"><span data-stu-id="ae405-103">ICorDebugProcess6::ProcessStateChanged Method</span></span>

<span data-ttu-id="ae405-104">프로세스가 실행 중임을 [ICorDebug](icordebug-interface.md) 에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="ae405-104">Notifies [ICorDebug](icordebug-interface.md) that the process is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae405-105">구문</span><span class="sxs-lookup"><span data-stu-id="ae405-105">Syntax</span></span>  
  
```cpp  
HRESULT ProcessStateChanged(   [in] CorDebugStateChange change);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ae405-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ae405-106">Parameters</span></span>  

 `change`  
 <span data-ttu-id="ae405-107">진행 [ProcessStateChanged](icordebugprocess6-processstatechanged-method.md) 열거형의 멤버</span><span class="sxs-lookup"><span data-stu-id="ae405-107">[in] A member of the [ProcessStateChanged](icordebugprocess6-processstatechanged-method.md) enumeration</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ae405-108">설명</span><span class="sxs-lookup"><span data-stu-id="ae405-108">Remarks</span></span>  

 <span data-ttu-id="ae405-109">디버거는이 메서드를 호출 하 여 프로세스가 실행 중임을 [ICorDebug](icordebug-interface.md) 에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="ae405-109">The debugger calls this method to notify [ICorDebug](icordebug-interface.md) that the process is running.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ae405-110">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae405-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae405-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ae405-111">Requirements</span></span>  

 <span data-ttu-id="ae405-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ae405-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae405-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ae405-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ae405-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ae405-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ae405-115">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae405-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae405-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ae405-116">See also</span></span>

- [<span data-ttu-id="ae405-117">ICorDebugProcess6 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ae405-117">ICorDebugProcess6 Interface</span></span>](icordebugprocess6-interface.md)
- [<span data-ttu-id="ae405-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ae405-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
