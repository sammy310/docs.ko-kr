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
ms.openlocfilehash: 40b944f6a1204bfe506ed64408be30f68adf3170
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675258"
---
# <a name="icordebugprocess2setdesiredngencompilerflags-method"></a><span data-ttu-id="7ca60-102">ICorDebugProcess2::SetDesiredNGENCompilerFlags 메서드</span><span class="sxs-lookup"><span data-stu-id="7ca60-102">ICorDebugProcess2::SetDesiredNGENCompilerFlags Method</span></span>

<span data-ttu-id="7ca60-103">런타임이 해당 이미지를 현재 프로세스에 로드 하기 위해 미리 컴파일된 이미지에 포함 되어야 하는 플래그를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ca60-103">Sets the flags that must be embedded in a precompiled image in order for the runtime to load that image into the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ca60-104">구문</span><span class="sxs-lookup"><span data-stu-id="7ca60-104">Syntax</span></span>  
  
```cpp  
HRESULT SetDesiredNGENCompilerFlags (  
    [in] DWORD    pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7ca60-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7ca60-105">Parameters</span></span>  

 `pdwFlags`  
 <span data-ttu-id="7ca60-106">진행 올바른 미리 컴파일된 이미지를 선택 하는 데 사용 되는 컴파일러 플래그를 지정 하는 [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="7ca60-106">[in] A value of the [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) enumeration that specifies the compiler flags used to select the correct pre-compiled image.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7ca60-107">설명</span><span class="sxs-lookup"><span data-stu-id="7ca60-107">Remarks</span></span>  

 <span data-ttu-id="7ca60-108">`SetDesiredNGENCompilerFlags`메서드는 런타임이이 프로세스에 이미지를 로드 하도록 미리 컴파일된 이미지에 포함 되어야 하는 플래그를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ca60-108">The `SetDesiredNGENCompilerFlags` method specifies the flags that must be embedded in a precompiled image so that the runtime will load that image into this process.</span></span> <span data-ttu-id="7ca60-109">이 메서드에 의해 설정 된 플래그는 올바른 미리 컴파일된 이미지를 선택 하는 데만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ca60-109">The flags set by this method are used only to select the correct precompiled image.</span></span> <span data-ttu-id="7ca60-110">이러한 이미지가 없는 경우 런타임은 MSIL (Microsoft 중간 언어) 이미지 및 JIT (just-in-time) 컴파일러를 대신 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ca60-110">If no such image exists, the runtime will load the Microsoft intermediate language (MSIL) image and the just-in-time (JIT) compiler instead.</span></span> <span data-ttu-id="7ca60-111">이 경우 디버거는 [ICorDebugModule2:: SetJITCompilerFlags](icordebugmodule2-setjitcompilerflags-method.md) 메서드를 사용 하 여 JIT 컴파일에 필요한 만큼 플래그를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ca60-111">In that case, the debugger must still use the [ICorDebugModule2::SetJITCompilerFlags](icordebugmodule2-setjitcompilerflags-method.md) method to set the flags as desired for the JIT compilation.</span></span>  
  
 <span data-ttu-id="7ca60-112">이미지가 로드 되었지만 해당 이미지에 대 한 JIT 컴파일 (이미지에 제네릭을 포함 하는 경우)이 발생 해야 하는 경우 메서드에 의해 지정 된 컴파일러 플래그가 `SetDesiredNGENCompilerFlags` 추가 JIT 컴파일에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ca60-112">If an image is loaded, but some JIT compiling must take place for that image (which will be the case if the image contains generics), the compiler flags specified by the `SetDesiredNGENCompilerFlags` method will apply to the extra JIT compilation.</span></span>  
  
 <span data-ttu-id="7ca60-113">`SetDesiredNGENCompilerFlags` [ICorDebugManagedCallback:: CreateProcess](icordebugmanagedcallback-createprocess-method.md) 콜백 중에 메서드를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ca60-113">The `SetDesiredNGENCompilerFlags` method must be called during the [ICorDebugManagedCallback::CreateProcess](icordebugmanagedcallback-createprocess-method.md) callback.</span></span> <span data-ttu-id="7ca60-114">나중에 메서드를 호출 하려고 하면 `SetDesiredNGENCompilerFlags` 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ca60-114">Attempts to call the `SetDesiredNGENCompilerFlags` method afterwards will fail.</span></span> <span data-ttu-id="7ca60-115">또한 열거형에 정의 되어 있지 않거나 지정 된 프로세스에 유효 하지 않은 플래그를 설정 하려고 하면 `CorDebugJITCompilerFlags` 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ca60-115">Also, attempts to set flags that are either not defined in the `CorDebugJITCompilerFlags` enumeration or are not legal for the given process will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ca60-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7ca60-116">Requirements</span></span>  

 <span data-ttu-id="7ca60-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7ca60-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ca60-118">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7ca60-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7ca60-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7ca60-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7ca60-120">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ca60-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ca60-121">참조</span><span class="sxs-lookup"><span data-stu-id="7ca60-121">See also</span></span>

- [<span data-ttu-id="7ca60-122">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7ca60-122">ICorDebug Interface</span></span>](icordebug-interface.md)
- [<span data-ttu-id="7ca60-123">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7ca60-123">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
