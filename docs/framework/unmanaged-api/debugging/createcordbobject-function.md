---
title: CreateCordbObject 함수
ms.date: 03/30/2017
api_name:
- CreateCoredbObject
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CreateCordbObject
helpviewer_keywords:
- remote debugging API [Silverlight]
- CreateCordbObject function
- Silverlight, remote debugging
ms.assetid: b259821d-4fa7-464d-85cf-304dfffc8089
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f546d7707c40f7f26a46177ae972a988e54e1e45
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61965835"
---
# <a name="createcordbobject-function"></a><span data-ttu-id="cfcd7-102">CreateCordbObject 함수</span><span class="sxs-lookup"><span data-stu-id="cfcd7-102">CreateCordbObject Function</span></span>
<span data-ttu-id="cfcd7-103">디버거 인터페이스를 만듭니다 ([ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)) 원격 프로세스에서 관리 되는 디버깅 세션을 인스턴스화하기 위한 기능을 제공 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfcd7-103">Creates a debugger interface ([ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)) that provides functionality for instantiating a managed debugging session on a remote process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfcd7-104">구문</span><span class="sxs-lookup"><span data-stu-id="cfcd7-104">Syntax</span></span>  
  
```  
HRESULT CordbCreateObject (  
       [in]  int         iDebuggerVersion,   
       [out] IUnknown**  ppCordb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cfcd7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cfcd7-105">Parameters</span></span>  
 `iDebuggerVersion`  
 <span data-ttu-id="cfcd7-106">[in] 대상 프로세스의 디버거 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="cfcd7-106">[in] Debugger version of the target process.</span></span> <span data-ttu-id="cfcd7-107">원격 디버깅의 경우 이 매개 변수는 CorDebugVersion_2_0이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfcd7-107">This parameter must be CorDebugVersion_2_0 for remote debugging.</span></span>  
  
 `ppCordb`  
 <span data-ttu-id="cfcd7-108">[out] 캐스트할 수 있는 개체에 대 한 포인터에 대 한 포인터를 [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) 인터페이스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfcd7-108">[out] Pointer to a pointer to an object that will be cast to an [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interface and returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cfcd7-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="cfcd7-109">Return Value</span></span>  
 <span data-ttu-id="cfcd7-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="cfcd7-110">S_OK</span></span>  
 <span data-ttu-id="cfcd7-111">프로세스의 CLR 수가 성공적으로 확인되었으며 해당 핸들 및 경로 배열이 제대로 채워졌습니다.</span><span class="sxs-lookup"><span data-stu-id="cfcd7-111">The number of CLRs in the process was successfully determined, and the corresponding handle and path arrays were properly filled.</span></span>  
  
 <span data-ttu-id="cfcd7-112">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="cfcd7-112">E_INVALIDARG</span></span>  
 <span data-ttu-id="cfcd7-113">`ppCordb`가 null이거나 `iDebuggerVersion`이 CorDebugVersion_2_0이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="cfcd7-113">`ppCordb` is null, or `iDebuggerVersion` is not CorDebugVersion_2_0.</span></span>  
  
 <span data-ttu-id="cfcd7-114">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="cfcd7-114">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="cfcd7-115">`ppCordb`에 대해 충분한 메모리를 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cfcd7-115">Unable to allocate enough memory for `ppCordb`</span></span>  
  
 <span data-ttu-id="cfcd7-116">E_FAIL(또는 다른 E_ 반환 코드)</span><span class="sxs-lookup"><span data-stu-id="cfcd7-116">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="cfcd7-117">기타 실패</span><span class="sxs-lookup"><span data-stu-id="cfcd7-117">Other failures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cfcd7-118">설명</span><span class="sxs-lookup"><span data-stu-id="cfcd7-118">Remarks</span></span>  
 <span data-ttu-id="cfcd7-119">합니다 [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) 인터페이스에서 반환 되는 `ppCordb` 관리 되는 모든 디버깅 서비스에 대 한 최상위 디버깅 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="cfcd7-119">The [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interface that is returned in `ppCordb` is the top-level debugging interface for all managed debugging services.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cfcd7-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cfcd7-120">Requirements</span></span>  
 <span data-ttu-id="cfcd7-121">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="cfcd7-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cfcd7-122">**헤더:** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="cfcd7-122">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="cfcd7-123">**라이브러리:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="cfcd7-123">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="cfcd7-124">**.NET framework 버전:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="cfcd7-124">**.NET Framework Versions:** 3.5 SP1</span></span>
