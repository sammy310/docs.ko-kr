---
title: ICorDebugModule::EnableJITDebugging 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugModule.EnableJITDebugging
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::EnableJITDebugging
helpviewer_keywords:
- ICorDebugModule::EnableJITDebugging method [.NET Framework debugging]
- EnableJITDebugging method [.NET Framework debugging]
ms.assetid: 0a65e2a4-5bb6-496c-ae6f-40474426b5a6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 642c4fd600d10ef89a08aa32bef5c8e7455552c7
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57473824"
---
# <a name="icordebugmoduleenablejitdebugging-method"></a><span data-ttu-id="663cb-102">ICorDebugModule::EnableJITDebugging 메서드</span><span class="sxs-lookup"><span data-stu-id="663cb-102">ICorDebugModule::EnableJITDebugging Method</span></span>
<span data-ttu-id="663cb-103">Just-in-time (JIT) 컴파일러가이 모듈 내에서 메서드에 대 한 디버깅 정보를 유지할지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="663cb-103">Controls whether the just-in-time (JIT) compiler preserves debugging information for methods within this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="663cb-104">구문</span><span class="sxs-lookup"><span data-stu-id="663cb-104">Syntax</span></span>  
  
```  
HRESULT EnableJITDebugging(  
    [in] BOOL bTrackJITInfo,  
    [in] BOOL bAllowJitOpts  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="663cb-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="663cb-105">Parameters</span></span>  
 `bTrackJITInfo`  
 <span data-ttu-id="663cb-106">[in] 이 값을 설정 `true` 는 MSIL (intermediate language) 버전의 Microsoft 및이 모듈에서 각 메서드의 JIT 컴파일된 버전 간의 매핑 정보를 유지 하기 위해 JIT 컴파일러를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="663cb-106">[in] Set this value to `true` to enable the JIT compiler to preserve mapping information between the Microsoft intermediate language (MSIL) version and the JIT-compiled version of each method in this module.</span></span>  
  
 `bAllowJitOpts`  
 <span data-ttu-id="663cb-107">[in] 이 값을 설정 `true` 디버깅에 대 한 특정 관련 JIT 최적화를 사용 하 여 코드를 생성 하는 JIT 컴파일러를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="663cb-107">[in] Set this value to `true` to enable the JIT compiler to generate code with certain JIT-specific optimizations for debugging.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="663cb-108">설명</span><span class="sxs-lookup"><span data-stu-id="663cb-108">Remarks</span></span>  
 <span data-ttu-id="663cb-109">JIT 디버깅이 디버거가 활성 상태일 때 로드 되는 모든 모듈에 대해 기본적으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="663cb-109">JIT debugging is enabled by default for all modules that are loaded when the debugger is active.</span></span> <span data-ttu-id="663cb-110">프로그래밍 방식으로 사용 하도록 설정 하거나 사용 하지 않도록 설정 된 전역 설정을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="663cb-110">Programmatically enabling or disabling the settings overrides global settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="663cb-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="663cb-111">Requirements</span></span>  
 <span data-ttu-id="663cb-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="663cb-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="663cb-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="663cb-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="663cb-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="663cb-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="663cb-115">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="663cb-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
