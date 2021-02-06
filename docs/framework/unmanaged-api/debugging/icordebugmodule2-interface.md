---
description: '자세히 알아보기: ICorDebugModule2 인터페이스'
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
ms.openlocfilehash: 28de1f0d3411218ac92991d4fceda0612c8199bf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99659935"
---
# <a name="icordebugmodule2-interface"></a><span data-ttu-id="8cef3-103">ICorDebugModule2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8cef3-103">ICorDebugModule2 Interface</span></span>

<span data-ttu-id="8cef3-104">ICorDebugModule 인터페이스에 대 한 논리적 확장으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cef3-104">Serves as a logical extension to the ICorDebugModule interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8cef3-105">메서드</span><span class="sxs-lookup"><span data-stu-id="8cef3-105">Methods</span></span>  
  
|<span data-ttu-id="8cef3-106">메서드</span><span class="sxs-lookup"><span data-stu-id="8cef3-106">Method</span></span>|<span data-ttu-id="8cef3-107">설명</span><span class="sxs-lookup"><span data-stu-id="8cef3-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8cef3-108">ApplyChanges 메서드</span><span class="sxs-lookup"><span data-stu-id="8cef3-108">ApplyChanges Method</span></span>](icordebugmodule2-applychanges-method.md)|<span data-ttu-id="8cef3-109">메타 데이터의 변경 내용과 MSIL (Microsoft 중간 언어) 코드의 변경 내용을 실행 중인 프로세스에 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cef3-109">Applies the changes in the metadata and the changes in the Microsoft intermediate language (MSIL) code to the running process.</span></span>|  
|[<span data-ttu-id="8cef3-110">GetJITCompilerFlags 메서드</span><span class="sxs-lookup"><span data-stu-id="8cef3-110">GetJITCompilerFlags Method</span></span>](icordebugmodule2-getjitcompilerflags-method.md)|<span data-ttu-id="8cef3-111">이에 대 한 JIT (just-in-time) 컴파일을 제어 하는 플래그를 가져옵니다 `ICorDebugModule2` .</span><span class="sxs-lookup"><span data-stu-id="8cef3-111">Gets the flags that control the just-in-time (JIT) compilation for this `ICorDebugModule2`.</span></span>|  
|[<span data-ttu-id="8cef3-112">ResolveAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="8cef3-112">ResolveAssembly Method</span></span>](icordebugmodule2-resolveassembly-method.md)|<span data-ttu-id="8cef3-113">지정 된 메타 데이터 토큰에서 참조 하는 어셈블리를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cef3-113">Resolves the assembly referenced by the specified metadata token.</span></span>|  
|[<span data-ttu-id="8cef3-114">SetJITCompilerFlags 메서드</span><span class="sxs-lookup"><span data-stu-id="8cef3-114">SetJITCompilerFlags Method</span></span>](icordebugmodule2-setjitcompilerflags-method.md)|<span data-ttu-id="8cef3-115">이에 대 한 JIT 컴파일을 제어 하는 플래그를 설정 합니다 `ICorDebugModule2` .</span><span class="sxs-lookup"><span data-stu-id="8cef3-115">Sets the flags that control the JIT compilation for this `ICorDebugModule2`.</span></span>|  
|[<span data-ttu-id="8cef3-116">SetJMCStatus 메서드</span><span class="sxs-lookup"><span data-stu-id="8cef3-116">SetJMCStatus Method</span></span>](icordebugmodule2-setjmcstatus-method.md)|<span data-ttu-id="8cef3-117">이에 있는 모든 클래스의 모든 메서드에 대 한 내 코드만 (JMC) 상태를 지정 된 값으로 설정 합니다 `ICorDebugModule2` . 단, `pTokens` 배열의 값은 반대 값으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cef3-117">Sets the Just My Code (JMC) status of all methods of all the classes in this `ICorDebugModule2` to the specified value, except those in the `pTokens` array, which it sets to the opposite value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8cef3-118">설명</span><span class="sxs-lookup"><span data-stu-id="8cef3-118">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8cef3-119">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8cef3-119">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8cef3-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8cef3-120">Requirements</span></span>  

 <span data-ttu-id="8cef3-121">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8cef3-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8cef3-122">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8cef3-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8cef3-123">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8cef3-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8cef3-124">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8cef3-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cef3-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8cef3-125">See also</span></span>

- [<span data-ttu-id="8cef3-126">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8cef3-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
