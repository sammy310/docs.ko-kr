---
title: ICorDebugCode2 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugCode2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode2
helpviewer_keywords:
- ICorDebugCode2 interface [.NET Framework debugging]
ms.assetid: 9321903b-7dea-40d8-ba32-99016c00cc46
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9cb7be64089a55e7b653fcd6272219abba311af8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960807"
---
# <a name="icordebugcode2-interface"></a><span data-ttu-id="b53ef-102">ICorDebugCode2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b53ef-102">ICorDebugCode2 Interface</span></span>

<span data-ttu-id="b53ef-103">"ICorDebugCode"의 기능을 확장 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b53ef-103">Provides methods that extend the capabilities of "ICorDebugCode".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b53ef-104">메서드</span><span class="sxs-lookup"><span data-stu-id="b53ef-104">Methods</span></span>  
  
|<span data-ttu-id="b53ef-105">메서드</span><span class="sxs-lookup"><span data-stu-id="b53ef-105">Method</span></span>|<span data-ttu-id="b53ef-106">Description</span><span class="sxs-lookup"><span data-stu-id="b53ef-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b53ef-107">GetCodeChunks 메서드</span><span class="sxs-lookup"><span data-stu-id="b53ef-107">GetCodeChunks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md)|<span data-ttu-id="b53ef-108">이 코드 개체가 구성 된 코드의 청크를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b53ef-108">Gets the chunks of code that this code object is composed of.</span></span>|  
|[<span data-ttu-id="b53ef-109">GetCompilerFlags 메서드</span><span class="sxs-lookup"><span data-stu-id="b53ef-109">GetCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcompilerflags-method.md)|<span data-ttu-id="b53ef-110">네이티브 이미지 생성기 (Ngen.exe)를 사용 하 여이 코드 개체가 JIT (just-in-time) 컴파일 또는 생성 된 조건을 지정 하는 플래그를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b53ef-110">Gets the flags that specify the conditions under which this code object was either just-in-time (JIT) compiled or generated using the native image generator (Ngen.exe).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b53ef-111">설명</span><span class="sxs-lookup"><span data-stu-id="b53ef-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b53ef-112">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b53ef-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b53ef-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b53ef-113">Requirements</span></span>  
 <span data-ttu-id="b53ef-114">**플랫폼** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b53ef-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b53ef-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b53ef-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b53ef-116">**라이브러리** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b53ef-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b53ef-117">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b53ef-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b53ef-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="b53ef-118">See also</span></span>

- [<span data-ttu-id="b53ef-119">ICorDebugCode3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b53ef-119">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)
- [<span data-ttu-id="b53ef-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b53ef-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
