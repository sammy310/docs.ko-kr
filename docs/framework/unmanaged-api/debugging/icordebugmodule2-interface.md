---
title: ICorDebugModule2 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugModule2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2
helpviewer_keywords:
- ICorDebugModule2 interface [.NET Framework debugging]
ms.assetid: 0847e64f-fdbe-4c96-8168-da20fdc84d80
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d8fe1a25c4bc1f5e19f49f0d660d0aad5a180ea2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69911898"
---
# <a name="icordebugmodule2-interface"></a><span data-ttu-id="2b4df-102">ICorDebugModule2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2b4df-102">ICorDebugModule2 Interface</span></span>

<span data-ttu-id="2b4df-103">ICorDebugModule 인터페이스에 대 한 논리적 확장으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b4df-103">Serves as a logical extension to the ICorDebugModule interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2b4df-104">메서드</span><span class="sxs-lookup"><span data-stu-id="2b4df-104">Methods</span></span>  
  
|<span data-ttu-id="2b4df-105">메서드</span><span class="sxs-lookup"><span data-stu-id="2b4df-105">Method</span></span>|<span data-ttu-id="2b4df-106">Description</span><span class="sxs-lookup"><span data-stu-id="2b4df-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2b4df-107">ApplyChanges 메서드</span><span class="sxs-lookup"><span data-stu-id="2b4df-107">ApplyChanges Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md)|<span data-ttu-id="2b4df-108">메타 데이터의 변경 내용과 MSIL (Microsoft 중간 언어) 코드의 변경 내용을 실행 중인 프로세스에 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b4df-108">Applies the changes in the metadata and the changes in the Microsoft intermediate language (MSIL) code to the running process.</span></span>|  
|[<span data-ttu-id="2b4df-109">GetJITCompilerFlags 메서드</span><span class="sxs-lookup"><span data-stu-id="2b4df-109">GetJITCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-getjitcompilerflags-method.md)|<span data-ttu-id="2b4df-110">이 `ICorDebugModule2`에 대 한 JIT (just-in-time) 컴파일을 제어 하는 플래그를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2b4df-110">Gets the flags that control the just-in-time (JIT) compilation for this `ICorDebugModule2`.</span></span>|  
|[<span data-ttu-id="2b4df-111">ResolveAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="2b4df-111">ResolveAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-resolveassembly-method.md)|<span data-ttu-id="2b4df-112">지정 된 메타 데이터 토큰에서 참조 하는 어셈블리를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b4df-112">Resolves the assembly referenced by the specified metadata token.</span></span>|  
|[<span data-ttu-id="2b4df-113">SetJITCompilerFlags 메서드</span><span class="sxs-lookup"><span data-stu-id="2b4df-113">SetJITCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjitcompilerflags-method.md)|<span data-ttu-id="2b4df-114">이 `ICorDebugModule2`에 대 한 JIT 컴파일을 제어 하는 플래그를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b4df-114">Sets the flags that control the JIT compilation for this `ICorDebugModule2`.</span></span>|  
|[<span data-ttu-id="2b4df-115">SetJMCStatus 메서드</span><span class="sxs-lookup"><span data-stu-id="2b4df-115">SetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjmcstatus-method.md)|<span data-ttu-id="2b4df-116">이 `ICorDebugModule2` 에 있는 모든 클래스의 모든 메서드에 대 한 내 코드만 (JMC) 상태를 지정 된 값으로 설정 합니다. 단 `pTokens` , 배열의 값은 반대 값으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b4df-116">Sets the Just My Code (JMC) status of all methods of all the classes in this `ICorDebugModule2` to the specified value, except those in the `pTokens` array, which it sets to the opposite value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2b4df-117">설명</span><span class="sxs-lookup"><span data-stu-id="2b4df-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2b4df-118">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2b4df-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b4df-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2b4df-119">Requirements</span></span>  
 <span data-ttu-id="2b4df-120">**플랫폼** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2b4df-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b4df-121">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2b4df-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2b4df-122">**라이브러리** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2b4df-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2b4df-123">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b4df-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b4df-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="2b4df-124">See also</span></span>

- [<span data-ttu-id="2b4df-125">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2b4df-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
