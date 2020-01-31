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
ms.openlocfilehash: b28e457ea0b51d320581c0fbe36574698081ea36
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792955"
---
# <a name="icordebugmodule2setjitcompilerflags-method"></a><span data-ttu-id="761a7-102">ICorDebugModule2::SetJITCompilerFlags 메서드</span><span class="sxs-lookup"><span data-stu-id="761a7-102">ICorDebugModule2::SetJITCompilerFlags Method</span></span>
<span data-ttu-id="761a7-103">이 ICorDebugModule2의 JIT (just-in-time) 컴파일을 제어 하는 플래그를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="761a7-103">Sets the flags that control the just-in-time (JIT) compilation of this ICorDebugModule2.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="761a7-104">구문</span><span class="sxs-lookup"><span data-stu-id="761a7-104">Syntax</span></span>  
  
```cpp  
HRESULT SetJITCompilerFlags (  
    [in] DWORD dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="761a7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="761a7-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="761a7-106">진행 [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) 열거형 값의 비트 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="761a7-106">[in] A bitwise combination of the [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) enumeration values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="761a7-107">주의</span><span class="sxs-lookup"><span data-stu-id="761a7-107">Remarks</span></span>  
 <span data-ttu-id="761a7-108">`dwFlags` 값이 잘못 된 경우 `SetJITCompilerFlags` 메서드가 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="761a7-108">If the `dwFlags` value is invalid, the `SetJITCompilerFlags` method will fail.</span></span>  
  
 <span data-ttu-id="761a7-109">`SetJITCompilerFlags` 메서드는이 모듈에 대 한 [ICorDebugManagedCallback:: LoadModule](icordebugmanagedcallback-loadmodule-method.md) callback 내 에서만 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="761a7-109">The `SetJITCompilerFlags` method can be called only from within the [ICorDebugManagedCallback::LoadModule](icordebugmanagedcallback-loadmodule-method.md) callback for this module.</span></span> <span data-ttu-id="761a7-110">`ICorDebugManagedCallback::LoadModule` 콜백이 전달 된 후에 호출 하려고 하면 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="761a7-110">Attempts to call it after the `ICorDebugManagedCallback::LoadModule` callback has been delivered will fail.</span></span>  
  
 <span data-ttu-id="761a7-111">편집 하며 계속 하기는 64 비트 또는 Win9x 플랫폼에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="761a7-111">Edit and Continue is not supported on 64-bit or Win9x platforms.</span></span> <span data-ttu-id="761a7-112">따라서 `dwFlags`에 설정 된 CORDEBUG_JIT_ENABLE_ENC 플래그를 사용 하 여 두 플랫폼 중 하나에서 `SetJITCompilerFlags` 메서드를 호출 하는 경우에는 `SetJITCompilerFlags` 메서드와 [ICorDebugModule2:: ApplyChanges](icordebugmodule2-applychanges-method.md)와 같이 편집 하며 계속 하기와 관련 된 모든 메서드가 실패 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="761a7-112">Therefore, if you call the `SetJITCompilerFlags` method on either of these two platforms with the CORDEBUG_JIT_ENABLE_ENC flag set in `dwFlags`, the `SetJITCompilerFlags` method and all methods specific to Edit and Continue, such as [ICorDebugModule2::ApplyChanges](icordebugmodule2-applychanges-method.md), will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="761a7-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="761a7-113">Requirements</span></span>  
 <span data-ttu-id="761a7-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="761a7-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="761a7-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="761a7-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="761a7-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="761a7-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="761a7-117">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="761a7-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
