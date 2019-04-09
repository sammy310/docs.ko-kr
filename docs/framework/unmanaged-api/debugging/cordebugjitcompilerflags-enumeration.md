---
title: CorDebugJITCompilerFlags 열거형
ms.date: 03/30/2017
api_name:
- CorDebugJITCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugJITCompilerFlags
helpviewer_keywords:
- CorDebugJITCompilerFlags enumeration [.NET Framework debugging]
ms.assetid: c0774f70-5bed-45e8-9922-fdad778c4c33
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 66a8ba59d221bb3fa2e815a1cbcfa79c474666cc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59105471"
---
# <a name="cordebugjitcompilerflags-enumeration"></a><span data-ttu-id="17be2-102">CorDebugJITCompilerFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="17be2-102">CorDebugJITCompilerFlags Enumeration</span></span>
<span data-ttu-id="17be2-103">관리되는 JIT(Just-In-Time) 컴파일러의 동작에 영향을 주는 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="17be2-103">Contains values that influence the behavior of the managed just-in-time (JIT) compiler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17be2-104">구문</span><span class="sxs-lookup"><span data-stu-id="17be2-104">Syntax</span></span>  
  
```  
typedef enum CorDebugJITCompilerFlags {  
  
    CORDEBUG_JIT_DEFAULT = 0x1,  
    CORDEBUG_JIT_DISABLE_OPTIMIZATION = 0x3,  
    CORDEBUG_JIT_ENABLE_ENC = 0x7  
  
} CorDebugJITCompilerFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="17be2-105">멤버</span><span class="sxs-lookup"><span data-stu-id="17be2-105">Members</span></span>  
  
|<span data-ttu-id="17be2-106">멤버</span><span class="sxs-lookup"><span data-stu-id="17be2-106">Member</span></span>|<span data-ttu-id="17be2-107">설명</span><span class="sxs-lookup"><span data-stu-id="17be2-107">Description</span></span>|  
|------------|-----------------|  
|`CORDEBUG_JIT_DEFAULT`|<span data-ttu-id="17be2-108">컴파일러는 컴파일 데이터를 추적 해야 하 고 최적화를 사용 하면를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="17be2-108">Specifies that the compiler should track compilation data, and allows optimizations.</span></span>|  
|`CORDEBUG_JIT_DISABLE_OPTIMIZATION`|<span data-ttu-id="17be2-109">컴파일러 최적화가 사용 하지 않도록 설정 하지만 컴파일 데이터를 추적 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="17be2-109">Specifies that the compiler should track compilation data, but disables optimizations.</span></span>|  
|`CORDEBUG_JIT_ENABLE_ENC`|<span data-ttu-id="17be2-110">컴파일러는 컴파일 데이터를 사용 하지 않도록 설정 최적화를 추적 하도록 및 편집 하며 계속 기술을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="17be2-110">Specifies that the compiler should track compilation data, disables optimizations, and enables Edit and Continue technologies.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="17be2-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="17be2-111">Requirements</span></span>  
 <span data-ttu-id="17be2-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="17be2-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17be2-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="17be2-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="17be2-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="17be2-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="17be2-115">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="17be2-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="17be2-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="17be2-116">See also</span></span>

- [<span data-ttu-id="17be2-117">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="17be2-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
