---
description: '자세히 알아보기: ICorDebugDebugEvent:: GetEventKind 메서드'
title: ICorDebugDebugEvent::GetEventKind 메서드
ms.date: 03/30/2017
ms.assetid: c37aaceb-c948-46bd-a943-08be4cbb76f4
ms.openlocfilehash: 9e15eb82195fae8aa3797ea47cb04d0bb407d2ad
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99764322"
---
# <a name="icordebugdebugeventgeteventkind-method"></a><span data-ttu-id="8e75e-103">ICorDebugDebugEvent::GetEventKind 메서드</span><span class="sxs-lookup"><span data-stu-id="8e75e-103">ICorDebugDebugEvent::GetEventKind Method</span></span>

<span data-ttu-id="8e75e-104">이 `ICorDebugDebugEvent` 개체가 나타내는 이벤트의 종류를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8e75e-104">Indicates what kind of event this `ICorDebugDebugEvent` object represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e75e-105">구문</span><span class="sxs-lookup"><span data-stu-id="8e75e-105">Syntax</span></span>  
  
```cpp  
HRESULT GetEventKind(  
    [out]CorDebugDebugEventKind *pDebugEventKind  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8e75e-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8e75e-106">Parameters</span></span>  

 <span data-ttu-id="8e75e-107">pDebugEventKind</span><span class="sxs-lookup"><span data-stu-id="8e75e-107">pDebugEventKind</span></span>  
 <span data-ttu-id="8e75e-108">이벤트 유형을 나타내는 [Cordebugdebugeventkind](cordebugdebugeventkind-enumeration.md) 열거형 멤버에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8e75e-108">A pointer to a [CorDebugDebugEventKind](cordebugdebugeventkind-enumeration.md) enumeration member that indicates the type of event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8e75e-109">설명</span><span class="sxs-lookup"><span data-stu-id="8e75e-109">Remarks</span></span>  

 <span data-ttu-id="8e75e-110">`pDebugEventKind`의 값에 따라 `QueryInterface`를 호출하여 추가 데이터를 포함하는 보다 정확한 디버그 이벤트 인터페이스를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e75e-110">Based on the value of `pDebugEventKind`, you can call `QueryInterface` to get a more precise debug event interface that has additional data.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8e75e-111">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e75e-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e75e-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8e75e-112">Requirements</span></span>  

 <span data-ttu-id="8e75e-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e75e-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e75e-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8e75e-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8e75e-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8e75e-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8e75e-116">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e75e-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e75e-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8e75e-117">See also</span></span>

- [<span data-ttu-id="8e75e-118">ICorDebugDebugEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8e75e-118">ICorDebugDebugEvent Interface</span></span>](icordebugdebugevent-interface.md)
- [<span data-ttu-id="8e75e-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8e75e-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
