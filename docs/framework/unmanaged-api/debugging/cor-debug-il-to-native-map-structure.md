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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 03ce77dd7407db8289abfefba13d71a9af053e10
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59142053"
---
# <a name="cordebugiltonativemap-structure"></a><span data-ttu-id="fc7c5-102">COR_DEBUG_IL_TO_NATIVE_MAP 구조체</span><span class="sxs-lookup"><span data-stu-id="fc7c5-102">COR_DEBUG_IL_TO_NATIVE_MAP Structure</span></span>
<span data-ttu-id="fc7c5-103">MSIL(Microsoft Intermediate Language) 코드를 네이티브 코드에 매핑하는 데 사용되는 오프셋을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="fc7c5-103">Contains the offsets that are used to map Microsoft intermediate language (MSIL) code to native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc7c5-104">구문</span><span class="sxs-lookup"><span data-stu-id="fc7c5-104">Syntax</span></span>  
  
```  
typedef struct COR_DEBUG_IL_TO_NATIVE_MAP {  
    ULONG32  ilOffset;  
    ULONG32  nativeStartOffset;  
    ULONG32  nativeEndOffset;  
} COR_DEBUG_IL_TO_NATIVE_MAP;  
```  
  
## <a name="members"></a><span data-ttu-id="fc7c5-105">멤버</span><span class="sxs-lookup"><span data-stu-id="fc7c5-105">Members</span></span>  
  
|<span data-ttu-id="fc7c5-106">멤버</span><span class="sxs-lookup"><span data-stu-id="fc7c5-106">Member</span></span>|<span data-ttu-id="fc7c5-107">설명</span><span class="sxs-lookup"><span data-stu-id="fc7c5-107">Description</span></span>|  
|------------|-----------------|  
|`ilOffset`|<span data-ttu-id="fc7c5-108">MSIL 코드의 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="fc7c5-108">The offset of the MSIL code.</span></span>|  
|`nativeStartOffset`|<span data-ttu-id="fc7c5-109">네이티브 코드의 시작 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="fc7c5-109">The offset of the start of the native code.</span></span>|  
|`nativeEndOffset`|<span data-ttu-id="fc7c5-110">네이티브 코드의 끝 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="fc7c5-110">The offset of the end of the native code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fc7c5-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fc7c5-111">Requirements</span></span>  
 <span data-ttu-id="fc7c5-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="fc7c5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc7c5-113">**헤더:** CorProf.idl, CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="fc7c5-113">**Header:** CorProf.idl, CorDebug.idl</span></span>  
  
 <span data-ttu-id="fc7c5-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fc7c5-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="fc7c5-115">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="fc7c5-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fc7c5-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="fc7c5-116">See also</span></span>

- [<span data-ttu-id="fc7c5-117">GetILToNativeMapping 메서드</span><span class="sxs-lookup"><span data-stu-id="fc7c5-117">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md)
- [<span data-ttu-id="fc7c5-118">GetILToNativeMapping 메서드</span><span class="sxs-lookup"><span data-stu-id="fc7c5-118">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getiltonativemapping-method.md)
- [<span data-ttu-id="fc7c5-119">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="fc7c5-119">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="fc7c5-120">디버깅</span><span class="sxs-lookup"><span data-stu-id="fc7c5-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
