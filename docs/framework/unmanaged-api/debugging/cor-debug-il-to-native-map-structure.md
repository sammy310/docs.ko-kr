---
description: '다음에 대 한 자세한 정보: COR_DEBUG_IL_TO_NATIVE_MAP 구조체'
title: COR_DEBUG_IL_TO_NATIVE_MAP 구조체
ms.date: 03/30/2017
api_name:
- COR_DEBUG_IL_TO_NATIVE_MAP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_DEBUG_IL_TO_NATIVE_MAP
helpviewer_keywords:
- COR_DEBUG_IL_TO_NATIVE_MAP structure [.NET Framework debugging]
ms.assetid: 06f3b504-085f-4142-934a-25381fe23d4c
topic_type:
- apiref
ms.openlocfilehash: ec722b86f95e75d4ac00e04e8a602c6b6da64de5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99747194"
---
# <a name="cor_debug_il_to_native_map-structure"></a><span data-ttu-id="caf7d-103">COR_DEBUG_IL_TO_NATIVE_MAP 구조체</span><span class="sxs-lookup"><span data-stu-id="caf7d-103">COR_DEBUG_IL_TO_NATIVE_MAP Structure</span></span>

<span data-ttu-id="caf7d-104">MSIL(Microsoft Intermediate Language) 코드를 네이티브 코드에 매핑하는 데 사용되는 오프셋을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="caf7d-104">Contains the offsets that are used to map Microsoft intermediate language (MSIL) code to native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="caf7d-105">구문</span><span class="sxs-lookup"><span data-stu-id="caf7d-105">Syntax</span></span>  
  
```cpp  
typedef struct COR_DEBUG_IL_TO_NATIVE_MAP {  
    ULONG32  ilOffset;  
    ULONG32  nativeStartOffset;  
    ULONG32  nativeEndOffset;  
} COR_DEBUG_IL_TO_NATIVE_MAP;  
```  
  
## <a name="members"></a><span data-ttu-id="caf7d-106">구성원</span><span class="sxs-lookup"><span data-stu-id="caf7d-106">Members</span></span>  
  
|<span data-ttu-id="caf7d-107">멤버</span><span class="sxs-lookup"><span data-stu-id="caf7d-107">Member</span></span>|<span data-ttu-id="caf7d-108">설명</span><span class="sxs-lookup"><span data-stu-id="caf7d-108">Description</span></span>|  
|------------|-----------------|  
|`ilOffset`|<span data-ttu-id="caf7d-109">MSIL 코드의 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="caf7d-109">The offset of the MSIL code.</span></span>|  
|`nativeStartOffset`|<span data-ttu-id="caf7d-110">네이티브 코드의 시작 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="caf7d-110">The offset of the start of the native code.</span></span>|  
|`nativeEndOffset`|<span data-ttu-id="caf7d-111">네이티브 코드의 끝 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="caf7d-111">The offset of the end of the native code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="caf7d-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="caf7d-112">Requirements</span></span>  

 <span data-ttu-id="caf7d-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="caf7d-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="caf7d-114">**헤더:** Corprof.idl, CorDebug .idl</span><span class="sxs-lookup"><span data-stu-id="caf7d-114">**Header:** CorProf.idl, CorDebug.idl</span></span>  
  
 <span data-ttu-id="caf7d-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="caf7d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="caf7d-116">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="caf7d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="caf7d-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="caf7d-117">See also</span></span>

- [<span data-ttu-id="caf7d-118">GetILToNativeMapping 메서드</span><span class="sxs-lookup"><span data-stu-id="caf7d-118">GetILToNativeMapping Method</span></span>](../profiling/icorprofilerinfo-getiltonativemapping-method.md)
- [<span data-ttu-id="caf7d-119">GetILToNativeMapping 메서드</span><span class="sxs-lookup"><span data-stu-id="caf7d-119">GetILToNativeMapping Method</span></span>](icordebugcode-getiltonativemapping-method.md)
- [<span data-ttu-id="caf7d-120">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="caf7d-120">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="caf7d-121">디버깅</span><span class="sxs-lookup"><span data-stu-id="caf7d-121">Debugging</span></span>](index.md)
