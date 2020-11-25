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
ms.openlocfilehash: 0c8398b9e423414f32a391edcd5ea1c709af37f5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696559"
---
# <a name="cordebugjitcompilerflags-enumeration"></a><span data-ttu-id="8653d-102">CorDebugJITCompilerFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="8653d-102">CorDebugJITCompilerFlags Enumeration</span></span>

<span data-ttu-id="8653d-103">관리되는 JIT(Just-In-Time) 컴파일러의 동작에 영향을 주는 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="8653d-103">Contains values that influence the behavior of the managed just-in-time (JIT) compiler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8653d-104">구문</span><span class="sxs-lookup"><span data-stu-id="8653d-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugJITCompilerFlags {  
  
    CORDEBUG_JIT_DEFAULT = 0x1,  
    CORDEBUG_JIT_DISABLE_OPTIMIZATION = 0x3,  
    CORDEBUG_JIT_ENABLE_ENC = 0x7  
  
} CorDebugJITCompilerFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="8653d-105">멤버</span><span class="sxs-lookup"><span data-stu-id="8653d-105">Members</span></span>  
  
|<span data-ttu-id="8653d-106">멤버</span><span class="sxs-lookup"><span data-stu-id="8653d-106">Member</span></span>|<span data-ttu-id="8653d-107">설명</span><span class="sxs-lookup"><span data-stu-id="8653d-107">Description</span></span>|  
|------------|-----------------|  
|`CORDEBUG_JIT_DEFAULT`|<span data-ttu-id="8653d-108">컴파일러가 컴파일 데이터를 추적 하 고 최적화를 허용 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8653d-108">Specifies that the compiler should track compilation data, and allows optimizations.</span></span>|  
|`CORDEBUG_JIT_DISABLE_OPTIMIZATION`|<span data-ttu-id="8653d-109">컴파일러가 컴파일 데이터를 추적 하지만 최적화를 사용 하지 않도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8653d-109">Specifies that the compiler should track compilation data, but disables optimizations.</span></span>|  
|`CORDEBUG_JIT_ENABLE_ENC`|<span data-ttu-id="8653d-110">컴파일러가 컴파일 데이터를 추적 하 고, 최적화를 사용 하지 않도록 설정 하 고, 편집 하며 계속 하기 기술을 사용 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8653d-110">Specifies that the compiler should track compilation data, disables optimizations, and enables Edit and Continue technologies.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8653d-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8653d-111">Requirements</span></span>  

 <span data-ttu-id="8653d-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8653d-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8653d-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8653d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8653d-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8653d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8653d-115">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8653d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8653d-116">참조</span><span class="sxs-lookup"><span data-stu-id="8653d-116">See also</span></span>

- [<span data-ttu-id="8653d-117">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="8653d-117">Debugging Enumerations</span></span>](debugging-enumerations.md)
