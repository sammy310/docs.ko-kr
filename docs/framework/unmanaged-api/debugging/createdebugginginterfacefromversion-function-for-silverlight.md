---
title: Silverlight용 CreateDebuggingInterfaceFromVersion 함수
ms.date: 03/30/2017
f1_keywords:
- CreateDebuggingInterfaceFromVersion
helpviewer_keywords:
- CreateDebuggingInterfaceFromVersion function
- debugging API [Silverlight]
- Silverlight, debugging
ms.assetid: 35c7a18f-133a-4584-bd25-bb338568b0c6
ms.openlocfilehash: 85b5a5a630f399d0e036de434365e2e4f8f02dea
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793831"
---
# <a name="createdebugginginterfacefromversion-function-for-silverlight"></a><span data-ttu-id="11090-102">Silverlight용 CreateDebuggingInterfaceFromVersion 함수</span><span class="sxs-lookup"><span data-stu-id="11090-102">CreateDebuggingInterfaceFromVersion Function for Silverlight</span></span>
<span data-ttu-id="11090-103">[Createversionstringfrommodule 함수](createversionstringfrommodule-function.md)에서 반환 되는 CLR (공용 언어 런타임) 버전 문자열을 수락 하 고 해당 디버거 인터페이스 (일반적으로 [ICorDebug](icordebug-interface.md))를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="11090-103">Accepts a common language runtime (CLR) version string that is returned from the [CreateVersionStringFromModule function](createversionstringfrommodule-function.md), and returns a corresponding debugger interface (typically, [ICorDebug](icordebug-interface.md)).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11090-104">구문</span><span class="sxs-lookup"><span data-stu-id="11090-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  LPCWSTR      szDebuggeeVersion,  
    [out] IUnknown**   ppCordb,  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="11090-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="11090-105">Parameters</span></span>  
 `szDebuggeeVersion`  
 <span data-ttu-id="11090-106">진행 [Createversionstringfrommodule 함수](createversionstringfrommodule-function.md)에서 반환 하는 대상 디버기에 있는 CLR의 버전 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="11090-106">[in] Version string of the CLR in the target debuggee, which is returned by the [CreateVersionStringFromModule function](createversionstringfrommodule-function.md).</span></span>  
  
 `ppCordb`  
 <span data-ttu-id="11090-107">[out] COM 개체(`IUnknown`)에 대한 포인터의 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="11090-107">[out] Pointer to a pointer to a COM object (`IUnknown`).</span></span> <span data-ttu-id="11090-108">이 개체는 반환 되기 전에 [ICorDebug](icordebug-interface.md) 개체로 캐스팅 됩니다.</span><span class="sxs-lookup"><span data-stu-id="11090-108">This object will be cast to an [ICorDebug](icordebug-interface.md) object before it is returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="11090-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="11090-109">Return Value</span></span>  
 <span data-ttu-id="11090-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="11090-110">S_OK</span></span>  
 <span data-ttu-id="11090-111">`ppCordb` [ICorDebug interface](icordebug-interface.md) 인터페이스를 구현 하는 유효한 개체를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="11090-111">`ppCordb` references a valid object that implements the [ICorDebug interface](icordebug-interface.md) interface.</span></span>  
  
 <span data-ttu-id="11090-112">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="11090-112">E_INVALIDARG</span></span>  
 <span data-ttu-id="11090-113">`szDebuggeeVersion` 또는 `ppCordb`가 null입니다.</span><span class="sxs-lookup"><span data-stu-id="11090-113">Either `szDebuggeeVersion` or `ppCordb` is null.</span></span>  
  
 <span data-ttu-id="11090-114">CORDBG_E_DEBUG_COMPONENT_MISSING</span><span class="sxs-lookup"><span data-stu-id="11090-114">CORDBG_E_DEBUG_COMPONENT_MISSING</span></span>  
 <span data-ttu-id="11090-115">CLR 디버깅에 필요한 구성 요소를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="11090-115">A component that is necessary for CLR debugging cannot be located.</span></span> <span data-ttu-id="11090-116">즉, mscordbi.dll 또는 mscordaccore.dll이 대상 CoreCLR.dll과 동일한 디렉터리에 없습니다.</span><span class="sxs-lookup"><span data-stu-id="11090-116">This means that either mscordbi.dll or mscordaccore.dll was not found in the same directory as the target CoreCLR.dll.</span></span>  
  
 <span data-ttu-id="11090-117">CORDBG_E_INCOMPATIBLE_PROTOCOL</span><span class="sxs-lookup"><span data-stu-id="11090-117">CORDBG_E_INCOMPATIBLE_PROTOCOL</span></span>  
 <span data-ttu-id="11090-118">mscordbi.dll 또는 mscordaccore.dll이 대상 CoreCLR.dll과 동일한 버전이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="11090-118">Either mscordbi.dll or mscordaccore.dll is not the same version as the target CoreCLR.dll.</span></span>  
  
 <span data-ttu-id="11090-119">E_FAIL(또는 다른 E_ 반환 코드)</span><span class="sxs-lookup"><span data-stu-id="11090-119">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="11090-120">[ICorDebug 인터페이스](icordebug-interface.md)를 반환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="11090-120">Unable to return an [ICorDebug interface](icordebug-interface.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="11090-121">주의</span><span class="sxs-lookup"><span data-stu-id="11090-121">Remarks</span></span>  
 <span data-ttu-id="11090-122">반환된 인터페이스는 대상 프로세스의 CLR에 연결하고 CLR에서 실행 중인 관리 코드를 디버그하기 위한 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="11090-122">The interface that is returned provides the facilities for attaching to a CLR in a target process and debugging the managed code that the CLR is running.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11090-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="11090-123">Requirements</span></span>  
 <span data-ttu-id="11090-124">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="11090-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11090-125">**헤더:** dbgshim.dll</span><span class="sxs-lookup"><span data-stu-id="11090-125">**Header:** dbgshim.h</span></span>  
  
 <span data-ttu-id="11090-126">**라이브러리:** dbgshim.dll</span><span class="sxs-lookup"><span data-stu-id="11090-126">**Library:** dbgshim.dll</span></span>  
  
 <span data-ttu-id="11090-127">**.NET Framework 버전:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="11090-127">**.NET Framework Versions:** 3.5 SP1</span></span>
