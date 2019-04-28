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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 80559ef685a2dbf48d65e0d81432a5edbd5528bb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698150"
---
# <a name="iclrdebuggingcanunloadnow-method"></a><span data-ttu-id="ab2f7-102">ICLRDebugging::CanUnloadNow 메서드</span><span class="sxs-lookup"><span data-stu-id="ab2f7-102">ICLRDebugging::CanUnloadNow Method</span></span>
<span data-ttu-id="ab2f7-103">라이브러리에서 제공 하는 여부를 확인 한 [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) 인터페이스 사용에서 되었거나 언로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f7-103">Determines whether a library that was provided by an [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) interface is still in use or can be unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab2f7-104">구문</span><span class="sxs-lookup"><span data-stu-id="ab2f7-104">Syntax</span></span>  
  
```  
HRESULT CanUnloadNow(HMODULE hModule);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ab2f7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ab2f7-105">Parameters</span></span>  
 `hmodule`  
 <span data-ttu-id="ab2f7-106">[in] 대상 프로세스에서 모듈의 기본 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f7-106">[in] The base address of a module in the target process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ab2f7-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="ab2f7-107">Return Value</span></span>  
 <span data-ttu-id="ab2f7-108">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f7-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="ab2f7-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ab2f7-109">HRESULT</span></span>|<span data-ttu-id="ab2f7-110">설명</span><span class="sxs-lookup"><span data-stu-id="ab2f7-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ab2f7-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="ab2f7-111">S_OK</span></span>|<span data-ttu-id="ab2f7-112">참조 되는 모듈 `hmodule` 언로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f7-112">The module that is referenced by `hmodule` can be unloaded.</span></span>|  
|<span data-ttu-id="ab2f7-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="ab2f7-113">S_FALSE</span></span>|<span data-ttu-id="ab2f7-114">참조 되는 모듈 `hmodule` 사용 중입니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f7-114">The module that is referenced by `hmodule` is still in use.</span></span>|  
|<span data-ttu-id="ab2f7-115">COR_E_NOT_CLR</span><span class="sxs-lookup"><span data-stu-id="ab2f7-115">COR_E_NOT_CLR</span></span>|<span data-ttu-id="ab2f7-116">표시 된 모듈이 CLR 모듈이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f7-116">The indicated module is not a CLR module.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="ab2f7-117">예외</span><span class="sxs-lookup"><span data-stu-id="ab2f7-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ab2f7-118">설명</span><span class="sxs-lookup"><span data-stu-id="ab2f7-118">Remarks</span></span>  
 <span data-ttu-id="ab2f7-119">이 메서드는 모든 참조를 확인 인스턴스의 `ICorDebug*` 릴리스된 인터페이스 이며 스레드가 없는 현재 호출 내 합니다 [iclrdebugging:: Openvirtualprocess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="ab2f7-119">This method checks to see if all instances of `ICorDebug*` interfaces have been released and no thread is currently within a call to the [ICLRDebugging::OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab2f7-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ab2f7-120">Requirements</span></span>  
 <span data-ttu-id="ab2f7-121">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ab2f7-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab2f7-122">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ab2f7-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ab2f7-123">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ab2f7-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ab2f7-124">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab2f7-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab2f7-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="ab2f7-125">See also</span></span>

- [<span data-ttu-id="ab2f7-126">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ab2f7-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="ab2f7-127">디버깅</span><span class="sxs-lookup"><span data-stu-id="ab2f7-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
