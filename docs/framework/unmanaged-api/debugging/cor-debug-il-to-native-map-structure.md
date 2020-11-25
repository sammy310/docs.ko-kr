---
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
ms.openlocfilehash: 61544d0dfe876f35fdfbe5afa945fad0620c0eb5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726654"
---
# <a name="cor_debug_il_to_native_map-structure"></a><span data-ttu-id="4459f-102">COR_DEBUG_IL_TO_NATIVE_MAP 구조체</span><span class="sxs-lookup"><span data-stu-id="4459f-102">COR_DEBUG_IL_TO_NATIVE_MAP Structure</span></span>

<span data-ttu-id="4459f-103">MSIL(Microsoft Intermediate Language) 코드를 네이티브 코드에 매핑하는 데 사용되는 오프셋을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="4459f-103">Contains the offsets that are used to map Microsoft intermediate language (MSIL) code to native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4459f-104">구문</span><span class="sxs-lookup"><span data-stu-id="4459f-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_DEBUG_IL_TO_NATIVE_MAP {  
    ULONG32  ilOffset;  
    ULONG32  nativeStartOffset;  
    ULONG32  nativeEndOffset;  
} COR_DEBUG_IL_TO_NATIVE_MAP;  
```  
  
## <a name="members"></a><span data-ttu-id="4459f-105">멤버</span><span class="sxs-lookup"><span data-stu-id="4459f-105">Members</span></span>  
  
|<span data-ttu-id="4459f-106">멤버</span><span class="sxs-lookup"><span data-stu-id="4459f-106">Member</span></span>|<span data-ttu-id="4459f-107">설명</span><span class="sxs-lookup"><span data-stu-id="4459f-107">Description</span></span>|  
|------------|-----------------|  
|`ilOffset`|<span data-ttu-id="4459f-108">MSIL 코드의 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="4459f-108">The offset of the MSIL code.</span></span>|  
|`nativeStartOffset`|<span data-ttu-id="4459f-109">네이티브 코드의 시작 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="4459f-109">The offset of the start of the native code.</span></span>|  
|`nativeEndOffset`|<span data-ttu-id="4459f-110">네이티브 코드의 끝 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="4459f-110">The offset of the end of the native code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4459f-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4459f-111">Requirements</span></span>  

 <span data-ttu-id="4459f-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4459f-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4459f-113">**헤더:** Corprof.idl, CorDebug .idl</span><span class="sxs-lookup"><span data-stu-id="4459f-113">**Header:** CorProf.idl, CorDebug.idl</span></span>  
  
 <span data-ttu-id="4459f-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4459f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4459f-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4459f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4459f-116">참조</span><span class="sxs-lookup"><span data-stu-id="4459f-116">See also</span></span>

- [<span data-ttu-id="4459f-117">GetILToNativeMapping 메서드</span><span class="sxs-lookup"><span data-stu-id="4459f-117">GetILToNativeMapping Method</span></span>](../profiling/icorprofilerinfo-getiltonativemapping-method.md)
- [<span data-ttu-id="4459f-118">GetILToNativeMapping 메서드</span><span class="sxs-lookup"><span data-stu-id="4459f-118">GetILToNativeMapping Method</span></span>](icordebugcode-getiltonativemapping-method.md)
- [<span data-ttu-id="4459f-119">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="4459f-119">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="4459f-120">디버깅</span><span class="sxs-lookup"><span data-stu-id="4459f-120">Debugging</span></span>](index.md)
