---
description: '자세히 알아보기: ICorDebugCode2 인터페이스'
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
ms.openlocfilehash: 29fd657ec56993d47ee57aa41c81b45e75352697
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99765050"
---
# <a name="icordebugcode2-interface"></a><span data-ttu-id="65891-103">ICorDebugCode2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="65891-103">ICorDebugCode2 Interface</span></span>

<span data-ttu-id="65891-104">"ICorDebugCode"의 기능을 확장 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="65891-104">Provides methods that extend the capabilities of "ICorDebugCode".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="65891-105">메서드</span><span class="sxs-lookup"><span data-stu-id="65891-105">Methods</span></span>  
  
|<span data-ttu-id="65891-106">메서드</span><span class="sxs-lookup"><span data-stu-id="65891-106">Method</span></span>|<span data-ttu-id="65891-107">설명</span><span class="sxs-lookup"><span data-stu-id="65891-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="65891-108">GetCodeChunks 메서드</span><span class="sxs-lookup"><span data-stu-id="65891-108">GetCodeChunks Method</span></span>](icordebugcode2-getcodechunks-method.md)|<span data-ttu-id="65891-109">이 코드 개체가 구성 된 코드의 청크를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="65891-109">Gets the chunks of code that this code object is composed of.</span></span>|  
|[<span data-ttu-id="65891-110">GetCompilerFlags 메서드</span><span class="sxs-lookup"><span data-stu-id="65891-110">GetCompilerFlags Method</span></span>](icordebugcode2-getcompilerflags-method.md)|<span data-ttu-id="65891-111">이 코드 개체가 네이티브 이미지 생성기 (Ngen.exe)를 사용 하 여 컴파일 또는 생성 된 JIT (just-in-time) 인 조건을 지정 하는 플래그를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="65891-111">Gets the flags that specify the conditions under which this code object was either just-in-time (JIT) compiled or generated using the native image generator (Ngen.exe).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="65891-112">설명</span><span class="sxs-lookup"><span data-stu-id="65891-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="65891-113">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="65891-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65891-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="65891-114">Requirements</span></span>  

 <span data-ttu-id="65891-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="65891-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65891-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="65891-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="65891-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="65891-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="65891-118">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65891-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65891-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="65891-119">See also</span></span>

- [<span data-ttu-id="65891-120">ICorDebugCode3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="65891-120">ICorDebugCode3 Interface</span></span>](icordebugcode3-interface.md)
- [<span data-ttu-id="65891-121">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="65891-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
