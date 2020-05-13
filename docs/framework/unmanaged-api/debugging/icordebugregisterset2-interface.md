---
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
ms.openlocfilehash: f989f1c1f29c63af54ff125f4ad1aaa2bcee6757
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378209"
---
# <a name="icordebugregisterset2-interface"></a><span data-ttu-id="733fa-102">ICorDebugRegisterSet2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="733fa-102">ICorDebugRegisterSet2 Interface</span></span>
<span data-ttu-id="733fa-103">64 개 이상의 레지스터가 있는 하드웨어 플랫폼에 대 한 [ICorDebugRegisterSet](icordebugregisterset-interface.md) 인터페이스의 기능을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="733fa-103">Extends the capabilities of the [ICorDebugRegisterSet](icordebugregisterset-interface.md) interface for hardware platforms that have more than 64 registers.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="733fa-104">메서드</span><span class="sxs-lookup"><span data-stu-id="733fa-104">Methods</span></span>  
  
|<span data-ttu-id="733fa-105">메서드</span><span class="sxs-lookup"><span data-stu-id="733fa-105">Method</span></span>|<span data-ttu-id="733fa-106">설명</span><span class="sxs-lookup"><span data-stu-id="733fa-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="733fa-107">GetRegisters 메서드</span><span class="sxs-lookup"><span data-stu-id="733fa-107">GetRegisters Method</span></span>](icordebugregisterset2-getregisters-method.md)|<span data-ttu-id="733fa-108">비트 마스크로 지정 된 각 레지스터의 값 (현재 코드를 실행 중인 컴퓨터)을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="733fa-108">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>|  
|[<span data-ttu-id="733fa-109">GetRegistersAvailable 메서드</span><span class="sxs-lookup"><span data-stu-id="733fa-109">GetRegistersAvailable Method</span></span>](icordebugregisterset2-getregistersavailable-method.md)|<span data-ttu-id="733fa-110">사용 가능한 레지스터의 비트맵을 제공 하는 바이트 배열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="733fa-110">Gets an array of bytes that provides a bitmap of the available registers.</span></span>|  
|[<span data-ttu-id="733fa-111">SetRegisters 메서드</span><span class="sxs-lookup"><span data-stu-id="733fa-111">SetRegisters Method</span></span>](icordebugregisterset2-setregisters-method.md)|<span data-ttu-id="733fa-112">.NET Framework 버전 2.0에서 구현 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="733fa-112">Not implemented in the .NET Framework version 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="733fa-113">설명</span><span class="sxs-lookup"><span data-stu-id="733fa-113">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="733fa-114">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="733fa-114">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="733fa-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="733fa-115">Requirements</span></span>  
 <span data-ttu-id="733fa-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="733fa-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="733fa-117">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="733fa-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="733fa-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="733fa-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="733fa-119">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="733fa-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="733fa-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="733fa-120">See also</span></span>

- [<span data-ttu-id="733fa-121">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="733fa-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="733fa-122">ICorDebugRegisterSet 인터페이스</span><span class="sxs-lookup"><span data-stu-id="733fa-122">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
