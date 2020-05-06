---
title: ICLRDebugging::CanUnloadNow 메서드
ms.date: 03/30/2017
api_name:
- ICLRDebugging.CanUnloadNow Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebugging::CanUnloadNow
helpviewer_keywords:
- CanUnloadNow method [.NET Framework debugging]
- ICLRDebugging::CanUnloadNow method [.NET Framework debugging]
ms.assetid: 62e0630c-8cb7-45d2-b622-5a472abfd8cf
topic_type:
- apiref
ms.openlocfilehash: 16d15101534b88d7da4093dab73b48b5c09a192c
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860394"
---
# <a name="iclrdebuggingcanunloadnow-method"></a><span data-ttu-id="e01a7-102">ICLRDebugging::CanUnloadNow 메서드</span><span class="sxs-lookup"><span data-stu-id="e01a7-102">ICLRDebugging::CanUnloadNow Method</span></span>
<span data-ttu-id="e01a7-103">[ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md) 인터페이스에서 제공 된 라이브러리가 아직 사용 중인지 또는 언로드될 수 있는지를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01a7-103">Determines whether a library that was provided by an [ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md) interface is still in use or can be unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e01a7-104">구문</span><span class="sxs-lookup"><span data-stu-id="e01a7-104">Syntax</span></span>  
  
```cpp  
HRESULT CanUnloadNow(HMODULE hModule);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e01a7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e01a7-105">Parameters</span></span>  
 `hmodule`  
 <span data-ttu-id="e01a7-106">진행 대상 프로세스에 있는 모듈의 기본 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="e01a7-106">[in] The base address of a module in the target process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e01a7-107">Return Value</span><span class="sxs-lookup"><span data-stu-id="e01a7-107">Return Value</span></span>  
 <span data-ttu-id="e01a7-108">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e01a7-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="e01a7-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e01a7-109">HRESULT</span></span>|<span data-ttu-id="e01a7-110">Description</span><span class="sxs-lookup"><span data-stu-id="e01a7-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e01a7-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="e01a7-111">S_OK</span></span>|<span data-ttu-id="e01a7-112">에서 `hmodule` 참조 하는 모듈을 언로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e01a7-112">The module that is referenced by `hmodule` can be unloaded.</span></span>|  
|<span data-ttu-id="e01a7-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="e01a7-113">S_FALSE</span></span>|<span data-ttu-id="e01a7-114">에서 `hmodule` 참조 하는 모듈이 아직 사용 되 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e01a7-114">The module that is referenced by `hmodule` is still in use.</span></span>|  
|<span data-ttu-id="e01a7-115">COR_E_NOT_CLR</span><span class="sxs-lookup"><span data-stu-id="e01a7-115">COR_E_NOT_CLR</span></span>|<span data-ttu-id="e01a7-116">표시 된 모듈이 CLR 모듈이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="e01a7-116">The indicated module is not a CLR module.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="e01a7-117">예외</span><span class="sxs-lookup"><span data-stu-id="e01a7-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e01a7-118">설명</span><span class="sxs-lookup"><span data-stu-id="e01a7-118">Remarks</span></span>  
 <span data-ttu-id="e01a7-119">이 메서드는 모든 `ICorDebug*` 인터페이스 인스턴스가 해제 되었고 현재 [ICLRDebugging:: openvirtualprocess](iclrdebugging-openvirtualprocess-method.md) 메서드 호출 내에 스레드가 없는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01a7-119">This method checks to see if all instances of `ICorDebug*` interfaces have been released and no thread is currently within a call to the [ICLRDebugging::OpenVirtualProcess](iclrdebugging-openvirtualprocess-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e01a7-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e01a7-120">Requirements</span></span>  
 <span data-ttu-id="e01a7-121">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e01a7-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e01a7-122">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e01a7-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e01a7-123">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e01a7-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e01a7-124">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e01a7-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e01a7-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e01a7-125">See also</span></span>

- [<span data-ttu-id="e01a7-126">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e01a7-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="e01a7-127">디버깅</span><span class="sxs-lookup"><span data-stu-id="e01a7-127">Debugging</span></span>](index.md)
