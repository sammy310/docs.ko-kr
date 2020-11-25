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
ms.openlocfilehash: 359db27878ea4adf794bcd6221d4b5387026e5c0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710313"
---
# <a name="icordebugmoduleenablejitdebugging-method"></a><span data-ttu-id="32809-102">ICorDebugModule::EnableJITDebugging 메서드</span><span class="sxs-lookup"><span data-stu-id="32809-102">ICorDebugModule::EnableJITDebugging Method</span></span>

<span data-ttu-id="32809-103">JIT (just-in-time) 컴파일러에서이 모듈의 메서드에 대 한 디버깅 정보를 유지할지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="32809-103">Controls whether the just-in-time (JIT) compiler preserves debugging information for methods within this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32809-104">구문</span><span class="sxs-lookup"><span data-stu-id="32809-104">Syntax</span></span>  
  
```cpp  
HRESULT EnableJITDebugging(  
    [in] BOOL bTrackJITInfo,  
    [in] BOOL bAllowJitOpts  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="32809-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="32809-105">Parameters</span></span>  

 `bTrackJITInfo`  
 <span data-ttu-id="32809-106">진행 `true` Jit 컴파일러에서이 모듈의 각 메서드에 대 한 MSIL (Microsoft 중간 언어) 버전과 jit 컴파일된 버전 사이의 매핑 정보를 유지 하도록 하려면이 값을로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="32809-106">[in] Set this value to `true` to enable the JIT compiler to preserve mapping information between the Microsoft intermediate language (MSIL) version and the JIT-compiled version of each method in this module.</span></span>  
  
 `bAllowJitOpts`  
 <span data-ttu-id="32809-107">진행 `true` Jit 컴파일러에서 디버깅을 위해 특정 jit 특정 최적화를 사용 하 여 코드를 생성할 수 있도록 하려면이 값을로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="32809-107">[in] Set this value to `true` to enable the JIT compiler to generate code with certain JIT-specific optimizations for debugging.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="32809-108">설명</span><span class="sxs-lookup"><span data-stu-id="32809-108">Remarks</span></span>  

 <span data-ttu-id="32809-109">JIT 디버깅은 디버거가 활성 상태일 때 로드 되는 모든 모듈에 대해 기본적으로 사용 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="32809-109">JIT debugging is enabled by default for all modules that are loaded when the debugger is active.</span></span> <span data-ttu-id="32809-110">프로그래밍 방식으로 설정을 사용 하거나 사용 하지 않도록 설정 하면 전역 설정이 재정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="32809-110">Programmatically enabling or disabling the settings overrides global settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32809-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="32809-111">Requirements</span></span>  

 <span data-ttu-id="32809-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="32809-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32809-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="32809-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="32809-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="32809-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="32809-115">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32809-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
