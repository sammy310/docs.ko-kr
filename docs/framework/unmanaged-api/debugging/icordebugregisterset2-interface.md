---
description: '자세히 알아보기: ICorDebugRegisterSet2 인터페이스'
title: ICorDebugRegisterSet2 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2
helpviewer_keywords:
- ICorDebugRegisterSet2 interface [.NET Framework debugging]
ms.assetid: d7fbccbf-3b6b-4db8-a96d-768e1cb6b1a6
topic_type:
- apiref
ms.openlocfilehash: 3501325df188879f5687347ef329f490b487d9d8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803609"
---
# <a name="icordebugregisterset2-interface"></a><span data-ttu-id="9cd58-103">ICorDebugRegisterSet2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9cd58-103">ICorDebugRegisterSet2 Interface</span></span>

<span data-ttu-id="9cd58-104">64 개 이상의 레지스터가 있는 하드웨어 플랫폼에 대 한 [ICorDebugRegisterSet](icordebugregisterset-interface.md) 인터페이스의 기능을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cd58-104">Extends the capabilities of the [ICorDebugRegisterSet](icordebugregisterset-interface.md) interface for hardware platforms that have more than 64 registers.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9cd58-105">메서드</span><span class="sxs-lookup"><span data-stu-id="9cd58-105">Methods</span></span>  
  
|<span data-ttu-id="9cd58-106">메서드</span><span class="sxs-lookup"><span data-stu-id="9cd58-106">Method</span></span>|<span data-ttu-id="9cd58-107">설명</span><span class="sxs-lookup"><span data-stu-id="9cd58-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9cd58-108">GetRegisters 메서드</span><span class="sxs-lookup"><span data-stu-id="9cd58-108">GetRegisters Method</span></span>](icordebugregisterset2-getregisters-method.md)|<span data-ttu-id="9cd58-109">비트 마스크로 지정 된 각 레지스터의 값 (현재 코드를 실행 중인 컴퓨터)을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9cd58-109">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>|  
|[<span data-ttu-id="9cd58-110">GetRegistersAvailable 메서드</span><span class="sxs-lookup"><span data-stu-id="9cd58-110">GetRegistersAvailable Method</span></span>](icordebugregisterset2-getregistersavailable-method.md)|<span data-ttu-id="9cd58-111">사용 가능한 레지스터의 비트맵을 제공 하는 바이트 배열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9cd58-111">Gets an array of bytes that provides a bitmap of the available registers.</span></span>|  
|[<span data-ttu-id="9cd58-112">SetRegisters 메서드</span><span class="sxs-lookup"><span data-stu-id="9cd58-112">SetRegisters Method</span></span>](icordebugregisterset2-setregisters-method.md)|<span data-ttu-id="9cd58-113">.NET Framework 버전 2.0에서 구현 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="9cd58-113">Not implemented in the .NET Framework version 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9cd58-114">설명</span><span class="sxs-lookup"><span data-stu-id="9cd58-114">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9cd58-115">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9cd58-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9cd58-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9cd58-116">Requirements</span></span>  

 <span data-ttu-id="9cd58-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9cd58-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9cd58-118">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9cd58-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9cd58-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9cd58-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9cd58-120">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9cd58-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cd58-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9cd58-121">See also</span></span>

- [<span data-ttu-id="9cd58-122">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9cd58-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="9cd58-123">ICorDebugRegisterSet 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9cd58-123">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
