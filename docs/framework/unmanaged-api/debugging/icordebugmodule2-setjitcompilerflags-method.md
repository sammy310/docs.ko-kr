---
title: ICorDebugModule2::SetJITCompilerFlags 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.SetJITCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::SetJITCompilerFlags
helpviewer_keywords:
- ICorDebugModule2::SetJITCompilerFlags method [.NET Framework debugging]
- SetJITCompilerFlags method [.NET Framework debugging]
ms.assetid: ea574c84-c622-4589-9a14-b55771af5e06
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c71ccbc62ea026a55a7e84f6925a78850594a813
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61942521"
---
# <a name="icordebugmodule2setjitcompilerflags-method"></a><span data-ttu-id="19d5d-102">ICorDebugModule2::SetJITCompilerFlags 메서드</span><span class="sxs-lookup"><span data-stu-id="19d5d-102">ICorDebugModule2::SetJITCompilerFlags Method</span></span>
<span data-ttu-id="19d5d-103">이 ICorDebugModule2 컴파일하는 시간 (JIT)를 제어 하는 플래그를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="19d5d-103">Sets the flags that control the just-in-time (JIT) compilation of this ICorDebugModule2.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19d5d-104">구문</span><span class="sxs-lookup"><span data-stu-id="19d5d-104">Syntax</span></span>  
  
```  
HRESULT SetJITCompilerFlags (  
    [in] DWORD dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="19d5d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="19d5d-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="19d5d-106">[in] 비트 조합 합니다 [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) 열거형 값입니다.</span><span class="sxs-lookup"><span data-stu-id="19d5d-106">[in] A bitwise combination of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="19d5d-107">설명</span><span class="sxs-lookup"><span data-stu-id="19d5d-107">Remarks</span></span>  
 <span data-ttu-id="19d5d-108">경우는 `dwFlags` 값이 유효 하지는 `SetJITCompilerFlags` 메서드가 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="19d5d-108">If the `dwFlags` value is invalid, the `SetJITCompilerFlags` method will fail.</span></span>  
  
 <span data-ttu-id="19d5d-109">합니다 `SetJITCompilerFlags` 메서드 내 에서만 호출할 수 있습니다 합니다 [icordebugmanagedcallback:: Loadmodule](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadmodule-method.md) 이 모듈에 대 한 콜백입니다.</span><span class="sxs-lookup"><span data-stu-id="19d5d-109">The `SetJITCompilerFlags` method can be called only from within the [ICorDebugManagedCallback::LoadModule](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadmodule-method.md) callback for this module.</span></span> <span data-ttu-id="19d5d-110">후에 메서드를 호출 하려고 합니다 `ICorDebugManagedCallback::LoadModule` 콜백이 전달 된 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="19d5d-110">Attempts to call it after the `ICorDebugManagedCallback::LoadModule` callback has been delivered will fail.</span></span>  
  
 <span data-ttu-id="19d5d-111">편집 하며 계속 하기 64 비트 또는 Win9x 플랫폼에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="19d5d-111">Edit and Continue is not supported on 64-bit or Win9x platforms.</span></span> <span data-ttu-id="19d5d-112">따라서 호출 하는 경우는 `SetJITCompilerFlags` CORDEBUG_JIT_ENABLE_ENC 플래그가 설정 된이 두 플랫폼 중 하나에서 메서드 `dwFlags`의 `SetJITCompilerFlags` 메서드와 모든 메서드를 특정 편집 하며 계속 하기, 같은를 [ICorDebugModule2:: ApplyChanges](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md)에 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="19d5d-112">Therefore, if you call the `SetJITCompilerFlags` method on either of these two platforms with the CORDEBUG_JIT_ENABLE_ENC flag set in `dwFlags`, the `SetJITCompilerFlags` method and all methods specific to Edit and Continue, such as [ICorDebugModule2::ApplyChanges](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md), will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19d5d-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="19d5d-113">Requirements</span></span>  
 <span data-ttu-id="19d5d-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="19d5d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19d5d-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="19d5d-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="19d5d-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="19d5d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="19d5d-117">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19d5d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
