---
title: ICorDebugProcess2::SetDesiredNGENCompilerFlags 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.SetDesiredNGENCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::SetDesiredNGENCompilerFlags
helpviewer_keywords:
- ICorDebugProcess2::SetDesiredNGENCompilerFlags method [.NET Framework debugging]
- SetDesiredNGENCompilerFlags method [.NET Framework debugging]
ms.assetid: 98320175-7c5e-4dbb-8683-86fa82e2641f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e061c3f3dc95e63339d6fd5f82b3cb4d38a4b6c6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948826"
---
# <a name="icordebugprocess2setdesiredngencompilerflags-method"></a><span data-ttu-id="b4277-102">ICorDebugProcess2::SetDesiredNGENCompilerFlags 메서드</span><span class="sxs-lookup"><span data-stu-id="b4277-102">ICorDebugProcess2::SetDesiredNGENCompilerFlags Method</span></span>
<span data-ttu-id="b4277-103">미리 컴파일된 이미지를 현재 프로세스에 해당 이미지를 로드 하려면 런타임에 대 한 순서 대로 포함 되어야 하는 플래그를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4277-103">Sets the flags that must be embedded in a precompiled image in order for the runtime to load that image into the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4277-104">구문</span><span class="sxs-lookup"><span data-stu-id="b4277-104">Syntax</span></span>  
  
```  
HRESULT SetDesiredNGENCompilerFlags (  
    [in] DWORD    pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b4277-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b4277-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="b4277-106">[in] 값을 [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) 컴파일러 플래그를 지정 하는 열거형 올바른 미리 컴파일된 이미지를 선택 하는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4277-106">[in] A value of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration that specifies the compiler flags used to select the correct pre-compiled image.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b4277-107">설명</span><span class="sxs-lookup"><span data-stu-id="b4277-107">Remarks</span></span>  
 <span data-ttu-id="b4277-108">`SetDesiredNGENCompilerFlags` 메서드는 런타임에서이 프로세스에 해당 이미지를 로드 하는 미리 컴파일된 이미지에 포함 되어야 하는 플래그를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4277-108">The `SetDesiredNGENCompilerFlags` method specifies the flags that must be embedded in a precompiled image so that the runtime will load that image into this process.</span></span> <span data-ttu-id="b4277-109">이 메서드에 의해 설정 된 플래그는 올바른 미리 컴파일된 이미지 선택에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4277-109">The flags set by this method are used only to select the correct precompiled image.</span></span> <span data-ttu-id="b4277-110">이러한 이미지가 없는 경우 런타임에 로드 됩니다 Microsoft 중간 언어 (MSIL) 이미지 및 (JIT)-just-in-time 컴파일러 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4277-110">If no such image exists, the runtime will load the Microsoft intermediate language (MSIL) image and the just-in-time (JIT) compiler instead.</span></span> <span data-ttu-id="b4277-111">이 경우 디버거가 계속 사용 해야 합니다는 [ICorDebugModule2::SetJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjitcompilerflags-method.md) JIT 컴파일에 대해 필요에 따라 플래그를 설정 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="b4277-111">In that case, the debugger must still use the [ICorDebugModule2::SetJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjitcompilerflags-method.md) method to set the flags as desired for the JIT compilation.</span></span>  
  
 <span data-ttu-id="b4277-112">이미지를 로드 하지만 약간의 JIT 컴파일을 수행 해야 합니다 (될 경우 이미지는 제네릭을 포함 하는 경우) 해당 이미지에 대 한 경우에 지정 된 컴파일러 플래그는 `SetDesiredNGENCompilerFlags` 메서드 추가 JIT 컴파일으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4277-112">If an image is loaded, but some JIT compiling must take place for that image (which will be the case if the image contains generics), the compiler flags specified by the `SetDesiredNGENCompilerFlags` method will apply to the extra JIT compilation.</span></span>  
  
 <span data-ttu-id="b4277-113">합니다 `SetDesiredNGENCompilerFlags` 메서드를 호출 하는 동안 합니다 [icordebugmanagedcallback:: Createprocess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4277-113">The `SetDesiredNGENCompilerFlags` method must be called during the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback.</span></span> <span data-ttu-id="b4277-114">호출 하려고 합니다 `SetDesiredNGENCompilerFlags` 나중에 메서드가 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4277-114">Attempts to call the `SetDesiredNGENCompilerFlags` method afterwards will fail.</span></span> <span data-ttu-id="b4277-115">또한에 정의 된 잘못 된 플래그를 설정 하려고 시도 합니다 `CorDebugJITCompilerFlags` 열거형 또는 지정된 된 프로세스에 적합 하지 않은 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4277-115">Also, attempts to set flags that are either not defined in the `CorDebugJITCompilerFlags` enumeration or are not legal for the given process will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4277-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b4277-116">Requirements</span></span>  
 <span data-ttu-id="b4277-117">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b4277-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4277-118">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b4277-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b4277-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b4277-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b4277-120">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4277-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4277-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="b4277-121">See also</span></span>

- [<span data-ttu-id="b4277-122">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b4277-122">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [<span data-ttu-id="b4277-123">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b4277-123">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
